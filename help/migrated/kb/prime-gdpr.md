---
jcr-language: en_us
title: Adobe Learning Manager 的 GDPR 合规性
description: AdobeLearning Manager的GDPR合规性
contentowner: dvenkate
source-git-commit: 864b1796f1ca99ae7b5643e8c58d1756ff2461a1
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 39%

---



# Adobe Learning Manager 的 GDPR 合规性

>[!IMPORTANT]
>
>本文档的内容不属于法律意见，也无意于替代法律意见。 要获取有关 GDPR 的法律意见与建议，请咨询贵公司的法务部门。

+++什么是GDPR？

GDPR是欧盟推出的一项新法规，于2018年5月25日生效。 该法规在数据隐私方面加强了管控，并允许最终用户对他们自己的个人数据进行掌控。

+++

+++您作为AdobeLearning Manager客户，如何或为什么需要使用此功能？

虽然GDPR是欧盟法规，但它适用于全球范围内需要收集个人信息的商业实体，因为这些实体收集的用户个人信息有可能来自欧盟居民。  作为Learning Manager客户，请评估GDPR是否适用于您的组织。

+++

+++作为Learning Manager的供应商，Adobe在这其中扮演了什么角色？

根据GDPR的规定，如果贵公司为欧盟居民提供产品或服务，且可以确定收集、跟踪和监控欧盟用户数据的方式和原因，则贵公司将被视为 [数据控制器](https://gdpr-info.eu/art-24-gdpr/). 作为 Adobe Learning Manager 客户，如果您执行上述任意一项活动，即被视为数据控制者。

代表控制器处理数据的企业将被考虑  [数据处理器](https://gdpr-info.eu/art-28-gdpr/). 作为云端托管LMSAdobeLearning Manager的供应商，Adobe扮演着数据处理者的角色。 下面是有关  [GDPR与您的业务](https://www.adobe.com/privacy/general-data-protection-regulation.html).

+++

+++Learning Manager如何让您实现GDPR合规？

Adobe Learning Manager 内置以下工具和流程，可帮助您满足 GDPR 合规性要求。为了使超出该产品范围的流程也能够完全合规，您可能仍需要咨询您的合规团队进行评估。

**“被遗忘权” — 适用于数据控制者：** GDPR要求数据控制器支持“忘记权”功能，以供其用户使用。 这意味着任何用户都有权请求数据控制者永久删除任何存储为该用户的个人数据。 现在，如果您收到了这样的请求，并进一步判断请求有效，则可以使用 Adobe Learning Manager 中提供的“被遗忘权”功能，即[清除用户](../administrators/feature-summary/purge-users.md)功能。此功能允许管理员永久删除与特定个人相关的所有数据。在收到个人用户提出的相应请求之后，Adobe Learning Manager 会立即从其数据库中永久删除相关数据，随后还会自动清除相关备份日志（备份日志用于系统恢复）。

**“被遗忘权”- 适用于数据处理者：**&#x200B;最终用户还可以自行联系 Adobe，以请求删除其个人身份信息 (PII)。在这种情况下，Adobe Learning Manager 将自动检测哪些帐户拥有该用户的个人身份信息；与此同时，Adobe 会立即通知管理员哪些帐户提出了这样的请求。然后，管理员可以评估请求的有效性，并通过“清除用户”功能对请求进行呼叫。

**访问权：** GDPR允许最终用户请求控制器可能已为该最终用户存储的数据的权利。 为支持此请求，Learning Manager允许管理员自行生成“学习者成绩单”，并与用户共享。

**通过设计、数据加密保护隐私：** 我们使用一流的加密标准来处理传输中数据和静止数据，以确保数据安全。 使用的加密算法是SHA-256。 这种加密算法可确保您存储的所有数据得到充分保护而不会被滥用。

+++

