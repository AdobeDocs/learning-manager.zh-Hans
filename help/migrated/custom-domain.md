---
jcr-language: en_us
title: 自定义域支持
description: Adobe Learning Manager 的 Azure 实例不支持自定义域。
contentowner: saghosh
exl-id: 162ce268-48e3-4c7e-acb1-5181cebbb18d
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 67%

---

# 自定义域支持

Adobe Learning Manager 的 Azure 实例不支持自定义域。

## 概述 {#overview}

客户可通过自定义域支持获取对其域名的完全控制权，并在其 Adobe Learning Manager 帐户中使用该域名。客户需单独购买自定义域，然后可在 Adobe 团队的协助下，将其设置为学习平台的登录 URL。

如此一来，客户便可以定制登录与访问体验，不会留有 Adobe 或 Adobe Learning Manager 的任何痕迹。

例如，您希望自定义域，以便您的用户获得与在Adobe域中相同的体验。 如果ABC Inc要培训其客户，则希望他们登录到一个名为`abc.com/mylearning`的域，而不是`learningmanager.adobe.com/abc-inc/mylearning`。

>[!NOTE]
>
>您必须先注册域，然后Adobe将指导您完成自定义URL。


自定义域功能需要额外付费。 请联系您的客户成功经理以了解更多详细信息。

* 对于学习者角色，域将以`https://cdn.<customer_custom_domain>/`开头，例如`https://cdn.elearningstage1.cpdomaintest.in/`
* 对于所有其他角色，域将以`https://<customer_custom_domain>/`开头。 例如，`https://elearningstage1.cpdomaintest.in/`

`<customer_custom_domain>`是可自定义的部分。

## 如何在帐户中设置自定义域 {#howtosetupacustomdomainonanaccount}

客户必须拥有域名并从提供商处购买域，此为先决条件。

假设客户拥有一个虚构的域，名为 **acme.com**。 客户希望从 **learning.acme.com** 获取 Adobe Learning Manager 内容。

设置自定义域的步骤如下。

1. 客户须在域中&#x200B;**添加 3 条 CNAME** 记录：

   * **learning.acme.com：**&#x200B;由Adobe共享的Learning Manager的ALB公共终结点
   * **lrs.learning.acme.com：**&#x200B;由learning.acme.com指向的ALB公共终结点
   * **cdn.learning.acme.com：**&#x200B;由Adobe共享的CDN终结点

1. 客户须为以下网域提供 SSL 证书：

   * learning.acme.com
   * lrs.learning.acme.com
   * cdn.learning.acme.com

1. Adobe 会将这些 SSL 证书上传到 AWS ALB，为这些域处理请求。
1. Adobe 会在其 SAN 证书中加入 learning.acme.com。
1. Adobe 会为客户生成 SP 元数据，元数据中将包含自定义域的 URL。

   * 如果客户希望通过社交帐号登录，则 Adobe 必须在允许的 URL 列表中纳入社交网站的重定向 URL 模式。
   * 如果客户已启用 SSO，则客户必须与其 IDP 合作，以便将域纳入重定向 URL 中。 客户必须与 Adobe 共享 IDP 元数据 XML。 之后，Adobe 必须更新客户帐户的 SSO 设置。

1. Adobe 随后将修改 S3 CORS 规则，以纳入客户的域。
