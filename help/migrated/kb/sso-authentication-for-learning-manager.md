---
description: 本文档帮助您配置SSO身份验证以登录Learning Manager帐户。
jcr-language: en_us
title: 使用SSO身份验证登录Learning Manager
contentowner: dvenkate
source-git-commit: a186a600e632e9a564c4ff30d1897c2cdf0d5aac
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 0%

---



# 使用SSO身份验证登录Learning Manager

本文档帮助您配置SSO身份验证以登录Learning Manager帐户。

要配置SSO身份验证，请执行以下步骤：

1. 打开 **[!UICONTROL 设置]** > **[!UICONTROL 登录方法。]**

   ![](assets/login-methods.png)

1. 选择 **[!UICONTROL 内部用户]** 或 **[!UICONTROL 外部用户]** 那得视你的要求而定。
1. 单击旁边的下拉菜单  **[!UICONTROL 登录]** 选项并选择 **[!UICONTROL 单点登录]**.

   ![](assets/single-sign-on.png)

1. 要调整单点登录(SSO)设置，请单击  **[!UICONTROL 改变。]**

   ![](assets/change.png)

1. 输入  **[!UICONTROL IDP启动的身份验证URL]** ，并通过单击以下链接上传您的XML文件： **[!UICONTROL idp元数据XML文件。]**

   ![](assets/sso-configuration.png)

   您在Learning Manager中配置的SSO应支持SAML 2.0。

   您现在可以使用SSO身份验证登录Learning Manager。

