---
jcr-language: en_us
title: Okta Active Directory 与 Adobe Learning Manager 集成
description: Okta Active Directory 与 Adobe Learning Manager 集成
contentowner: nluke
exl-id: 6d7711a9-7a7f-49b7-8948-9a42407463b3
source-git-commit: f964dd3f1adeadb76f4843c9af229ce5f09afde1
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 55%

---

# Okta Active Directory 与 Adobe Learning Manager 集成 {#okta-active-directory-integration-with-adobe-learning-manager}

在本文档中，您将了解如何集成Adobe Learning Manager与Okta Active Directory (AD)。 集成Adobe Learning Manager与Okta AD时，您可以：

* 在 Okta AD 中检查和控制 Adobe Learning Manager 用户的访问权限。
* 支持用户使用其 Okta AD 帐户自动登录 Adobe Learning Manager。
* 在 Okta 门户集中管理您的帐户。

Adobe Learning Manager 支持由身份提供商 (IdP) 和服务提供商 (SP) 发起的 SSO。

## 在 OKTA 中创建应用程序

1. 登录到Okta AD。

   >[!NOTE]
   >
   >您不需要ALM管理员访问权限即可创建应用程序和设置IDP。

1. 单击&#x200B;**[!UICONTROL 应用程序]**。 将打开 Okta 中的应用程序商店。

   ![](assets/cp-application-store.png)

   *在Okta中查看应用程序商店*

1. 单击&#x200B;**[!UICONTROL 创建应用程序集成]**。

   ![](assets/cp-app-integrations.png)

   *选择“创建应用程序集成”*

1. 从新的应用程序集成窗口中选择&#x200B;**[!UICONTROL SAML 2.0]**。

   ![](assets/cp-saml2.0.png)

   *选择SAML2.0选项*

1. 选择&#x200B;**[!UICONTROL 创建SAML集成]** > **[!UICONTROL 常规设置页面]**。 输入应用程序名称。

   请注意，该名称可以为任意名称，以唯一标识您的应用程序。 完成后，单击&#x200B;**[!UICONTROL “下一步”]**。

   ![](assets/cp-saml-integration.png)

   *输入应用程序的名称*

1. 在“配置 SAML”设置页面上执行以下步骤：

   **对于IDP设置：**

   1. 在“单点登录URL”字段中，键入URL： [https://learningmanager.adobe.com/saml/SSO](https://learningmanager.adobe.com/saml/SSO)
   1. 在“受众URL”字段中，键入URL： [https://learningmanager.adobe.com](https://learningmanager.adobe.com/)
   1. 在&#x200B;**名称ID格式**&#x200B;下拉框中，选择&#x200B;**电子邮件地址**。
   1. 在&#x200B;**应用程序用户名**&#x200B;下拉列表中，选择 Okta 用户名。
   1. 如需传递任意附加属性，可在&#x200B;**属性语句**（可选）中添加属性

   ![](assets/cp-saml-integration-step1.png)

   *添加SAML属性*

   **对于SP设置：**

   1. 在“单点登录URL”字段中，键入URL： [https://learningmanager.adobe.com/saml/SSO](https://learningmanager.adobe.com/saml/SSO)
   1. 在“受众URL”字段中，键入URL： [https://learningmanager.adobe.com](https://learningmanager.adobe.com/)
   1. 在名称 ID 格式下拉框中，选择&#x200B;**电子邮件地址**。
   1. 在应用程序用户名下拉列表中，选择 Okta 用户名。
   1. 单击&#x200B;**显示高级设置**。
   1. 在&#x200B;**签名算法**&#x200B;中，选择 RSA-SHA256
   1. 在&#x200B;**断言算法**&#x200B;中，选择 SHA256
   1. 在&#x200B;**断言加密** Dropbox 中，选择&#x200B;**加密**。

   1. 在&#x200B;**加密证书**&#x200B;选项中，上传由 Adobe 共享的证书文件。
   1. 如需传递任何附加属性，可在&#x200B;**属性语句**（可选）下添加属性。

   ![](assets/cp-saml-integration-step2.png)

   *添加其他属性*

   完成后，单击&#x200B;**[!UICONTROL “下一步”]**。

1. **反馈**&#x200B;选项卡是可选的。 选择选项并提供反馈后，单击&#x200B;**[!UICONTROL 完成]**。

   ![](assets/cp-saml-integration-step3.png)

   *完成SAML设置*

## 提取由 IDP 启用的 URL 和元数据文件

要查看由IdP/SP启用的URL和元数据文件，请执行以下步骤：

1. 打开已创建的应用程序。
1. 在&#x200B;**单点登录**&#x200B;选项卡下，单击&#x200B;**[!UICONTROL 查看说明]**。

   ![](assets/cp-prime-sso.png)

   *选择SSO选项卡*

   **对于IDP：**

   1. 身份提供商单点登录 URL 为 IdP 启用的 URL。
   1. 复制&#x200B;**可选**&#x200B;字段下存在的所有文本。
   1. 打开新的记事本文档并粘贴复制的文本。
   1. 单击&#x200B;**[!UICONTROL 文件]** > **[!UICONTROL 另存为]** >“filename.xml”。 此文件将为元数据文件。

   **对于SP：**

   1. 身份提供商单点登录 URL 为 IdP 启用的 URL。
   1. 身份提供者颁发者为实体 ID。
   1. 复制&#x200B;**可选**&#x200B;字段下存在的所有文本。
   1. 打开新的记事本文档并粘贴复制的文本。
   1. 单击“**[!UICONTROL 文件]**”>“**[!UICONTROL 另存为]**”>“**[!UICONTROL filename.xml]**”。 此文件将为元数据文件。

   ![](assets/cp-saml-integration-step4.png)

   *保存SP XML文件*

   您需要将此文件保存为 XML 格式。

## 配置 Adobe Learning Manager SSO

要配置 Adobe Learning Manager SSO，请执行下文中提到的步骤。

<!--

article not in TOC

[SSO Authentication](/help/migrated/kb/sso-authentication-for-learning-manager.md)
-->
