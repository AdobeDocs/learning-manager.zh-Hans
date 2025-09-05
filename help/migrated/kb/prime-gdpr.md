---
jcr-language: en_us
title: Adobe Learning Manager 的 GDPR 合规性
description: Adobe Learning Manager符合GDPR规范
contentowner: dvenkate
exl-id: 8ea31464-b4ce-49e8-b471-5630f0216aa4
source-git-commit: a01ec6117ad49a1f9af0b31d48ad19ddc8443dde
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 39%

---

# Adobe Learning Manager 的 GDPR 合规性

>[!IMPORTANT]
>
>本文档的内容不属于法律意见，也无意于替代法律意见。 要获取有关 GDPR 的法律意见与建议，请咨询贵公司的法务部门。

Adobe Learning Manager致力于遵守GDPR，确保以安全且透明的方式管理用户数据。 它提供了基本的GDPR功能，例如清除用户（永久删除所有个人数据）的能力，并允许管理员生成学习者成绩单，以便根据请求与用户共享信息。

在传输和存储期间，所有用户数据都使用如SHA-256这样的标准通过高度加密得到保护。 对于某些集成，学习者必须进行身份验证，确保在共享任何数据前获得其同意。 这些隐私和安全控制可帮助使用Adobe Learning Manager的组织始终遵守GDPR并保护学习者信息。

+++什么是 GDPR？

GDPR是欧盟推出的一项新法规，于2018年5月25日生效。 该法规在数据隐私方面加强了管控，并允许最终用户对他们自己的个人数据进行掌控。

+++

+++作为 Adobe Learning Manager 的客户，GDPR 如何或为何适用于您？

虽然GDPR是欧盟法规，但它适用于全球范围内需要收集个人信息的商业实体，因为这些实体收集的用户个人信息有可能来自欧盟居民。  作为Learning Manager客户，请评估GDPR是否适用于您的组织。

+++

+++作为 Adobe Learning Manager 的供应商，Adobe 在这其中扮演了怎样的角色？

根据GDPR的规定，如果贵公司为欧盟居民提供产品或服务，且可以确定收集、跟踪和监控欧盟用户数据的方式和原因，则贵公司即被视为[数据控制者](https://gdpr-info.eu/art-24-gdpr/)。 作为 Adobe Learning Manager 客户，如果您执行上述任意一项活动，即被视为数据控制者。

代表控制器处理数据的企业被视为[数据处理者](https://gdpr-info.eu/art-28-gdpr/)。 作为云端托管LMS Adobe Learning Manager的供应商，Adobe扮演着数据处理者的角色。 下面是有关[GDPR和您的业务](https://www.adobe.com/privacy/general-data-protection-regulation.html)的一些更多详细信息。

+++

+++Adobe Learning Manager 如何让您满足 GDPR 合规性要求？

Adobe Learning Manager 内置以下工具和流程，可帮助您满足 GDPR 合规性要求。为了使超出该产品范围的流程也能够完全合规，您可能仍需要咨询您的合规团队进行评估。

**被遗忘权 — 适用于数据控制者：** GDPR要求数据控制者支持“被遗忘权”功能，以供其用户使用。 这意味着任何用户都有权请求数据控制者永久删除任何存储为该用户的个人数据。 现在，如果您收到了这样的请求，并进一步判断请求有效，则可以使用 Adobe Learning Manager 中提供的“被遗忘权”功能，即[清除用户](../administrators/feature-summary/purge-users.md)功能。此功能允许管理员永久删除与特定个人相关的所有数据。在收到个人用户提出的相应请求之后，Adobe Learning Manager 会立即从其数据库中永久删除相关数据，随后还会自动清除相关备份日志（备份日志用于系统恢复）。

**“被遗忘权”- 适用于数据处理者：**&#x200B;最终用户还可以自行联系 Adobe，以请求删除其个人身份信息 (PII)。在这种情况下，Adobe Learning Manager 将自动检测哪些帐户拥有该用户的个人身份信息；与此同时，Adobe 会立即通知管理员哪些帐户提出了这样的请求。然后，管理员可以评估请求的有效性，并通过“清除用户”功能对请求进行呼叫。

**访问权：** GDPR允许最终用户有权请求控制器可能已为该最终用户存储的数据。 为支持此请求，Learning Manager允许管理员自行生成“学习者成绩单”，并与用户共享。

**从设计入手，通过数据加密保护隐私：**&#x200B;为了确保数据的安全性，我们使用了最高级的数据加密标准来处理传输过程中的数据以及处于静止状态的数据。 使用的加密算法是SHA-256。 这种加密算法可确保您存储的所有数据得到充分保护而不会被滥用。

+++
