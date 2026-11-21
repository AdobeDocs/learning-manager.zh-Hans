---
description: 在讲师编辑会话详细信息时，获取Adobe Learning Manager中的Webhook事件，并使学习者通知和已连接系统保持最新。
jcr-language: en_us
title: 接收讲师会话编辑的Webhook事件
exl-id: 6fa4b71b-a8f4-40a2-ab57-bb7f3016542c
source-git-commit: 90b45cb128b74ecb33a89bf42ef4d6e960101ff0
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%
---

# 讲师用于学习对象实例编辑的Webhook事件

Adobe Learning Manager提供Webhook事件，用于在学习对象(LO)实例（例如讲师主导的课程会话）被修改时通知外部系统。 以前，这些事件仅在管理员或作者修改学习对象实例时触发。 讲师编辑会话详细信息时现在也会触发Webhook事件。

您可以使用这些事件通过教师更改使外部系统（如电子邮件服务、日历、报告工具或分析平台）保持最新。 例如，您可以在会话时间发生变化时通知学习者。

讲师的编辑使用现有的学习对象实例修改事件，因此未引入新的事件类型。

>[!NOTE]
>
>只有当活动Webhook订阅学习对象实例修改事件时，讲师才能编辑以触发Webhook。 了解如何[以集成管理员身份创建和管理Webhook](/help/migrated/integration-admin/feature-summary/webhooks.md#create-manage-webhooks)。

## 支持的讲师编辑

当讲师编辑以下任何会话详细信息时，会触发Webhook事件：

* 会话计时

* 积分

* 时区

* 地点

* 注册限制

* 轮候表限制

* 允许提交

## Webhook负载结构

每个Webhook请求包含以下顶层结构：

```json
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

无论谁修改学习对象实例，均使用相同的结构。 有效负载不指示讲师、管理员或作者是否进行了更改。

当讲师更改会话详细信息（如时区、注册限制或轮候表限制）时，Webhook会将此事件发送到侦听器URL。 使用此事件可检索最新会话详细信息并通知学习者或更新外部系统。

## 检索更新的会话详细信息

Webhook事件标识已修改的LO实例。 要获取更新后的会话详细信息，请从事件中使用`loId`调用Learning Manager公共API (Prime API)：

```http
GET /primeapi/v2/learningObjects/{loId}
```

找到与响应中的`loInstanceId`匹配的实例，然后将其与系统中存储的数据进行比较。

## 生成与Webhook事件的集成

您可以使用这些Webhook事件执行以下操作：

* 当会话详细信息（如日期、时间、时区或地点更改）发生变化时，通过外部电子邮件或消息服务发送学习者通知。

* 将会话数据与外部日历、报告或分析系统同步。

* 跟踪会话的注册限制或轮候表限制被修改时的容量变化。

* 通过将学习对象和实例标识符一起记录`eventId`、`timestamp`和`eventInfo`来维护审核跟踪。

至少，Webhook处理程序应：

* 验证负载并分析`events[]`。

* 使用`eventName`标识学习对象实例修改事件。

* 使用`loId`和`loInstanceId`查找系统中相应的记录，并调用公共API检索当前会话详细信息。

* 如果同一事件被多次传递，请使用`eventId`来阻止重复处理。

同一事件也会针对讲师、管理员和作者所做的编辑发送，因此您的集成可能会比以往更频繁地收到该事件。 在发送通知之前，将检索到的会话详细信息与系统中的数据进行比较。 然后，仅在相关详细信息更改时通知学习者。
