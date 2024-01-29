---
jcr-language: en_us
title: 无法注册为外部用户
description: 外部学习者无法注册到AdobeLearning Manager中的配置文件。
contentowner: nluke
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---



# 无法注册为外部用户

## 问题

外部学习者无法注册到配置文件。

## 错误

电子邮件ID已注册。 请使用其他电子邮件。

![](assets/cp-register-profile.png)

*已注册电子邮件的错误消息*

## 描述

有时会出现用户无法注册到外部配置文件的情况。 用户在注册时收到上述错误。

## 原因

此问题会在以下任一情况下发生：

* 用户已注册到其他外部配置文件。
* 用户已是内部学习者。
* 用户处于已删除状态。

## 解决方案：

**场景1：** 用户已注册到其他外部配置文件。

1. 以管理员身份登录。
1. 下 **管理**，单击 **[!UICONTROL 用户]** > **[!UICONTROL 外部]**.
1. 通过单击“使用的坐席”，打开用户已注册的配置文件

   ![](assets/cp-seats-used.png)

   *打开用户的个人资料*

1. 选择用户，单击 **[!UICONTROL 动作]** > **[!UICONTROL 更改配置文件]**.

   ![](assets/cp-change-profile.png)

   *更改用户的个人资料*

   此时将打开窗口以选择新的配置文件，如下所示。

   ![](assets/cp-select-profiles.png)

   *选择用户配置文件*

1. 选中后，单击 **[!UICONTROL 更改]**.

**场景2：** 用户已是内部学习者。

1. 以管理员身份登录。
1. 下 **管理**，单击 **[!UICONTROL 用户]** > **[!UICONTROL 内部]**.
1. 单击打开学习者配置文件，然后单击“编辑”图标。

   ![](assets/cp-internal-learner.png)

   *打开内部学习者配置文件*

1. 更改或添加学习者的电子邮件地址 *_old* 到现有电子邮件地址。 此操作将释放该电子邮件地址。

   例如，如果学习者的电子邮件地址 *<abc@adobe.com>，* 将其更改为 *<abc_old@adobe.com>*

1. 点击 **保存** 以保留所做的更改。

**场景3**：用户为已删除状态。

1. 以管理员身份登录。
1. 下 **管理**，单击 **[!UICONTROL 用户]** > **[!UICONTROL 用户清理]**.
1. 选择“学习者”，然后单击“编辑”图标。

   ![](assets/cp-deleted-learner.png)

   *编辑用户电子邮件地址*

1. 更改或添加学习者的电子邮件地址 *_old* 到现有电子邮件地址。 此操作将释放该电子邮件地址。

   例如，如果学习者的电子邮件地址 **<abc@adobe.com>**，将其更改为 **<abc_old@adobe.com>**.
