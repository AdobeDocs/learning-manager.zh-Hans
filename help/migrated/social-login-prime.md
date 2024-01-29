---
jcr-language: en_us
title: Learning Manager中的社交登录
description: Learning Manager中的社交登录
contentowner: saghosh
preview: true
source-git-commit: ccdb222228f76fdae63ebb0a808824ad6ac1db7f
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 0%

---



# Learning Manager中的社交登录

您可以使用Facebook、LinkedIn或Twitter凭据登录Learning Manager。

## 设置社交登录 {#setupsociallogin}

1. 如果您希望客户成功经理设置帐户，请联系他/她。

   否则，请执行以下步骤。

1. 搜索要在其中设置社交登录的帐户。
1. 将登录名更改为SSO。
1. 单击“高级”。 指定以下JSON。

   ```
   \{"linkedIn":true,"microsoft":true,"twitter":true,"facebook":true,"editingAllowed":true
   ```

   如果是不正确的JSON，则会出现异常。

   此社交登录功能仅用于INTERNAL用户。

