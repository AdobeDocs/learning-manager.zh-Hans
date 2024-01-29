---
jcr-language: en_us
title: Okta Active Directory与AdobeLearning Manager集成
description: Okta Active Directory与AdobeLearning Manager集成
contentowner: nluke
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 0%

---



# Okta Active Directory与AdobeLearning Manager集成 {#okta-active-directory-integration-with-adobe-learning-manager}

在本文档中，您将了解如何集成AdobeLearning Manager与Okta Active Directory (AD)。 集成AdobeLearning Manager与Okta AD后，您可以：

* 在Okta AD中检查和控制Learning Manager用户的访问权限。
* 支持用户使用其Okta AD帐户自动登录AdobeLearning Manager。
* 在Okta门户集中管理您的帐户。

AdobeLearning Manager支持由身份提供商(IdP)和服务提供商(SP)启用的SSO。

## 在OKTA中创建应用程序

1. 以管理员身份登录Okta AD。
1. 点击 **[!UICONTROL 应用程序]**. 此操作将在Okta中打开应用程序商店。

   ![](assets/cp-application-store.png)

   *在Okta中查看应用程序商店*

1. 点击 **[!UICONTROL 创建应用程序集成]**.

   ![](assets/cp-app-integrations.png)

   *选择创建应用程序集成*

1. 选择 **[!UICONTROL SAML 2.0]** 从新的应用程序集成窗口。

   ![](assets/cp-saml2.0.png)

   *选择“SAML2.0”选项*

1. 选择 **[!UICONTROL 创建SAML集成]** > **[!UICONTROL “常规设置”页面]**. 输入应用程序名称。

   请注意，该名称可以为任意名称，以唯一标识您的应用程序。 完成后，单击 **[!UICONTROL 下一个]**.

   ![](assets/cp-saml-integration.png)

   *输入应用程序的名称*

1. 在“配置SAML设置”页面上执行以下步骤：

   **对于IDP设置：**

   1. 在“单点登录URL”字段中，键入URL： [https://learningmanager.adobe.com/saml/SSO](https://learningmanager.adobe.com/saml/SSO)
   1. 在“受众URL”字段中，输入URL： [https://learningmanager.adobe.com](https://learningmanager.adobe.com/)
   1. 在 **名称ID格式** 下拉框，选择 **电子邮件地址**.
   1. 在 **应用程序用户名** 下拉列表中，选择Okta用户名。
   1. 如需传递任何附加属性，可在属性列表的 **属性语句** （可选）

   ![](assets/cp-saml-integration-step1.png)

   *添加SAML属性*

   **对于SP设置：**

   1. 在“单点登录URL”字段中，键入URL： [https://learningmanager.adobe.com/saml/SSO](https://learningmanager.adobe.com/saml/SSO)
   1. 在“受众URL”字段中，输入URL： [https://learningmanager.adobe.com](https://learningmanager.adobe.com/)
   1. 在名称ID格式下拉框中，选择 **电子邮件地址**.
   1. 在应用程序用户名下拉列表中，选择Okta用户名。
   1. 单击 **显示高级设置**.
   1. 下 **签名算法**，选择RSA-SHA256
   1. 在 **断言算法**，选择SHA256
   1. 在 **断言加密** dropbox，选择 **已加密**.

   1. 在 **加密证书** 选项，然后上传Adobe共享的证书文件。
   1. 如需传递任何附加属性，可在属性列表的 **属性语句** （可选）。

   ![](assets/cp-saml-integration-step2.png)

   *添加其他属性*

   完成后，单击 **[!UICONTROL 下一个]**.

1. 该 **反馈**  tab为可选。 选择选项并提供反馈后，单击 **[!UICONTROL 完成]**.

   ![](assets/cp-saml-integration-step3.png)

   *完成SAML设置*

## 提取由IDP启用的URL和元数据文件

要查看由IdP/SP启用的URL和元数据文件，请执行以下步骤：

1. 打开已创建的应用程序。
1. 在 **单点登录** 选项卡，单击 **[!UICONTROL 查看说明]**.

   ![](assets/cp-prime-sso.png)

   *选择“SSO”选项卡*

   **对于IDP：**

   1. 身份提供商单点登录URL是IdP启用的URL。
   1. 复制以下项下的所有文本 **可选** 字段。
   1. 打开新的记事本文档并粘贴复制的文本。
   1. 点击 **[!UICONTROL 文件]** > **[!UICONTROL 另存为]** > “filename.xml”。 此文件将是元数据文件。

   **对于SP：**

   1. 身份提供商单点登录URL是IdP启用的URL。
   1. 身份提供方颁发者为实体ID。
   1. 复制以下项下的所有文本 **可选** 字段。
   1. 打开新的记事本文档并粘贴复制的文本。
   1. 点击 **[!UICONTROL 文件]** > **[!UICONTROL 另存为]** > **[!UICONTROL filename.xml]**. 此文件将是元数据文件。

   ![](assets/cp-saml-integration-step4.png)

   *保存SP XML文件*

   您需要将此文件保存为XML格式。

## 配置AdobeLearning Manager SSO

要配置AdobeLearning Manager SSO，请执行下文中提到的步骤。

<!--

article not in TOC

[SSO Authentication](/help/migrated/kb/sso-authentication-for-learning-manager.md)
-->