---
description: ALM中的API更改
jcr-language: en_us
title: 4月版中的API更改
source-git-commit: 3b35c16d74c83329cee24ee9ad007a53ccbd8cf3
workflow-type: tm+mt
source-wordcount: '4093'
ht-degree: 0%

---


# 2026年4月版中的API更改

2026年4月版Adobe Learning Manager引入了针对以下内容的公共API的增强功能：替代项和对等项、对内容的时间窗口访问、内容驱动的测试尝试、未登录体验和工作辅助处理。 这些更改旨在实现大致向后兼容，同时实现更精确的集成。

## 学习路径的自适应学习

此版本为自适应学习路径添加了完全的公共API支持。 学习路径(LP)现在可以定义自适应规则，控制哪些部分和子学习对象（子LO）对不同的学习者组可见，且公共API可反映此行为。

以下端点会受到影响：

- GET/primeapi/v2/learningObjects？filter.loTypes=learningPath
- GET/primeapi/v2/learningObjects/{loId}

新的布尔型属性attributes.isAdaptive表示学习程序使用自适应规则。 当此标志为true时，将自适应地解释sections属性。

对于学习者调用，仅返回对当前学习者可见的部分。 每个部分包括学习对象ID(loId)的列表、强制标志和基于该学习者的自适应配置计算的强制LOCount以及sectionId。 relationship.subLOs关系现在也已过滤，因此它仅包含该学习者可见的子学习对象。

对于管理员调用，节还可显示adaptiveConfig阵列。 这将说明每个用户组的自适应规则，包括userGroupId、userGroupName以及该部分对于该组是否是必需的。 面向管理员的工具可使用此功能可视化和管理自适应规则。

重置学习计划的完成情况

此版本引入了用于为学习对象（包括自适应学习计划）__刷新（重置）完成__&#x200B;的API。 这支持再培训、定期合规性更新或计划重新启动等场景。

有新的端点可用：

```
POST /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/refreshCompletion
```

此操作需要适当的写入权限，并会重置给定用户上下文中指定学习对象实例的完成状态。 适用于管理员端自动操作或范围有限的学习者工具。

该功能的批量版本是通过作业API计划的。 请求形状旨在通过电子邮件、用户ID或用户组ID将用户作为目标，例如：

```
{  
  "emails": ["[user1@example.com](mailto:user1@example.com)", "[user2@example.com](mailto:user2@example.com)"],  
  "userIds": ["12345", "67890"],  
  "userGroupIds": ["ug1", "ug2"]  
}  
```

当集成需要重新启动每个计划或课程中的学习者时，应使用此API。 客户端必须优雅地处理错误响应： API可能会拒绝刷新请求，其中重置不适用（例如，不存在完成或不支持的学习对象类型时）。

## 对等项和替代完成

为了支持多个学习对象可以满足相同要求的实施，该版本引入了等效项和替代完成作为公共API。

学习对象端点现在包含以下信息：

```
- GET /primeapi/v2/learningObjects
- GET /primeapi/v2/learningObjects/{loId}
```

新的布尔型属性attributes.isAlternateComplete指示学习者完成给定学习对象是否是替代或等效学习对象的结果，而不是对象本身。 如果为true，则relationship.alternateCompletions关系会列出充当替代项的学习对象。 这允许下游报告和控制面板区分直接完成和替代完成，并显示哪个替代完成了该要求。

此外，通过相关学习对象视图，可以发现能够满足学习对象的潜在替代项。 这通过以下方式显示：

```
GET /primeapi/v2/learningObjects/{loId}/relatedLOs?type=sourceAlternateLOs&limit={n}
```

此响应返回可充当替代的学习对象，并且包含一个meta.count字段，该字段指示此类替代的总数（与当前限制无关）。 集成可以使用此信息来显示推荐的等效项，或构建替代映射的管理视图。

## 报告和分析用例

生成报告或分析的用户应更新其逻辑，以将isAlternateComplete和alternateCompletions添加到其报告工作流中。

使用完成数据的报告集成（例如，LT导出、自定义数据仓库源或BI仪表板）应扩展其逻辑，以读取并保留学习对象API的isAlternateComplete和relationship.alternateCompletions属性：

- 当isAlternateComplete==false时：\
  将记录视为学习对象的&#x200B;__直接完成__，与今天相同。
- 当isAlternateComplete为true==：
   - 在报表中将记录标记为&#x200B;__备用完成__（例如，值为DIRECT与ALTERNATE的“Completion Method”列）。
   - 使用relationships.alternateCompletions.data[*].id捕获&#x200B;__哪个源学习对象__&#x200B;已授予此完成权限（例如，“课程B已通过备用课程A完成”）。

典型用例：

- _合规性报告_ — 显示合规性课程是通过已批准的等效课程完成的，并列出符合要求的源课程。
- _计划进度仪表板_ — 将直接完成路径&#x200B;_的学习者_&#x200B;与通过替代满足路径的学习者区分开来，以便获得更准确的进度和修正视图。
- _审核记录_ — 对于任何标记为isAlternateComplete=true的学习对象，审核者可以确切地看到使用了哪些替代培训授予该完成。

如果不合并这两个字段，下游报告会将替代完成视为常规完成，并且&#x200B;_无法解释_*为什么*&#x200B;学习者显示为已完成他们从未直接参加的培训。

## 学习者与管理员学习对象API行为

学习者和管理员学习对象API的多语言工作辅助结构相同。 学习者范围仅返回对学习者可见的这些工作辅助，但对于每个可见的工作辅助，它通过多个资源实体（每个区域设置一个）和多区域设置本地化元数据显示所有已配置的区域设置。 管理员范围返回管理员可以管理的所有工作辅助，并具有相同的学习对象模型和区域设置特定的资源ID。 具有学习者范围的客户端应选择attributes.locale最匹配学习者内容语言的资源，而管理员工具可枚举用于报告和管理的所有区域设置。

## 具有注释功能的清单

为了支持审阅者可以共享有关基于清单的活动结构化反馈的工作流程，此版本通过学习对象资源API提供了&#x200B;*清单注释*&#x200B;和审阅者可见性控件。

与清单相关的元数据显示在learningObjectResource实体(JApiLOResource，“type”：“learningObjectResource”)上，这些实体表示课程或其他学习对象中的清单资源。

该信息可通过以下方式获得：

```
GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources
```

当学习对象实例包含清单类型资源时，所包含数组中相应的learningObjectResource条目会在属性下显示注释和审阅者可见性属性，并在关系下显示审阅者身份。

### 新的清单注释属性

对于清单资源，learningObjectResource上可能存在以下属性：

- attributes.checklistComment\
  审阅者为学习者留下的自由文本注释，例如：\
  &quot;checklistComment&quot;： &quot;性能卓越！ 所有安全协议都得到正确遵守。”\
  仅当满足以下条件时&#x200B;_才填充此属性：_
   - showChecklistComment为true，并且
   - 清单配置已启用enable_reviewer_remarks。
- attributes.showChecklistComment\
  指示是否应向学习者显示审阅者注释的布尔标志：\
  &quot;showChecklistComment&quot;： true\
  仅当在清单配置中启用了&#x200B;_enable_ reviewer_remarks时，_才存在此属性。\
  客户端应使用此标志决定是否要在学习者体验中呈现checklistComment。
- attributes.showReviewerNameToLearner\
  用于控制学习者是否应查看审阅者身份的布尔标志：\
  &quot;showReviewerNameToLearner&quot;： true\
  为true时，客户端可以使用checklistReviewedBy关系（请参阅下文）解析并显示审阅者的姓名（例如，通过用户查找API）。

其他清单特定的上下文（例如checklistEvaluationStatus、isChecklistMandatory、resourceSubType：“CHECKLIST”和submissionDate）也可在同一learningObjectResource上使用，以支持更丰富的清单UI和报告。

### 审阅者身份关系

当需要显示审阅者姓名时，learningObjectResource包含指向审阅者用户的关系：

```
"relationships": {
  "checklistReviewedBy": {
    "data": {
      "id": "user_id",
      "type": "user"
    }
  }
}
```

仅当满足以下条件时&#x200B;_才填充此关系：_

- showReviewerNameToLearner为true，且
- checklistReviewedBy不为null（即，清单已审阅）。

客户端应用程序应：

1. 检查attributes.showReviewerNameToLearner。
2. 如果为true且存在relationship.checklistReviewedBy.data，请调用相应的用户API将“id”：“user_id”解析为显示名称。
3. 根据需要，将审阅者姓名显示在清单注释或状态旁边。

### 访问清单资源和注释

要检索给定学习对象的清单资源及其注释，客户应执行以下操作：

- 通话

```
GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources
```

- 在回复中：
   - 使用主learningObject中的relationship.instances查找所包括的相关learningObjectInstance条目。
   - 在每个learningObjectInstance中，遵循relationships.loResources查找learningObjectResource条目。
   - 在以下位置过滤learningObjectResource条目：
      - attributes.resourceSubType == &quot;CHECKLIST&quot;（针对清单资源），以及
      - （可选）attributes.showChecklistComment==true以查找包含学习者可见注释的核对清单。

- 对于每个清单learningObjectResource，请使用：
   - attributes.checklistComment（如果存在，并且showChecklistComment为true）
   - attributes.checklistEvaluationStatus（例如，“PASSED”）
   - attributes.showReviewerNameToLearner
   - relationship.checklistReviewedBy（如果存在）以确定审阅者。

此模式允许无头或自定义客户端直接从Prime API呈现全面的清单体验，包括状态、必填/可选标记和审阅者反馈。

### 报告和UX注意事项

- _报告和分析_
可合并在核对清单上跟踪学习者绩效的集成：
   - 通过/失败或其他状态指示符的checklistEvaluationStatus。
   - isChecklist必须区分必要和可选清单活动。
   - 反馈范围审计中是否存在checklistComment和showChecklistComment。
- _学习者体验_
UI实现应：
   - 在显示注释之前，请尊重showChecklistComment。
   - 使用showReviewerNameToLearner和checklistReviewedBy确定是显示审阅者的姓名，还是保持审阅的匿名状态。
   - 当评论被禁用或不存在，但仍显示评估状态和提交信息时，可顺畅地返回。

## 工作辅助的多语言支持

为了支持必须以多种语言向学习者和管理员提供工作辅助的实施，此版本扩展了工作辅助处理，以对每个区域设置返回&#x200B;*一个资源*，而不是返回单个硬编码的en-US资源。

多语言工作辅助将继续使用现有的层次结构：

_学习对象_ (lo) → _学习对象资源_ (loResource) → _资源_

无需对API合同进行任何更改。 任何本地化的工作辅助都自然地适合此结构，每个区域设置使用不同的资源实体，并在learningObject/learningObjectResource级别共享本地化的元数据。

工作辅助数据通过以下方式显示：

```
GET /primeapi/v2/learningObjects/jobAid:{jobAidId}?include=instances.loResources.resources
```

当工作辅助具有多个语言变体时，包含的数组将包含多个“类型”：“资源”条目 — 每个区域设置一个条目（例如，en-US、fr-FR、es-ES），所有条目均通过单个learningObjectResource链接。

### 多语言工作辅助结构

多语言工作辅助使用：

- _learningObject （类型：learningObject）_
   - 包含具有多个条目（例如en-US、fr-FR）的本地化元数据，以便客户端能以适当的语言显示工作辅助标题/描述。
- _learningObjectInstance （类型： learningObjectInstance）_
   - 通过relationship.loResources引用一个或多个learningObjectResource条目。
- _learningObjectResource（类型：learningObjectResource）_
   - 保留常用配置（内容类型、版本等） 以及多区域设置、本地化的元数据。
   - 通过relationship.resources链接到一个或多个资源实体。
- _资源（类型：资源）_
   - *每个区域设置*&#x200B;一个，每个区域设置都有自己的ID、区域设置、名称和URL（位置/下载URL）。

对于多语言工作辅助，典型的模式是：

- learningObjectResource，包含适用于en-US和fr-FR的localizedMetadata
- relationships.resources.data指向：
   - 区域设置的资源： &quot;en-US&quot;
   - 区域设置的资源： &quot;fr-FR&quot;

客户端可以通过将学习者的区域设置与resource.attributes.locale字段匹配来选择适当的资源。

### 工作辅助的新资源ID格式

为了正确区分工作辅助资源的多个本地化变体，_资源ID格式已更改_。

_旧（旧版）资源ID格式_

以前，工作辅助资源使用不透明的ID格式，例如：

jobAid:131032_-1_-1_2_resource

此格式未对区域设置进行编码，因此API实际上只会公开单个资源（通常是en-US）。

_新资源ID格式（多语言识别）_

新格式为：

```
jobAid:<jobAidId>_<version>_<localeCode>
```

示例：

- jobAid:131032_2_en-US
- jobAid:131032_2_fr_FR
- jobAid:131032_2_es_ES

视觉细分：

```
jobAid:131032_2_fr_FR

        │      │ │ │

        │      │ │ └──► Locale Code (fr_FR, en_US, es_ES, etc.)

        │      │ └────► Version (2)

        │      └──────► JobAid ID (131032)

        └─────────────► Resource Type Prefix ("jobAid:")
```

此结构允许客户端：

- 快速确定资源所属的工作辅助和版本。
- 需要时，直接从资源ID推断区域设置。

### 向后兼容性： 

```/resources/{resourceId}```

旧版资源端点仍然可用：

```GET /primeapi/v2/resources/{resourceId}

```

它现在&#x200B;_向后兼容_，同时具有新ID和旧ID格式：

- _旧ID格式_（例如，jobAid:131032_-1_-1_2_resource）
   - 继续工作。
   - 返回与该旧标识符（通常是原始en-US资源）关联的&#x200B;_首次创建的资源_。
- _新ID格式_（例如，jobAid:131032_2_fr_FR）
   - 返回与该ID对应的&#x200B;_精确的特定于区域设置的资源_。
   - 这允许精确检索和操纵本地化的工作辅助变体。

当前存储或引用旧资源ID的集成可以继续运行而不会发生更改，同时建议较新的实现采用新的ID格式进行特定于区域设置的操作。

### 集成和UX注意事项

- _学习者/管理员UI_
   - 使用learningObject.localizedMetadata和learningObjectResource.localizedMetadata以相应的语言显示标题和说明。
   - 使用resource.attributes.locale为学习者区域设置选择正确的URL（位置/下载网址）。
   - 如果学习者的精确区域设置不可用，请实施回退行为（例如，回退到美国英语）。
- _API和存储_
   - 对于新集成，请存储&#x200B;_新格式的资源ID_ (```jobAid:<jobAidId>_<version>_<localeCode>```)以启用明确的特定于区域设置的检索。
   - 旧版ID仍可与/resources/{resourceId}一起使用，但它们无法区分区域设置。

## 启动模块的时隙限制

某些学习体验必须仅在规定的时间范围内可用。 此版本显示有关学习对象资源的时段信息，并引入了一个验证端点，用于检查学习者是否可以在当前时间启动资源。

通过终结点提供时隙元数据：

```GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources```

在学习对象资源级别，timeSlot对象现在可能存在于属性中，startTime和endTime值以UTC表示。 此选项指定启动资源的时间。

在启动模块之前，集成可以调用新的验证终结点：

```GET /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/loResources/{loResourceId}/canStart```

此端点适用于学习者阅读场景，根据配置的时隙、交付类型和其他后端规则，返回当前是否允许学习者启动资源。

自定义播放器和客户端应用程序应使用canStart强制执行基于时间的访问，并使用timeSlot元数据显示有关内容何时可用或何时过期的明确消息。 应明确处理来自canStart的负面响应，以告知学习者内容为何暂时无法启动或无法再启动。

## 多次尝试、内容驱动测验

某些内容包会实施其自己的尝试跟踪，而不是仅依赖Adobe Learning Manager。 此版本引入了一个标记，指示何时由内容本身驱动尝试进行。

通过：

```GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources```

学习对象资源现在可能公开布尔属性hasContentDrivenAttemptTracking。 如果为True，则测试或模块在内部管理尝试（例如，通过SCORM或xAPI逻辑），平台的标准尝试计数器可能无法完全反映学习者的体验。

显示尝试计数或控制重试行为的集成应检查此标志。 启用后，他们不应仅从平台元数据推断尝试限制，并应准备好依赖内容端报告（例如，通过xAPI语句）或业务特定的规则。

## 工作辅助资源ID格式中的行为更改

此版本以工作辅助资源ID的格式引入了一个重要的&#x200B;__行为更改__。 虽然不涉及新端点，但这会对存储或解析这些ID的系统产生直接影响。

以前，工作辅助资源ID使用的格式如下：

```jobAid:<jobAidId>_-1_-1_2_resource```

在2026年4月版中，此格式被简化且更明确的格式取代：

```jobAid:<jobAidId>_<version>_<localeCode>```

例如：

jobAid:131032_2_fr_FR

这些组件包括：

- ```<jobAidId>```：数字工作辅助ID（例如，131032），
- ```<version>```：工作辅助的版本号（例如，2），
- ```<localeCode>```：区域设置代码（例如，en_US、fr_FR、es_ES）。

为资源编制索引或保留在工作辅助资源ID中的任何集成必须更新其分析和存储逻辑以识别新格式。 由于标识符本身发生变化，强烈建议您在升级到2026年4月版后重新构建由工作辅助资源ID键入的任何本地索引。

## 通过迁移设置课程横幅图像

现在，您可以作为标准迁移工作流程的一部分，在Adobe Learning Manager中设置或更新课程横幅图像。 这可以帮助您启动或清理大型目录，同时保持课程页面的视觉一致性，而无需手动编辑

### 定义横幅图像的位置

在&#x200B;_course.csv_&#x200B;迁移文件中配置了横幅图像，您已经使用该图像提供课程元数据，例如：

- ID
- courseName
- courseCreationDate
- 或
- 作者
- thumbnailUrl

通过此增强功能，course.csv规范为课程横幅图像额外添加了&#x200B;_可选列_。 从Learning Manager帐户下载的CSV规范中定义了准确的标头名称（例如，它可能显示为bannerUrl或bannerImageUrl）。

横幅列：

- 指向要用作&#x200B;_课程横幅_&#x200B;的图像文件。
- 工作方式与thumbnailUrl相同，即使用已配置内容存储库(Box/FTP)中的可用图像。

### 准备迁移的横幅图像

1. 上传横幅图像：遵循现有的目录结构，将横幅图像文件放在与其他迁移资源相同的Box或FTP位置。
2. 检查文件格式：
使用一种支持的图像格式（例如png、jpg、jpeg、gif），如系统要求中所述：
   1. [*系统要求*](/help/migrated/system-requirements.md)
3. 更新course.csv：在新的横幅列中，引用横幅图像的相对路径或标识符。 一个概念性示例：

```
id,courseName,courseCreationDate,state,author,thumbnailUrl,bannerUrl  
12345,DEMO1,2018-05-05T08:56:21.000Z,Published,Sudheer,pic1.png,banners/banner1.png  
45678,DEMO2,2018-05-05T08:56:21.000Z,Published,Sudheer,pic2.png,banners/banner2.png  
```

### 在迁移运行期间应用横幅

更新course.csv后，该流程与任何其他迁移相同：

1. _上传CSV_
将更新后的course.csv（以及任何其他相关文件）上传到为迁移配置的Box/FTP文件夹。 文件名必须与csv_specifications.zip中指定的名称完全匹配（区分大小写）。
2. _启动Sprint运行_
在Adobe Learning Manager中，作为集成管理员，开始迁移包含course.csv的_sprint运行_。\
   迁移引擎会读取横幅列并将横幅图像应用于每个课程。
3. _查看结果和错误日志_
Sprint之后：
   1. 验证&#x200B;_作者_&#x200B;和&#x200B;_学习者_&#x200B;应用程序中的横幅。
   2. 如果某些行失败（例如，由于文件路径无效或格式不受支持），请从迁移运行中下载错误CSV并更正数据。

### 新课程与现有课程

横幅字段适用于两种情况：

- _通过迁移创建的新课程_
首次从course.csv创建课程并填充横幅列后，系统会立即设置该横幅。
- _现有课程（改良/更正）_
如果使用相同的课程ID和新的横幅值重新运行迁移：
   - Learning Manager会找到现有课程。
   - 横幅图像已&#x200B;_更新_&#x200B;为CSV中指定的新图像。

实际列名称和路径必须与&#x200B;_下载的CSV规范_&#x200B;和内容存储库布局匹配。

## 删除LearningProgramCourse中的顺序列

Adobe Learning Manager现在支持在迁移期间使用&#x200B;_学习路径（学习计划）_&#x200B;中课程订购的简化模型。 作为此更改的一部分，将从learning _program_ course.csv迁移文件中删除_顺序列_。

之前，learning_program_course.csv文件包含了一列（通常称为“顺序”或“类似”），用于：

- 根据学习计划中每个课程列中的数值，明确设置该课程的&#x200B;_位置_。
- 需要管理员或脚本手动维护此数字序列，尤其是在插入或重新排序课程时。

现在，Adobe Learning Manager不再使用learning_program_course.csv中的顺序列来确定课程顺序。 相反，迁移CSV侧重于&#x200B;_哪些课程属于哪个学习计划_，而不是如何按数字排序。

## 对迁移CSV的影响

### learning_program_course.csv

您应将旧版订单列视为已移除或已忽略：

- 在迁移期间，不要依靠顺序控制学习计划中的课程顺序。
- 如果您仍有旧版模板中的订单列：
   - Learning Manager在排序时会忽略该字段。
   - 您可以随着时间的推移将其从CSV中安全地删除，以简化迁移文件。
- 所需的核心映射仍然是：
   - 学习计划ID↔课程ID（以及任何其他仍记载的列，如ID、learningProgramId、courseId和日期）。

请始终从您的Learning Manager帐户中参考最新的&#x200B;[_CSV规范_](https://experienceleague.adobe.com/zh-hans/docs/learning-manager/using/integration/migration-manual)（通过csv_specifications.zip），以确认当前的标题集和要求。

## 课程实例上的时区代码

从此版本开始，课程实例模型(learningObjectInstance)将显示一个新属性：

timeZoneCode — 一个字符串字段，用于将课程实例显式链接到帐户配置的时区之一。

这允许客户端：

- 以一致的API驱动方式解析课程实例的时区。
- 正确解释并显示该实例的所有实例级别日期/时间，而不考虑用户自己的时区。

### 显示时区代码的位置

该字段将添加到learningObjectInstance模型的属性中
仅限课程实例。

示例：

```
{
  "id": "course:1262748_1359228",
  "type": "learningObjectInstance",
  "attributes": {
    "dateCreated": "2019-08-06T13:50:39.000Z",
    "isAET": false,
    "isDefault": true,
    "timeZoneCode": "356",
    "isFlexible": false,
    "state": "Active",
    "localizedMetadata": [
      {
        "locale": "en-US",
        "name": "Default instance"
      }
    ]
  }
}
```

### 如何解析timeZoneCode

数值timeZoneCode是帐户时区目录的查找密钥，可通过帐户API公开：

```http
GET /primeapi/v2/account
Authorization: Bearer <access_token>
```

响应中列出了时区：

```
"data": {
  "attributes": {
    "timeZones": [
      {
        "name": "Etc/GMT+12",
        "timeZoneCode": "356",
        "utcOffset": -720,
        "utcOffsetCode": "UTC-12:00(Etc/GMT+12)",
        "zoneId": "Etc/GMT+12"
      },
      "..."
    ]
  }
}
```

### 建议的客户端流：

1. 调用GET/account一次，缓存租户的attributes.timeZones。
2. 对于每个课程实例：
   - 读取attributes.timeZoneCode。
   - 在timeZoneCode匹配的时区中查找相应的条目。
   - 使用该条目的zoneId、utcOffset和utcOffsetCode来显示和调度逻辑。

## 用户组成员资格的异步公共API

### 简介

Adobe Learning Manager公开两个&#x200B;_管理异步API_&#x200B;以管理用户组(UG)成员资格：

- POST/async/userGroups/{userGroupId}/users — 将用户异步添加到UG
- DELETE/async/userGroups/{userGroupId}/users — 从UG异步删除用户

这些API接受您的批处理并返回&#x200B;_事件ID_，而不是在同一请求中更新成员资格。 实际结果稍后通过Webhook传递。

在以下情况下使用它们：

- 您管理的是大型组或频繁的批量更新。
- 延迟的重要性低于可靠性和吞吐量。
- 您构建的是集成(HR、CRM、LXP)，而不是单击UI。

对于小型交互式管理员操作，您可以继续使用同步`/userGroups/{id}/users` API。

### 身份验证和基本URL

这些API是标准&#x200B;__v2管理API__&#x200B;表面的一部分。

- [基本URL （生产）](https://learningmanager.adobe.com/docs/primeapi/v2/)
- 身份验证：作用域为`admin:write`的OAuth 2.0访问令牌
- 必需的标头：
   - 授权：持有人&lt;access_token>
   - 内容类型：application/json
   - 接受：application/json

有关常规管理员API行为和范围，请参阅：

- [开发人员手册](/help/migrated/integration-admin/feature-summary/developer-manual.md)
- [API参考指南](https://learningmanager.adobe.com/docs/primeapi/v2/)

### 请求格式

__添加__&#x200B;和&#x200B;__移除__&#x200B;使用完全相同的身体形状。

#### 主体

```
{
  "metadata": {
    "event_id": "my-optional-correlation-id",
    "sourceSystem": "HRIS",
    "batchId": "hr_2026_03_30_0001"
  },
  "data": [
    { "type": "user", "id": "11101219" },
    { "type": "user", "id": "11101220" }
  ]
}
```

#### 数据（必填）

data是此批的用户资源标识符列表。

- `type`必须是“用户”。
- `id`是ALM中的&#x200B;_数字用户ID_（不是电子邮件，不是UUID）。

#### 约束

- `data`必须存在且非空。
- 至少需要一个用户。
- 每个请求的最大负载大小为20个用户。
- 所有ID都必须是数字，且必须引用有效用户。

如果上述任一情况失败，则API会返回错误，并且没有排队内容。

#### 元数据（可选）

`metadata`是您想要在Webhook中回显的任何其他相关数据。

典型用法：

- `event_id` — 生成的相关ID。
- `sourceSystem` — 上游系统的名称。
- `batchId` — 批处理或作业标识符。

该服务在Webhook响应中返回未更改的此对象，以使回调与内部作业相匹配。

约束：

- 可选；可以完全省略。
- 所有键和值的组合长度不得超过1000个字符。

### 响应格式

两个端点都使用事件ID同步响应：

```
{ "event_id": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5" }
```

行为：

- 如果传递`metadata.event_id`，则使用该值。
- 否则，服务会生成一个UUID。

您应始终：

- 将此`event_id`存储为批的主标识符。
- 预计在Webhook回调中收到相同的值。

查看[用于添加和删除用户组成员资格的Webhook](/help/migrated/integration-admin/feature-summary/webhooks.md#webhooks-for-adding-and-removing-user-group-membership)，了解更多详情。

## 常见问题解答

_2026年4月版如何更改自适应学习计划的learningObjects API？_

此版本在学习计划上添加了一个isAdaptive标志，并允许章节和子学习对象了解学习者。 在自适应程序中，学习者仅能看到基于自适应规则对他们可见的部分和子学习对象，而管理员能看到用户组的基础自适应配置。

_如果集成假设始终返回所有节和子学习对象，我是否需要更新集成？_

是。 对于自适应学习计划，API现在仅返回对当前学习者可见的章节和子学习对象。 客户端代码应将响应视为权威的（可能是经过筛选的）视图，而不是采用完整的列表。

_如何以编程方式重置学习者完成课程或学习计划的情况？_

使用新端点：

```POST /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/refreshCompletion```
当权限和状态允许时，这将重置目标实例的完成情况。

_如何判断学习者是否通过替代或等效的学习对象完成了某些工作？_

检查学习对象的isAlternateComplete属性。 如果为true，则alternateCompletions关系列出作为该学习者完成的替代项的学习对象。

_如何查找所有能够满足特定学习对象的替代字？_

使用以下端点：

```GET /primeapi/v2/learningObjects/{loId}/relatedLOs?type=sourceAlternateLOs&limit={n}```

并使用数据数组（用于替代）和meta.count （用于替代的总数）。

_如何确定此时是否允许学习者启动模块？_

首先，从以下位置获取资源的timeSlot：

```GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources```
然后使用：

```GET /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/loResources/{loResourceId}/canStart```

_hasContentDrivenAttemptTracking对资源意味着什么？_

它表示尝试跟踪由内容本身控制（例如，通过SCORM/xAPI逻辑），而不是仅由平台计数器控制。 如果情况属实，请不要仅依赖平台尝试次数或您的UX和报告限制。

_如何获取适用于未登录用户（公共体验）的菜单？_

使用：

```GET /primeapi/v2/templates/menus?include=pages,subMenus.pages&isNonLoggedIn=true```

这将返回为匿名用户过滤的菜单和页面结构，适用于Experience Builder或其他无头站点。

_使用effectiveModifiedDate筛选工作辅助时发生了什么变化？_

将filter.effectiveModifiedDate与filter.loTypes=jobAid相结合的请求现在仅可正确返回指定日期范围内的工作辅助。

_工作辅助资源ID格式发生了什么变化，我应该如何处理？_

ID格式已从如下值更改：

```jobAid:<jobAidId>_-1_-1_2_resource```

收件人：

```jobAid:<jobAidId>_<version>_<localeCode>```

例如jobAid:131032_2_fr_FR。 必须更新任何存储或分析工作辅助资源ID的系统，在升级到2026年4月版后，您应计划重建由这些ID键控的本地索引。
