---
description: ALM中的API更改
jcr-language: en_us
title: 2026年5月修补程序版本中的API更改
source-git-commit: 24f54599749bce60916a57634144b0ca7f6a6d10
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 0%

---


# 2026年5月修补程序版本中的API更改

## GET/learningObjects API增强

当包含GET关系时，/learningObjects API现在会在learningObjectInstance资源中包含新的startDate属性。

**终结点**
/learningObjects/{id}？include=instancesGET

**更改**
新字段startDate已添加在下方：
included[].attributes.startDate

**描述**
startDate表示学习对象实例的预定开始日期和时间。

**示例**
https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects/course:13209797？include=instances
示例响应（已截断）

```
{
  "id": "course:13209797_16226533",
  "type": "learningObjectInstance",
  "attributes": {
    "dateCreated": "2026-05-20T04:35:46.000Z",
    "isAET": false,
    "isDefault": true,
    "isFlexible": false,
    "startDate": "2026-10-06T18:29:59.000Z",
    "state": "Active",
    "timeZoneCode": "IST"
  }
}
```

**备注**

* 仅针对适用的学习对象实例返回该字段。
* 该值以ISO 8601 UTC日期时间格式返回。
* 现有集成仍可向后兼容。
