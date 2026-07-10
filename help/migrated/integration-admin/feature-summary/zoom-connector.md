---
description: 了解如何将Zoom连接器与Adobe Learning Manager集成
jcr-language: en_us
title: Zoom连接器
contentowner: mmanuel
source-git-commit: 481eed24a5ac72329228c8d27b625d443bd637ce
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 1%

---


# Adobe Learning Manager中的Zoom连接器

## 简介

Adobe Learning Manager中的Zoom连接器允许与Zoom无缝集成，以提供实时虚拟教室会话。 通过此集成，讲师可以直接从Learning Manager主持Zoom会议、注册学习者以及跟踪出席和完成数据。 学习者会收到自动邀请，并且可以通过其Adobe Learning Manager帐户加入会话。 会话结束后，出勤和性能数据会同步回Adobe Learning Manager以进行报告和跟踪。

## 设置Zoom连接器

要配置Zoom连接器，请执行以下操作：

1. 以集成管理员身份登录Adobe Learning Manager.
2. 将鼠标悬停在&#x200B;**缩放**&#x200B;图块上。

   ![](assets/zoom-connector1.png)
   _在Adobe Learning Manager中配置Zoom连接器_

3. 选择&#x200B;**连接**。 此时将打开Zoom连接器设置页面。
4. 在相应字段中键入以下帐户详细信息。 您可以从Zoom帐户管理员处获取这些凭据：

   * 连接名称
   * 缩放帐户ID
   * 客户端 ID
   * 客户端密钥
   * 超级管理员电子邮件地址

   ![](assets/zoom-connector2.png)
   _键入配置详细信息以设置Zoom连接器_

5. 选择&#x200B;**连接**&#x200B;以建立集成。

>[!NOTE]
>
>启用连接器时，**学习者必须为其Zoom和Adobe Learning Manager帐户使用相同的电子邮件地址**，以确保用户数据正确同步。

## 创建Zoom课程

建立连接后：

1. 以&#x200B;**作者**&#x200B;身份登录并创建新的虚拟教室课程。
2. 选择&#x200B;**Zoom**&#x200B;作为课程创建期间的会议系统。
3. 通过管理员、经理或自助注册为学习者分配课程。
4. 注册后，学习者会收到一封包含课程详细信息的电子邮件。
5. 学习者可以登录其Adobe Learning Manager帐户来访问课程并加入Zoom会话。

## 跟踪出勤和完成情况

虚拟会话结束后：

* Adobe Learning Manager会自动从Zoom接收完成状态。
* 管理员可以在Adobe Learning Manager中查看出勤和得分报告，以跟踪学习者的参与程度和表现。

## 创建缩放服务器到服务器OAuth应用程序

要将Zoom连接器与Adobe Learning Manager结合使用，必须创建Zoom服务器到服务器OAuth应用程序并配置所需范围。

### 所需的OAuth范围

在Zoom中创建应用程序时，请确保选择以下范围：

```
| Scope Description | Zoom Scope |
|---|---|
| View all user meetings | meeting:read:admin |
| View and manage all user meetings | meeting:write:admin |
| View report data | report:read:admin |
| View all user information | user:read:admin |
| Manage users | user:write:admin |
| Add a meeting registrant | meeting:write:registrant:admin |
| List all meeting registrants | meeting:read:list_registrants:admin |
| Manage sub-account meetings | meeting:write:meeting:master |
| View meeting participants report | report:read:list_meeting_participants:admin |
```
