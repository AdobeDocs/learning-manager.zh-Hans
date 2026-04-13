---
description: 了解OIDC登录方法
jcr-language: en_us
title: 使用OpenID Connect登录Adobe Learning Manager
source-git-commit: 7c430e3fbb2716455310f2130d73af10ce2e56c7
workflow-type: tm+mt
source-wordcount: '1402'
ht-degree: 0%

---


# 使用OpenID Connect (OIDC)登录Adobe Learning Manager

了解OpenID Connect如何在Adobe Learning Manager中面向学习者、作者和管理员登录。 本文涵盖的是相关经验，而不是实施。

## 了解OpenID Connect登录

OpenID Connect (OIDC)是基于Web标准构建的通用登录方法。 许多组织为员工和合作伙伴使用身份提供者（例如，Okta、Google Workspace或Microsoft Entra ID）。

当您的组织为Adobe Learning Manager启用OIDC时：

* 您使用组织通常的登录页面登录，而不是仅适用于Adobe Learning Manager的密码，除非组织另有选择。
* 在您进行身份验证后，Adobe Learning Manager将收到您组织允许的信息（如电子邮件和配置文件属性），并为您打开合适的体验：学习者、作者、管理员或您的帐户支持的其他角色。

OIDC是您的帐户可能提供的其他登录选项的替代方法，如基于Adobe ID或SAML的单点登录(SSO)。 您的管理员决定可使用哪些方法。

## 组织选择OpenID Connect的原因

组织经常选择OIDC是因为：

* 用户看到的企业或云身份体验与其用于其他应用程序的体验相同。
* 密码策略、多重身份验证和帐户生命周期在身份提供者中进行管理，这与其他企业应用程序一致。
* 从用户和IT的角度来看，OIDC遵循的模式类似于其他新式的登录流程，没有与某些仅适用于SAML的设置相关的更繁重的文档交换。

您的体验仍然良好：转到Learning Manager，从公司告知您的位置登录，然后登录到应用程序。

## 登录时看到的内容

### 打开Adobe Learning Manager

您可以使用：

* 您的环境的主Adobe Learning Manager URL
* 您的组织配置的自定义域（如果适用）
* 电子邮件、邀请或自行注册页面中的链接
* 特定课程、目录页面或资源的书签或深层链接

如果您的帐户使用OIDC，则开始登录时通常会将您的浏览器重定向到您组织的身份提供方。

### 使用您的组织登录

在您的身份提供方的页面上，输入您的凭据并完成您的组织需要的任何额外步骤，例如多重身份验证。 当OIDC是正在使用的方法时，会在Adobe Learning Manager自己的登录表单之外执行此步骤。 从您的角度看，这就像登录到您的公司或学校帐户。 在此步骤中，您可能看不到&#x200B;*OIDC*&#x200B;或&#x200B;*OAuth*&#x200B;等技术术语。

### 返回Adobe Learning Manager

成功登录后，您的浏览器将返回Adobe Learning Manager。 然后，产品将：

* 根据您组织的设置，使用您的身份提供者共享的电子邮件和配置文件信息识别您
* 在Adobe Learning Manager中应用您的权限（学习者、作者、管理员、集成管理员等）
* 根据Adobe Learning Manager为您的帐户分配角色的方式，打开适当的应用程序或区域（例如，与管理员或作者体验相比的学习者体验）

如果出现问题（例如，未配置您的帐户或您的组织阻止访问），您可能会看到错误或无法继续。 请联系您的内部IT团队或Adobe Learning Manager管理员。

## 对OpenID Connect使用其他登录选项

Adobe Learning Manager可以支持一个帐户使用多种登录方法（多个SSO选项）。 例如：

* 某些用户使用Adobe ID登录
* 其他应用程序使用SAML SSO
* 其他人使用OIDC

您会看到哪些选项取决于帐户的配置方式。 为您的组织启用OIDC本身不会删除其他方法，除非您的管理员更改该配置。

## 支持的功能和场景

当您的组织将OIDC与Adobe Learning Manager一起使用时，支持以下行为，这符合预计其他企业登录方法的工作方式。

### 表1. 常见场景中的OIDC支持

| 面积 | 这对您意味着什么 |
| --- | --- |
| 内部和外部用户 | 员工和受邀的外部用户（例如，合作伙伴）可以在管理员启用的OIDC中使用，包括在设置您的帐户后从自助注册链接开始的工作流。 |
| 首次访问 | 如果策略允许，则您首次成功的OIDC登录可以根据您组织的规则在Adobe Learning Manager中创建或链接您的用户，类似于其他SSO选项。 |
| 配置文件和属性 | 电子邮件和其他属性等信息可通过身份提供者随时间进行更新，以使您的Adobe Learning Manager配置文件与您的组织的目录在管理员配置的范围内保持一致。 |
| 深层链接 | 支持指向Learning Manager中特定页面或资源（而非主页）的链接。 当您的组织设置允许时，您可以在登录后放置所需的内容。 |
| 返回路径 | 完成身份验证后，您可以返回您尝试访问的地方（例如，与您开始使用的课程或目录URL相同的位置），而不是始终登录在通用主页上。 |
| 自定义域 | 如果您的公司对Adobe Learning Manager使用自定义主机名，则在该上下文中也支持OIDC登录。 |
| 移动设备 | 支持通过受支持的浏览器或体验在手机和平板电脑上登录。 |
| 从Publish切换为Adobe Learning Manager (Prime) | 如果您的帐户使用OIDC且与您的集成设置一致，则涉及将内容从互联工具发布到Learning Manager的工作流程仍受支持。 |
| 基于标识符的登录 | 您的帐户依赖于稳定标识符（仅电子邮件除外）来匹配帐户，而您的管理员配置支持将这些流用于OIDC。 |

如果特定的工作流程无法正常工作，可能是身份提供者设置、帐户配置或Adobe Learning Manager角色分配造成的。 您的管理员可以验证。

## 角色在登录后如何工作

Adobe Learning Manager确定您可以从帐户的角色和权限执行哪些操作，而不是从OIDC协议本身执行哪些操作。 OIDC仅确定令您的身份提供者满意的您是谁，以及您的组织与Adobe Learning Manager共享哪些内容。

* 学习者通常可以查看培训、目录和学习方案。
* 作者可以创建或监管内容。
* 管理员管理用户、配置和报告。

如果您降落在了错误的区域或缺少预期的访问权限，请让您的Adobe Learning Manager管理员检查您的配置文件和组成员资格。

## 常见问题疑难解答

### 表2. OIDC登录疑难解答

| 问题 | 试用功能 |
| --- | --- |
| 重定向循环或空白页面 | 清除Learning Manager URL和身份提供者的Cookie、尝试使用其他浏览器或尝试使用专用窗口。 如果问题仍然存在，请联系IT。 公司代理或身份提供方会话策略有时会干扰。 |
| 身份提供者登录后“拒绝访问”或类似情况 | 您的身份提供者接受了您，但Adobe Learning Manager可能没有匹配的用户，或者您的帐户可能缺少许可证或角色。 请与Adobe Learning Manager管理员联系。 |
| 错误的语言或个人资料详细信息 | 属性映射由您的组织控制。 询问您的管理员目录属性是否应驱动区域设置或配置文件字段。 |
| 深层链接会打开主页，而不是资源 | 返回路径和深层链接的行为可能取决于链接和会话的共享方式。 在完全登录后重试该链接，或询问管理员外部用户是否支持该链接格式。 |

## 管理员应了解的事项

如果您为公司配置Adobe Learning Manager，则会用您身份提供方的应用程序注册设置OIDC：客户端标识符、授权端点、令牌、用户信息以及Adobe Learning Manager用于完成登录的重定向URL。 这些值来自身份提供方的文档。 您的身份提供者和Learning Manager之间的设置必须匹配，以便用户看到流畅的重定向和返回。

最终用户不需要管理这些值。 他们只需要正确的Learning Manager URL（或自定义域）以及团队提供的邀请或自行注册链接（如适用）。

## 摘要

* OIDC允许用户通过其组织的标准身份提供商登录Adobe Learning Manager，并具有熟悉的重定向和返回流程。
* 登录后，Adobe Learning Manager使用电子邮件和共享属性识别用户并应用角色（学习者、作者、管理员等）。
* 根据您的帐户配置，支持自助注册、多个SSO选项、属性更新、首次用户配置、深层链接、返回路径、自定义域、移动、Publish到Adobe Learning Manager和基于标识符的匹配。
* 在管理员将其保持启用状态后，其他登录方法（例如Adobe ID或SAML）仍可用。
