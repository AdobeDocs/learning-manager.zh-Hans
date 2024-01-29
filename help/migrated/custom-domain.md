---
jcr-language: en_us
title: 自定义域支持
description: Learning Manager的Azure实例不支持自定义域。
contentowner: saghosh
source-git-commit: 8635072782253cbac3f913953797cae7c0bc5ef4
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---



# 自定义域支持

Learning Manager的Azure实例不支持自定义域。

## 概述 {#overview}

自定义域支持允许客户完全控制其可用于Learning Manager中帐户的域名。 客户需要单独购买自定义域，然后与Adobe团队合作，将其设置为其学习平台的登录URL。

如此一来，客户便可以定制登录和访问体验，不会看到任何Adobe或AdobeLearning Manager。

例如，您希望自定义域，以便您的用户获得与在Adobe域中相同的体验。 如果ABC公司想培训客户，则希望他们登录到一个名为 `abc.com/mylearning`，而不是 `learningmanager.adobe.com/abc-inc/mylearning`.

>[!NOTE]
>
>您必须先注册域，然后Adobe将指导您完成自定义URL。


自定义域功能需要额外付费。 请联系您的客户成功经理以了解更多详细信息。

* 对于学习者角色，域名将以 `https://cdn.<customer_custom_domain>/` 例如， `https://cdn.elearningstage1.cpdomaintest.in/`
* 对于所有其他角色，域将以 `https://<customer_custom_domain>/`. 例如， `https://elearningstage1.cpdomaintest.in/`

`<customer_custom_domain>` 是可自定义的部件。

## 如何在帐户上设置自定义域 {#howtosetupacustomdomainonanaccount}

客户必须拥有域名并从提供商处购买域，此为先决条件。

例如，假设客户拥有虚拟域， **acme.com**. 客户希望从以下渠道获得Learning Manager内容 **learning.acme.com**.

请按照以下步骤设置自定义域。

1. 客户必须 **添加三个CNAME** 域中的记录：

   * **learning.acme.com网站：** 由Adobe共享的Learning Manager的ALB公共终结点
   * **lrs.learning.acme.com网站：** learning.acme.com指向的ALB公共终结点
   * **cdn.learning.acme.com网站：** 由Adobe共享的CDN终结点

1. 客户必须提供以下域的SSL证书：

   * learning.acme.com
   * lrs.learning.acme.com
   * cdn.learning.acme.com

1. Adobe将这些SSL证书上传到AWS ALB，以便为域请求提供服务。
1. Adobe将在其SAN证书中添加learning.acme.com。
1. Adobe将为客户生成SP元数据，因为元数据将包含自定义域URL。

   * 如果客户希望通过社交帐号登录，则Adobe必须在允许的URL列表中包含社交网站的重定向URL模式。
   * 如果客户已启用SSO，则客户必须结合其IDP，才能在重定向URL中包含其域。 客户必须与Adobe共享IDP元数据XML。 然后，Adobe必须更新客户帐户的SSO设置。

1. 然后，Adobe将修改S3 CORS规则，以包括客户的域。
