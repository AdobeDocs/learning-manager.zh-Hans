---
description: 了解Adobe Learning Manager 2024年11月版的新增功能和增强功能
jcr-language: en_us
title: 2024年11月新增功能摘要
exl-id: 4dfe0e31-d202-4a6e-8c4f-43851218699f
source-git-commit: 7b84a4565ccf109ed4789f4963d6e250f5d0a852
workflow-type: tm+mt
source-wordcount: '3264'
ht-degree: 1%

---

# 2024年11月新增功能摘要 {#new-features-summary}

了解Adobe Learning Manager 2024年11月版的新增功能和增强功能。

* **AI支持的搜索：**&#x200B;将词汇搜索和语义搜索相结合，以获得更智能、可感知上下文的结果。
* **Webhook**：与Webhook集成以将实时信息发送到特定URL。
* **学习工具互操作性(LTI)**：支持LTI以实现与其他LMS平台的互操作性。
* **可信集成**：通过“可信”管理和共享外部徽章。
* **合规性信息板增强功能**：与其他管理员共享信息板，并在学习者主页上设置默认合规性小组件。
* **多语言支持**：为教室和虚拟教室模块创建特定于语言的实例。
* **自定义角色**：增强了对用户角色和权限的控制。
* **完成评论**：将学习者标记为完成时添加评论。
* **用户组报告**：使用详细报告管理用户组。
* **轮候表报告**：下载课程实例的轮候表学习者列表。
* **辅助功能增强**：支持刊头和公司徽标上的替代文本。
* **支持印地语**：支持印地语的界面语言。
* **亵渎检查**：阻止包含禁止单词的社交帖子。
* **电子邮件模板优化**：针对讲师分配和会话取消的合并优化电子邮件模板。
* **MS团队完成标准**：设置VILT会话的最低出席时间。
* **新迁移工作流程**：迁移更改包括课程和模块的完成条件以及将模块迁移到文件夹中。

>[!NOTE]
>
>观看此[网络研讨会](https://cdn.content.adobelearningmanageracademy.com/public/newlearner/newlearner_0dc0f1e8.html#/overviewPage?instanceId=11932477&loId=11231360&loType=course)，了解有关此版本中新增功能的更多信息。

## Adobe Learning Manager中的AI支持搜索

Adobe Learning Manager正在改进学习者搜索课程或培训的方式。 它引入了人工智能驱动的搜索功能，将词汇搜索和语义搜索相结合。 搜索现在更加智能，因为它会查找特定词语，并理解这些词语背后的背景和意图。 高级搜索能够理解查询的含义并提供相关结果。 它标识了搜索的主要重点，为您提供最完整的结果集。

>[!NOTE]
>
>AI支持的搜索仅适用于学习者。

有关详细信息，请参阅此文章[高级搜索](/help/migrated/learners/feature-summary/advanced-search.md)。

## Webhook

Adobe Learning Manager允许与Webhook集成以将实时信息（如课程注册、课程创建和其他信息）发送到特定URL。

ALM中的Webhook允许一个实体通过HTTP自动将数据发送到另一个应用程序。 这样，应用程序就可以向其他应用程序提供信息，而无需经常请求这些信息。 例如，如果用户完成学习管理系统(LMS)课程，Webhook会自动将该信息发送到其他平台，如CRM或报告工具。 Webhook通常用于集成中，以自动化流程并减少系统之间手动更新的需求。 通过提供要向其发送数据的回调URL来设置Webhook。

有关更多信息，请参阅这篇文章[Webhook](/help/migrated/integration-admin/feature-summary/webhooks.md)。

## 学习工具互操作性

Adobe Learning Manager现在支持LTI，以增强Adobe Learning Manager和其他学习管理系统(LMS)之间的互操作性。

### 什么是LTI？

LTI（学习工具互操作性）是一项标准，允许第三方工具和内容提供商连接学习管理系统(LMS)。 用户可直接在其LMS中访问外部内容提供商提供的外部学习内容，而无需登录或导航到其他LMS。

**LTI作为工具提供程序**：LTI作为工具提供程序允许外部系统与LMS集成。 Adobe Learning Manager充当LTI工具提供商，允许其他LMS平台直接在其LMS中从Adobe Learning Manager访问课程、证书或学习路径。

**LTI作为工具使用者**：LTI作为工具使用者允许LMS通过学习工具互操作性(LTI)集成外部工具。 在这种情况下，LMS是使用外部工具提供的服务。 Adobe Learning Manager充当LTI工具消费者，可集成第三方学习工具。 这允许Adobe Learning Manager学习者使用Adobe Learning Manager内的第三方工具中的课程、证书或学习路径。

有关更多信息，请参阅此文章[学习工具互操作性](/help/migrated/integration-admin/feature-summary/learning-tools-interoperability.md)。

## 有信心

借助Credly功能，ALM中的管理员可让学习者通过平台在各个社交媒体渠道管理和共享外部徽章。

### 什么是Credly？

Credly是一个数字凭据平台，允许学习者和组织获取、分享和验证专业成就，例如徽章或认证。 学习者可以通过其Credly个人资料在社交媒体和其他位置管理和共享徽章。

### 与Adobe Learning Manager可靠集成

首先，在Adobe Learning Manager (ALM)中添加Credly连接器。 接下来，从Crely迁移现有徽章，以确保学习者成就的连续性。 最后，在Adobe Learning Manager中创建适合学习路径的技能，以提高学习者的发展和认可度。

有关详细信息，请参阅此文章[相信](/help/migrated/integration-admin/feature-summary/credly-integration.md)

## 合规性信息板

在此版本中，管理员现在可以与其他管理员、自定义管理员和商店经理共享信息板，使其可即时访问合规性信息板。 他们现在可以在学习者主页上设置默认合规性构件，允许学习者跟踪其合规性要求。 有关详细信息，请参阅这篇文章[合规性信息板](/help/migrated/administrators/feature-summary/reports.md#share-compliance-dashboard-with-admins-and-custom-admins)。

## 多语言支持

Adobe Learning Manager (ALM)现在允许作者使用教室和虚拟教室模块的语言标记创建语言特定的实例。 学习者可以使用自己的首选语言访问CR/VC模块。 例如，作者可以创建包含两个实例的CR/VC模块：一个使用英语，另一个使用法语。 学习者可以使用自己的首选语言选择实例。

有关更多信息，请参阅这篇文章[添加不同区域设置的学习对象](/help/migrated/authors/feature-summary/add-new-language-learning-objects.md#multi-language-support-for-crvc-instances-with-language-tagging)。

## 自定义角色

通过自定义角色，管理员可以为不同的用户组定义特定的角色和责任，从而确保更好地进行管理和控制。 在此版本中，ALM通过提供对以下部分的更详细控制来增强自定义角色。

* 用户
* 课程
* 学习路径
* 认证
* 工作辅助
* 目录

管理员可以根据用户责任分配精确的权限，确保每个组仅有权访问相关功能和内容。 这些增强的控制功能允许对关键部分进行更精细的管理。

以管理员身份登录并导航到&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 自定义角色]**&#x200B;以创建和管理自定义角色。

有关详细信息，请参阅此文章[自定义角色](/help/migrated/administrators/feature-summary/custom-role.md)。

## 完成注释

管理员现在可以在将课程、学习路径或认证中的学习者标记为完成时添加评论。 管理员可以同时为一个或多个学习者添加注释，注释显示在[学习者成绩单](/help/migrated/administrators/feature-summary/reports.md#learner-transcripts)报告中。

有关详细信息，请参阅此文章[完成注释](/help/migrated/administrators/feature-summary/courses.md#completion-comments)。

## 用户组报告

Adobe Learning Manager的新&#x200B;**[!UICONTROL 用户组报告]**&#x200B;通过提供在管理员离开时不受管理的组的可见性，来帮助管理用户组。 管理员可以访问&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 用户组]**&#x200B;部分下的报告。 它提供有关每个组的详细信息，包括：

* 用户组类型
* 组名称
* 描述
* 创建者（名称）
* 创建者（电子邮件）
* 创建时间： （UTC时区）
* 用户数

有关详细信息，请参阅此文章[用户组报告](/help/migrated/administrators/feature-summary/add-users-user-groups.md#user-group-report)。

## 轮候表报告

Adobe Learning Manager的新&#x200B;**[!UICONTROL 轮候表报告]**&#x200B;允许管理员下载课程所有实例的轮候学习者列表。 管理员和讲师可以从&#x200B;**[!UICONTROL 课程]**&#x200B;或&#x200B;**[!UICONTROL 会话概述]**&#x200B;页面上的&#x200B;**[!UICONTROL 轮候表]**&#x200B;部分访问此报告。 轮候表报告可从“管理员”和“讲师”部分下载。

下面是“轮候表”报告中可用的列：

* 课程名称
* 实例名称
* 实例 ID
* 实例状态
* 用户名
* 电子邮件
* 用户唯一 ID
* 注册日期 (UTC 时区)
* 状态
* 轮候编号
* 轮候表限制
* 名额限制

请参阅此文章[轮候表报告（管理员）](/help/migrated/administrators/feature-summary/courses.md#waitlist-report)和[轮候表报告（讲师）](/help/migrated/instructors/feature-summary/learners.md#waitlist-report)，从管理员和讲师部分下载报告。

## 学习者主页中的辅助功能

Adobe Learning Manager现在支持为所有刊头使用替换文本，以提高学习者的辅助功能。 这让有特殊需求的学习者可以使用屏幕阅读器阅读替代文本并了解图像。 您可以选择多种语言并为每种语言提供替代文本。 确保添加相应语言的替代文本。 确保您的帐户中的公司徽标还包括带有公司名称的替代文本。
有关详细信息，请参阅这篇文章[公告](/help/migrated/administrators/feature-summary/announcements.md#masthead)。

## 支持印地语

Adobe Learning Manager现在引入了印地语作为平台的界面语言之一，并支持该平台在印度发展。 支持以印地语为母语的使用者可确保用户能够完全访问所有功能、报告和整体用户体验。

>[!NOTE]
>
>系统以PDF格式生成的徽章证书不支持印地语。

要更改界面语言，请执行以下步骤：

1. 以&#x200B;**[!UICONTROL 管理员]**&#x200B;身份登录。
2. 转到&#x200B;**[!UICONTROL 配置文件设置]** > **[!UICONTROL 界面语言]**。
3. 选择&#x200B;**[!UICONTROL 印地语]**&#x200B;作为界面语言。


## 社交帖子的亵渎检查

Adobe Learning Manager现已在学习者应用程序中阻止包含禁止单词的社交帖子。 这有助于保持业务的专业性和合规性，尤其是在医疗保健等敏感领域。

## 电子邮件模板优化

### 为学习者分配讲师时向其发送电子邮件

现有电子邮件&#x200B;**[!UICONTROL 您已被添加为讲师]**，并且&#x200B;**[!UICONTROL VCProvider会话详细信息]**&#x200B;已合并到一封电子邮件中&#x200B;**[!UICONTROL 您已被添加为UserType]**。 根据用户的角色，**[!UICONTROL UserType]**&#x200B;将为&#x200B;**[!UICONTROL 讲师]**&#x200B;或&#x200B;**[!UICONTROL 组织者]**。 之前，这些电子邮件在UI中不可用。 这些模板现已合并到一封电子邮件中，并添加到UI中。 管理员可以在&#x200B;**[!UICONTROL 电子邮件模板]**&#x200B;部分中访问此模板。 默认情况下，所有新帐户和现有帐户都将启用此设置，但管理员可以在同一部分中禁用或启用此设置。 每当创建会话并分配讲师时，都将发送此电子邮件，无论是用于Zoom、Teams、Connect还是其他服务。

### 取消会话时向学习者发送电子邮件

从会话中删除的讲师现在将仅收到一封会话取消电子邮件。 之前，他们会收到取消订阅和更新电子邮件。 留在会话中的讲师将收到会话更新电子邮件以及新的会话邀请。

## MS团队完成标准

目前，即使学习者加入虚拟讲师指导培训(VILT)课程仅有几秒钟，也将其标记为已参加。 在此版本中，我们引入了团队模块的完成标准，以确保更准确的出勤率。 作者现在可以设置学习者必须在VILT会话中花费的最少时间以计算其出勤情况。

这是默认禁用的后端功能。 请联系您的CSM以启用它。

## 更新电子邮件发送的新IP地址

为了增强电子邮件传送的可靠性，我们正在向现有池中添加新的IP地址。 为确保电子邮件通信不间断，请根据需要更新组织的电子邮件设置。

目前，我们使用以下IP地址进行电子邮件发送：

* 149.72.162.66
* 167.89.5.155

以下IP地址将添加到我们的电子邮件传递池：

* 159.183.228.93
* 159.183.225.26
* 159.183.218.22
* 168.245.57.144

>[!NOTE]
>
>如果需要，我们建议与您的IT团队协作，将IP地址添加到允许的URL列表中。

## 迁移更改

迁移工作流程中进行了以下更改：

* 将模块迁移到特定的文件夹中。
* 添加了模块的完成标准。
* 添加了课程的完成标准

### 模块迁移中的更改

将模块迁移到ALM时，默认情况下，这些模块将保存在公共文件夹中。 在此版本中，我们在[module_version.csv](assets/module_version.csv)文件中添加了一个名为`folder`的新列。 管理员可以使用此列指定模块迁移后应存放的文件夹名称。 管理员还可以通过列出以逗号分隔的文件夹名称，将单个模块放入多个文件夹中。

文件夹列使用字符串数据类型，它是一个可选列。 以下是文件夹列的条件：

* 添加的文件夹名称应为ALM帐户中现有的内容文件夹。
* 这些值应为逗号分隔的字符串。
* 如果为已存在于其他文件夹中的模块添加新文件夹名称，新值将不会覆盖或替换分配的文件夹。 模块将添加到新文件夹中，并且可以在现有文件夹中找到。
* 如果值为空，则该文件夹将默认为&#x200B;**[!UICONTROL Public]**。

有关详细信息，请参阅[module_version csv spec](assets/4-module_version.xlsx)文件。

### 模块迁移中的更改 — 完成标准

管理员可以在模块迁移期间指定模块的完成标准。 在此版本中，我们在[module_version.csv](assets/module_version.csv)中添加了新列`completionCriteria`、`viewPercent`和`quizData`。

以下是新列的条件：

1. `completionCriteria`：

   * 数据类型应为字符串值，支持的值为：
      * `LAUNCH_CONTENT`
      * `VIEW_PERCENT`
      * `QUIZ`
      * `MARK_COMPLETE`
   * 仅在模块级别为自学模块类型添加完成标准。
   * 静态内容支持的值为`LAUNCH_CONTENT`和`VIEW_PERCENT`。
   * 交互式内容支持的值为`LAUNCH_CONTENT`、`VIEW_PERCENT`和`QUIZ`。
   * 支持HTML5内容的值为`LAUNCH_CONTENT`和`MARK_COMPLETE`。

2. `viewPercent`：

   * 此列的数据类型应为整数，并且值必须介于0和100之间。
   * 当completionCriteria设置为`VIEW_PERCENT`时，请在此列中输入所需的视图百分比或将其留空。

3. `quizData`：

   * 数据类型应为字符串值，支持的值为`QUIZ_ATTEMPTED`、`QUIZ_PASSED`和`QUIZPASSED_OR_LIMITREACHED`。
   * 在`completionCriteria`设置为`QUIZ`时，请在`quizData`列中输入相应的测验值。

有关详细信息，请参阅[module_version csv spec](assets/4-module_version.xlsx)文件。

### 课程迁移中的更改 — 完成标准

管理员可以在课程迁移期间指定课程的完成标准。 在此版本中，我们在[course.csv](assets/course.csv)中添加了一个名为`completionCriteria`的新列。

以下是`completionCriteria`列的条件：

* 数据类型应为字符串或数字，并且是可选字段。
* 值应为`ALL`、`X`和`SELECTEDMODULES`。
* X是一个整数值，它应大于0且小于模块的总数。
* 如果将`completionCriteria`设置为`SELECTEDMODULES`，则需要在[course_module.csv](assets/course_module.csv)文件中标记必修模块。
* 在`optionalCriteria`列中输入`TRUE`或`FALSE`。 如果将值设置为`TRUE`，则会将模块设置为必填。

有关更多信息，请参阅[课程csv规范](assets/3-course.xlsx)和[course_module csv规范](assets/6-course_module.xlsx)文件。

## API 更改

下面是API更改：

* **搜索API**：
   * 新增带选项的模式过滤器： classicSearch和advanceSearch。
   * snippetTypes的新loMetadata选项。
* **公告API**：
   * 包含刊头说明的altText属性。
* **实例API**：
   * 用于检索区域设置详细信息的新的区域设置属性。
* **亵渎检查**：
   * 更新了API，以检查社交帖子上的评论和回复中是否有禁止的字词：
* **RPM和突发限制**：
   * 为所有API添加了RPM（每分钟请求数）和突发限制。
* **徽章API**：
   * 用于检索有关外部徽章信息的新属性externalProvider。
* **作业API**：
   * 使用作业API下载用户组报告和自定义角色审核报告。

### 搜索API中的更改

搜索API现在有一个包含两个选项的新模式筛选器： `classicSearch`和`advanceSearch`。 `snippetTypes`还有一个新的`loMetadata`选项。 若要获得最佳结果，请在使用`advanceSearch`模式时在`snippetTypes`中包含`loMetadata`。

### 公告API变更

`GET /announcements API`现在包含用于提供刊头说明的`altText`属性。

#### 使用cURL的请求示例：

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 12345678' 'https://abcd.adobe.com/primeapi/v2/announcements/123456'
```

#### 示例响应：

```
{
  "links": {
    "self": "https://abcd.adobe.com/primeapi/v2/announcements/123456"
  },
  "data": {
    "id": "12345",
    "type": "adminAnnouncement",
    "attributes": {
      "actionUrl": "google.com",
      "announcementType": "MASTHEAD",
      "expiryDate": "2038-01-19T03:14:07.000Z",
      "liveDate": "2024-07-31T11:11:30.000Z",
      "contentMetaData": [
        {
          "contentType": "IMAGE",
          "contentUrl": "https://abcd.adobe.com",
          "locale": "en-US",
          "altText": "Moonlight - english changed new",
          "thumbnailUrl": "https://abcd.adobe.com/"
        },      ]
    }
  }
}
```

### 实例API中的更改

新`locale`属性已添加到以下API以检索区域设置详细信息。

* `GET /learningObjects/{loId}/instances/{loInstanceId}`
* `GET /learningObjects/{id}?include=instances,enrollment.loInstance`
* `GET /learningObjects?include=instances,enrollment.loInstance`
* `GET /learningObjects/{id}/relatedLOs?include=instances,enrollment.loInstance`
* `POST /learningObjects/query?include=instances,enrollment.loInstance`
* `POST /search/query?include=model.instances`
* `GET /search?include=model.instances`

#### 使用cURL的请求示例：

```
curl --location 'http://abcd.com/primeapi/v2/learningObjects/course:1234567/instances/course:1234567_1234567' \
```

#### 示例请求：

```
{
    "links": {
        "self": "http://abcd.com/primeapi/v2/learningObjects/course:1234567/instances/course:1234567_1234567"
    },
    "data": {
        "id": "course:1234567_1234567",
        "type": "learningObjectInstance",
        "attributes": {
            "dateCreated": "2024-02-27T09:21:25.000Z",
            "isAET": false,
            "isDefault": true,
            "isFlexible": false,
            "locale": "en-US",
            "state": "Active",
            "localizedMetadata": [
                {
                    "locale": "en-US",
                    "name": "Default instance"
                }
            ]
        },
        "relationships": {
            "learningObject": {
                "data": {
                    "id": "course:1234567",
                    "type": "learningObject"
                }
            },
            "loResources": {
                "data": [
                    {
                        "id": "course:123456_1234567_1234567_1",
                        "type": "learningObjectResource"
                    }
                ]
            }
        }
    }
}
```

### 用于亵渎检查的公共API更改

更新了以下API，可对社交帖子上的评论和回复进行亵渎检查。

* `POST /boards/{id}/posts `
* `PATCH /posts/{id}`
* `POST /posts/{id}/comments`
* `PATCH /comments/{id}`
* `POST /comments/{id}/replies`
* `PATCH /replies/{id}`

如果在帖子中找到受限单词，则将发送以下回复。

#### 示例响应：

```
{
  "status": "FORBIDDEN",
  "title": "BAD_WORD_FOUND",
  "source": {
    "info": "Unacceptable word found in post"
  }
}
```

### RPM和突发限制的变化

在此版本中，为所有API添加了RPM（每分钟请求数）和突发限制。 可以在Swagger页面上检查每个API的最大RPM。

RPM是您在一分钟内可以发送到API服务器的请求数。 突发限制允许在短时间内处理更多请求，超出通常的速率限制。 例如，`learningObject` API允许每分钟最多15个请求。 如果超出此限制，则API将返回错误消息。

### 徽章API的更改

新属性`externalProvider`已添加到以下API，以检索有关外部徽章的信息，包括徽章ID和提供者名称。

* `GET /badges `
* `GET /badges/{id}`
* `GET /skills?include=levels.badge`
* `GET /skills/{id}?include=levels.badge`
* `GET /learningObjects/{loId}/instances/{loInstanceId}?include=badge`
* `GET /users/{userId}/userBadges`
* `GET /users/{userId}/userBadges/{id}`

#### 使用cURL的请求示例：

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 123456789' 'https://abcd.adobe.com/primeapi/v2/badges/44'
```

#### 示例响应：

```
{
  "links": {
    "self": "https://abcd.adobe.com/primeapi/v2/badges/44"
  },
  "data": {
    "id": "44",
    "type": "badge",
    "attributes": {
      "imageUrl": "https://abcd.com/accountassets/1/badges/download.png",
      "name": "external badge",
      "state": "Active",
      "externalProvider": {
        "id": "1234sjd-b272-4de1-9b60-1234567",
        "provider": "credly"
      }
    }
  }
}
```

### 通过作业API下载用户组和自定义角色审核报告

用户可以使用`Job API`下载&#x200B;**[!UICONTROL 用户组报告]**&#x200B;和&#x200B;**[!UICONTROL 自定义角色审核报告]**。

#### 用户组报告下载请求示例：

```
curl -X POST --header 'Content-Type: application/vnd.api+json;charset=UTF-8' --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 12345678' -d '{ \ 
     "data": { \ 
         "type": "job", \ 
         "attributes": { \ 
             "jobType": "generateUserGroupReport" \ 
         } \ 
    } \ 
 }' 'https://abcd.adobe.com/primeapi/v2/jobs'
```

#### 下载自定义角色审核报告的请求示例：

```
curl -X POST --header 'Content-Type: application/vnd.api+json;charset=UTF-8' --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 1234567' -d '{
    "data": {
        "type": "job",
        "attributes": {
            "description": "description of your choice",
            "jobType": "generateCustomRoleAuditReport",
            "payload":{
                 "fromDate": "2020-01-01T18:30:00.000Z",
                 "toDate": "2024-09-31T18:30:00.000Z",
                 "locale":  "en-US"
            }
        }
   }
}
```

### 无请求正文的错误消息

对于请求正文为必填内容，但API中未提供该正文的情况，我们引入了特定的错误消息。

#### 示例错误消息：

```
{
    "status": "BAD_REQUEST",
    "title": "Generic Error"
}
```

## 报告增强功能

管理员可以在&#x200B;**管理员** > **报告**&#x200B;部分中找到这些报告更改。

### “学习成绩单”报告

**[!UICONTROL 学习成绩单]**&#x200B;报告将包含两个新列：

* **[!UICONTROL 模块ID]**：显示每个模块的唯一标识符。 此新列已在现有&#x200B;**[!UICONTROL 模块]**&#x200B;列之后添加。
* **[!UICONTROL 课程实例ID]**：显示每个课程实例的唯一标识符。此新列已添加到现有&#x200B;**[!UICONTROL 实例]**&#x200B;列之后。
* **[!UICONTROL 完成注释]**：此列捕获管理员在标记用户完成时输入的注释。 此新列已在报告末尾添加。


### 会话摘要报告

**[!UICONTROL 会话摘要]**&#x200B;报告将包含三个新列：

* **[!UICONTROL 模块ID]**&#x200B;列已添加到&#x200B;**[!UICONTROL 会话名称]**&#x200B;列之前。
* **[!UICONTROL 会话ID]**&#x200B;列已添加在&#x200B;**[!UICONTROL 会话名称]**&#x200B;列之前。
* **[!UICONTROL 课程实例ID]**&#x200B;列已添加到&#x200B;**[!UICONTROL 实例名称]**&#x200B;列之后。
* 在&#x200B;**[!UICONTROL 注册计数]**&#x200B;列之后添加了&#x200B;**[!UICONTROL 完成计数]**&#x200B;列。

## 本次更新中修复的错误

* 修复了在Android和iOS设备上提交文件期间从活动模块上传视频时发生的错误。
* 修复了在移动应用程序上打开课程时出现的问题；Web版本可正常运行。
* 修复了在Safari中查看工作辅助和其他资源的问题。
* 修复了阻止用户下载移动应用程序上的工作辅助的问题。
* 修复了修补程序用户API文档中的错误。
* 修复了从课程中删除会话时，组织者未收到电子邮件通知的问题。
* 修复了从课程中删除并重新发布模块后，组织者不会收到会话取消电子邮件的问题。
* 添加了在外部用户创建期间在电子邮件地址中包含特殊字符“+”和“ — ”的支持。
* 修复了Marketo连接器统一报告同步在CSV记录值中包含双引号时失败的问题
* 修复了`/skills`端点为Admin API返回正确状态，但学习者API持续显示不正确或缓存的数据的问题。
* 修复了帐户未设置Go1连接器时，免费增值课程的Go1入门培训失败的问题。
* 修复了学习路径(LP)中的课程在学习者已完成LP时无法通过迁移访问的问题。
* 修复了当用户经理和跳级经理均设置为SU（超级用户）而非管理员且未包含在CSV中时，增量用户CSV失败的问题。
* 修复了信息板报告中商店经理的范围问题。
* 修复了在删除草稿课程时未删除xapi_iri的问题。
* 修复了在某些情况下无法添加唯一学习对象ID的问题。
* 修复了学习计划中的IsEmbeddable属性在共享学习计划中无法正确更新的问题。
* 修复了影响“学习者”视图中的学习路径总持续时间显示的问题。
* 修复了允许学习者在删除其帐户后，通过自行注册链接进行注册的问题。
* 修复了在创建课程期间，在课程描述中添加链接时，`www`被删除的问题。
* 修复了隐藏信息和下载工作辅助无法正常工作的问题。
* 修复了通过具有IP ID的自注册链接添加的新用户无法进行单点登录(SSO)的问题。
* 修复了在删除公告后无法获取通知消息数据的问题。
* 修复了通过电子邮件搜索用户时搜索结果不足的问题。

## 系统要求

查看[Adobe Learning Manager系统要求](/help/migrated/system-requirements.md)。

## 发行说明

请查看[发行说明](/help/migrated/release-note/release-notes.md)以了解最新发行更新。

## Adobe Learning Manager 的早期版本

* [2024年7月版](/help/migrated/whats-new-july-2024.md)
* [2024年3月版](/help/migrated/whats-new-march-2024.md)
