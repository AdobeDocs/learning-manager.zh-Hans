---
jcr-language: en_us
title: 用户在 Adobe Learning Manager 中被自动删除
description: 用户在 Adobe Learning Manager 中被删除，但管理员从未执行过任何此类操作。
contentowner: nluke
exl-id: 9e293da3-bcbf-4798-b391-aef53ef8d946
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 61%

---

# 用户在 Adobe Learning Manager 中被自动删除 {#user-gets-auto-deleted-in-learning-manager}

## 问题

用户在 Adobe Learning Manager 中被删除，但管理员从未执行过任何此类操作。

## 原因

Adobe Learning Manager 中，某个选项应用后，如果用户在一定时间内没有登录系统，便会自动从系统中删除。

## 如何更改/应用设置？

### 对于内部学习者

1. 以&#x200B;**管理员身份**&#x200B;登录。
1. 在“**配置**”下，单击“**设置**”>“**常规**”。
1. 在“常规”设置页面中，找到选项&#x200B;**“自动删除内部用户”**。
1. 单击&#x200B;**[!UICONTROL 编辑]**&#x200B;以在字段中输入天数，如果学习者未在输入的天数内访问系统，则将自动删除该学习者。

   ![](assets/cp-autodelete-internal.png)

   *编辑天数*

>[!NOTE]
>
>   如果您不想自动删除用户，请将该字段留空。


1. 单击“**[!UICONTROL 保存]**”保留所做的设置。

### 对于外部学习者：

1. 以&#x200B;**管理员**&#x200B;身份登录。
1. 在“**管理**”下，单击“**[!UICONTROL 用户]**”>“**[!UICONTROL 外部]**”。
1. 单击需要应用该设置的外部用户的名称。

   此时将打开&#x200B;**“编辑外部注册配置文件”**&#x200B;窗口。

1. 单击左下角的&#x200B;**[!UICONTROL 高级设置]**。

   ![](assets/cp-autodelete-external.png)

   *选择“高级设置”选项*

1. 在&#x200B;**登录要求**&#x200B;字段中输入天数，如果学习者未在输入的天数内访问系统，则将自动删除该学习者。
1. 单击“**[!UICONTROL 保存]**”保留所做的设置。
