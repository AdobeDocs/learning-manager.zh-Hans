---
jcr-language: en_us
title: Adobe Learning Manager 与 Slack 集成
description: Adobe Learning Manager 与 Slack 集成
contentowner: dvenkate
source-git-commit: 864b1796f1ca99ae7b5643e8c58d1756ff2461a1
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 43%

---



# Adobe Learning Manager 与 Slack 集成

我们已&#x200B;**移除****Slack**&#x200B;作为Learning Manager中的连接器。 您将无法再访问Slack连接器。

作为 Slack 用户，您可以将 Slack 应用程序目录中的 Adobe Learning Manager 应用程序安装到您的 Slack 团队中，然后直接从 Slack 中浏览 Adobe Learning Manager 的内容。您可以与Primebot交互以在Learning Manager中搜索新课程、查看推荐内容并收到临近截止日期的通知。 您还可以注册并直接从Slack中学习。

Learning Manager的Azure实例不支持Learning ManagerSlack应用程序。

## 安装 Adobe Learning Manager 应用程序 {#installingadobecaptivateprimeapp}

作为学员，您可以在您的 Slack 帐户中安装 Adobe Learning Manager 应用程序。 要安装应用程序，请在您的 Slack 帐户中打开 App 目录并搜索 Adobe Learning Manager。下载并安装该应用程序。 如果您的帐户中未批准该应用程序，请联系您的集成管理员进行批准。 如果已获得批准，您将能够登录。

## 批准学员以集成管理员身份登录 {#approvinglearnersigninasanintegrationadmin}

作为集成管理员，要审批学习者在Slack上使用Prime应用程序的权限，请执行以下步骤。

1. 从左窗格中选择&#x200B;**[!UICONTROL 应用程序]**，然后单击&#x200B;**[!UICONTROL 特色应用程序]**&#x200B;选项卡。

   ![](assets/featuredapps.jpg)

1. 单击&#x200B;**[!UICONTROL Slack]**&#x200B;图块>松弛集成页打开。 单击右上角的&#x200B;**[!UICONTROL 批准]**&#x200B;以批准该应用程序。

   ![](assets/approval.png)

1. 返回到&#x200B;**[!UICONTROL 应用程序]**&#x200B;页面。 批准后，Slack应显示在&#x200B;**[!UICONTROL 外部应用程序]**&#x200B;选项卡中。
1. 学习者现在可以使用Slack登录其Prime帐户。

## 原始功能 {#primebotfunctionalities}

您现在可以开始与Primebot交互。 以下是机器人的功能。

1 — 命令

&#42;/prime&#42;可用于有关您的Adobe Learning Manager帐户的一次性尖锐查询。

可用子命令包括：

/prime查找`<query>` — 搜索课程、认证等。

/prime推荐 — 显示推荐

/prime截止日期 — 显示逾期和即将到来的截止日期

/prime注册 — 显示注册

/prime skills — 显示技能

/prime通知 — 显示通知

/prime目录 — 显示目录

/prime邀请 — [仅限管理员]邀请当前团队中的Slack用户试用primebot

/prime配置文件 — 显示配置文件

/prime注销 — 注销此Slack团队中的Prime帐户

/prime帮助 — 显示帮助消息

2 — 推荐

您可以尝试使用`show my recommendations`等短语，从您的Adobe Learning Manager帐户获取推荐课程、认证和学习计划的个性化列表。

3 — 搜索

您可以尝试`search for machine learning`或`search for artificial intelligence`等短语。 您可以使用短语（如`search for machine learning certifications`、`search for artificial intelligence courses`或`search for adobe photoshop job aids`）指定学习对象的类型。 您还可以使用短语（如`search for machine learning in Lynda catalog`）在目录中搜索。

4 — 截止日期

使用短语（如`show my deadlines`）从您的Adobe Learning Manager帐户获取逾期和即将到来的截止日期的列表。 您可以用`show my overdue deadlines`或`show my upcoming deadlines`等短语筛选过期或即将到来的截止日期。
