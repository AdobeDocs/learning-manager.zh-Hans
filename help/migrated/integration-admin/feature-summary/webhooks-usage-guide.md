---
jcr-language: en_us
title: Webhook使用指南
description: 了解Webhook使用情况、最佳实践和限制
contentowner: chandrum
source-git-commit: d7f7652c38c3eb623be083fd2fdde36eec25c1e4
workflow-type: tm+mt
source-wordcount: '3377'
ht-degree: 1%

---

# Webhook使用指南

Webhook是Web应用程序自动且实时彼此通信的一种方式。

传统API需要等待用户请求信息，而实时API则会在数据发生时共享数据。 Webhook充当实时API，每当发生指定事件时帮助立即共享数据。

## 实体

要了解Webhook事件，我们首先需要了解所涉及实体以及这些事件的触发条件。

### 学习对象

以下是学习对象（课程、学习路径或认证）的支持事件。

#### “草稿”

从UI创建学习对象时，它将以&#x200B;**草稿**&#x200B;模式启动。 这意味着学习对象尚未发布，学习者无法使用。 只要学习对象仍然是草稿，就会触发&#x200B;**LEARNING_OBJECT_DRAFT**&#x200B;事件。 对草稿的任何后续更新也将触发此事件。

#### 更新

发布学习对象后，其状态会从&#x200B;**草稿**&#x200B;更改为&#x200B;**已发布**。 在此过渡期间，Webhook会生成&#x200B;**LEARNING_OBJECT_MODIFICATION**&#x200B;事件，因为学习对象正在从&#x200B;**草稿**&#x200B;修改为&#x200B;**已发布**。 学习对象的所有后续修改和更新也将触发&#x200B;**LEARNING_OBJECT_MODIFICATION**&#x200B;事件。

当学习对象停用时，也会触发&#x200B;**LEARNING_OBJECT_MODIFICATION**&#x200B;事件。 此已停用操作将基础实例标记为已更新，因为一旦父学习对象处于已停用状态，这些实例即会停用。

#### 删除

删除学习对象后，将生成&#x200B;**LEARNING_OBJECT_DELETION**&#x200B;事件。 此事件表示学习对象已被删除，学习者无法再访问。

除实时事件外，学习对象事件还具有批处理（非实时）对应对象，该对应对象作为&#x200B;**LEARNING_OBJECT_MODIFICATION_BATCH**&#x200B;事件的一部分触发。 在通过迁移工作流程创建或修改学习对象时，会发生此事件。 由于不支持通过迁移来草稿和删除学习对象操作，因此这些操作没有对应的草稿或删除事件。

### 学习对象实例

以下是学习对象实例支持的事件。

#### 更新

创建实例后，将生成&#x200B;**LEARNING_OBJECT_INSTANCE_MODIFICATION**&#x200B;事件。 Adobe Learning Manager中的学习对象实例不具有&#x200B;**草稿**&#x200B;状态；因此，Adobe Learning Manager不支持&#x200B;**LEARNING_OBJECT_INSTANCE_DRAFT事件**。 每当创建、修改或弃用实例时，都会生成此事件。

此事件除了在创建、更新或弃用实例时生成之外，在其父学习对象标记为&#x200B;**弃用**&#x200B;时也会自动生成。 这是因为当学习对象停用时，基础实例也需要标记为&#x200B;**已停用**。

#### 删除

删除实例后，将生成&#x200B;**LEARNING_OBJECT_INSTANCE_DELETION**&#x200B;事件。 此事件仅适用于包含自学模块的课程实例，因为Adobe Learning Manager仅允许管理员删除模块类型为自学模块的课程实例。 Adobe Learning Manager不支持明确删除其他类型的课程模块，不支持删除学习路径实例或认证实例的课程模块。

学习对象实例还具有非实时对应项，它作为&#x200B;**LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH**&#x200B;事件的一部分公开。 此事件在通过迁移工作流程创建或修改学习对象实例时触发。 由于迁移不支持草稿或删除学习对象实例的操作，因此相应的草稿或删除事件不可用。

### 注册

学习者执行注册操作后，会触发实时注册事件。 根据学习对象类型，实时注册事件可能分为以下类别之一：

* COURSE_ENROLLMENT
* LEARNING_PATH_ENROLLMENT
* CERTIFICATION_ENROLLMENT

注册事件中除这些实时事件外还有批量交易方。 每当管理员、经理或平台触发注册时，都会触发非实时注册事件。 根据学习对象类型，批量注册事件可以是以下之一：

* COURSE_ENROLLMENT_BATCH
* LEARNING_PATH_ENROLLMENT_BATCH
* CERTIFICATION_ENROLLMENT_BATCH

### 取消注册

学习者执行取消注册操作时，会触发实时取消注册事件。 根据学习对象类型，实时取消注册事件可能分为以下类别之一：

* COURSE_UNENROLLMENT
* LEARNING_PATH_UNENROLLMENT
* CERTIFICATION_UNENROLLMENT

除了这些事件之外，还有一些批量取消注册事件。 每当管理员、经理或平台标记取消注册时，系统都会触发非实时取消注册事件。 根据学习对象类型，批量取消注册事件可以是以下之一：

* COURSE_UNENROLLMENT_BATCH
* LEARNING_PATH_UNENROLLMENT_BATCH
* CERTIFICATION_UNENROLLMENT_BATCH

### 完成

学习者完成学习对象时，系统即会触发实时完成事件。 根据学习对象类型，实时完成事件可分为以下类别之一：

* COURSE_COMPLETED
* LEARNING_PATH_COMPLETED
* CERTIFICATION_COMPLETED

除了这些实时事件之外，还有批量完成事件。 例如，当管理员、经理或平台将学习对象标记为完成时，将触发非实时完成事件。 根据学习对象类型，批量完成事件可分为以下类别之一：

* COURSE_COMPLETED_BATCH
* LEARNING_PATH_COMPLETED_BATCH
* CERTIFICATION_COMPLETED_BATCH

### 学习者进度

每当学习者注册学习对象并开始模块时，系统都会跟踪其进度。 此数据包含在&#x200B;**LEARNER_PROGRESS**&#x200B;事件中。 由于进度跟踪依赖于复杂的聚合逻辑（非实时），因此事件可能会延迟多达15分钟。

### CI统计信息

只要课程实例的名额或轮候表可用性发生变化，就会触发&#x200B;**CI_STATS**&#x200B;实时事件。 仅在实例级别捕获此数据。 此外，此事件仅针对课程触发，而不针对其他学习路径或认证触发，因为名额和轮候表可用性是课程及其实例的特定属性。

## 事件顺序

Adobe Learning Manager可确保为每个帐户排列事件。 但是，在关联注册或完成与进度事件之间的报文时可能存在差异。 发生这种情况的原因是，学习者进度事件最多可延迟15分钟，因为进度跟踪依赖于复杂的聚合逻辑，而后者不是实时的。 此外，进度事件来自不同的数据源，因此不能保证其顺序与注册和完成事件相关。 因此，Adobe Learning Manager在客户端侦听这些事件时提供了最佳做法。

如果完成事件发生在学习者进度事件之前，则客户端可以忽略学习者进度事件。 这是因为学习者进度事件最多可延迟15分钟，而完成事件可能在收到进度事件之前触发。 由于收到完成事件即表示学习对象已完成，因此进度已达到100%。

在极少数情况下，注册事件会在学习者进度事件之后发生，客户端可以忽略注册事件。 这是因为只有在学习者注册学习对象后才能跟踪进度。 换言之，收到进度事件表示学习对象已开始，且仅在成功注册后发生。

## 实时事件与批处理事件

如上所述，某些事件具有实时和非实时对应项。 可能有一些关于何时订购实时事件以及何时订购非实时事件的问题。 根据上述实体，可遵循以下准则。

### 实时事件

| S.No | Webhook事件 | 描述 |
|---|---|---|
| 1 | CI_STATS | 在课程实例的名额或轮候表可用性发生变化时触发。 |
| 2 | COURSE_ENROLLMENT | 在学习者注册课程时触发。 |
| 3 | COURSE_COMPLETED | 在学习者完成课程时触发。 |
| 4 | LEARNING_PATH_ENROLLMENT | 在学习者注册学习路径时触发。 |
| 5 | LEARNING_PATH_COMPLETED | 在学习者完成学习路径时触发。 |
| 6 | CERTIFICATION_ENROLLMENT | 学习者注册认证时触发。 |
| 7 | CERTIFICATION_COMPLETED | 在学习者完成认证时触发。 |
| 8 | COURSE_UNENROLLMENT | 在学习者取消课程注册时触发。 |
| 9 | LEARNING_PATH_UNENROLLMENT | 在学习者取消注册学习路径时触发。 |
| 10 | CERTIFICATION_UNENROLLMENT | 在学习者取消注册认证时触发。 |
| 11 | LEARNING_OBJECT_DRAFT | 在创建处于草稿状态的学习对象时触发。 |
| 12 | LEARNING_OBJECT_DELETION | 删除学习对象时触发。 |
| 13 | LEARNING_OBJECT_MODIFICATION | 在修改学习对象期间触发。 |
| 14 | LEARNING_OBJECT_INSTANCE_MODIFICATION | 在创建或修改学习对象实例期间触发。<div><b>注意：</b>建议仅在发布课程后使用课程实例。</div> |
| 15 | LEARNING_OBJECT_INSTANCE_DELETION | 在删除学习对象实例期间触发。 |

### 非实时事件

| S.No | Webhook事件 | 描述 |
|---|---|---|
| 1 | COURSE_ENROLLMENT_BATCH | 管理员/经理/平台在课程中注册学习者时触发。 |
| 2 | COURSE_COMPLETED_BATCH | 在管理员/经理/平台将课程标记为已完成时触发。 |
| 3 | LEARNING_PATH_ENROLLMENT_BATCH | 在管理员/经理/平台为学习者注册学习路径时触发。 |
| 4 | LEARNING_PATH_COMPLETED_BATCH | 在管理员/经理将学习路径标记为已完成时触发。 |
| 5 | CERTIFICATION_ENROLLMENT_BATCH | 管理员/经理/平台在认证中注册学习者时触发。 |
| 6 | CERTIFICATION_COMPLETED_BATCH | 在管理员/经理/平台将认证标记为已完成时触发。 |
| 7 | LEARNER_PROGRESS | 模块完成后，跟踪学习者的进度。 |
| 8 | COURSE_UNENROLLMENT_BATCH | 在管理员/经理/平台取消注册课程中的学习者时触发。 |
| 9 | LEARNING_PATH_UNENROLLMENT_BATCH | 在管理员/经理/平台从学习路径中取消注册学习者时触发。 |
| 10 | CERTIFICATION_UNENROLLMENT_BATCH | 在管理员/经理/平台取消注册学习者时触发。 |
| 11 | LEARNING_OBJECT_MODIFICATION_BATCH | 在通过迁移工作流程修改学习对象时触发。 |
| 12 | LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH | 在通过迁移工作流程创建或修改学习对象实例时触发。 |

### 学习对象及其实例

* 当您想要侦听管理员、作者等角色通过UI操作对学习对象所做的更改时，请订阅实时事件。
* 每当要侦听通过迁移工作流程对学习对象所做的更改时，可订阅非实时事件或批处理事件。

### 注册、取消注册和完成

* 每当要侦听学习者执行的注册、取消注册或完成时，请订阅实时事件。
* 每当希望侦听由管理员、经理、平台等标记的注册、取消注册或完成时，请订阅非实时事件或批处理事件。

### 学习者进度

* 每当要侦听学习者的进度更改时，请订阅该事件。

>[!NOTE]
>
>在上述方案中（注册、取消注册、完成和进度），由用户ID和loInstanceId组成的属性复合可以唯一标识记录。

### 课程实例统计信息

* 每当要侦听名额或轮候表可用性的更改时，请订阅实时&#x200B;**CI_STATS**&#x200B;事件。

## Webhook事件负载

作为Webhook响应负载的一部分，Adobe Learning Manager将发出唯一标识实体所需的属性。 这些应用程序将按照公共API使用的标准以相同的格式发出，以确保Webhook数据与公共API数据同步。 查看[示例负载](/help/migrated/integration-admin/feature-summary/webhooks-usage-guide.md#sample-payloads-for-the-events)以查看各种事件的负载。

## 使用Webhook构建外部数据库或通知服务

我们听过的一个用例是，在客户一方构建数据库时，Webhook可能会有所帮助。 Adobe Learning Manager拥有自己的数据库和架构，但客户无权访问它们。

问题是：客户如何使用来自Webhook的事件构建数据库？

由于Adobe Learning Manager不会直接公开表记录和架构，因此客户可以依靠Webhook解决方案通过使用事件填充外部数据库来构建外部数据库。 在此版本中，我们提供了学习对象、学习对象实例、注册、取消注册、完成、进度和课程实例状态的事件。

### 通过学习对象事件构建数据库

学习对象事件公开`loId`和`loType`以标识实体。 但是，仅凭这些属性不足以构建外部学习对象数据库。 客户将需要其他字段来进一步描述学习对象。
有两种方法可获取其他数据：

#### 生成培训数据报告以获取所有数据

在通过迁移等工作流程批量创建学习对象时，应使用此方法。 此处的目标是生成&#x200B;**[!UICONTROL 培训数据]**&#x200B;报告，其中包含作为迁移工作流程的一部分引入的所有学习对象。 要优化导入过程，建议将导出开始时间设置为触发迁移的时间。 这将确保报告中仅导出通过迁移导入的学习对象，因为历史数据将已在客户数据库中可用。

#### 从公共APIGET/learningObjects — 管理员范围中查询信息

在通过实时工作流程创建学习对象时，应使用此方法。 客户应拥有自己的缓存层，以批量处理通过事件发出的学习对象，然后通过传递这些学习对象ID来查询`GET /learningObjects` API。 具有缓存层的原因是为了确保不会超出公共API速率限制。 目前，我们将` GET /learningObject` API的管理速率限制设置为每小时500个请求。 如果超过此限制，公共API服务将通过&#x200B;**HTTP 429“请求过多”消息**&#x200B;进行响应。

### 从学习对象实例和CI_STATS事件生成数据库

学习对象实例事件会发出课程和学习路径的`loInstanceId`、`loId`和`loType`属性。 同样，**CI_STATS**&#x200B;事件仅适用于课程，因为`seatLimit`、`seatAvailability`、`waitListLimit`、`waitlistAvailability`等仅适用于课程。

在某些用例中，需要其他实例数据，如实例名称、状态等。 要获取其他实例数据，应遵循以下方法：

#### 从public-apiGET/learningobjects — 管理员范围中查询信息

客户可以使用上述`GET /learningObjects` API以及包含的实例来获取有关实例的信息。 他们仍应遵循[部分](/help/migrated/integration-admin/feature-summary/webhooks-usage-guide.md#query-the-information-from-the-public-api-get-learningobjects-admin-scope)中提及的方法，以确保费率限制不会被违反。


>[!NOTE]
>
>1. 认证没有ALM中的实例概念。
>2. 无需为CI_STATS获取其他数据，因为已在学习对象实例事件中获取相同的信息。

### 从注册、取消注册、完成和进度事件构建数据库

学习者注册、取消注册、完成和进度在Adobe Learning Manager中作为单独事件发出。 学习者由`userId`属性标识。 但是，某些情况下可能需要客户提供其他学习者信息，例如姓名、电子邮件等。 要获取此数据，客户可以按照下面概述的方法操作：

#### 从管理员或连接器导出用户报告

每当涉及批量注册、批量取消注册等批量工作流程时，应遵循此方法。 Adobe Learning Manager的用户报告包含与用户相关的所有信息。 通过关联从Webhook事件获取的`userId`，客户可以查找此报告（其可能会在客户端公开为数据库、缓存或API终结点）以获取其他详细信息，例如名称、电子邮件、UUID等。 此方法可用于每周或每天同步用户。

#### 从公共APIGET/users — 管理员范围查询信息

当用户在上述报告中不可用时，可以遵循此方法。 方法1和2的组合可确保过去创建的所有现有用户都可以被&#x200B;**[!UICONTROL 用户报告]**&#x200B;覆盖，而新创建的用户仍然可以从API获取。 如果&#x200B;**[!UICONTROL 用户报告]**&#x200B;没有数据，客户可以将userIds作为输入参数发送到`GET /users` API以获取用户信息。 应在客户端缓存这些信息，以防止同一组用户重复调用公共API。 请注意，我们目前将GET/users API的管理员速率限制设置为每小时500个请求。 超过此限制的任何请求将导致&#x200B;**HTTP 429请求过多**&#x200B;个响应。

## 容错

ALM Webhook系统的容错为订阅者提供建议，以供其处理潜在问题，例如事件丢失、重复事件和乱序交付。

ALM的连接超时配置为10秒，套接字超时配置为5秒。 期望客户端在收到消息后立即确认消息。 这是为了确保客户端在处理消息时不会滞后。 如果存在耗时的下游处理过程，客户端仍应立即确认该事件，然后在其终端处理下游处理过程。

### 数据保留

事件会保留7天。 如果在此时间内未处理这些文档，则会永久失去这些文档。 如果恢复是在最后一天进行的，并且需要更多时间，则系统不会延长保留期。
如果生成事件的速度快于事件的使用速度，则某些事件可能会丢失。 尽管这种情况并不常见，但订阅者应进行监控，以防其成为长期问题。

### Webhook禁用

当订阅者无法响应Webhook事件时，ALM系统使用指数回退重试Webhook，以避免订阅者不知所措。

重试过程以5秒的初始间隔开始。 如果订户没有响应，等待时间将增加一倍，达到10、20、40和80秒，最终增加到最多5分钟。 达到5分钟后，系统将继续每5分钟重试一次，直到7天的保留期结束为止。 如果订阅者在此整个期间仍未响应，则将自动禁用Webhook。 我们将定期向订户发送提醒电子邮件。

### 重复事件

如果订阅者在处理某个事件后需要超过5秒的时间作出响应，则系统可能会尝试再次处理同一事件。 建议使用事件ID来跟踪已处理的事件。 此外，如果Webhook在发送事件后崩溃，但在保存该事件之前处理了该事件，则可能会重试同一组事件。 建议使用批处理ID或单个事件ID来识别和忽略任何重复项。

### 无序事件

ALM试图将事件保持正确的顺序，但有时事件可能会无序传递，尤其是在实时和非实时事件之间。

如果管理员一次在课程中注册多名学习者，则注册事件会标记为非实时。 但是，如果学习者快速完成课程，则该完成事件将标记为实时事件，并且可能会在注册事件之前交付。

### 容错建议

为防止发生这些故障，订阅者应主动监视Webhook事件，并对遗漏事件、重复交付或序列无序等问题设置警报。

## Webhook事件的特定准则

1. 如果首先收到LEARNER_PROGRESS事件，则忽略下列事件：

   * COURSE_ENROLLMENT
   * COURSE_ENROLLMENT_BATCH
   * LEARNING_PATH_ENROLLMENT
   * LEARNING_PATH_ENROLLMENT_BATCH
   * CERTIFICATION_ENROLLMENT
   * CERTIFICATION_ENROLLMENT_BATCH

2. 如果LEARNER_PROGRESS事件发生在以下事件之后，请将其忽略：

   * COURSE_COMPLETED
   * COURSE_COMPLETED_BATCH
   * LEARNING_PATH_COMPLETED
   * LEARNING_PATH_COMPLETED_BATCH
   * CERTIFICATION_COMPLETED
   * CERTIFICATION_COMPLETED_BATCH

3. 使用timestamp字段确定是忽略还是处理事件（LEARNER_PROGRESS事件除外）。

## Webhook事件使用最佳实践

* Webhook解决方案用于处理高吞吐量系统，在这些系统中，速度和低延迟至关重要。 因此，客户应确保在收到事件后立即确认该事件。 即使客户一方需要额外处理（如从报告获取数据、API或执行其他操作），也应在收到事件后立即发送确认，并由客户在稍后处理事件。
* 如果未能尽快确认事件，可能会影响事件的实时性质，因为后续事件只有在收到以前的确认后才会发出。
* 客户端可以使用HTTP 202 Accepted状态代码进行响应，以确认事件已被接受。

## 限制

* 学习对象类别下的Webhook事件不考虑工作辅助，因为它们通常用于帮助学习者完成其他学习对象。
* 学习对象实例停用将被视为更新事件。 实例不会存在删除事件，因为它只能停用，不能删除。
* 会话更改将作为实例更新事件的一部分进行捕获。 这仅适用于课程。 学习路径实例或认证实例的传播不会来自较低级别的实体。
* 如果学习路径包含课程，而学习者通过学习路径完成课程，则将生成两个&#x200B;**LearnerProgress**&#x200B;事件 — 一个用于课程，一个用于学习路径。
* 某些工作流会异步计算学习对象的属性，如持续时间和交付类型。 因此，当cron作业处理完毕后，将生成这些学习对象的事件。

## 事件的有效负载示例

+++CI_STATS

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12345-0458-4450-b5dd-6bc1ef4f8b50",
      "eventName": "CI_STATS",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123456785-LoSt",
      "data": {
        "loInstanceId": "course:12345678_14448475",
        "waitlistCount": 0,
        "enrollmentCount": 10,
        "seatLimit": 30
      }
    }
  ]
}
```

+++

+++COURSE_ENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12345c1-4576-4ec5-a057-3a6f078cc9d6",
      "eventName": "COURSE_ENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123424713000-040366-10488-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++COURSE_ENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234ec1-4576-4ec5-a057-3a6f078cc9d6",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123424713000-040366-10488-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++COURSE_COMPLETED

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "c2345c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "12345823000-040363-12018-0",
      "data": {
        "userId": 11080928,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14448484",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
        "hasPassed": true
      }
    }
  ]
}
```

+++

+++COURSE_COMPLETED_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "c23458c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123456823000-040363-12018-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14448484",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
        "hasPassed": true
      }
    }
    ]
}
```

+++

+++LEARNING_PATH_ENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234791-338f-4c4c-83bc-9f73ea794965",
      "eventName": "LEARNING_PATH_ENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123404248000-040653-71396-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:1234567",
        "loInstanceId": "learningProgram:1234567_109139",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++LEARNING_PATH_ENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12340791-338f-4c4c-83bc-9f73ea794965",
      "eventName": "LEARNING_PATH_ENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123404248000-040653-71396-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:1234557",
        "loInstanceId": "learningProgram:1234557_109139",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++LEARNING_PATH_COMPLETED

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "123404e-d554-4027-944b-086debefdddf",
      "eventName": "LEARNING_PATH_COMPLETED",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234604391000-040653-314618-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:92348",
        "loInstanceId": "learningProgram:92348_95662",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
        "hasPassed": true
      }
    }
  ]
  }
```

+++

+++LEARNING_PATH_COMPLETED_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12344e-d554-4027-944b-086debefdddf",
      "eventName": "LEARNING_PATH_COMPLETED_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123404391000-040653-314618-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:92348",
        "loInstanceId": "learningProgram:92348_95662",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
        "hasPassed": true
      }
    } 
    ]
    }
```

+++

+++CERTIFICATION_ENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234e776-148e-4128-80e9-b896a460b655",
      "eventName": "CERTIFICATION_ENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "12344672000-040654-559128-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:123418",
        "loInstanceId": "certification:123418_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
}
```

+++

+++CERTIFICATION_ENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "123472ec1-4576-4ec5-a057-3a6f078cc9d6",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234524713000-040366-10488-0",
      "data": {
        "userId": 12345678,
        "loId": "course:123456798",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++CERTIFICATION_COMPLETED

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123454768000-040654-756257-0",
      "data": {
        "userId": 123456728,
        "loId": "certification:123418",
        "loInstanceId": "certification:134518_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++CERTIFICATION_COMPLETED_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "123453bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234604768000-040654-756257-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:123418",
        "loInstanceId": "certification:123418_160299",
        "loType": "certification",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z"
      }
    }
  ]
  }
```

+++

+++LEARNER_PROGRESS

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "d1234d3a4-c3df-44fa-a1cf-7edd6e3d2075",
      "eventName": "LEARNER_PROGRESS",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235604551000-297002-5823-0",
      "data": {
        "loId": "course:7542090",
        "loType": "course",
        "userId": 12380928,
        "loInstanceId": "course:7232090_10423047",
        "dateStarted": "2024-11-08T03:49:52.000Z",
        "progressPercent": 50
      }
}
]
}
```

+++

+++COURSE_UNENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "f3237817-8cb8-40ea-a441-813bec1c7724",
      "eventName": "COURSE_UNENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1345506253000-040298-24078-0",
      "data": {
        "userId": 12311591,
        "loId": "course:12324298",
        "loInstanceId": "course:12324298_14450088",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
      }
    }
  ]
}
```

+++

+++COURSE_UNENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "f2317817-8cb8-40ea-a441-813bec1c7724",
      "eventName": "COURSE_UNENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "17235506253000-040298-24078-0",
      "data": {
        "userId": 12311591,
        "loId": "course:12324298",
        "loInstanceId": "course:12324298_14450088",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL"
    }
   }
  ]
}
```

+++

+++LEARNING_PATH_UNENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "823df878-1dfd-47ac-9bfe-7d4952e3edd1",
      "eventName": "LEARNING_PATH_UNENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235506667000-040299-28209-0",
      "data": {
        "userId": 12311591,
        "loId": "learning_program:123157",
        "loInstanceId": "learning_program:123157_109139",
        "loType": "learning_program",
        "enrollmentSource": "SELF_ENROLL",
      }
    }
]
}
```

+++

+++LEARNING_PATH_UNENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "8e23f878-1dfd-47ac-9bfe-7d4952e3edd1",
      "eventName": "LEARNING_PATH_UNENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235506667000-040299-28209-0",
      "data": {
        "userId": 12311591,
        "loId": "learning_program:123157",
        "loInstanceId": "learning_program:123157_109139",
        "loType": "learning_program",
        "enrollmentSource": "ADMIN_ENROLL"
      }
    }
]
}
```

+++

+++CERTIFICATION_UNENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "7232766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235507900000-040304-1065-0",
      "data": {
        "userId": 12311591,
        "loId": "certification:123199",
        "loInstanceId": "certification:123199_162078",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL"
      }
    }
  ]
}
```

+++

+++CERTIFICATION_UNENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "7202766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1735507900000-040304-1065-0",
      "data": {
        "userId": 12511591,
        "loId": "certification:139199",
        "loInstanceId": "certification:139199_162078",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_DRAFT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12345da9f-26ec-453c-b56a-cdf18a841948",
      "eventName": "LEARNING_OBJECT_DRAFT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234519188000-040344-48604-0",
      "data": {
        "loId": "course:1234091",
        "loType": "course"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_DELETION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234a690-5517-4c09-9cde-d953cdd8582c",
      "eventName": "LEARNING_OBJECT_DELETION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235605296000-040656-662792-0",
      "data": {
        "loId": "course:12319716",
        "loType": "course"
      }
    }
   ]
}
```

+++

+++LEARNING_OBJECT_MODIFICATION

```
{
  "accountId": 8308,
  "events": [
    {
      "eventId": "223e068-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123350842000-039736-54153-0",
      "data": {
        "loId": "learningProgram:123836",
        "loType": "learningProgram"
      }
    }
   ]
}
```

+++

+++LEARNING_OBJECT_MODIFICATION_BATCH

```
{
  "accountId": 8308,
  "events": [
    {
      "eventId": "1234e068-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235350842000-039736-54153-0",
      "data": {
        "loId": "learningProgram:123836",
        "loType": "learningProgram"
      }
    }
   ]
}
```

+++

+++LEARNING_OBJECT_INSTANCE_MODIFICATION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "121da98-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235603297000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12324298_14453691",
        "loId": "course:12324298",
        "loType": "course"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1231da98-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123603297000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12324298_14453691",
        "loId": "course:12324298",
        "loType": "course"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_INSTANCE_DELETION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12d16e90-d73a-457b-83f3-666ba9654edb",
      "eventName": "LEARNING_OBJECT_INSTANCE_DELETION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235605491000-040657-236307-0",
      "data": {
        "loInstanceId": "course:12319674_14453849",
        "loId": "course:12319674",
        "loType": "course"
      }
    }
  ]
}
```

+++
