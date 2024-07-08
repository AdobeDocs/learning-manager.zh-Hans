---
description: 了解 Adobe Learning Manager 2024 年 7 月版中的新增功能和增强功能
jcr-language: en_us
title: 新功能摘要
source-git-commit: 7e3b19d29b9de23ea489c5651ef0aef1d4ec3005
workflow-type: tm+mt
source-wordcount: '2178'
ht-degree: 2%

---


# 新功能摘要 {#new-features-summary}

了解 Adobe Learning Manager 2024 年 7 月版中的新增功能和增强功能。

## 合规性仪表板中的增强功能

### 什么是合规性仪表板？ {#whatiscompliancedashboard}

使用 Adobe Learning Manager **中的**&#x200B;合规性信息板&#x200B;]**，**[!UICONTROL &#x200B;经理可以监控学习者实现学习目标的进度。他们可以检查团队成员是否在截止日期前完成并跟上他们的学习过程，这有助于确保合规性。 管理员可以设置合规性信息板并与经理共享。

要在“管理员”应用程序中访问合规性信息板，请选择“学习摘要”**[!UICONTROL >“报告]**”>**[!UICONTROL **[!UICONTROL “合规性信息板&#x200B;]**”。]**

### 版本中发生的变化

通过增强的合规性信息板，管理员和经理可以查看与其特定类别（例如，销售、市场营销和法律）相关的合规性类型课程、学习路径或认证。 管理员可以将自定义合规性课程分类为特定类别。 自定义合规性类别由目录标签提供支持。  管理员可以创建课程信息板并将其共享给经理。 然后，经理可以在各自的实例上查看相同的仪表板。 此外，还增强了合规性仪表板的用户界面和合规性电子邮件通知。![](assets/compliance-dashboard-admin.png)

#### 工作流

以下是使用增强的合规性信息板的步骤：

| 角色 | 任务 | 更多信息 |
|---|---|---|
| 管理员 | 创建自定义合规性标签 | 请参阅此文章 [创建自定义合规性标签](/help/migrated/administrators/feature-summary/reports.md#compliance-dashboard) ，了解更多信息 |
| 作者 | 将这些标签添加到课程 | 有关详细信息，请参阅此文章 [向课程/学习路径/认证](/help/migrated/authors/feature-summary/courses.md#add-compliance-labels-to-courselearning-pathcertification) 添加合规性标签。 |
| 管理员 | 创建包含合规性课程的仪表板并与经理共享 | 有关详细信息，请参阅此文章 [创建和共享合规性仪表板](/help/migrated/administrators/feature-summary/reports.md#create-and-share-a-compliance-dashboard) 。 |
| 经理 | 查看合规性仪表板 | 有关详细信息，请参阅此文章[合规性状态](/help/migrated/managers/feature-summary/manager-dashboard.md#compliance-status) |

## 学习者用户界面改版

>[!IMPORTANT]
>
>新的学习者 UI 将分阶段发布。

**学习者用户界面**&#x200B;已更新，设计更加优雅和现代。**[!UICONTROL 学习者主页]**、**[!UICONTROL 我的学习]**、**[!UICONTROL 目录]**&#x200B;和&#x200B;**[!UICONTROL 课程概述]**&#x200B;登录页面焕然一新。课程卡还具有以现代方式显示详细信息的新设计。 将鼠标悬停在课程卡片上会显示课程描述和发布日期。

>[!NOTE]
>
>改进后的用户界面仅适用于沉浸式布局。 移动网站或应用程序尚不支持这些更改，并将在未来的版本中进行更新。

![](assets/old-ui.png)
_旧用户界面_

![](assets/new-ui.png)
_新的用户界面_

### 此版本中的更改内容

**实现外观现代化**

全新的视觉元素符合现代设计趋势，使产品看起来直观而吸引人。 这包括新的刊头、侧面板和外观现代的小部件。

**增强的用户体验**

学习者现在可以在以下页面上查看类似的卡片视图：主页、目录、我的学习和课程概述页面，提供统一的体验。

查看 [学习者主页](/help/migrated/learners/feature-summary/learner-home-page.md) 了解更多信息。

**课程发布日期的更改**

借助此项增强功能，导入到 Adobe Learning Manager 中的 LinkedIn 和 Go1 课程的发布日期将成为 LinkedIn 和 Go1 的实际发布日期。 您也可以在用户界面上查看 LinkedIn 和 Go1 课程的实际发布日期。 有关详细信息，请查看 [课程卡](/help/migrated/learners/feature-summary/learner-home-page.md#course-cards) 。

## 对未登录体验的更新

通过未登录体验，您可以为未登录的客户创建实时体验。 这可以作为其营销活动的登录页面，提供足够的信息来鼓励注册。

### 此版本中的更改内容

客户可以购买高级计划来构建这种高度可扩展的非登录体验。 这种非记录体验由“培训数据访问](/help/migrated/integration-admin/feature-summary/connectors.md#training-data-access)”[提供支持，可使用 Adobe Learning Manager API 提供有关座位限制、占用座位、轮候名单限制和轮候表计数的实时数据。客户可以使用这些 API 为非登录学习者提供搜索和过滤功能以及完整的课程摘要。 有关 API 的更多信息，请参阅此文章 [非登录 API](/help/migrated/integration-admin/feature-summary/non-logged-in-apis.md) 。

>[!NOTE]
>
>请联系支持团队或CSAM购买高级计划。

## 支持多个库存单位 （SKU）

学习者现在可以将多个课程、学习路径或认证添加到购物车并一起购买。

### 版本中发生的变化

以前，学习者一次只能购买一门课程。 在此版本的 **Adobe Learning Manager** 中，他们可以使用购物车一次购买多个课程、学习路径或认证。

此功能仅在学习者应用程序（现有 UI、新学习者 UI 和移动沉浸式应用程序）中可用。

查看 [ALM 中的多项目购物车](/help/migrated/learners/feature-summary/multi-item-cart.md)

## 流体播放器中的 HTML5 内容支持

**Adobe Learning Manager** 现在支持将 HTML5 内容作为 .zip 文件上传到内容库。 上传后，这些文件可以作为模块包含在课程中。 此外，作者还可以定义自学 HTML5 模块的完成条件，允许学习者标记完成或在启动时自动完成。

### 此版本中的更改内容

Adobe Learning Manager 现在支持在自学课程中支持 HTML5 的内容。 作者可以将 HTML5 内容作为.zip文件添加到自学内容中。 学习者可以在流体播放器中查看 HTML5 内容。 借助这项新功能，学习者现在可以直接在流体播放器中将课程标记为已完成 对于自定进度的课程。 有关详细信息，请查看 [内容库中](/help/migrated/authors/feature-summary/content-library.md#add-html5-file-type-in-the-content-library) 的“添加 HTML5 文件类型”。

借助新的增强功能，只要作者已将完成条件设置为新选项 **[!UICONTROL 启动内容]**，那么在访问 URL 时，带有外部链接的课程将自动标记为已完成。 “活动模块”页面中添加了“完成条件&#x200B;]**”这个新选项**[!UICONTROL ，作者可以在这里设置外部链接的完成条件。有关详细信息，请查看 [活动模块](/help/migrated/authors/feature-summary/courses.md#add-html-link-in-the-activity-module) 中的“添加 HTML”链接。

![](assets/completion-criteria-activity-module.png)
_完成条件选项 - 活动模块_

## 移动应用程序上的课程逾期推送通知

学习者在错过课程截止日期时会收到推送通知。 借助这项新的增强功能，学习者现在可以选择将提醒暂停 24 小时，或者在下周收到每个逾期提醒时收到提醒。 这仅适用于截止日期逾期通知。 查看 安排 [推送通知](/help/migrated/learners/feature-summary/user-notifications.md#schedule-the-push-notification)

## 此版本中的 API 更改

### 搜索 API

搜索 API 包括以下更改：

学习者可以使用 API 在 ```GET /search``` 目录过滤器中搜索标签。 学习者可以通过选择 ```tag``` 参数值 ```filter.loTypes``` 来搜索标签。

**示例卷曲**

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 5a858f23924f4feafa38ae8d6c4d97b6' 'https://example.com/primeapi/v2/search?page[limit]=10&query=Business&autoCompleteMode=true&filter.loTypes=tag&sort=relevance&filter.ignoreEnhancedLP=true&matchType=phrase&persistSearchHistory=true&stemmed=false&highlightResults=true'
```

以下 API 中添加了新的过滤器、可用座位、可用候补名单和时间范围过滤器： ```GET /search``` 和 `GET /learningObjects`。

新的过滤器 `filter.session.includeEnrollmentDeadline` 已添加到以下 API ```GET /search```中。

### 帐户接口

在 API 中添加```GET /account```了新列 `custom_injections`、 `showComplianceLabel`和`complianceLabelDefaultID`，以获取用户终端节点的账户数据。

### 学习对象 API

以下是本次更新中对学习对象 API 所做的更改：

新的响应旧作者 ID 和 API 下 `authorDetails` 添加的其他 `GET /learningObjects` 详细信息。 此外，还添加了一个新的过滤器 `filter.authors`，用于过滤旧版作者及其课程。

调用 `effectivenessIndex` 的新属性将帮助您获取课程效果数据。

**示例卷曲**

```
curl --location 'https://example.com/primeapi/v2/learningObjects/course%3A9790045?enforcedFields%5BlearningObject%5D=effectivenessData' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth 598665ab5c8a99bea0e774d9faf7f3ca'
```

新的响应 `whoShouldTake`提供了有关谁应该参加本课程的详细信息，已添加到以下 API 中： `POST /learningObjects/query`、 `GET /learningObjects/{id}`和 `GET /learningObjects`。

**示例卷曲**

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 28a83fb8c87579af8ebc4434cc80f0c0' 'https://example.com/primeapi/v2/learningObjects/course%3A1131255' 
```

新的响应 `waitlistLimit`提供了有关候补名单限制的详细信息，已添加到 API 中 `GET /learningObjects` 。

提供学习对象总数的新响应 `count` 已添加到 API `GET/ learningObjects` 和 `POST/ learningObjects/query`中。

新的响应， `catalogFieldId` `fieldValueId` 并已添加到 `catalogLabels` API 中 `GET/ learningObjects` 。

学习者可在 API `GET /preview/learningObjects`中获取目录标签值。

### 获取市场数量的新 API

在此版本中，添加了一个新的 API `GET /search/marketplace/count` 。 这有助于您获取内容市场中可用学习对象的计数。

**示例卷曲**

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth d8631c7b0e3b5d2ae00422ef30aaecfc' 'https://example.com/primeapi/v2/search/marketplace/count?query=course'
```

**示例响应**

```
{
  "count": 54910
}
```

### 学习对象实例 API

以下是此更新中对学习对象实例 API 所做的更改：

在此版本中，学习对象实例 API `GET /learningObjects/{loId}/instances/{loInstanceId}`中添加了一个名为的新`gamificationEnabled`密钥。

**示例卷曲**

```
curl --location 'http://example.com/acapapi/primeapi/v2/learningObjects/learningProgram:12756/instances/learningProgram:12756_15644' 
```

`gamificationSettings`上述 API 的新属性，用于获取游戏设置的详细信息。例如： `GET /learningObjects/{loId}/instances/{loInstanceId}/gamificationSettings`.

**示例卷曲**

```
curl --location 'http://example.com/acapapi/primeapi/v2/learningObjects/learningProgram:103852/instances/learningProgram:103852_103526/gamificationSettings'
```

`leaderboard`上述 API 的新属性，用于获取游戏设置的详细信息。例如： `GET /learningObjects/{loId}/instances/{loInstanceId}/leaderboard`.

**示例卷曲**

```
curl --location 'https://example.com/primeapi/v2/learningObjects/learningProgram:106339/instances/learningProgram:106339_105775/leaderboard' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth de4b5ee6efdd42375130db27ff503dd4'
```

### 对偏移限制的更改

为了提高系统性能并更有效地管理资源利用率，Adobe 已弃用 GET /users 端点中管理员和学习者范围的高偏移值。 建议使用作业 API 检索具有偏移值的记录。

### 已弃用的 API

在 Adobe Learning Manager](/help/migrated/api-deprecations-list.md) 中查看 [API 弃用情况，获取产品中所有已弃用 API 的累积列表。

## 对报告的更改

### 合规性信息板

在此版本中，合规性信息板报告新增了两列：

* 状态
* 合规类型

这是对现有列的补充：

* 用户名
* 用户电子邮件
* 学习计划/认证/课程
* 类型
* 注册日期（UTC 时区）
* 截止日期（UTC 时区）
* 完成日期（UTC 时区）
* 进度百分比

### 培训报告

管理员>报告>自定义报告&#x200B;**和**&#x200B;作业 API **中的**&#x200B;培训报告包含名为“技能”**和**“标记”**的**&#x200B;列。 **** ****&#x200B;这些列现在重命名为&#x200B;**“技能和****标记**”。

### 内容审核报告

在此版本中， **[!UICONTROL 内容审核跟踪]** 报告现在在“修改类型”列中包含以下新属性：

* 用户组添加
* 删除用户组
* 自定义标签添加
* 自定义标签删除
* 共享目录添加
* 删除共享目录
* 共享目录更新

## 此更新中修复的错误

**活动提交**

* 尝试将文件重新上载到活动提交模块失败，网络调用中出现错误 500。

**API**

* 如果多个讲师具有相同的电子邮件地址，则创建 Connect VC 会议将失败。
* 注册到学习路径后，MS Teams VC 会在“概述”页上显示不正确的 URL。
* 作为作业 API 响应的一部分提供的用户报告预签名 URL 将在 6 小时后过期。
* 生成课程注册报告时，“课程名称”列显示的课程名称不正确。
* 当然，迁移工作者在调用批量 API 时无法发送唯一的 lo id，但该 id 被删除了。
* 当课程包含在用户可以访问的特定目录中时（默认目录处于禁用状态时），尽管设置阻止未注册的学习者查看课程，您仍可以通过学习对象/ID 端点检索课程的元数据。
* 在 GET /learningObject API 中，当技能名称中包含逗号时，技能筛选器无法按预期工作。
* SFTP 的数据保留工作线程中文件的时间戳元数据不一致。
* 如果删除并重新配置了任何连接器，则项目迁移状态显示为已关闭。
* 培训报告将“标记”作为列标题，而不是“标记”。
* 如果目录处于禁用状态，并且导出的任何课程只是已禁用目录的一部分，则 Commerce 连接器导出将失败。

**认证**

* 有时，将用户重新注册到定期认证会失败。

**自定义角色**

* 某些情况下，当自定义管理员尝试切换到讲师角色时，系统会显示错误 403 禁止显示。

**电子邮件模板和通知**

* 取消会话后，当从会话中移除最后一组讲师时，电子邮件通知将不会发送给该组讲师。
* 创建虚拟讲师指导培训后，组织者不会收到 MS Teams 的电子邮件通知。 只有在发布课程并启用电子邮件模板后，才会触发电子邮件。
* 有时，电子邮件模板包含不正确的日期格式和翻译。

**学习者**

* 当学习者注册了课程的多个实例并下载出勤报告时，该报告包含的信息不正确。
* 如果其他用户的私人帖子被添加到公共故事中，用户可以查看这些帖子。
* 在某些情况下，您无法取消为学习者注册认证。 尝试取消注册时会显示一条错误消息。
* 即使管理员在仅选择一个课程后将其标记为已完成，认证仍标记为已完成。
* 如果会话的结束时间更改为之前的日期，管理员无法将 VC 标记为完成。
* 对于轮候名单上的学习者，会话出席报告显示为“未参加”。

**学习者应用程序**

* 将课程备注下载为 PDF 格式后，备注会随机显示。 他们不服从命令。

**学习路径**

* 在学习路径中选择技能后，当您选择文本字段时，下拉列表不会按预期显示。
* 在某些情况下，您无法从学习路径中删除技能。

**学习计划**

* 如果灵活学习计划包含许多课程，则即使管理员将其标记为已完成，学习计划也不会完成。
* 学习者更改实例时，注册报告中last_modified_by列不会更新。

**举报**

* 在某些情况下，管理员无法导出培训报告。
* 当 SCORM 内容包含的问题或答案超过 32,767 个字符时，您将无法在 Excel 中下载课程测验报告。
* 选择“重置游戏”后，获得关卡的日期不会重置。

**搜索**

* 目前，导出所有用户组后，已删除的用户组也会显示在输出中。
* 由于间歇性搜索问题，无法搜索认证。

## 此版本中的已知问题

移动设备脱机播放器不加载 HTML5 内容。

## 系统要求

查看 [Adobe Learning Manager 系统要求](/help/migrated/system-requirements.md)。

## Adobe Learning Manager 的早期版本

* [2024 年 3 月版](/help/migrated/whats-new-march-2024.md)
* [2023 年 11 月版](/help/migrated/whats-new-november-2023.md)
