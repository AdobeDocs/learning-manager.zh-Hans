---
jcr-language: en_us
title: Adobe Learning Manager 中未显示选择按钮
description: 由于缺少单选按钮，管理员无法指定或删除角色、发送欢迎邮件或删除用户。
contentowner: nluke
exl-id: d2c86f9f-3e79-4f1f-992e-f92873940061
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 64%
---
# Adobe Learning Manager 中未显示选择按钮

## 问题

由于缺少单选按钮，管理员无法执行以下操作（不是详尽列表）：

* 分配或删除角色。
* 发送欢迎电子邮件。
* 删除用户。

## 原因

此问题是帐户的主题不正确所致。

![](assets/radio-buttons.png)

*单选按钮不可见*

## 解决方法

重新加载主题并修复单选按钮的外观。 执行以下操作：

1. 以管理员身份单击&#x200B;**[!UICONTROL “品牌推广”]**。
1. 在“**主题**”部分，单击“**[!UICONTROL 编辑]”。**
1. 选取任意主题并保存更改。

   ![](assets/set-themes.png)

   *选择任意主题*

1. 恢复为上一个主题并保存更改。
1. 注销 Adobe Learning Manager 然后重新登录。
