---
title: 此版本（2023年4月）的新增功能
description: 了解AdobeLearning Manager中的新功能和增强功能
hidefromtoc: true
source-git-commit: 1da0911a4d0c2ae5cb01bbb2b7955675b0dfcdde
workflow-type: tm+mt
source-wordcount: '3158'
ht-degree: 0%

---

# 此版本（2023年4月）的新增功能

## Microsoft TeamsAdobeLearning Manager应用程序

Microsoft Teams上新的AdobeLearning Manager应用程序旨在促进工作流程中的学习并提升社交学习。 学习者无需切换到Microsoft Teams即可访问浏览器平台内的学习内容。 请联系CSAM以获取MS Teams上AdobeLearning Manager应用程序的Beta版。

有关详细信息，请参阅 [Microsoft TeamsAdobeLearning Manager应用程序](/help/migrated/adobe-learning-manager-app-microsoft-teams.md).

## 对讲师指导培训(ILT)体验的增强

对讲师指导培训(ILT)体验进行了一些改进。 主要增强功能包括：根据位置筛选会话的功能、在不损失进度的情况下切换实例(VILT)的功能、用于管理预订会话中冲突的新“计划助理”功能、将“技能”附加到讲师以及根据技能选择讲师的功能。

### 更改的内容

* 管理员应用程序的“技能”页面中提供了上传技能讲师映射的选项。
* 在“技能”页面上，新增了一列“讲师”。 该列显示了针对该技能的讲师数量。 如果单击“讲师”列中的数字，系统会将您重定向到弹出窗口，其中显示已分配给某项技能的讲师数量。

有关详细信息，请参阅 [向讲师分配技能](/help/migrated/administrators/feature-summary/skills-levels.md#assign-skills-to-instructors).

![讲师CSV](assets/instructor-csv-new.png)

### 日程安排助理

管理预订讲师和教室或虚拟教室时的冲突。 如果您希望在指定讲师参加课程之前知道其在什么时间和日期可以参加，请使用“计划助理”。

作者、管理员和自定义管理员/作者可以使用计划助手。

有关详细信息，请参阅 [日程安排助理](/help/migrated/authors/feature-summary/courses.md#scheduling-assistant).

## 全新AdobeLearning Manager移动应用程序

一款适用于Android和iOS的全新AdobeLearning Manager移动应用程序，可让学习者随时随地顺畅地访问学习内容。 该应用程序允许学习者在移动设备上使用培训，并稍后在其桌面上恢复培训。 移动应用程序支持通知、文件上传、轻松标记书签和共享学习内容、社交学习等，为学习者提供了更多灵活性并支持即时学习。

![全新移动地图界面图像](assets/mobile-app.png)

从Google Play Store和Apple App Store下载移动设备。 系统将提示旧版应用程序的用户下载并安装新应用程序。

在此版本中，应用程序支持以下功能：

新的移动应用程序支持此版本中的以下主要功能：

* 增强的搜索功能，包括在搜索输入框中显示学习者最近的搜索和组织中的热门搜索。
* 能够下载学习者成绩单。
* 即兴通知中心 — 在应用程序内向学习者提供重要更新，作为通知
* 在“目录”/“我的学习”页面中排序和筛选学习对象的功能
* 为学习对象(LO)添加书签的功能 — 已添加书签的LO将在学习者主页上的“由我保存”部分中提供。
* 支持增强型LP
* 可以将移动界面语言更改为AdobeLearning Manager支持的任意语言。
* 支持外部认证、CR/VC会话和活动模块中的文件上传。
* 能够在应用程序中提交L1课程反馈。
* 支持深层链接。
* 支持社交学习。
* 徽章支持。
* 支持外部用户登录。

**此版本不支持的功能**

* 支持在移动应用程序内参加课程时多次尝试测试模块。
* 允许您指定搜索参数的搜索选项，例如课程元数据、标签和用于指定搜索范围的技能。
* 管理员启用的自定义公告，显示为移动应用程序中用户的弹出窗口。
* 您无法在应用程序的技能页面上添加技能。
* 离线时参加课程。

有关详细信息，请参阅 [AdobeLearning Manager移动应用程序](/help/migrated/learners/feature-summary/ipad-android-tablet-users.md).

## 使用任意二维码扫描应用程序扫描Learning Manager二维码

AdobeLearning Manager现在支持在本机相机应用程序的帮助下以更用户直观的方式扫描二维码，而无需下载扫描二维码的应用程序。

为了支持以前的工作流程（在此版本中，您可以使用ALM应用程序的菜单扫描二维码），我们提供了有关如何切换到新工作流程的信息。

由于改进了基于二维码的工作流程，因此将不再支持此版本之前生成的旧二维码。 因此，如果您已使用旧版Learning Manager为将在本版本之后举行的教室或虚拟教室会话生成二维码，则必须生成新的二维码。

### 推荐公告增强功能

在此版本中，我们已将推荐区域从组织更新为基于用户组（学习者所属组）的建议，以显示学习者的相关课程。

管理员可以根据学习者的个人资料为学习者指定特定课程或培训。 然后，学习者可以根据其所属的配置文件搜索课程。

**更改的内容**

“公告”页面上有一个选项，可以向学习者说明推荐本课程或培训的原因。

![创建批注](assets/create-announcement.png)

### 新管理员设置

管理员在“设置”>“显示过滤器面板”中有一个名为“组”的新选项。 启用“组”后，“学习者”主页上的“组”过滤器会显示。 然后，学习者可以选择根据用户组显示课程。

|   | 启用该选项时 | 禁用该选项时 |
|--- |--- |--- |
| 已启用组选项 | <ul><li> 在磁贴上显示用户组以及指向目录页面的链接。</li><li> 目录过滤器中会显示用户组。</li></ul> | <ul><li>“用户组”的名称不显示在磁贴上。</li><li>目录过滤器中未列出用户组。</li></ul> |
| 组选项已禁用 | <ul><li>以纯文本形式显示课程磁贴上用户组的名称。</li><li>目录过滤器中未列出用户组。</li></ul> | <ul><li>课程磁贴不显示用户组的文本或名称。</li><li>目录过滤器中未列出用户组。</li></ul> |

**工作原理**

管理员可为任何用户组添加课程并发布公告。

学习者可以在主页看到一个包含推荐课程的区域栏，并在磁贴上看到一个课程链接。

![推荐删除学习者](assets/recommendation-strip-learner.png)

学习者单击链接或“转到目录”按钮后，系统会将学习者重定向到课程目录页面。 然后，学习者会根据目录和“我的学习”页面中的用户组查看要筛选的用户组列表。

![搜索结果](assets/search-results.png)

## 使用位置搜索会话

### 管理教室位置

有时，您希望学习者根据位置在日历上筛选会话。 使用“教室位置”对话框或CSV文件添加位置后，学习者可进行筛选。

![添加教室位置](assets/add-classroom-locations.png)

有关详细信息，请参阅 [添加教室位置](/help/migrated/administrators/feature-summary/settings.md#classroom-locations).

### 日历小组件

作为学习者，您可以按位置过滤分配给您的会话。 转到日历小组件，选择筛选会话，然后选择位置。

![未应用过滤器](assets/no-filters-applied.png)

![日历上未应用筛选器的会话](assets/sessions-on-calendar-no-filters.png)

![应用于位置的过滤器](assets/location-filter-applied.png)

![日历上应用了位置筛选器的会话](assets/session-with-location-filters-applied.png)

此外，如果作者在创建课程时添加了培训位置，则培训位置现在会显示在“课程概述”页面上。

### 管理员

作为管理员，您可以控制学习者是否可以根据位置筛选课程。 在“设置”>“常规”中，启用或禁用“培训位置”。

有关详细信息，请参阅 [管理员设置](/help/migrated/administrators/feature-summary/settings.md).

## 试用体验更改

创建试用帐户后，内容市场中的课程即会立即可用。

## 聊天机器人

使用聊天机器人与客服专员或多个客服专员聊天。 只有试用帐户的管理员和自定义管理员才能使用此功能。

该聊天机器人将：

* 欢迎您给我留言。
* 提供产品信息或产品演示选项。
* 将聊天转接给实时客服专员。
* 保留您的聊天历史记录。

![聊天机器人](assets/chatbot-new.png)

## 观察核对表的改进

作者现在可以选择Managers和Store/Location Managers作为清单的审阅人。 经理和商店/位置经理（如果被选为“审阅人”）还可以查看和完成其团队的检查列表，而无需切换到讲师角色。 讲师继续查看清单。 系统会向注册时核对清单的实例审阅者（讲师/经理）发送新的“审阅核对清单”通知。

如果在清单模块中添加经理作为审阅者，则他们能够在经理应用程序中审阅清单。 讲师应继续按预期审阅清单。

有关详细信息，请参阅 [观察清单](/help/migrated/authors/feature-summary/courses.md#observation-checklist).

## 其他增强功能

### 学习者搜索

搜索结果还分类为：

* 您最近执行的搜索
* 您组织中的热门搜索

学习者的搜索功能也得到了改进。 学习者现在可以使用双引号“……”、加号“+”和减号“ — ”运算符，更快地查找相关结果，并获得类似Google搜索体验。

* 使用双引号(“……”)搜索包含确切短语或单词的课程。 例如，输入“数据科学”将返回以短语“数据科学”开头的课程。
* 使用+运算符可确保只显示包含特定短语或单词的结果。 例如，“计算机编程+python”将仅显示包含“python”一词的计算机编程课程。
* 使用 — 运算符可确保仅显示不包含特定短语或字词的结果。 例如，“计算机编程 — python”将显示除包含单词“python”之外的所有计算机编程课程。

### 学习对象的弹出窗口发生冲突

当学习者的会话发生冲突时，“概述”页面会显示注册时弹出窗口。 如果从目录页面或概述页面注册，而学习者已有冲突的会话，则将触发有冲突的弹出窗口，其中显示冲突的会话详细信息。 即使学习者有冲突的会话，也可以注册新会话。

![警告](assets/learner-pop-up.png)

请注意，此消息只是一个警告。 您仍可以注册课程。

### 新建模板

由于取消注册，我们添加了一个名为“会话已取消”的新电子邮件模板。 用户取消注册培训时，他们会收到取消电子邮件。

### 课程的新定价功能

管理员现在可以在管理员设置>基本信息部分中设置帐户的货币。 管理员可以指定符号以及ISO货币代码，例如USD、GBP等。 所有新帐户的默认值均为$。 此更改仅适用于非学习者应用程序。 管理员能以学习者身份预览课程时，可以看到这一变化。 货币符号也会显示在学习者成绩单和培训报告中。

有关详细信息，请参阅 [管理员设置](/help/migrated/administrators/feature-summary/settings.md).

### 切换实例

注册课程特定实例的学习者可以查看课程所有可用实例的列表，并切换到更适合它们的另一个实例。 切换的原因可能是学习者错过了参加之前的实例，或者新实例的会话时间更合适或其他。

学习者在课程中完成的任何进度、学习者测验分数等都会结转到新实例。 此功能主要用于教室和混合课程，但我们应支持所有类型的课程，包括自学课程。

无论如何设置“实例切换”选项，“查看所有实例”都会显示。 如果课程包含多个实例，学习者现在可以查看所有实例的选项。

如果启用“实例切换”选项，则学习者可以切换到各种实例，直到完成课程。 如果禁用此选项，学习者可以查看实例，但无法注册课程。

当学习者选择 **查看所有实例**，学习者可以查看所有课程实例。

![查看所有实例](assets/view-all-instances-new.png)

管理员可以为学习者切换实例。

![切换实例](assets/switch-instances.png)

![切换实例选择](assets/switch-instances-select.png)

在学习者或管理员应用程序完成课程的任何实例之前，您无法切换实例。

作者在创建课程时，可以在启用或禁用“实例切换”之间切换。 实例切换仅适用于免费课程。

有关详细信息，请参阅 [实例配置](/help/migrated/authors/feature-summary/courses.md).

**学习者**

学习者可以从轮候课程实例切换到其他实例。 他们可以在学习路径或认证中切换课程实例。

注册学习路径或认证后，他们可以在课程页面上单击“查看实例”，然后切换实例。

>[!NOTE]
>
>经理指派的注册类型不支持实例切换配置。
>
>如果您正在从Flex LP切换实例，则进度将转移到其他实例。

### 用户审查追踪

“用户审查追踪”报告将捕获关于执行实例“从实例”切换到“到实例”、按时间、日期等的学习者的信息。

![查看用户审查追踪报告](assets/user-audit-trail.png)

有关详细信息，请参阅 [用户审查追踪报告](/help/migrated/administrators/feature-summary/reports.md#useraudittrailreports).

### 讲师利用率报告

此报告捕获讲师在讲授所分配的会话时每天花费的时间（以分钟为单位）。 自选定开始日期起三个月内，可下载报告。

有关详细信息，请参阅 [讲师利用率报告](/help/migrated/administrators/feature-summary/reports.md#instructor-utilization-report).

![讲师利用率报告](assets/instructor-utilization.png)

### 工作辅助报告

新增一份报告，跟踪帐户中的工作辅助以及有关工作辅助的各种信息，如语言、类型、持续时间、作者、标签等。

有关详细信息，请参阅 [工作辅助注册报告](/help/migrated/administrators/feature-summary/reports.md).

### 发送给注册特定课程实例的学习者的定向临时电子邮件

管理员和作者能够向注册特定课程实例的学习者发送有针对性的临时电子邮件通信。 课程和学习计划新增了发送实例级电子邮件的选项。

![发送实例级电子邮件](assets/adhoc-email.png)

*发送实例级电子邮件*

在“创建公告”对话框中， “电子邮件和培训”选项以及实例默认处于选中状态。 指定主题，键入消息，然后单击“保存”。

有关详细信息，请参阅 [实例级电子邮件](/help/migrated/administrators/feature-summary/courses.md#send-instance-level-emails).

### 管理员通过公告向学习者发送定向临时电子邮件

对于管理员，添加了一种新的公告类型 — “作为电子邮件”。 这可用于向选定用户组的学习者或注册特定培训的学习者发送有针对性的临时电子邮件。

如果自定义管理员和作者具有必要的访问权限，则他们也可以在实例级别查看此选项。

有关详细信息，请参阅 [公告](/help/migrated/administrators/feature-summary/announcements.md#as-email).

### 新电子邮件模板

在此版本中，我们为跳级经理添加了电子邮件模板。 这些模板适用于经理收到有关其二级报告的电子邮件时，这些报告缺少任何课程、学习路径或认证截止日期。 此外，当他们的二级报告即将到达这些课程、学习路径或认证的完成截止日期时，他们将会收到电子邮件。

* 跳过课程完成级别升级 — 截止日期前
* 错过课程截止日期时的越级升级
* 学习路径完成的跳过级别升级 — 截止日期前
* 错过学习路径截止日期的级别升级
* 跳过级别升级以完成认证 — 截止日期前
* 错过认证截止日期的越级升级

默认情况下，这些选项处于启用状态。

## 此版本中的API更改

### 新报告

我们向jobs API添加了一个新的属性jobType。 该属性接受以下值：

* **generateInstructorUtilisationReport**：返回讲师的利用率报告。
* **generateJobAidMetadataReport**：返回工作辅助报告的元数据。

**端点**：POST/primeapi/v2/jobs

generateJobAidMetadataReport请求：

```javascript {line-numbers="true"}
{ 
    "data": { 
        "type": "job", 
            "attributes": { 
                "description": "description of your choice", 
                "jobType": "generateJobAidMetadataReport" 
            } 
    }
} 
```

generateJobAidMetadataReport响应：

```javascript {line-numbers="true"}
{ 
  "links": { 
    "self": "https://learningmanagerstage1.adobe.com/primeapi/v2/jobs" 
  }, 
  "data": { 
    "id": "31126", 
    "type": "job", 
    "attributes": { 
      "dateCreated": "2023-02-28T18:36:48.000Z", 
      "description": "description of your choice", 
      "jobType": "generateJobAidMetadataReport", 
      "status": { 
        "code": "Submitted" 
      } 
    } 
  } 
} 
```

generateInstructorUtilisationReport请求：

```javascript {line-numbers="true"}
{
    "data": { 
        "type": "job", 
            "attributes": { 
                "description": "description of your choice", 
                "jobType": "generateInstructorUtilisationReport", 
                "payload": { 
                    "year": "2023", 
                    "month": "2" 
                } 
            } 
    } 
}
```

generateInstructorUtilisationReport响应：

```javascript {line-numbers="true"}
{ 
  "links": { 
    "self": "https://learningmanagerstage1.adobe.com/primeapi/v2/jobs" 
  }, 
  "data": { 
    "id": "31130", 
    "type": "job", 
    "attributes": { 
      "dateCreated": "2023-02-28T18:43:43.000Z", 
      "description": "description of your choice", 
      "jobType": "generateInstructorUtilisationReport", 
      "payload": { 
        "month": "2", 
        "year": "2023" 
      }, 
      "status": { 
        "code": "Submitted" 
      } 
    } 
} 
} 
```

欲了解更多信息，请参见 [API参考文档](https://captivateprime.adobe.com/docs/primeapi/v2/).

### 学习者实例切换

注册学习者API可让您访问所有可用实例并切换到课程的其他实例。 新实例会继承上一课程的所有属性。

我们添加了一个新的查询参数enrollmentID，正在为其请求信息。

>[!NOTE]
>
>仅以下情况需要正文：
>
>1. 灵活的学习计划
>1. 课程实例切换

### 帐户

响应包含新属性currencyCode。

**端点**：GET/primeapi/v2/account

### 讲师的技能和技能级别关联

我们引入了一项新功能，此功能可捕获讲师的技能专业知识，即对于每个讲师，他们的专业知识将得到保持，并可用于搜索和过滤等下游操作。

添加了以下属性：

* instructorSkills
* instructorSkillLevel

**端点**：GET/primeapi/v2/account /&lt;account_id>/instructorskill/search

### ILT更改

| 描述 | 新参数/响应 | 端点 |
|--- |--- |--- |
| 列出所有城市 | filter.cityName=true/false | GET/primeapi/v2/data |
| 搜索和筛选城市 | filter.cityName=city_name<br>还支持以逗号分隔的城市列表 |
| GET/primeapi/v2/search |
| 退货单详细信息 | include=room | /primeapi/v2/users/GET`<id>`/日历 |
| 用于筛选城市的学习对象 | filter.cityName=city_name <br> 还支持以逗号分隔的城市列表。 | GET/primeapi/v2/learningObjects |
| 添加城市面板 | 响应包含新属性filterPanelSetting=true/false。 | GET/primeapi/v2/account |

### 有冲突的学习者会话

检索实例的所有冲突会话的列表。

我们添加了以下字段：

* loId
* loInstanceID

**端点**： `GET /primeapi/v2/learningObjects/{loId}/instances/loInstanceId/conflictingSessions?page[offset]=0&page[limit]=10`

### VC中的教室

执行基于位置的虚拟教室课程搜索。 资源模型中存在一个新的属性roomLocation，用于指示创建VC课程时提供的自由形式位置。

我们进行了以下更改：

**学习对象**

learningObjects API的新查询参数filter.loFormat=Virtual Classroom。

**端点**：GET/primeapi/v2/learningObjects

**日历**

日历API的新查询参数filter.allSessions=false。 参数的缺省值为false。 如果设为true，则API返回学习者的所有日历会话。

**端点**： `GET /primeapi/v2/users/<id>/calendar?filter.allSessions=false`

### 学习者搜索历史记录

**Search**

新的查询参数persistSearchHistory。 默认值为true，这将持续查询搜索建议。

**端点**：GET/primeapi/v2/search？persistSearchHistory=true

**建议**

新的查询参数suggestionType。 接受的值为：

* learnerHistory（默认）
* accounthistory

**端点**：GET/primeapi/v2/search/suggestions/？suggestionType=learnerHistory

### 用户组筛选

学习对象和搜索API将提供过滤器，以通过指定的过滤器获取属于用户组的所有学习对象。 API支持筛选器作为逗号分隔列表。

我们提供了一个新的过滤器filter.lo.announcementGroups来获取属于提供的用户组过滤器的所有学习对象。

这可以是一个多值逗号分隔列表，以便灵活使用，处理过程将基于多个组之间的“OR”运算。 即，获取给定用户组下的所有学习对象。

### 自定义组

您可以通过API在自定义组中添加和删除外部用户。

**POST**

POST/userGroups/{id}/users

**正文**

```javascript {line-numbers="true"}
"data": [ 
     { 
           "type": "user",  
           "id": "{id}"   
     }  
]  
```

**DELETE**

DELETE/userGroups/{id}/users

**正文**

```javascript {line-numbers="true"}
"data": [  
     {  
          "type": "user",  
           "id": "11218291"  
     }  
]   
```

### 宣布对学习者应用程序中的学习对象进行用户组筛选

* GET/users/{userId}/userGroups API有一个新参数filter.announcedGroupsOnly，它采用布尔值(true/false)。 此选项仅过滤管理员宣布的用户组。 此参数的默认值为false。
* GET/learningObjects API有一个新参数filter.declainedGroups ，它接受公告组ID以筛选结果。
* GET/search API有一个新参数filter.declainedGroups ，它接受公告组ID以筛选结果。

示例响应如下：

```javascript {line-numbers="true"}
{
  "links": {
    "self": "https://learningmanagerstage1.adobe.com/primeapi/v2/recommendations?page[offset]=0&page[limit]=10&strip=1&filter.recType=announcement&filter.loTypes=course"
  },
  "data": [
    {
      "id": "course:5836866_10855885_recommendation",
      "type": "recommendation",
      "attributes": {
        "reason": [
          "Based on your Group - UGforAnnouncement"
        ],
        "reasonModel": [
          {
            "modelId": 1781592,
            "modelType": "userGroup",
            "modelValues": {
              "group_name": "UGforAnnouncement"
            },
            "template": "Based on your Group - {{group_name}}"
          }
        ]
      },
      "relationships": {
        "learningObject": {
          "data": {
            "id": "course:5836866",
            "type": "learningObject"
          }
        }
      }
    },
    {
      "id": "course:7013328_10855885_recommendation",
      "type": "recommendation",
      "attributes": {
        "reason": [
          "Based on your Group - All Learners"
        ],
        "reasonModel": [
          {
            "modelId": 1410724,
            "modelType": "userGroup",
            "modelValues": {
              "group_name": "All Learners"
            },
            "template": "Based on your Group - {{group_name}}"
          }
        ]
      },
      "relationships": {
        "learningObject": {
          "data": {
            "id": "course:7013328",
            "type": "learningObject"
          }
        }
      }
    },
    {
      "id": "course:6408989_10855885_recommendation",
      "type": "recommendation",
      "attributes": {},
      "relationships": {
        "learningObject": {
          "data": {
            "id": "course:6408989",
            "type": "learningObject"
          }
        }
      }
    },
    {
      "id": "course:6409761_10855885_recommendation",
      "type": "recommendation",
      "attributes": {},
      "relationships": {
        "learningObject": {
          "data": {
            "id": "course:6409761",
            "type": "learningObject"
          }
        }
      }
    },
    {
      "id": "course:6979586_10855885_recommendation",
      "type": "recommendation",
      "attributes": {},
      "relationships": {
        "learningObject": {
          "data": {
            "id": "course:6979586",
            "type": "learningObject"
          }
        }
      }
    }
  ]
}
```

## 发行说明

如需了解Learning Manager网页版应用程序和设备应用程序的当前和往期版本，请参阅 [发行说明](/help/migrated/release-note/release-notes.md).

## 错误修复

如要查看本次更新中修复的错误，请参阅 [修复的错误列表](release-note/release-notes.md#bugs-fixed-in-this-release).

## 系统要求

[Learning Manager系统要求](/help/migrated/system-requirements.md)
