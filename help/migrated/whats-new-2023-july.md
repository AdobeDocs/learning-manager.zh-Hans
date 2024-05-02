---
title: 此版本（2023年7月）的新增功能
description: 了解 Adobe Learning Manager 中的新功能和增强功能
hidefromtoc: true
exl-id: c6f192b6-f377-47b2-9151-516ac8179543
source-git-commit: ebf4ea065ba799b957b8ce275fd1690f18b26556
workflow-type: tm+mt
source-wordcount: '2059'
ht-degree: 67%

---

# 此版本（2023年7月）的新增功能

## 改进建议

Adobe Learning Manager 引入了一个经改良的全新课程推荐系统。 此推荐功能使用AI算法和用户的兴趣（如产品、角色和级别）来提供个性化的内容推荐。

有关更多信息，请参阅 [Adobe Learning Manager 中的推荐](recommendations-adobe-learning-manager.md)。

## 多注册

在此版本的 Adobe Learning Manager 中，我们引入了学习者多注册功能，允许学习者在一个或多个时间段注册多个课程实例。

有关更多信息，请参阅[多注册](/help/migrated/authors/feature-summary/courses.md)。

### 在移动应用程序或沉浸式体验中进行多注册

学习者无法从移动应用程序/沉浸式体验中注册多个实例。 移动应用程序和沉浸式移动Web不支持多注册。

>[!NOTE]
>
>启用多注册后，系统会将多行添加到每个课程的学习者成绩单报告中（每个实例占一行）。
>
>如果报告自动化设置预期每个课程仅有一行，则必须在启用多注册功能之前对报告自动化进行必要的调整。

### 多注册实例中的徽章格式

为了在多注册实例中支持徽章，徽章格式已更改为 `userId_badgeId_COURSE_courseId_courseInstanceId`.

### 使用无头模式以多注册方式启动播放器

在此版本中，我们变更了用于与无头播放器通信的库。

在多注册中，必须传递包装在对象内的参数。

```
{{startplayer(argument_object) ,
where
argument_object=
{ loId = <loId>, accountId = <accountId>, userId =<userId>, accessToken = <accessToken>, domId = <elementId>, onModuleLoaded = fn(), isMultiEnrolled=<boolean>, instanceId=<instanceId> }
}}
```

## Exavault连接器的弃用

此版本的 Adobe Learning Manager 将包括一个使用 AWS Transfer 系列 SFTP 协议的新连接器。

这项更改还将替换 ExaVault 连接器，这将导致新用户无法再使用该连接器。 您可以使用任何开源 FTP 客户端替换 ExaVault。 有关详细信息，请参阅 [从AdobeFTP管理器过渡](transition-from-ftp-manager.md).

## Outlook中针对课堂和虚拟会话的提醒

在Adobe Learning Manager中创建的已添加到学习者Outlook日历中的教室和虚拟教室会话，现在支持来自Outlook的提醒（与Outlook中的会议提醒类似）。

## 为课程指定技能的增强功能

我们对作者技能分配工作流程进行了增强。 课程“设置”页面上的“技能”建议列表现在包含预先输入搜索功能。 作者现在可以通过输入前几个字符来搜索技能，同时，系统将根据输入内容将建议显示在“技能”下拉列表中。 借助此增强功能，作者无需滚动浏览完整列表，即可找到技能并将其分配给课程。

## 经经理批准的课程工作流程改进

经理批准的课程现在可为经理和学习者提供相应的错误信息。

![错误消息](assets/error-messages.png)

经理现在可查看相关错误消息，其中包含无法批准课程注册请求的信息（例如，注册截止日期已过）。 向学习者显示错误和补救措施。

## 新学习计划报告

管理员/自定义管理员现在可以导出帐户中所有学习计划的列表以及元数据，如状态、相应的用户组、触发信息、学习计划中包含的课程/学习路径，以及提醒信息。

## 报告以跟踪即将弃用的实例

培训报告包含额外的列，以显示课程或学习路径中实例的完成截止日期，以便管理员和作者了解哪些实例将被弃用并采取必要措施。

## 用于捕获学习者课程分级的增强功能

当用户完成课程中的最后一个模块时，屏幕上会弹出一个收集课程星级评分的窗口。

![评级](assets/ratings.png)

## 自定义电子邮件模板

Adobe Learning Manager 中的电子邮件模板现在包括完全可编辑的部分，这为根据消息和品牌偏好自定义电子邮件通信提供了更大的灵活性。

有关更多信息，请参阅[自定义电子邮件模板](/help/migrated/administrators/feature-summary/email-templates.md#flexibility-in-customizing-the-templates)。

## 日程安排助理的增强功能

微调为教室或虚拟会话选择讲师的过程。 已将用户组过滤器添加到“计划助理”中的“讲师”字段。 作者现在可以根据“讲师技能”和任何其他参数（如位置、语言、职称等）筛选讲师。

有关更多信息，请参阅[“计划助手”中的用户组过滤器](/help/migrated/authors/feature-summary/courses.md#user-group-filter)。

## 学习对象弃用工作流程的增强功能

作者现在可以为课程提供&#x200B;**自动停用**&#x200B;日期。 这有助于防止目录随着时间的推移而增加，且无需返回并手动弃用课程。

管理员还可以在帐户级别决定访问“弃用”学习对象的性质。

培训报告包含一个新的列， **自动报废日期**，以显示每个学习对象的停用日期（如果已设置）。

## 按作者划分的目录标签值

作者现在可以在创建或编辑课程时为其添加目录标签值。 管理员可以在帐户级别启用此功能。 作者添加新的目录标签值后，它将在预先搜索时显示。

![选择目录](assets/select-catalog.png)

## 针对管理员、作者和经理角色的课程搜索增强功能

对管理员、作者和经理角色的搜索功能进行了增强。 他们现在可以使用关键字搜索标题。 搜索增强适用于课程、学习路径和认证。

## 迁移失败通知

如果在迁移期间或使用 PowerBI、FTP、Box 等数据连接器时导入或导出操作失败，系统会通过电子邮件向集成管理员发送通知。

## 通过API进行多管理器配置

新的 API 已添加到托管的 API Office 集，以支持多经理配置。

## 注册API的增强功能

对注册 API 进行了增强，以支持和优化大规模批量注册。

## 移动应用程序 — 离线内容查看

学习者可以在离线模式下下载和使用内容。 离线查看不支持灵活的嵌套式学习路径。

*在此版本中，仅支持英语内容查看脱机内容。*

## 辅助功能

为增强辅助功能，我们实施了多项改进，包括增强了屏幕阅读器的可读性。

## 移动应用程序支持

在下一个主要版本中，Adobe Learning Manager 移动应用程序将仅支持三个最新的移动操作系统版本。

## LinkedIn 上的内容

Safari 浏览器上的沉浸式应用程序无法如期加载 LinkedIn 内容。 要解决此问题，请执行以下操作：

1. 在设备上，选择 **[!UICONTROL 设置]** > **[!UICONTROL Safari]**.
1. 禁用&#x200B;**防止跨站点追踪**。
1. 禁用&#x200B;**阻止所有 Cookie**。
1. 登录沉浸式应用程序。
1. 播放内容。
1. 允许弹出窗口。

## 其他增强功能

### 在 MS Teams 中切换实例

在完成课程之前，学习者可以切换到不同的课程实例并保留课程进度。

### MS Teams中的多注册支持

无论先前的实例是否完成，学习者都可以注册其他课程实例。 这样学习者将可以注册同一课程的多个实例。

### 课程备注支持在 MS Teams 中完成多注册

课程实例级别提供课程备注以支持多注册。

## API 更改

有关 API 更改的详细信息，请参阅 [Adobe Learning Manager API 引用](https://captivateprime.adobe.com/docs/primeapi/v2/)。

### 对新建议的API支持

**GET/account**

如果启用了 prlRecommendation，则返回。

**请求**

`https://learningmanagerstage1.adobe.com/primeapi/v2/account`

**GET/data？filter.recommendationCriteria=product**

返回产品/主题列表。 结果取决于帐户设置，这些帐户设置将确认学习者是否能看到所有产品，或目录是否在产品/主题中可见。

**请求**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=product&filter.showAllRecommenda`

**`GET /data?filter.recommendationCriteria=role`**

返回推荐角色的列表。

**请求**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=role&filter.showAllRecommendationCriteria=false`

**`GET /data?filter.recommendationCriteria=level`**

返回推荐角色的列表。

**请求**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=level&filter.showAllRecommendationCriteria=false`

**POST/search/query**

搜索还包含查询中的产品和角色参数。 查询和正文没有变化。 我们将添加新的排序选项

**请求**

`https://learningmanagerstage1.adobe.com/primeapi/v2/search/query?...`

**GET/learningObjects**

如果 PRL 推荐处于活动状态，学习对象模型将返回带作者标记的推荐。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects?sort=recommendationScore&filter.recommendationProducts=...&filter.recommendationRoles=...&filter.excludeIgnoredRecommendations=true`

POST /learningObjects/query

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

按推荐产品 ID 检索 PRL 产品。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationProducts`

GET /recommendationRoles

按推荐产品 ID 检索 PRL 产品。 仅返回（学习对象）的可见角色。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/prlRecommendations/roles`

`POST /users/{id}/recommendationPreferences`

创建/重新创建（覆盖）PRL 推荐首选项。 有效负载示例：

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

删除产品或角色的 PRL 推荐用户首选项。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/users/123/recommendationPreferences?ids=recommendationRole:123,recommendationRole:234`

参数：

Ids = 要删除的 ID 列表

**PATCH/users/{id}/recommendationPreferences**

部分添加/更新。 有效负载示例：

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

将学习对象添加到被阻止的推荐中。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`DELETE /recommendationPreferences/learningObjects/{id}/ignore`**

从被阻止的推荐中删除学习对象。

**请求URL**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`GET /users/{id}/recommendationStrips`**

检索要用于显示 PRL 推荐的所有条带

### 支持API多注册

**GET/primeapi/v2/account**

新增了两个属性：

* instanceSwitchEnabled
* multiEnrollmentEnabled

**GET/users/{userId}/userNotifications**

已将课程实例 ID 添加到新元数据属性的通知中。

**GET/learningObjects**

注册关系仅显示主要注册，即首次注册或首次完成。

**`GET /learningObjects/{id}`**

注册关系仅显示主要注册，即首次注册或首次完成。

**`GET /learningObjects/{loId}/instances/{loInstanceId}`**

新的关系被添加到学习对象实例模型中。

**`GET /enrollments/{id}`**

检索多个已注册课程的注册。

**`DELETE /enrollments/{id}`**

取消注册特定的学习对象实例。

**POST/注册**

支持在不同实例中注册。

**GET/注册**

仅获取学习对象的主要注册。

**`GET /learningObjects/{id}/note`**

检索课程的备注列表。

**`GET /learningObjects/{lo_id}/instances/{loi_id}/note`**

检索课程和实例的备注列表。

**`GET /learningObjects/{id}/resources/{loResourceId}/note`**

检索课程中资源的备注列表。

**`POST /learningObjects/{id}/resources/{loResourceId}/note`**

在给定课程的模块中为课程添加备注。

**`DELETE /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

根据特定实例（loResource ID 的一部分）从给定模块中删除特定的备注。

**`GET /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

检索课程模块中给定实例（loResourceId 的一部分）的特定备注。

**`PATCH /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

根据特定实例（loResource ID 的一部分）更新给定模块中的特定备注。

**管理员API更改**

* GET /users/{id}/enrollments
* POST/users/{id}/enrollments
* DELETE/users/{id}/enrollments/{enrollmentId}
* PATCH /users/{id}/enrollments/{enrollmentId}

### 端点的强制字段

产品和角色仅在实施时加载。

示例请求

* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects/course%3A7418798?enforcedFields[learningObject]=products`
* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/users/11255638/userBadges?include=model&page[offset]=0&page[limit]=10&sort=dateAchieved&enforcedFields[learningObject]=products,roles`

### 因实施而导致的搜索API更改（英语区域设置）

词干分析是将单词还原为词根形式的过程。 这可确保在搜索期间与单词的各种变体匹配。 例如，walk和walk可以源自相同的根词：walk。 词干设定后，搜索中任一单词的出现次数将与另一个单词的出现次数匹配。

在此版本中，我们为英语区域设置添加了词干，其中包括以下变体 — en_US、en_AU、en_GB。

如果搜索结果中要求词干提取，则会提及词干属性。 默认情况下，该选项设置为False。

API查询参数：

* matchType=phrase_and_match
* 词干=true

### 删除 V1 端点

V1 API 将在此版本中停用。 有关更多信息，请参阅[开发人员手册](/help/migrated/integration-admin/feature-summary/developer-manual.md)。

### 有关课程注册或取消注册的通知

此版本在新的元数据属性中引入了对于课程实例ID的支持和通知。

### L1反馈支持

允许学习者在多注册功能的每个实例级别提供反馈。

**API：** `POST /enrollments/{id}/l1Feedback`

### 学习对象必填字段列表

在此版本中，您必须将章节、prequisiteConstraints、prerequisiteLO、subLO、supplementaryResources、supplementaryLO、instances、catalogLabels明确发送到learningObject。

例如，

`enforcedFields[learningObject]=prerequisiteLOs,instances`

### 下一版本的弃用通知

* 学习者 API 的覆盖标志。
* 我们将更改 highlightResults=false 的默认值。 此外，我们还将更改snippetType=courseName的默认值。
* 我们将弃用搜索端点中的matchType=bool。
* autoCompleteMode具有 [已弃用] 标记并提供与autoCompleteMode =false相同的功能，我们添加了一个名为Match的matchType。

### 多注册徽章ID格式

为了支持多注册实例徽章，我们即将课程徽章的格式从 `userId_badgeId_COURSE_courseId to userId_badgeId_COURSE_courseId_courseInstanceId` 以唯一地识别徽章。

## 发行说明

如需了解Learning Manager网页版应用程序和设备应用程序的当前和往期版本，请参阅 [发行说明](/help/migrated/release-note/release-notes.md).

## 此版本中的已知问题或限制

此版本的限制如下：

### 在移动应用程序中查看离线内容

在应用程序中查看离线内容时，不支持以下内容：

* Flex 课程、学习计划或认证。
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
* POST 调用的内容。

### 推荐

新推荐系统中的产品/角色/级别不支持以下内容：

* Adobe Experience Manager、Teams、SFDC 和未登录用户。
* 移动应用程序不支持在“推荐”页面上编辑产品和角色。
* 在迁移期间无法进行映射。
* 自动标记LinkedIn、内容市场和其他外部课程、学习计划或认证。
* 正式启用后恢复为基于技能的订阅或经典订阅。
* 学习者应用程序上产品和角色的搜索菜单。
* 管理员应用程序上的课程、学习计划或认证以及用户的批量映射。

## 系统要求

[Adobe Learning Manager 系统要求](/help/migrated/system-requirements.md)
