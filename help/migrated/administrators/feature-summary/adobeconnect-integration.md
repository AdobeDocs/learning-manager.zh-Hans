---
jcr-language: en_us
title: Adobe Connect 集成
description: 作者可以在创建课程的过程中使用 Adobe Connect 创建虚拟教室课程。 要为 Adobe Learning Manager 帐户启用 Adobe Connect，请与所在公司的管理员联系。
contentowner: jayakarr
exl-id: 13458f93-9ea7-4aab-8b33-3c4f4dd5886d
source-git-commit: 857dddf46e3900fbe2db4e345da2d29050ef3c82
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 49%

---

# Adobe Connect 集成

公司的管理员可以配置 Adobe Learning Manager 帐户设置以启用 Adobe Connect 集成。

## 配置 Adobe Connect {#configureadobeconnect}

1. 以管理员身份登录，单击左侧窗格中的&#x200B;**[!UICONTROL “设置”]**&#x200B;以查看与公司相关的基本信息。单击左侧窗格中的&#x200B;**[!UICONTROL Adobe Connect]**。

   ![](assets/left-pane.png)

   *在左侧窗格中选择Adobe Connect*

1. 单击&#x200B;**[!UICONTROL Adobe Connect配置]**&#x200B;部分中的&#x200B;**[!UICONTROL 立即配置]**&#x200B;链接。

   <!--![](assets/configure-now-connect.png)-->

1. 提供公司的 Adobe Connect 域名和登录凭据。

   ![](assets/adobeconnect-config.png)

   *添加域名和凭据*

   Adobe Connect URL示例： mycompany.adobeconnect.com\
   您需要提供Adobe连接帐户管理员的电子邮件ID。

   Adobe Learning Manager 仅支持 Adobe 托管的 Connect 帐户。示例：.adobeconnect.com。

1. 单击&#x200B;**[!UICONTROL 集成].**

   验证电子邮件ID后，Learning Manager会显示消息“Connect成功集成”。 您可以使用 Adobe Connect 自动查看虚拟教室课程。

   Adobe Connect 帐户管理员应接受 Adobe Connect 的使用条款和条件。如果不接受，则登录身份验证会失败。创建 Adobe Connect 帐户后，请登录一次帐户。在首次登录时，会显示条款和条件页面。

   <!--![](assets/mail-confirmation.png)-->

## 添加虚拟教室会话信息 {#addvirtualclassroomsessioninformation}

如果虚拟教室课程的作者没有提供会话信息，那么管理员可提供会话详细信息。

以管理员身份登录，单击虚拟教室课程名称。单击左侧窗格中的&#x200B;**[!UICONTROL 实例]**，然后单击&#x200B;**[!UICONTROL 会话详细信息]**。  单击“会话详细信息”页面右上角的“编辑”图标以添加会话信息。

![](assets/session-creation-admin.png)

*添加虚拟教室会话信息*

通过 Adobe Learning Manager 和 Adobe Connect 集成来创建虚拟教室模块或会话，您的 Connect 帐户应支持多个会议室，提供足够数量的会议室和在线用户同时使用。这些会议室用于支持 Adobe Learning Manager 虚拟教室模块。Adobe Learning Manager 会为其中每个虚拟教室模块或会话动态创建新的 Connect 会议室。

您必须在 Adobe Learning Manager 之外单独购买 Adobe Connect。

## 学习者出席 {#learnersattendance}

如果虚拟教室课程的主持人不参加会话，那么参加会话的学习者将无法自动注册出席情况。在这种情况下，管理员可以手动记录出席情况。

单击虚拟教室课程，单击下一页左侧窗格中的“出勤情况”并记录出勤情况。

## 支持面向大量受众的Adobe Connect研讨会

在Connect中设置虚拟教室会话时，Adobe Learning Manager支持从Adobe Connect选择研讨会房间。 以前，管理员只能选择会议室类型。 此功能使具有有效研讨会许可证的管理员能够在ALM中安排和管理一次性或大型活动（最多1,500名与会者）。

有关研讨会会议室的详细信息，请参阅此[文章](https://helpx.adobe.com/cn/adobe-connect/using/creating-seminars.html)。

### 支持访问会话分析

讲师可以通过其会话信息板中提供的全新链接，访问其已完成Adobe Connect会话的会话分析。

![](assets/adobe-connect-session-url.png)
_选择会话URL_

此链接将打开Connect中的会话分析仪表板，其中提供了有关会话参与情况的详细见解。
此功能仅适用于通过Adobe Connect进行的会话。 会话分析包括：

* **[!UICONTROL 参与]**：实时会话的整体性能概述
* **[!UICONTROL 交互]**：参与者活动在不同窗格中的详细细目
* **[!UICONTROL 与会者活动]**：参与者参与摘要
* **[!UICONTROL 下载报告]**：用于下载特定于pod的参与数据的报告的选项

![](assets/session-dashboard.png)
_会话仪表板_

有关会话分析的更多信息，请参阅此[文章](https://helpx.adobe.com/in/adobe-connect/using/session-dashboard.html)。
