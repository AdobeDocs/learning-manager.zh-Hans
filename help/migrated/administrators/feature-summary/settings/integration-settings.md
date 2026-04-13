---
description: 详细了解集成设置如何将Adobe Learning Manager与第三方解决方案相连接
jcr-language: en_us
title: Adobe Learning Manager中的集成设置
source-git-commit: 03123dcd8d9066cdfcb0fe97e61acb3df625a23e
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 3%

---


# Adobe Learning Manager中的集成设置

## 登录方法

Adobe Learning Manager提供了多种登录方法，以确保内部和外部用户能够安全而灵活地访问。 管理员可以根据公司要求配置这些登录方法。

可用的登录方法有：

* ADOBE LEARNING MANAGER ID
* Adobe ID
* 单点登录

### 内部用户

通过“内部用户”部分，您可以专门为内部用户配置登录选项。 内部用户可以使用Adobe ID或单点登录(SSO)访问帐户。

**Adobe ID：**

* 内部用户可使用其Adobe ID凭据登录。
* 适用于已在使用Adobe服务的组织。

**单点登录(SSO)：**

* 允许SSO内部用户使用组织的身份提供者(IdP)。
* 支持基于SAML 2.0的身份验证，以实现无缝登录体验。

要允许内部用户进行SSO登录，请选择“为登录启用多个单点登录(SSO)”并开始配置SSO。

Adobe Learning Manager中的&#x200B;**[!UICONTROL SSO活动字段]**&#x200B;用于将单点登录(SSO)配置映射到特定的用户属性或组。 您可以将此字段配置为根据内部用户的组织、位置或其他条件为其启用多个SSO设置。

### 外部用户

通过Adobe Learning Manager中的“外部用户”部分，可管理需要对Adobe Learning Manager帐户具有有限访问权限的外部学习者，例如合作伙伴或机构。 此部分提供了用于创建注册配置文件、管理外部用户组和配置特定于外部学习者的设置的工具。

外部用户可以使用以下方式进行登录：

* Adobe ID：外部用户可使用其Adobe ID凭据登录。
* 单点登录(SSO)：如果管理员配置了外部用户，则外部用户可以通过SSO登录。
* Adobe Learning Manager ID：外部用户可以创建Learning Manager用户名和密码以访问平台。

**关键点：**

* 您可以为外部用户启用一种或多种登录方法。
* 如果选择Adobe Learning Manager ID，则外部用户必须创建自己的凭据。
* 可根据组织需求为外部用户配置SSO。

### Adobe Learning Manager中的SSO配置

Adobe Learning Manager支持单点登录(SSO)，允许用户仅进行一次身份验证即可访问多个应用程序。 管理员可以使用基于SAML 2.0的提供商为内部和外部用户配置SSO。

有关详细信息，请参阅[Adobe Learning Manager中的SSO登录](/help/migrated/administrators/feature-summary/multiple-sso-logins.md)。

>[!NOTE]
>
>* 一个帐户最多可以添加 20 个 SSO 配置。
>* 请联系Adobe支持以获取有关基于SAML 2.0的SSO提供商的帮助。

## 数据源

数据源允许您或集成管理员集成外部系统，以便导入和同步用户和学习数据。 此功能可确保无缝数据管理和与HRMS、Salesforce、FTP等系统的同步。

**数据源类型示例**

* **FTP连接器**：基于FTP的数据源允许组织通过安全文件传输协议将用户数据文件直接上传到Adobe Learning Manager。 这些连接对于批量导入用户信息、课程注册和其他批量数据操作尤为有用。
* **第三方集成**：Adobe Learning Manager支持通过预构建的连接器与各种企业系统集成。 这些集成可以包括人力资源管理系统、客户关系管理平台和其他学习管理系统。
*** Salesforce集成**：Salesforce连接器支持在Salesforce和Adobe Learning Manager之间直接同步用户数据、课程信息和学习记录。

有关详细信息，请参阅[Adobe Learning Manager中的连接器](/help/migrated/integration-admin/feature-summary/connectors.md)。

## 配对帐户

Adobe Learning Manager中的配对帐户允许您跨关联帐户共享已购买的名额和查看报告。 对于需要在不同帐户之间协作或共享资源的组织，此功能非常有用。

有关详细信息，请参阅Adobe Learning Manager中的[配对帐户](/help/migrated/administrators/feature-summary/peer-account.md)。





