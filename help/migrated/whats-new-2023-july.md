---
title: 此版本（2023年7月）的新增功能
description: 了解AdobeLearning Manager中的新功能和增强功能
hidefromtoc: true
source-git-commit: c55f9448082c9971c065eec95b59992db95e53dc
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 0%

---

# 此版本（2023年7月）的新增功能

## 改进建议

AdobeLearning Manager推出了全新的课程推荐系统。 此推荐功能使用AI算法和用户的兴趣（如产品、角色和级别）来提供个性化的内容推荐。

有关详细信息，请参阅 [AdobeLearning Manager中的Recommendations](recommendations-adobe-learning-manager.md).

## 多注册

在此版本的AdobeLearning Manager中，我们为学习者引入了多注册功能，允许学习者在一个或多个时间段注册多个课程实例。

有关详细信息，请参阅 [多次注册](/help/migrated/authors/feature-summary/courses.md).

### 在移动应用程序或沉浸式环境中进行多注册

学习者无法通过移动应用程序/沉浸式注册多个实例。 移动应用程序和沉浸式移动Web不支持多注册。

>[!NOTE]
>
>启用多注册后，每个课程的“学习者成绩单”报告中都会添加多行（每个实例一行）。
>
>如果报告自动化设置预期每个课程仅有一行，则必须在启用多注册功能之前对报告自动化进行必要的调整。

### 多注册实例中的徽章格式

为了在多注册实例中支持徽章，徽章格式已更改为 `userId_badgeId_COURSE_courseId_courseInstanceId`.

### 使用无头模式以多注册方式启动播放器

在此版本中，我们更改了用于与无头播放器通信的库。

在多注册中，必须传递包装在对象内的参数。

```
{{startplayer(argument_object) ,
where
argument_object=
{ loId = <loId>, accountId = <accountId>, userId =<userId>, accessToken = <accessToken>, domId = <elementId>, onModuleLoaded = fn(), isMultiEnrolled=<boolean>, instanceId=<instanceId> }
}}
```

## Exavault连接器的弃用

此版本AdobeLearning Manager将包含一个新连接器，该连接器将使用AWS传输系列的SFTP协议。

此更改还将替换ExaVault连接器，该连接器将不再适用于新用户。 您可以使用任何开源FTP客户端来替代ExaVault。 有关详细信息，请参阅 [从AdobeFTP管理器过渡](transition-from-ftp-manager.md).

## Outlook中针对课堂和虚拟会话的提醒

通过AdobeLearning Manager创建、已添加到学习者Outlook日历中的教室和虚拟教室会话，现在支持来自Outlook的提醒（与Outlook中的会议提醒类似）。

## 为课程指定技能的增强功能

我们对作者的技能分配工作流程进行了增强。 课程“设置”页面上的“技能建议”列表现在包含预先搜索功能。 作者现在可以通过键入前几个字符来搜索技能，建议将基于输入显示在“技能”下拉列表中。 借助此增强功能，作者无需滚动浏览完整列表即可查找并向课程分配技能。

## 经经理批准的课程工作流程改进

经理批准的课程现在可为经理和学习者提供相应的错误信息。

![错误消息](assets/error-messages.png)

经理现在可以在无法批准课程注册请求时查看相关的错误消息，其中包含相关信息（例如，已超过注册截止日期）。 学习者会看到错误和补救操作。

## 新学习计划报告

管理员/自定义管理员现在可以导出帐户中所有学习计划的列表和元数据，例如状态、适用的用户组、触发信息、学习计划中包含的课程/学习路径以及提醒信息。

## 报告以跟踪即将弃用的实例

培训报告还包含一个附加列，用于显示课程或学习路径中实例的完成截止日期，以便管理员和作者了解哪些实例即将停用，从而采取必要操作。

## 用于捕获学习者课程分级的增强功能

用户完成课程的最后一个模块后，会显示一个用于获取课程星级评级的弹出窗口。

![评级](assets/ratings.png)

## 自定义电子邮件模板

Learning Manager的电子邮件模板现在包含完全可编辑的部分，可让您根据消息传递和品牌推广首选项更加灵活地自定义电子邮件通信。

有关详细信息，请参阅 [自定义电子邮件模板](/help/migrated/administrators/feature-summary/email-templates.md#flexibility-in-customizing-the-templates).

## 日程安排助理的增强功能

微调为教室或虚拟会话选择讲师的过程。 已将用户组过滤器添加到“计划助理”中的“讲师”字段。 作者现在可以根据“讲师技能”和任何其他参数（如位置、语言、职称等）筛选讲师。

有关详细信息，请参阅 [“计划助理”中的用户组过滤器](/help/migrated/authors/feature-summary/courses.md#user-group-filter).

## 学习对象弃用工作流程的增强功能

作者现在可以提供 **自动弃用** 课程日期。 这样有助于防止目录数量随时间增加，并且需要返回并手动弃用课程。

管理员还可以在帐户级别决定访问“弃用”学习对象的性质。

培训报告包含一个新的列， **自动报废日期**，以显示每个学习对象的停用日期（如果已设置）。

## 按作者划分的目录标签值

作者现在可以在创建或编辑课程时添加其目录标签值。 管理员可以在帐户级别启用此功能。 作者添加新目录标签值后，它将成为预先排版搜索的一部分。

![选择目录](assets/select-catalog.png)

## 针对管理员、作者和经理角色的课程搜索增强功能

对管理员、作者和经理角色进行了搜索增强。 现在，他们将能够使用标题的关键字进行搜索。 这适用于课程、学习路径和认证。

## 迁移失败通知

在迁移过程中或使用数据连接器（例如PowerBI、FTP、Box等）时，如果任何导入或导出操作失败，则集成管理员会通过电子邮件收到通知。

## 通过API进行多管理器配置

已将新API添加到托管办公室API集，以支持多管理器配置。

## 注册API的增强功能

对注册API进行了增强，以支持和优化大规模批量注册。

## 移动应用程序 — 离线内容查看

学习者可以在离线模式下下载和使用内容。 离线查看不支持嵌套且灵活的学习路径。

*在此版本中，仅支持英语内容查看脱机内容。*

## 辅助功能

已实施多项改进以增强辅助功能，包括增强屏幕阅读器优化可读性。

## 移动应用程序支持

在下一个主要版本中，AdobeLearning Manager移动应用程序将仅支持三个最新的移动操作系统版本。

## linkedIn上的内容

linkedIn内容无法在Safari浏览器上的沉浸式应用程序上按预期加载。 要解决此问题，请执行以下操作：

1. 在设备上，选择 **[!UICONTROL 设置]** > **[!UICONTROL Safari]**.
1. 禁用 **防止跨站点跟踪**.
1. 禁用 **阻止所有Cookie**.
1. 登录到沉浸式应用程序。
1. 播放内容。
1. 允许弹出窗口。

## 其他增强功能

### 切换MS Teams中的实例

学习者可以切换到其他课程实例，直到其完成并保留课程进度。

### MS Teams中的多注册支持

学习者可以注册其他课程实例，与之前任何实例的完成状态无关。 这样做将使学习者注册同一课程的多个实例。

### 课程备注支持MS Teams中的多注册

课程备注在课程实例级别提供，以支持多注册。

## API更改

有关API更改的详细信息，请参阅 [AdobeLearning Manager API参考](https://captivateprime.adobe.com/docs/primeapi/v2/).

### 对新建议的API支持

**GET/account**

如果启用prlRecommendation，则返回。

**请求**

`https://learningmanagerstage1.adobe.com/primeapi/v2/account`

**GET/data？filter.recommendationCriteria=product**

返回产品/主题的列表。 结果取决于帐户设置，此设置可确认学习者是否对所有产品可见，或产品/主题是否对目录可见。

**请求**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=product&filter.showAllRecommenda`

**`GET /data?filter.recommendationCriteria=role`**

返回建议的角色列表。

**请求**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=role&filter.showAllRecommendationCriteria=false`

**`GET /data?filter.recommendationCriteria=level`**

返回建议的角色列表。

**请求**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=level&filter.showAllRecommendationCriteria=false`

**POST/search/query**

搜索还包括查询中的产品和角色参数。 查询和正文没有更改。 我们将添加新的排序选项

**请求**

`https://learningmanagerstage1.adobe.com/primeapi/v2/search/query?...`

**GET/learningObjects**

如果PRL建议已生效，学习对象模型会返回作者标记的建议。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects?sort=recommendationScore&filter.recommendationProducts=...&filter.recommendationRoles=...&filter.excludeIgnoredRecommendations=true`

POST/learningObjects/query

查询调用正文中支持以下属性：

```javascript {line-numbers="true"}
{
  "filter.announcedGroups": [
    "string"
  ],
  "filter.bookmarks": true,
  "filter.catalogIds": [
    "string"
  ],
  "filter.cityName": [
    "string"
  ],
  "filter.duration.range": [
    "string"
  ],
  "filter.effectiveModifiedDate.fromDate": "string",
  "filter.effectiveModifiedDate.toDate": "string",
  "filter.excludeIgnoredRecommendations": true,
  "filter.ignoreEnhancedLP": true,
  "filter.ignoreHigherOrderLOEnrollment": true,
  "filter.lang.subLOs": true,
  "filter.lang.twoLetterCode": true,
  "filter.learnerState": [
    "string"
  ],
  "filter.loFormat": [
    "string"
  ],
  "filter.loTypes": [
    "string"
  ],
  "filter.price": "string",
  "filter.priceRange": [
    "string"
  ],
  "filter.recommendationLevels": [
    "string"
  ],
  "filter.skill.level": [
    "string"
  ],
  "filter.skillName": [
    "string"
  ],
  "filter.tagName": [
    "string"
  ],
  "language": [
    "string"
  ],
  "preferredSortPartitionOrder": [
    "string"
  ],
  "showLoContentSource": true,
  "useCache": true,
  "filter.recommendationProducts": [
    {
      "levels": [
        "string"
      ],
      "name": "string"
    }
  ],
  "filter.recommendationRoles": [
    {
      "levels": [
        "string"
      ],
      "name": "string"
    }
  ]
}
```

**GET/recommendationProducts**

按recommendationProduct Id检索PRL产品。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationProducts`

GET/recommendationRoles

按recommendationProduct Id检索PRL产品。 将只返回（学习对象）的可见角色。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/prlRecommendations/roles`

`POST /users/{id}/recommendationPreferences`

创建/重新创建（覆盖） PRL推荐首选项。 示例有效负载：

```javascript {line-numbers="true"}
{
    "data": {
        "id": "userRecommendationPreferences:14755328",
        "type": "userRecommendationPreferences",
        "attributes": {
            "products": [
                {
                    "id": "recommendationProduct:1",
                    "dateCreated": "2023-05-07T20:00:00.000Z"
                },
                {
                    "id": "recommendationProduct:37",
                    "dateCreated": "2023-05-07T21:00:00.000Z"
                }
            ],
            "roles": [
                {
                    "id": "recommendationRole:23",
                    "dateCreated": "2023-05-07'T'21:00:00.000'Z'"
                },
                {
                    "id": "recommendationRole:1",
                    "dateCreated": "2023-05-07'T'20:01:00.000'Z'"
                },
                {
                    "id": "recommendationRole:2",
                    "dateCreated": "2023-05-07'T'19:02:00.000'Z'"
                },
                 {
                    "id": "recommendationRole:3",
                    "dateCreated": "2023-05-07'T'18:02:00.000'Z'"
                },
                {
                    "id": "recommendationRole:20",
                    "dateCreated": "2023-05-07'T'17:02:00.000'Z'",
                    "levels": [
                        "INTERMEDIATE"
                    ]
                }
            ]
        }
    }
}
```

**`GET /users/{id}/recommendationPreferences`**

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2//users/123/recommendationPreferences`

**`DELETE /users/{id}/recommendationPreferences`**

删除产品或角色的PRL推荐用户首选项。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/users/123/recommendationPreferences?ids=recommendationRole:123,recommendationRole:234`

参数：

Ids =要删除的ID列表

**PATCH/users/{id}/recommendationPreferences**

部分添加/更新。 示例有效负载：

```javascript {line-numbers="true"}
{
  "data": {
    "id": "userRecommendationPreferences:<USER_ID>",
    "type": "userRecommendationPreferences",
    "attributes": {
      "roles": [
        {
          "id": "recommendationRole:123",
          "type": "recommendationRole",
          "attributes": {
            "levels": [
              "INTERMEDIATE"
            ]
          }
        },
        {
          "id": "recommendationRole:123",
          "type": "recommendationRole",
          "attributes": {
            "levels": [
              "ADVANCED"
            ]
          }
        }
      ]
    }
  }
}
```

**POST/recommendationPreferences/learningObjects/{id}/ignore**

将学习对象添加到阻止推荐。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`DELETE /recommendationPreferences/learningObjects/{id}/ignore`**

从已阻止的建议中删除学习对象。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`GET /users/{id}/recommendationStrips`**

检索要用于显示prl建议的所有条带

### 支持API多注册

**GET/primeapi/v2/account**

添加了两个新属性：

* instanceSwitchEnabled
* multiEnrollmentEnable

**GET/users/{userId}/userNotifications**

在通知中的新元数据属性中添加了课程实例ID。

**GET/learningObjects**

登记关系仅显示主要登记，即首次登记或首次完成。

**`GET /learningObjects/{id}`**

登记关系仅显示主要登记，即首次登记或首次完成。

**`GET /learningObjects/{loId}/instances/{loInstanceId}`**

学习对象实例模型中添加了新的关系。

**`GET /enrollments/{id}`**

检索多注册课程的注册信息。

**`DELETE /enrollments/{id}`**

取消注册特定学习对象实例。

**POST/注册**

支持在不同实例中注册。

**GET/注册**

仅针对学习对象的主要注册获取注册。

**`GET /learningObjects/{id}/note`**

检索课程的备注列表。

**`GET /learningObjects/{lo_id}/instances/{loi_id}/note`**

检索课程和实例的备注列表。

**`GET /learningObjects/{id}/resources/{loResourceId}/note`**

检索课程中资源的备注列表。

**`POST /learningObjects/{id}/resources/{loResourceId}/note`**

在模块中添加给定课程的说明。

**`DELETE /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

根据特定实例（loResource Id的一部分）从给定模块中删除特定注释。

**`GET /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

检索给定实例（loResourceId的一部分）的课程模块中的特定注释。

**`PATCH /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

根据特定实例（loResource Id的一部分）更新给定模块中的特定注释。

**管理员API更改**

* GET/users/{id}/enrollments
* POST/users/{id}/enrollments
* DELETE/users/{id}/enrollments/{enrollmentId}
* PATCH/users/{id}/enrollments/{enrollmentId}

### 端点的强制字段

仅在强制执行时加载产品和角色。

请求示例

* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects/course%3A7418798?enforcedFields[learningObject]=products`
* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/users/11255638/userBadges?include=model&page[offset]=0&page[limit]=10&sort=dateAchieved&enforcedFields[learningObject]=products,roles`

### 因实施而导致的搜索API更改（英语区域设置）

词干分析是将单词还原为词根形式的过程。 这确保在搜索过程中单词的变体匹配。 例如，walk和walk可以源自相同的根词：walk。 词干设定后，搜索中任一单词的出现次数将与另一个单词的出现次数匹配。

在此版本中，我们为英语区域设置添加了词干，其中包括以下变体 — en_US、en_AU、en_GB。

如果搜索结果中需要词干，则词干分析属性将提及。 默认情况下，该选项设置为False

### 删除V1端点

此版本中的V1 API将停止工作。 欲了解更多信息，请参见 [开发人员手册](/help/migrated/integration-admin/feature-summary/developer-manual.md).

### 课程注册或取消注册的通知

此版本在新的元数据属性中引入了对于课程实例ID的支持和通知。

### L1反馈支持

使学习者能够在多注册功能的每个实例级别提供反馈。

**API：** `POST /enrollments/{id}/l1Feedback`

### 学习对象强制字段列表

在此版本中，您必须将章节、prequisiteConstraints、prerequisiteLO、subLO、supplementaryResources、supplementaryLO、instances、catalogLabels明确发送到learningObject。

例如，

`enforcedFields[learningObject]=prerequisiteLOs,instances`

### 下一版本的弃用通知

* 学习者API的覆盖标志。
* 我们将更改highlightResults=false的默认值。 此外，我们还将更改snippetType=courseName的默认值。
* 我们将弃用搜索端点中的matchType=bool。
* autoCompleteMode具有 [已弃用] 标记并提供与autoCompleteMode =false相同的功能，我们添加了一个名为Match的matchType。

### 多注册徽章ID格式

为了支持多注册实例徽章，我们即将课程徽章的格式从 `userId_badgeId_COURSE_courseId to userId_badgeId_COURSE_courseId_courseInstanceId` 以唯一地识别徽章。

## 发行说明

如需了解Learning Manager网页版应用程序和设备应用程序的当前和往期版本，请参阅 [发行说明](/help/migrated/release-note/release-notes.md).

## 此版本中的已知问题或限制

此版本的限制如下：

### 在移动应用程序中查看脱机内容

在应用程序中查看脱机内容时，不支持以下内容：

* Flex课程、学习计划或认证。
* 增强课程、学习计划或认证。
* 支持多测验的课程、学习计划或认证。
* Harvard Manage Mentor、Content Marketplace、GetAbstract或LinkedIn课程、学习计划或认证。
* 已启用先决条件的学习计划和证书。
* 已弃用的课程、学习计划或认证。
* 截止日期已过时的课程、学习计划或认证。
* 外部证书。
* 支持电子商务的课程、学习计划或认证。

以下学习路径、课程或认证存在一些脱机同步问题：

* 所有学习路径。
* 所有内部证书。
* POST调用的内容。

### Recommendations

新推荐系统中的产品/角色/级别不支持以下内容：

* Adobe Experience Manager、Teams、SFDC和未登录。
* 移动应用程序不支持在“推荐”页面上编辑产品和角色。
* 在迁移期间无法进行映射。
* 自动标记LinkedIn、内容市场和其他外部课程、学习计划或认证。
* 正式启用后恢复为基于技能的订阅或经典订阅。
* 学习者应用程序上产品和角色的搜索菜单。
* 管理员应用程序上的课程、学习计划或认证以及用户的批量映射。

## 系统要求

[Learning Manager系统要求](/help/migrated/system-requirements.md)
