---
jcr-language: en_us
title: Webhook
description: 了解Webhook，以将课程注册、课程创建和其他信息等实时信息发送到特定URL
contentowner: chandrum
exl-id: 472aaf2b-9c2f-4f43-a791-2b2d81e69471
source-git-commit: e4c3489db8207ead0416656161b918eba42f4582
workflow-type: tm+mt
source-wordcount: '765'
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
