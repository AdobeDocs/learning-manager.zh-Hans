---
title: Live Hub会话中的隐藏字幕
description: 了解隐藏字幕如何实时显示口语内容，以便讲师和学习者可以在实时中心会话期间关注它们。
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: 574ba5fd9ac9dc02130a39006574c9ca1ce6c1d1
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 4%
---

# 了解隐藏式字幕

在实时中心会话期间，系统会自动生成隐藏字幕，并在与会者发言时持续更新。 字幕显示在专用显示区域中，并以讲师在&#x200B;**会议室设置**&#x200B;中选择的语言显示。

讲师和参与者都可以查看字幕。 每个与会者可以独立显示或隐藏字幕，而不会影响其他与会者的字幕设置。

只有讲师才能更改字幕语言。 参与者只能使用讲师选择的语言查看字幕。 参与者无法更改字幕的语言。

## Live Hub如何确定字幕语言

Live Hub会根据以下优先级顺序自动选择字幕语言：

1. **课程语言：**&#x200B;如果字幕支持实时中心使用课程语言。 对于多语言课程，如果当前课程实例使用的语言不支持隐藏字幕，实时中心会选择第一个支持隐藏字幕的课程实例的语言。 有关详细信息，请查看[ALM](../../migrated/languages-supported.md)中支持的语言。
1. **帐户语言：**&#x200B;如果课程语言不受支持，Live Hub会检查帐户语言，并在受支持时使用它。

>[!NOTE]
>
>如果课程语言和帐户语言均不受支持，实时中心会选择英语作为字幕语言。 此外，字幕默认处于关闭状态，必须手动启用。

## 隐藏字幕支持的语言

Live Hub支持以下语言的隐藏字幕：

* 英语
* 法语
* 德语
* 中文
* 西班牙语
* Italiano
* 日语
* 葡萄牙语
* 丹麦语
* 荷兰语
* 芬兰语
* 土耳其语
* 韩语
* 挪威语
* 瑞典语
* 俄语

## 隐藏字幕的工作方式

在Live Hub会话中，会自动生成隐藏字幕。 字幕在专用面板中显示，并在参与者说话时不断更新。 讲师和学习者都可以查看字幕。

每个参与者可以按照自己的喜好显示或隐藏字幕。 更改此设置不会影响其他参与者。

![](assets/closed-captions-overview.png)
*显示会话中隐藏字幕的实时中心界面*

## 角色和权限

在Live Hub会话中，讲师和学习者均可使用&#x200B;**隐藏字幕**&#x200B;功能。 可用操作因用户角色而异。

| **讲师** | **学习者** |
|---|---|
| [显示隐藏式字幕](../getting-started-with-live-hub/manage-closed-captions-as-an-instructor.md#display-closed-captions) | [显示隐藏式字幕](../getting-started-with-live-hub/manage-closed-captions-as-a-learner.md#display-closed-captions) |
| [更改隐藏字幕的外观](../getting-started-with-live-hub/manage-closed-captions-as-an-instructor.md#change-the-appearance-of-closed-captions) | [更改隐藏字幕的外观](../getting-started-with-live-hub/manage-closed-captions-as-a-learner.md#change-the-appearance-of-closed-captions) |
| [选择字幕语言](../getting-started-with-live-hub/manage-closed-captions-as-an-instructor.md#select-the-caption-language) | |