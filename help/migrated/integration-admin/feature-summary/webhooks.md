---
jcr-language: en_us
title: Webhook
description: 了解Webhook，以将课程注册、课程创建和其他信息等实时信息发送到特定URL
contentowner: chandrum
exl-id: 472aaf2b-9c2f-4f43-a791-2b2d81e69471
source-git-commit: 3b35c16d74c83329cee24ee9ad007a53ccbd8cf3
workflow-type: tm+mt
source-wordcount: '1633'
ht-degree: 0%

---

# Webhook

Webhook允许一个实体在特定事件发生时自动向另一个实体发送实时数据或通知。 这样，应用程序就可以向其他应用程序提供信息，而无需经常请求这些信息。 例如，如果用户完成学习管理系统(LMS)课程，Webhook会自动将该信息发送到其他平台，如CRM或报告工具。 Webhook通常用于集成中，以自动化流程并减少系统之间手动更新的需求。 通过提供要向其发送数据的回调URL来设置Webhook。

## Webhook与API

Webhook和API都有助于系统相互通信，但工作方式不同。 通过API，仅在用户请求时共享信息。 例如，如果学习者需要课程进度数据，则会向API发送请求，然后该API会提供信息。 另一方面，当事件发生时，Webhook会立即自动发送数据。 例如，如果学习者完成课程，则学习者无需手动请求即可立即将数据发送到监听程序URL。

## 什么是实时API？

实时API允许应用程序在事件发生时立即交换数据。 传统API需要等待用户请求信息，而实时API则会在数据发生时共享数据。 Webhook充当实时API，每当发生指定事件时帮助立即共享数据。 实时API可确保无需任何手动请求即可立即传输此数据，从而使系统可即时保持更新。

## Webhook事件

Webhook事件是系统中发生的特定操作，可自动将数据发送到侦听器URL。 例如，当学习者注册课程时，将触发Webhook事件并将注册详细信息发送到侦听器URL。

Webhook事件分为两类：

* **实时事件**：事件得到处理并实时发送到目标URL
* **非实时事件**：事件在指定时间批量处理并发送，而不是实时发送

## 监听程序URL

监听器URL是在事件发生时接收数据信息的端点或目标。 每当发生特定事件（例如用户注册了课程），系统就会自动将详细信息发送到此URL，而无需任何手动请求。 监听程序URL是提供所有这些更新的地址。
Webhook会以JSON格式发送相关信息。 以下是Adobe Learning Manager中触发的事件有效负载示例：

```
{
  "accountId": 1010,
  "events": [
    {
      "eventId": "d5fb7071-10a9-46b2-9f9e-79dde346c052",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": 1727414643000,
      "eventInfo": "1727414643000-047210-84242-0",
      "data": {
        "userId": 4279332,
        "loId": "course:7374992",
        "loInstanceId": "course:7376092_10250977",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": 1727414643
      }
    }
  ]
}
```

## 创建和管理Webhook — 集成管理员

按照以下步骤在Adobe Learning Manager中创建Webhook集成：

1. 以&#x200B;**[!UICONTROL 集成管理员]**&#x200B;身份登录。
2. 在主页上，选择&#x200B;**[!UICONTROL Webhook]** > **[!UICONTROL 添加Webhook]**。

   ![](assets/create-webhook.png)
   _添加Webhook_

3. 键入Webhook的&#x200B;**[!UICONTROL 名称]**&#x200B;和&#x200B;**[!UICONTROL 描述]**。
4. 键入侦听器URL作为要在其中传递事件数据的&#x200B;**[!UICONTROL 目标URL]**。
5. 选择任一身份验证方法：
Webhook中的身份验证是一种安全方法，用于确保发送到侦听器URL的数据来自受信任的源。
   * **[!UICONTROL 无]**：无需身份验证。
   * **[!UICONTROL 基本]**：这是基于凭据的身份验证。 输入用户名和密码。
   * **[!UICONTROL 签名]**：系统创建特殊签名并将其添加到Webhook数据。 接收服务器会检查此代码，以确保数据是真实的，且尚未更改。 生成签名并使用它进行身份验证。 以JSON格式下载签名。
6. 从&#x200B;**[!UICONTROL 触发事件]**&#x200B;下拉列表中选择Webhook事件。

   >[!NOTE]
   >
   >您还可以通过从添加Webhook页面选择测试Webhook选项来测试Webhook。

7. 选择&#x200B;**[!UICONTROL 激活状态]**&#x200B;切换以启用Webhook。 启用后，每当发生所选事件时，都将传递数据。

>[!NOTE]
>
>您最多可以创建和管理5个Webhook。

### 编辑Webhook — 集成管理员

遵循这些步骤，从Adobe Learning Manager编辑Webhook：

1. 以&#x200B;**[!UICONTROL 集成管理员]**&#x200B;身份登录
2. 在主页上选择&#x200B;**[!UICONTROL Webhook]**。
3. 选择要编辑的Webhook。

   ![](assets/edit-webhook.png)
   _编辑Webhook_
4. 选择&#x200B;**[!UICONTROL 编辑]**&#x200B;以修改Webhook的详细信息，然后选择&#x200B;**[!UICONTROL 保存]**。

### 删除Webhook — 集成管理员

遵循这些步骤，从Adobe Learning Manager编辑Webhook：

1. 以&#x200B;**[!UICONTROL 集成管理员]**&#x200B;身份登录。
2. 在主页上选择&#x200B;**[!UICONTROL Webhook]**。
3. 选择要删除的Webhook。
4. 选择&#x200B;**[!UICONTROL 删除]**&#x200B;以删除Webhook。

![](assets/delete-webhooks.png)
_删除Webhook_

### 弃用Webhook — 集成管理员

请按照以下步骤弃用Webhook：

1. 以&#x200B;**[!UICONTROL 集成管理员]**&#x200B;身份登录。
2. 在主页上选择&#x200B;**[!UICONTROL Webhook]**。
3. 选择要编辑的Webhook。
4. 选择&#x200B;**[!UICONTROL 编辑]**&#x200B;并禁用&#x200B;**[!UICONTROL 激活状态]**&#x200B;以弃用Webhook。

![](assets/retire-webhook.png)
_弃用Webhook_

## 替代的Webhook {#webhooks-for-alternates}

ALM为替代完成提供专用Webhook事件，以支持自动化、集成以及与外部系统的同步。

该等事件允许外部消费者可靠地区分透过替代关系授出的直接完成与完成。

### 概述

学习者通过替代或关系完成课程时，ALM会触发与标准课程完成Webhook分离的Webhook事件。 这可确保集成在需要时以不同方式响应替代完成。

当发生追溯完成或追溯完成时，还会触发Webhook事件，包括历史更新以及关系更改。

### Webhook事件行为

* 当学习者通过目标课程的备用状态收到已完成时，会触发不同的Webhook事件。
* 该事件会在学习者完成已配置的源课程时生成，该源课程可通过替代关系满足目标要求。
* 完成直接课程时不会触发此Webhook。
* 启用回溯完成或回溯完成时，会为每个受影响的学习者和目标课程激发Webhook事件。

### Webhook负载详细信息

替代完成Webhook负载包括以下关键属性：

* **学习者ID**
标识收到替代完成的学习者。
* **源课程**
学习者直接完成的课程或学习路径。
* **目标课程**
通过替代关系标记为完成的课程。
* **完成方法**
表示完成方法是替代方法。
* **完成日期**
从源课程的完成日期派生。
* **关系类型**
指定关系是否为替代关系。

对于追溯完成情况，Webhook事件表示已撤销现有的替代完成。

### 集成注意事项

外部系统可以使用这些Webhook事件执行以下操作：

* 更新学习者记录
* 同步完成状态
* 触发通知或下游工作流
* 维护审核跟踪以便合规

Webhook使用者应明确区分直接完成和替代完成。

替代完成不会授予技能、徽章和游戏奖励。 在下游系统中应相应地处理反馈。

## 自适应学习路径的Webhook

### 简介

Adobe Learning Manager提供了&#x200B;**Webhook事件**，每当&#x200B;**学习路径（学习计划）**&#x200B;的完成状态被刷新时，都会通知外部系统。 这样，每当回滚或重新计算学习者的完成记录时，您都可以同步下游系统（例如HR、报告或分析平台）。

有两种新的Webhook事件类型可用：

**LEARNING_PATH_COMPLETION_ROLLBACK** - **学习者**&#x200B;自行刷新学习路径的完成状态时触发。

**LEARNING_PATH_COMPLETION_ROLLBACK_BATCH** - **管理员**&#x200B;刷新&#x200B;**一个或多个学习者**&#x200B;学习路径的完成状态时触发（例如，通过批量操作）。

这些事件使用&#x200B;**通用负载结构**，可由Webhook端点使用以更新或重新处理您端上的完成数据。

### 通用有效负载结构

每个Webhook请求包含以下顶层结构：

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "757b9d58-048c-4ae2-9fff-35f9def7ef29",
      "eventName": "LEARNING_PATH_COMPLETION_ROLLBACK",
      "timestamp": "2026-01-20T05:48:10.000Z",
      "eventInfo": "1768888090000-197513-137581-0",
      "data": {
        "userId": 13446697,
        "loId": "learningProgram:157165",
        "loInstanceId": "learningProgram:157165_148769",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2026-01-20T05:44:05.000Z"
      }
    }
  ]
}
```

**相同的结构**&#x200B;用于两种事件类型；只有eventName和数据内的值（例如，userId、loId、enrollmentSource）不同。

#### 示例：学习者发起的刷新

当学习者刷新其自身学习路径的完成状态时，Webhook会发送LEARNING_PATH_COMPLETION_ROLLBACK事件：

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "757b9d58-048c-4ae2-9fff-35f9def7ef29",
      "eventName": "LEARNING_PATH_COMPLETION_ROLLBACK",
      "timestamp": "2026-01-20T05:48:10.000Z",
      "eventInfo": "1768888090000-197513-137581-0",
      "data": {
        "userId": 13446697,
        "loId": "learningProgram:157165",
        "loInstanceId": "learningProgram:157165_148769",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2026-01-20T05:44:05.000Z"
      }
    }
  ]
}
```

当学习者明确请求刷新时，使用此事件在您的外部系统中&#x200B;**重新计算或重置学习者完成数据**。

#### 示例：管理员启动的批量刷新

当管理员为一个或多个学习者执行完成刷新（例如，更正组的历史完成情况）时，Webhook会发出LEARNING_PATH_COMPLETION_ROLLBACK_BATCH事件：

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "757b9d58-048c-4ae2-9fff-35f9def7ef29",
      "eventName": "LEARNING_PATH_COMPLETION_ROLLBACK_BATCH",
      "timestamp": "2026-01-20T05:48:10.000Z",
      "eventInfo": "1768888090000-197513-137581-0",
      "data": {
        "userId": 13446698,
        "loId": "learningProgram:157166",
        "loInstanceId": "learningProgram:157166_148770",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2026-01-21T05:44:05.000Z"
      }
    }
  ]
}
```

在批量操作中，您的Webhook端点可能会在单个请求中接收&#x200B;**多个事件对象**，每个学习者一个事件的完成情况已刷新。 集成应循环访问事件数组，并独立处理每个事件。

### 如何在集成中使用这些活动

您可以使用这些Webhook事件执行以下操作：

在回滚或重新计算完成时，**将完成记录**&#x200B;与外部LMS/LRS、HR或报告系统同步。

**触发下游工作流**，例如重新分配、通知或重新计算认证和徽章。

**通过将事件Id、时间戳和eventInfo以及学习者和学习路径标识符记录下来，来维护审核记录**。

至少，Webhook处理程序应：

验证负载并解析事件[]。
使用eventName确定更改是&#x200B;**learnerinitiated**&#x200B;还是&#x200B;**admin/batchinitiated**。

使用userId、loId和loInstanceId查找并更新系统中的相应记录。
如果同一事件被多次传递，则利用eventId可防止重复处理。

## 用于添加和删除用户组成员资格的Webhook

两种新的Webhook事件类型具有最终状态：

* 响应:ASYNCAPI_USERGROUP_USER_ADDED
* 响应:ASYNCAPI_USERGROUP_USER_REMOVED

### 示例有效负载

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5",
      "eventName": "RESPONSE:ASYNCAPI_USERGROUP_USER_REMOVED",
      "timestamp": "2026-03-18T13:38:12.000Z",
      "eventInfo": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5",
      "data": {
        "status": "SUCCESS",
        "request": {
          "metadata": { "event_id": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5" },
          "data": [ { "type": "user", "id": "13446641" } ]
        }
      }
    }
  ]
}
```

### 关键元素

* `accountId`标识ALM帐户。
* `events`是事件对象的数组。
* `eventId`与原始异步请求标识符匹配。
* `eventName`表示添加或删除操作。
* `timestamp`显示完成时间。
* `data.status`当前报告成功批处理为“SUCCESS”。
* `data.request`包含您发送的确切请求。

您的集成应主要关闭`eventId`（或`metadata.event_id`）和`status`。

### 示例

#### 异步添加用户

**步骤1. 进行异步调用**

POST/primeapi/v2/async/userGroups/12345/users

```
{
  "metadata": {
    "event_id": "sync-2026-03-30T10:15:00Z-ug-12345",
    "sourceSystem": "HRIS",
    "batchId": "hr_2026_03_30_0001"
  },
  "data": [
    { "type": "user", "id": "11101219" },
    { "type": "user", "id": "11101220" }
  ]
}
```

**步骤2. 读取立即响应**

```
{ "event_id": "sync-2026-03-30T10:15:00Z-ug-12345" }
```

您现在可以在系统中将此作业标记为已提交。

**步骤3. 处理Webhook**

Webhook回调示例：

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "sync-2026-03-30T10:15:00Z-ug-12345",
      "eventName": "RESPONSE:ASYNCAPI_USERGROUP_USER_ADDED",
      "timestamp": "2026-03-30T10:15:43.000Z",
      "data": {
        "status": "SUCCESS",
        "request": {
          "metadata": {
            "event_id": "sync-2026-03-30T10:15:00Z-ug-12345",
            "sourceSystem": "HRIS",
            "batchId": "hr_2026_03_30_0001"
          },
          "data": [
            { "type": "user", "id": "11101219" },
            { "type": "user", "id": "11101220" }
          ]
        }
      }
    }
  ]
}
```

一般消费者会：

* 查找内部作业。
* （可选）使用/userGroups/{id}/usersGET验证成员资格。
* 将作业标记为已完成。

#### 异步删除用户

移除是对称的，使用具有相同主体结构的DELETE。

```
{
  "metadata": {
    "event_id": "sync-2026-03-30T11:00:00Z-ug-12345",
    "sourceSystem": "HRIS",
    "batchId": "hr_2026_03_30_0002"
  },
  "data": [ { "type": "user", "id": "11101219" } ]
}
```

立即响应：

```
{ "event_id": "sync-2026-03-30T11:00:00Z-ug-12345" }
```

稍后，具有相同事件ID的RESPONSE:ASYNCAPI_USERGROUP_USER_REMOVED Webhook到达。

有关详细信息，请查看用户组成员资格的[异步公共API](/help/migrated/api-changes-alm.md#asynchronous-public-apis-for-user-group-membership)。
