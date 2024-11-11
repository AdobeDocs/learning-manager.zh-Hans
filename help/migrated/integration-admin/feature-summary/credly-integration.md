---
jcr-language: en_us
title: 有信心
description: 了解与ALM可信集成，以从平台跨各种社交媒体渠道管理和共享外部徽章
contentowner: chandrum
source-git-commit: a27c1566678d697512a75d94804b8804b5dc9b2b
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# 有信心

[Credly](https://info.credly.com/)是一个数字凭据平台，允许学习者和组织赚取、分享和验证专业成就，例如徽章或认证。 学习者可以通过其Credly个人资料在社交媒体和其他位置管理和共享徽章。

## 先决条件

为您的组织设置一个可信帐户。 在Adobe Learning Manager中使用学习者的电子邮件ID将学习者添加到“可信”。 如此一来，学习者就能在Credly和Adobe Learning Manager上看到徽章。

## 将Credly连接器添加到Adobe Learning Manager

按照以下步骤将Credly连接器添加到Adobe Learning Manager：

1. 以&#x200B;**[!UICONTROL 集成管理员]**&#x200B;身份登录。
2. 选择“**[!UICONTROL 可信]**”>“**连接**”以将“**[!UICONTROL 可信]**”连接器添加到Adobe Learning Manager。

   ![](assets/connector-credly.png)
   _添加Credly连接器_

3. 键入&#x200B;**[!UICONTROL 连接名称]**。
4. 键入&#x200B;**[!UICONTROL 组织ID]**&#x200B;和&#x200B;**[!UICONTROL 授权令牌]**。

   >[!NOTE]
   >
   >Credly中的每个徽章都附带一个组织ID和授权令牌。 从Credly复制这些值。

5. 键入&#x200B;**[!UICONTROL 主机名]**&#x200B;并选择&#x200B;**[!UICONTROL 连接]**。

## 从Credly迁移徽章

Adobe Learning Manager中的badge.csv允许从现有LMS或外部系统迁移徽章。 badge.csv已更新为两个新列：

* 外部徽章ID
* 外部徽章提供商。

外部徽章ID是指“可信”平台中的徽章模板ID，外部徽章提供商是“可信”。 在badge.csv中添加这些值，然后按照[迁移手册](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/migration-manual#migrationprocedure)中提到的步骤迁移csv。

## 创建技能 — 管理员

将徽章导入Adobe Learning Manager后，管理员可将此徽章创建为技能。 要了解如何创建技能，请参阅[创建和修改技能](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/skills-levels)。

### 为学习对象 — 作者分配技能/徽章

作者/管理员可以将这些凭据导入的ALM徽章分配给课程、学习路径或认证（而不仅仅是技能），并且在使用这些学习对象时，徽章将会实现并可以在Credly和ALM应用程序上查看。

学习者可以以“可信”登录，并查看“可信”平台中的徽章。 来自Credly，他们可以在LinkedIn和其他社交媒体等外部平台上分享徽章。

