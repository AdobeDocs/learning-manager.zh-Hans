---
jcr-language: en_us
title: 无法以外部用户身份注册
description: 外部学习者无法在Adobe Learning Manager中注册到配置文件。
contentowner: nluke
exl-id: b1a9ecb6-75a8-44f7-b169-f77d7a4f6c2c
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 50%

---

# 无法以外部用户身份注册

## 问题

外部学习者无法注册到配置文件。

## 错误

电子邮件 ID 已注册。 请使用其他电子邮件。

![](assets/cp-register-profile.png)

*已注册电子邮件的错误消息*

## 描述

有时会出现用户无法注册到外部配置文件的情况。 用户在注册时收到上述错误信息。

## 原因

出现以下任一场景时会出现此问题：

* 用户已注册到其他外部配置文件。
* 用户已是内部学习者。
* 用户为已删除状态。

## 解决方案：

**场景1：**&#x200B;用户已注册到其他外部配置文件。

1. 以管理员身份登录。
1. 在“**管理**”下，单击“**[!UICONTROL 用户]**”>“**[!UICONTROL 外部]**”。
1. 通过单击“使用的坐席”，打开用户已注册的配置文件

   ![](assets/cp-seats-used.png)

   *打开用户的个人资料*

1. 选择用户，单击&#x200B;**[!UICONTROL 操作]** > **[!UICONTROL 更改配置文件]**。

   ![](assets/cp-change-profile.png)

   *更改用户的配置文件*

   此时将打开窗口以选择新的配置文件，如下所示。

   ![](assets/cp-select-profiles.png)

   *选择用户配置文件*

1. 选中后，单击&#x200B;**[!UICONTROL “更改”]**。

**场景2：**&#x200B;用户已是内部学习者。

1. 以管理员身份登录。
1. 在“**管理**”下，单击“**[!UICONTROL 用户]**”>“**[!UICONTROL 内部]**”。
1. 单击打开学习者配置文件，然后单击“编辑”图标。

   ![](assets/cp-internal-learner.png)

   *打开内部学习者配置文件*

1. 更改学习者的电子邮件地址或将&#x200B;*_old*&#x200B;添加到现有电子邮件地址。 此操作将释放该电子邮件地址。

   例如，如果学习者的电子邮件地址为&#x200B;*<abc@adobe.com>，*&#x200B;则将其更改为&#x200B;*<abc_old@adobe.com>*

1. 单击“**保存**”以保留所做的更改。

**场景 3：**&#x200B;用户为已删除状态。

1. 以管理员身份登录。
1. 在“**管理**”下，单击“**[!UICONTROL 用户]**”>“**[!UICONTROL 用户清理]**”。
1. 选择“学习者”，然后单击“编辑”图标。

   ![](assets/cp-deleted-learner.png)

   *编辑用户电子邮件地址*

1. 更改学习者的电子邮件地址或将&#x200B;*_old*&#x200B;添加到现有电子邮件地址。 此操作将释放该电子邮件地址。

   例如，如果学习者的电子邮件地址为&#x200B;**<abc@adobe.com>**，则将其更改为&#x200B;**<abc_old@adobe.com>**。
