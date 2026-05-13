---
description: 了解如何将Marketo Engage连接器与Adobe Learning Manager集成
jcr-language: en_us
title: Marketo Engage 连接器
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 3%

---


# Adobe Learning Manager中的Marketo Engage连接器

## 简介

通过Marketo Engage连接器，Adobe Learning Manager可与营销自动化平台Marketo Engage无缝集成。 此集成可帮助营销人员通过将学习者行为数据与Adobe Learning Manager数据库同步来跟踪和处理来自Marketo的数据。

该Marketo Engage连接器使两个系统之间的数据无缝同步，并允许营销人员使用学习活动数据来创建有针对性的营销活动。

Marketo Engage连接器允许您：

- 将用户添加到Adobe Learning Manager时，自动在Marketo Engage数据库中添加或更新潜在客户。
- 在Marketo中将用户学习行为（例如课程注册、完成、技能分配和技能完成）同步为自定义对象。
- 使用此数据在Marketo中创建动态营销活动，利用&#x200B;**智能列表**&#x200B;等功能。

此集成可帮助营销人员根据在Adobe Learning Manager中的学习旅程来定位受众。

## 主要功能

- 基于Adobe Learning Manager用户自动创建和更新潜在客户。
- 将学习活动（注册、完成、技能成就）作为自定义对象导出到Marketo。
- 按需计划或触发导出。
- 支持统一报告，包括：
   - 用户报告
   - 学习成绩单
   - 用户技能报告

## 先决条件

在集成之前，请确保您的Marketo帐户支持通过API创建架构。

您需要以下详细信息才能创建连接：

- **连接名称**
- **客户端ID**
- **客户端密钥**
- **Marketo Engage域**

>[!NOTE]
>
>您可以从Marketo Engage应用的&#x200B;**LaunchPoint**&#x200B;下获取客户端ID和客户端密钥，并从&#x200B;**Web服务**&#x200B;部分获取域。

## 设置连接器

要设置Marketo Engage连接器，请执行以下操作：

1. 以集成管理员身份登录Adobe Learning Manager.
2. 将鼠标悬停在&#x200B;**Marketo Engage**&#x200B;磁贴上，然后选择&#x200B;**连接**。

   ![](assets/marketo-engage-connector1.png)
   _选择“连接”以配置Marketo Engage连接器_

3. 键入所需的凭据

   - 连接名称
   - 客户端 ID
   - 客户端密钥
   - Marketo Engage 域

   ![](assets/marketo-engage-connector2.png)
   _键入Marketo Engage连接器的所需详细信息_

4. 选择&#x200B;**连接**&#x200B;以建立连接。

## 活动和活动触发器

您可以根据以下事件触发数据导出到Marketo Engage：

- 新用户将添加到Adobe Learning Manager。
- 用户已注册一门课程。
- 用户完成课程。
- 用户已注册一项技能。
- 用户完成技能。

可以&#x200B;**按需**&#x200B;或&#x200B;**按计划**&#x200B;导出这些事件。

## 列映射

Marketo使用两个数据库：

- **潜在客户数据库** — 用于用户记录（潜在客户）
- **自定义对象数据库** — 用于自定义活动和事件记录

要在Adobe Learning Manager和Marketo之间映射字段，请执行以下操作：

1. Adobe Learning Manager中的&#x200B;**用户报告**&#x200B;字段显示在一列中。
2. 相邻列中列出了相应的&#x200B;**Marketo字段**。
3. 将适当字段从Learning Manager映射到Marketo以创建和更新潜在客户。
4. 映射之后，所有导出的用户都将显示为Marketo Lead数据库中的潜在客户。

**Marketo自定义对象**&#x200B;部分中导出的报告的前缀为“cp_”。

## 支持的导出事件

您可以将以下与用户相关的事件导出到您的Marketo Engage实例：

- 已添加新用户
- 已更新用户元数据
- 用户活动已更新
- 培训注册
- 自助注册
- 技能完成

这些导出内容有助于利用学习活动数据促进参与并个性化外联活动。
