---
jcr-language: en_us
title: Learning Manager中未显示选择按钮
description: 由于缺少单选按钮，管理员无法指定或删除角色、发送欢迎邮件或删除用户。
contentowner: nluke
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 0%

---



# Learning Manager中未显示选择按钮

## 问题

由于缺少单选按钮，管理员无法执行以下操作（不是详尽列表）：

* 分配或删除角色。
* 发送欢迎邮件。
* 删除用户。

## 原因

此问题是帐户的主题不正确所致。

![](assets/radio-buttons.png)

*单选按钮不可见*

## 分辨率

重新加载主题并修复单选按钮的外观。 请执行以下步骤：

1. 以管理员身份单击 **[!UICONTROL 品牌化]**.
1. 在 **主题** 部分，单击 **[!UICONTROL 编辑].**
1. 选取任意主题并保存更改。

   ![](assets/set-themes.png)

   *选择任何主题*

1. 恢复到上一个主题并保存更改。
1. 注销AdobeLearning Manager然后重新登录。
