---
description: 了解讲师和同类经理如何获得讨论区活动的电子邮件摘要，以及如何使用API管理设置和订阅者
jcr-language: en_us
title: 讨论区讲师通知
exl-id: 370c9add-5572-4555-8a95-ddb470c230f4
source-git-commit: 650ec8159a4291189dfc38b03701b7b96932233d
workflow-type: tm+mt
source-wordcount: '1231'
ht-degree: 0%
---

# 讨论区讲师通知

## 概述

讨论区讲师通知向讲师、同类经理和管理员发送电子邮件摘要，说明其所监控讨论区中最近的活动。 对于管理多个组群并同时参加多个讨论区的讲师而言，此功能非常有用。

学员经理是指管理一组学习者（一组学员）并按相同计划一起参加课程或项目的人员。

讲师不会单独打开每个讨论区，而是会按您配置的频率接收所订阅讨论区的实时应用程序内警报和电子邮件摘要。 您通过[`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-sequence)和[订户API](api-changes-dec-2026.md#api-get-subscribers)管理讨论区订阅和通知设置。

## 关键功能

* 您可以使用订阅者API（[`POST /boards/{id}/subscribers`](api-changes-dec-2026.md#api-subscribe-users)，作用域`admin:write`）将活动Adobe Learning Manager用户订阅到选定的讨论区。 发送通知时，用户必须有权访问该讨论区。
* 用户会收到有关已启用事件类型的实时应用程序内通知以及按讨论区分组的电子邮件摘要。 事件类型由[`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-sequence)中的帐户级别设置（`notifyNewPost`、`notifyComment`和`notifyReply`）控制。
* 摘要窗口是指其活动被收集到一个摘要电子邮件中的时间段。 在帐户级别使用`digestFrequencyHours`属性设置该属性，范围为1到168小时（例如，每日摘要为24小时）。 它适用于帐户中的所有用户。
* 您可以按用户ID或电子邮件地址订阅用户，并且可以在一个请求（[批量订阅](api-changes-dec-2026.md#bulk-subscriptions)）中添加多个用户。 首先在Learning Manager中以常规方式创建用户。
* 摘要电子邮件会列出已启用事件类型的每个新帖子、评论和回复，以及讨论区名称、作者的姓名和电子邮件地址以及一个直接链接。 它还显示自摘要时段开始以来的更新计数。
* `boardSubscriptionSettings` API和订阅者API是公共API，因此您无需用户界面即可管理设置和订阅（API驱动的集成）。

## 用例

以下用例显示讲师通知如何发挥作用：

| 用例 | 通知有何帮助 |
|---|---|
| 监控多个同类群组 | 讲师如果负责多个同类群组，可以从与这些同类群组关联的讨论区中接收汇总的活动。 |
| 查看学习者参与情况 | 同类经理可以监控新的撰稿情况并确定正在进行的讨论，而无需单独检查每个董事会。 |
| 跟踪跟进对话 | 摘要中的评论和答复可帮助讲师确定可能需要指导或审核的讨论。 |

## 重要注意事项

* 发送通知后，用户必须能够访问讨论区。 在交付时再次检查访问权限，而不仅仅是在订阅用户时。 如果订户无法访问讨论区，则保留订阅，但跳过该讨论区的通知。
* 摘要会以一封电子邮件的形式发送，因此，繁忙的讨论区可能会让它变得很长。 例如，一组约40名学习者可在6小时内发布数百条评论。
* 如果您的讨论区非常活跃，请使用较短的摘要频率（例如每六小时一次），这样每封电子邮件都可保持可管理性。 在[`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-create-settings)中使用`digestFrequencyHours`设置频率。
* 电子邮件摘要中的帖子数量限制为每篇文章20条。 同样的帽子独立地适用于每块板的评论(20)和回复(20)。 只有显示的列表会被截断；标题/副标题计数始终反映窗口的真实、未截断的活动。
* 订阅者的数量上限为每板200个。
* 由于内容直接通过电子邮件发送，而不是作为附件发送，因此电子邮件正文也有大小限制。

## 订阅模式、权限和资格

* 订户是从讨论区接收通知的用户。 董事会订阅独立于与董事会用户现有的跟进关系。
* 通过OAuth进行身份验证且具有`admin:read`和`admin:write`作用域的任何人都可以使用订阅设置和订阅者API。 `admin:read`允许您列出订户并读取设置。 `admin:write`允许您添加或删除订阅者并更改设置。
* 您可以订阅任何Learning Manager用户，但该用户必须存在、处于活动状态并有权访问该讨论区以接收通知。 发送通知和摘要时，将重新检查访问权限。
* 如果用户失去访问权限，将跳过该板的传送，并保留该订阅。 如果访问返回，则恢复传递。
* 您可以在一个请求（批量订阅）中将多个用户添加到讨论区。 如果已订阅用户，则请求仍会成功，并且不会创建重复项。 有关请求格式、207多状态响应和失败案例，请参阅[批量订阅](api-changes-dec-2026.md#bulk-subscriptions)。

## 摘要内容

### 包含的事件

当[`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-create-settings)中的匹配设置为`true`时，摘要包含新帖子、评论和回复： `notifyNewPost`、`notifyComment`和`notifyReply`。 你使用`POST`或`PATCH /boardSubscriptionSettings`设置这些项。 默认情况下，所有设置均为`false`。

### 排除的事件

摘要排除[`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-create-settings)（例如，`notifyComment`）中的匹配设置为`false`的事件。 没有符合条件的活动时不会发送摘要。

### 摘要电子邮件布局示例

系统会向每个具有符合条件的活动的订阅板发送摘要电子邮件。 其结构如下：

* **摘要行：**&#x200B;电子邮件将打开并显示讨论区上的总更新数（例如，7个更新）、按类型划分的细目（例如，新帖子和评论），以及计算活动开始的时间。
* **讨论区部分：**&#x200B;活动分组在讨论区名称下。 每个帖子都列在其下方。
* **项目详细信息：**&#x200B;每个帖子、评论或回复都显示创建它的用户的姓名和电子邮件地址，以及指向该项目的链接。
* **链接：**&#x200B;选择链接即可直接打开帖子、评论或回复。 收件人必须登录才能打开链接。
* **评论和回复：**&#x200B;这些评论和回复与帖子出现在同一封电子邮件中，因此讲师可以看到跟进对话以及新主题。

## 配置通知

### 使用API配置设置

您通过两个公共API管理通知：在帐户级别应用的[`boardSubscriptionSettings` API](api-changes-dec-2026.md#api-sequence)和为每个讨论区应用的[订户API](api-changes-dec-2026.md#api-get-subscribers)。 都使用OAuth作用域`admin:read`和`admin:write`。 按以下顺序调用它们：

1. 使用[`POST /boardSubscriptionSettings`](api-changes-dec-2026.md#api-create-settings)设置帐户级别设置。
1. 稍后需要时，使用[`PATCH /boardSubscriptionSettings`](api-changes-dec-2026.md#api-update-settings)更改设置。
1. 使用[`GET /boardSubscriptionSettings`](api-changes-dec-2026.md#api-get-settings)检索帐户级别设置。
1. 列出[`GET /boards/{id}/subscribers`](api-changes-dec-2026.md#api-get-subscribers)的讨论区订阅用户。
1. 将用户订阅到具有[`POST /boards/{id}/subscribers`](api-changes-dec-2026.md#api-subscribe-users)的讨论区。
1. 从包含[`DELETE /boards/{id}/subscribers/{userId}`](api-changes-dec-2026.md#api-unsubscribe-user)的讨论区取消订阅用户。

使用`boardSubscriptionSettings` API设置摘要频率（以小时为单位），并打开或关闭摘要的帖子、评论和回复。 例如，摘要频率为1小时的帐户每小时收到一封摘要电子邮件。 默认情况下，所有事件设置均为`false`。

### 管理订阅者

使用订阅者API选择将哪些活动Learning Manager用户订阅到哪些讨论区。 认购事项独立于现有董事会跟进关系。 用户必须能够看到讨论区才能接收其通知，这意味着用户应登录。 不可见性会禁止传送，但不会删除订阅。

### 启用该功能

要启用讲师通知，请创建帐户级别设置，然后将用户订阅至讨论区，如[2026年11月的API更改](api-changes-dec-2026.md)中所述。 之后，系统会收集在配置的时间间隔内创建的新帖子、评论和回复。 在间隔结束时，订户接收涵盖已订阅讨论区上合格活动的摘要通知。

了解有关2026年12月[ API更改](api-changes-dec-2026.md)中API更改的更多信息。
