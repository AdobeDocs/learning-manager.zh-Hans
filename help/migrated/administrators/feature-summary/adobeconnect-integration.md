---
jcr-language: en_us
title: Adobe Connect集成
description: 作者可以在创建课程的过程中使用Adobe Connect创建虚拟教室课程。 要为Learning Manager帐户启用Adobe Connect，您需要联系公司管理员。
contentowner: jayakarr
source-git-commit: 0052ccb2f5a8f9617bca2c7bad91c0cd18338b66
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---



# Adobe Connect集成

公司的管理员可以配置Learning Manager帐户的设置，以启用Adobe Connect集成。

## 配置Adobe Connect {#configureadobeconnect}

1. 在管理员登录中，单击 **[!UICONTROL 设置]** ，查看贵公司的基本信息。 点击 **[!UICONTROL Adobe Connect]** 在左侧窗格中。

   ![](assets/left-pane.png)

   *在左侧窗格中选择Adobe Connect*

1. 点击 **[!UICONTROL 立即配置]** 链接进入 **[!UICONTROL Adobe Connect配置]** 部分。

   <!--![](assets/configure-now-connect.png)-->

1. 提供公司的Adobe Connect域名和登录凭据。

   ![](assets/adobeconnect-config.png)

   *添加域名和凭据*

   Adobe Connect URL示例： mycompany.adobeconnect.com\
   您需要提供Adobe连接帐户管理员的电子邮件ID。

   Learning Manager仅支持Adobe托管的连接帐户。 示例：.adobeconnect.com。

1. 点击 **[!UICONTROL 集成].**

   验证电子邮件ID后，Learning Manager会显示消息“Connect成功集成”。 您可以使用Adobe Connect自动查看虚拟教室课程。

   Adobe Connect帐户管理员应接受Adobe Connect的使用条款和条件。 如果不接受，则登录身份验证可能会失败。 创建Adobe Connect帐户后，请登录一次帐户。 在首次登录时，会显示条款和条件页面。

   <!--![](assets/mail-confirmation.png)-->

## 添加虚拟教室会话信息 {#addvirtualclassroomsessioninformation}

如果虚拟教室课程的作者未提供会话信息，则管理员可提供会话详细信息。

以管理员身份登录，单击虚拟教室课程名称。 点击 **[!UICONTROL 实例]** ，然后单击 **[!UICONTROL 会话详细信息]**.  单击“会话详细信息”页面右上角的“编辑”图标以添加会话信息。

![](assets/session-creation-admin.png)

*添加虚拟教室会话信息*

通过AdobeLearning Manager和Adobe Connect集成来创建虚拟教室模块或会话，您的Connect帐户应支持多个会议室，提供足够数量的会议室和在线用户同时使用。 这些会议室用于托管Learning Manager虚拟教室模块。 Learning Manager会为其中每个虚拟教室模块或会话动态创建新的Connect会议室。

您必须在AdobeLearning Manager之外单独购买Adobe Connect。

## 学习者出席 {#learnersattendance}

如果虚拟教室课程的主持人不参加会话，那么参加会话的学习者将无法自动注册出席情况。 在这种情况下，管理员可以手动记录出席情况。

单击虚拟教室课程，单击下一页左侧窗格中的“出勤情况”并记录出勤情况。
