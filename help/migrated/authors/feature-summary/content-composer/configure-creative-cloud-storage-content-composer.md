---
jcr-language: en_us
title: 为Adobe Learning Manager Content Composer配置Creative Cloud存储空间
description: 了解如何为Adobe Learning Manager Content Composer配置Creative Cloud存储空间。 本指南介绍了为什么需要Creative Cloud存储空间、管理员如何分配Adobe Admin Console中的免费会员资格优惠，以及如何解决与存储相关的访问问题。
contentowner: saghosh
source-git-commit: 42512cc4cab0d0cdb1e9796610d6fc2f7b5c51d6
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 0%

---


>[!IMPORTANT]
>
>本文适用于哪些用户：需要为Adobe Learning Manager用户启用Creative Cloud存储空间以便他们可以访问和使用Content Composer的管理员。 对于解决与存储相关的登录或访问错误以及通过Adobe Admin Console分配免费会员资格产品的管理员，此功能特别有用。


Adobe Learning Manager (ALM) Content Composer要求用户具有与其AdobeCreative Cloud关联的帐户存储空间。 没有Creative Cloud存储空间的用户可能无法访问Content Composer，并且可能会遇到登录或与访问相关的错误。

为帮助组织为受影响的用户配置存储空间，Adobe提供了免费会员资格优惠，管理员可通过Adobe Admin Console分配此优惠。 此优惠包括Creative Cloud存储空间，可在用户尚无提供存储权利的计划时使用。

## 准备事项

确保：

* 您具有Adobe Admin Console管理员访问权限。
* 确定需要访问Content Composer的用户。
* 您已验证用户是否已有包含Creative Cloud存储空间的计划。

## 为什么用户需要Creative Cloud存储空间

Content Composer使用Creative Cloud存储来存储课程。 未将存储空间分配给其Adobe配置文件的用户在尝试使用Content Composer时可能会收到错误。

![内容书写器存储错误](../assets/coco-storage1.png)

许多Adobe客户已通过现有Creative Cloud产品拥有Adobe存储空间，不受影响。 但是，某些Adobe Learning Manager客户可能没有在默认情况下配置的存储空间，并且可能需要管理员来启用它。

## 为用户启用免费Creative Cloud存储空间

如果用户没有Creative Cloud存储空间，请从Adobe Admin Console分配免费会员资格优惠。

1. 使用具有管理员权限的帐户登录到[Adobe Admin Console](https://adminconsole.adobe.com/)。 只有管理员才能将产品和优惠分配给用户。
2. 从Admin Console中，选择“产品”>“试用和特别优惠”。

   ![Admin Console中的试用和特别优惠](../assets/coco-storage2.png)

3. 查找在试用和特别优惠下提供的免费会员资格优惠。 这是讨论的一项优惠，作为为尚未获得Creative Cloud权限的用户启用存储空间的推荐方法。

   ![免费会员资格优惠](../assets/coco-storage3.png)

4. 将免费会员资格优惠分配给所需用户。 只有具有适当Admin Console权限的管理员才能完成分配。
5. 分配后，确认用户有可用的Creative Cloud存储空间，然后要求用户再次登录Content Composer。

## 通过免费会员资格提供的存储空间

提供免费会员资格的用户大约可获得2 GB的Creative Cloud存储空间，在此空间中，他们可以使用Content Composer。

## 故障排除

**用户在访问内容书写器时收到错误**

验证用户的Adobe配置文件中是否有Creative Cloud存储空间可用。

**用户看不到免费会员资格优惠**

确认：

* 您是以管理员身份登录的。
* 您正在查看Adobe Admin Console的“产品”区域。
* 组织有资格访问该优惠。

## 常见问题解答

**每个Adobe Learning Manager用户是否自动接收Creative Cloud存储空间？**

数字 某些ALM用户可能没有默认配置的存储，并且可能需要通过免费会员资格优惠获得额外权利。

**用户能否自行启用存储空间？**

数字 Adobe管理员必须通过Admin Console分配存储权利。

**内容书写器是否需要Creative Cloud存储空间？**

是。 Content Composer依赖于其Creative Cloud与之关联的用户。

**如果用户遇到与存储相关的错误，管理员应该怎么做？**

验证用户是否具有Creative Cloud存储权利。 否则，请通过Adobe Admin Console分配免费会员资格优惠，然后让用户重试。

**如果管理员仍有访问或权限问题，应该怎么做？**

如果Adobe Admin Console管理员在分配Creative Cloud存储空间或调试与访问权限相关的问题时脸部问题，则该问题可能需要企业帐户级别支持。 在这种情况下，请通过Admin Console中的可用支持选项联系Adobe企业支持部门。

有关详细信息，请查看[Adobe企业支持选项](https://helpx.adobe.com/business/enterprise/get-help/support-options/support-for-enterprise.html)
