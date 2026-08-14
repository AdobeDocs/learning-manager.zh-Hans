---
description: 了解Adobe Learning Manager 2026年8月版的新增功能和增强功能
jcr-language: en_us
title: Adobe Learning Manager 2026年8月版的新增功能
exl-id: da46f186-3ff3-422a-af49-31c7405fd584
source-git-commit: f5a988186fdc44d64389ad850af57bde10b728e9
workflow-type: tm+mt
source-wordcount: '2647'
ht-degree: 0%

---

# Adobe Learning Manager 2026年8月版中的新增功能

## 成绩册

Adobe Learning Manager中的分数簿为课程添加加权分数，允许作者为每个分数模块分配贡献百分比，并设置课程完成的最低总分数。 学习者可以在整个课程中跟踪自己的成绩，管理员可以查看最终分数并下载相关成绩单。

### gradebook的功能

启用评分书的课程会根据分配给各模块的权重百分比，结合各个模块的分数，从而计算每个学习者的最终分数。 这样可提供精确的加权绩效衡量标准，而不是简单的得分总和或仅基于完成度的通过/失败标记。

Gradebook支持两种完成模型：

* **仅限必修模块**：所有必修模块完成后，课程即告完成。 Gradebook分数仍会被计算并显示，但汇总分数不会有助于通过标准。

* **必需模块加上汇总分数**：学习者必须同时完成所有必需模块，并达到汇总分数等于或高于最低通过阈值。 要达到及格水平，必须同时满足这两个条件。

### 课程分数的计算方式

对于每个可评分模块，对课程总分的贡献为：

（得分÷最高得分）×重量% =模块贡献

课程总分是所有模块评分的总和。 所有可评分模块的权重百分比加起来必须正好是100。 在满足此条件之前，无法保存gradebook配置。

课程总分是所有模块评分的总和。 所有可评分模块的权重百分比加起来必须正好是100。 在满足此条件之前，无法保存gradebook配置。

各模块之间的评分等级不需要一致。 一次课堂课程得分为100，一个SCORM模块得分为10，可以在同一个Gradebook中共存。 公式在应用权重之前将每个贡献规范化。

**可评分和不可评分的模块**

只有生成分数的模块才有资格获得权重。 可评分模块类型包括：

* 启用了评分的SCORM、AICC和xAPI内容
* Captivate内容包
* Adobe Learning Manager中的原生测验
* 讲师或管理员输入分数的教室和虚拟教室会话
* 讲师或管理员评分的活动模块

不可评分的模块类型、PDF文件、视频文件、音频文件、PowerPoint演示文稿、Word文档、Excel文件和HTML内容，不能分配权重百分比，也不影响总分数。 完成课程可能仍需要这些模块。 启用“包含不参与最终分级的模块”选项后，这些模块将显示在成绩簿中，且没有权重值。

了解有关[作者的Gradebook](/help/migrated/authors/feature-summary/alm-author-gradebook.md)的更多信息。

## 分层内容文件夹

内容库现在最多支持三个级别的专用文件夹层次结构。 管理员创建文件夹结构并控制哪些自定义角色可以访问哪些1级文件夹。 访问会自动级联到1级文件夹中的所有子文件夹。

作者可以在文件夹之间复制和移动内容，按文件夹筛选内容库，并在向课程添加模块时浏览层次结构。

关键功能：

* 最多三个嵌套级别（每个父级最多25个子文件夹）
* 仅在1级分配基于角色的访问权限
* 内容可以出现在多个文件夹中，而不会重复
* 公用文件夹和专用文件夹结构互斥
* 在课程创作中选择模块时浏览文件夹体验

详细了解[分层内容文件夹 — 管理员级功能](/help/migrated/administrators/feature-summary/settings/advanced-settings.md#content-folder)。 详细了解[分层内容文件夹 — 作者级功能](/help/migrated/authors/feature-summary/content-library.md#add-content-to-a-folder)。

如果要将学习内容从其他平台迁移到Adobe Learning Manager并保留现有文件夹组织，可使用CSV文件创建分层文件夹结构并将内容文件与适当的文件夹关联。 详细了解[迁移内容文件夹层次结构](/help/migrated/integration-admin/feature-summary/migration-manual.md#migratecontentfolderhierarchy)中的迁移。

## Live Hub (Beta)

Live Hub是Adobe Learning Manager中由AI提供支持的虚拟培训体验，可帮助组织提供引人入胜且有影响力的实时学习。 Live Hub具有AI驱动的意见调查、分组讨论室协调、持久学习空间和AI驱动的协助等智能功能，可提高讲师的工作效率，同时降低会话交付的复杂性。

主要亮点：

* 利用原生Adobe Learning Manager体验提升实时学习能力，从而提高教学质量和学习者成果。
* 为您的讲师提供由AI提供支持的共同促进者，通过智能投票、问答支持和突破室见解来促进参与。
* 使用AI生成的摘要和按主题搜索的会话记录，帮助您的学习者从每个会话中获得更多内容。
* 衡量参与度分析的重要性，该分析不仅限于出勤率，还能揭示真正的学习参与度。
* 协助作者使用AI技术支持的讲师查找器，按技能、可用性、首选时间、时区以及当前利用率匹配合适的讲师。

详细了解[开始使用Live Hub](./getting-started-with-live-hub/getting-started-live-hub.md)。

## Adobe Learning Manager Content Composer (Beta)

Adobe Learning Manager现在包括Content Composer，这是一种AI本机课程创作工具，可在几分钟内将您从普通语言提示提升为结构化、可发布的课程。

主要功能：

* 对话AI可指导作者完成培训目标、源资料和学习目标，从而生成完整的课程简介和概述。
* 基于文档的生成功能将AI输出限制为上传的文件，这对于合规性、法规和基于过程的培训至关重要。
* 一门课程即可生成完整的课程，如课程、主题、文本、图像、知识检查以及分级测验。
* 具有浅色和深色模式、字体控件、页眉和页脚支持以及JSON导出功能的视觉主题系统，可帮助实现高级自定义。
* 发布前可配置的完成标准、成功标准、测验设置和SCORM版本。
* 等等。

了解有关[Adobe Learning Manager Content Composer](/help/migrated/authors/feature-summary/content-composer/content-composer-help.md)的更多信息。


## 基于组件的电子邮件模板生成器

组织现在可以使用现代的WYSIWYG组件编辑器在Adobe Learning Manager中创建企业级品牌化电子邮件通知。 管理员可以使用可重复使用的页眉、页脚和品牌元素一次性构建全局布局，并将其应用于帐户级别的所有电子邮件模板。 然后，可以在课程或实例级别自定义各个模板，默认情况下继承父版面，仅在需要时覆盖父版面。

关键功能：

* 具有可重用组件（文本、图像、按钮、分隔符、页眉、页脚）库的WYSIWYG编辑器
* 变量支持：插入动态字段，例如学习者姓名、课程名称和截止日期
* 链接模板和未链接的模板层次结构：对链接模板的更改会传播到所有子模板；未链接的模板可以单独编辑
* 多语言模板支持
* 发布前预览并测试发送
* 向后兼容性：现有电子邮件模板继续工作

详细了解[基于组件的电子邮件生成器](/help/migrated/administrators/feature-summary/email-builder.md)。

## 外部学习支持

学习者现在可以直接从学习者信息板提交平台外培训（如认证、研讨会、会议和外部课程），以供经理审批。 获批提交内容会显示在学习者成绩单中。

关键功能：

* 包含标准和自定义字段的可配置提交表单
* 具有评论支持功能的经理审阅和批准工作流程
* 获批提交内容会显示在包含完整元数据的学习者成绩单中
* 管理员可以配置必填字段，包括自定义字段
* 管理员和学习者成绩单中的新列：外部学习名称、完成注释、自定义字段列
* API支持：五个新的学习者范围端点，用于创建、检索和更新提交内容

了解有关[外部学习支持 — 管理员级功能](/help/migrated/administrators/feature-summary/settings/basic-settings.md)的更多信息。 了解有关[外部学习支持 — 经理级功能](/help/migrated/managers/feature-summary/review-external-learning-requests.md)的更多信息。 了解有关[外部学习支持 — 学习者级别功能](/help/migrated/learners/feature-summary/submit-external-learning.md)的更多信息。

## AI功能

### 面向学习者的AI助理

除了回答分配学习内容中的问题外，AI学习者助理现在还支持四种新功能：

* **课程摘要**：使用/命令选择目录项并生成摘要，而无需打开课程
* **学习对象比较**：使用/命令选择最多两个学习对象，并要求助理进行比较
* **Adobe Experience League答案**：助手现在从Adobe Learning Manager帮助文档获取操作方法问题的答案
* **第三方内容查询**：可查询Go1和LinkedIn学习目录内容（仅限元数据；仅英语；添加目录后需要1-2小时才能摄取）

了解有关[学习者AI Assistant](/help/migrated/learners/feature-summary/learner-ai-assistant.md)的更多信息。

### 学习路径代理

学习者现在可以与AI Assistant进行引导式对话，以根据他们的目标、背景和可用时间生成自定义、有序的学习路径。 系统会自动创建学习路径，并为学习者注册。

关键功能：

* 多轮对话可指导学习者选择主题、查看课程和确认路径
* 每个对话最多可包含五个建议的学习主题
* 从分配的目录中选择课程
* 在学习者主页上最多可见10条个性化学习路径
* 可以与同事共享已完成的路径

详细了解[学习路径代理](/help/migrated/learners/feature-summary/learning-path-agent.md)。

### Insights代理

Insights代理可帮助管理员通过自然语言查询分析学习数据。 询问有关注册趋势、完成率、学习者参与度和技能差距的问题。 客服专员会生成报告和可视化效果以作为响应。

了解有关[Insights代理](/help/migrated/administrators/feature-summary/insights-agent.md)的更多信息。

<!--
### Gen AI credits

Adobe Learning Manager integrates AI-powered features managed through a credit-based system linked to Agent Orchestrator licenses. This system requires administrators to activate features, set credit limits, and monitor usage via the Billing page. Linking the Adobe Learning Manager account to an Adobe Admin Console organization with an active Agent Orchestrator license is essential for enabling Gen AI features.

View [Gen AI credits](/help/migrated/administrators/feature-summary/billing-management.md#genaicredits) for more information.
-->

## 渠道（Beta版）

渠道提供了一种从Web和Confluence页面组织、发布和发现视频内容的集中方式。 管理员可以通过连接支持的网页或Confluence页面来创建和管理渠道，配置渠道设置，控制可见性，以及从源同步内容。 学习者可以从单个位置浏览可用渠道、订阅目标渠道和观看精选视频内容。

详细了解[创建声道](/help/migrated/administrators/feature-summary/create-channels.md)。

## Report Builder

Report Builder为管理员提供了灵活的自助报告工具，不只是Adobe Learning Manager其他地方提供的固定报告类型。 管理员可以将来自多个数据集（例如“用户”、“用户组”、“课程”和“学习路径”、“模块”、“成绩单”、“目录”等）的字段加入到一个定制的报告中，而不是仅限于预定义的报告结构。

报告创建一次并保存，以便重复使用。 无需在每次下载时重新生成筛选器、重新应用分组或重新加入数据集。 可以按需下载保存的报告、与其他管理员共享的报告或设置订阅，以便收件人定期自动接收更新的报告。

详细了解[Report Builder](/help/migrated/administrators/feature-summary/alm-report-builder.md)。

## 自定义角色更改

现在，可通过自定义角色定义中“用户”下的“高级”权限级别，向自定义管理员授予扩展的用户管理功能。

有两种访问级别可用：

| 访问级别 | 自定义管理员可以执行的操作 |
|---|---|
| **只读** | 查看所有自定义角色、导入日志和删除用户；下载自定义角色报告 |
| **完全控制** | 所有只读权能，以及：创建、编辑、删除和分配自定义角色；通过CSV导入用户；清除已删除的用户 |

### 限制

**仅手动创建角色**：扩展的自定义角色管理功能仅适用于通过Adobe Learning Manager管理员界面创建的角色。 不支持通过CSV上传功能导入的角色。

在主题[高级用户权限解锁的内容](/help/migrated/administrators/feature-summary/custom-role.md#whatadvanceduserpermissionunlocks)中了解有关自定义角色更改的详细信息。

## LTI深层链接

集成管理员现在可以为LTI工具配置启用LTI深层链接，从而允许课程作者直接从外部LMS浏览和嵌入Adobe Learning Manager课程，而无需手动复制课程URL。

启用后，作者将在外部LMS活动配置中看到&#x200B;**选择内容**&#x200B;按钮。 他们可以浏览已批准的目录、选择课程并确认选择 — 所有字段都会自动填充。

详细了解[LTI深层链接](/help/migrated/integration-admin/feature-summary/lti-deep-links.md)。

## 教室位置

教室位置现在支持结构化的&#x200B;**四字段位置格式**，包括国家/地区、州/省/地区、城市和位置名称，从而更轻松地跨区域管理和组织培训位置。 此更新包括从旧版单字段格式进行一次性迁移，并添加了对&#x200B;**位置名称**&#x200B;和&#x200B;**位置信息**&#x200B;字段的多语言支持，从而使学习者能够获取本地化的教室详细信息。

详细了解[教室位置](/help/migrated/administrators/feature-summary/classroom.md)。

## 报告版本中的更改

详细了解[报告Adobe Learning Manager 2026年8月版中的更改](/help/migrated/reporting-changes-august-2026.md)。

## 此版本中的API更改

了解有关Adobe Learning Manager 2026年8月版[API更改的更多信息](/help/migrated/api-changes-august-2026.md)。

## 版本中的其他增强功能

| 增强功能 | 描述 |
|---|---|
| **MQA：最新与最高分数** | 对于多次尝试的模块，作者现在可以选择是否在学习者成绩单中记录最新尝试分数或最高尝试分数，并将其用于评分簿计算。 “最新”是现有的默认设置，并且在未配置该设置时保持不变。 有关详细信息，请详细了解[面向作者的Gradebook](/help/migrated/authors/feature-summary/alm-author-gradebook.md#configurescoresettingsmultipleattempts)。 |
| **内容库中的内容预览** | 作者现在可以直接在内容库中预览上传的内容文件，然后再将它们添加到课程中。 了解有关[预览内容库](/help/migrated/authors/feature-summary/content-library.md#previewcontentlibrary)的更多信息。 |
| **增量用户报告** | 新的基于API的用户报告仅返回自上次请求以来创建或修改的用户，从而减少使用自动用户同步工作流程的大型帐户的数据传输。 详细了解[增量用户报告](/help/migrated/incremental-user-report.md)。 |
| **流体播放器中的11种新语言** | 流体播放器现在支持11种其他语言，包括从右到左(RTL)脚本支持。 了解有关[流体播放器](/help/migrated/learners/feature-summary/fluidic-player.md)的更多信息。 |
| **LTI模块迁移** | 现在可以使用迁移工具将现有的LTI 1.1模块迁移到LTI 1.3。 详细了解[模块的LTI迁移](/help/migrated/integration-admin/feature-summary/migration-manual.md#migrationofltimodules)。 |
| **电子邮件生成器：支持富文本编辑器** | Adobe Learning Manager中的电子邮件模板现在支持富文本格式、附件和自定义自动化。 详细了解[电子邮件生成器](/help/migrated/administrators/feature-summary/email-builder.md)。 |
| **电子邮件生成器：预览功能** | 您可以使用“预览”选项检查您撰写的电子邮件，以查看它看起来像收件人的末尾。 详细了解[电子邮件生成器](/help/migrated/administrators/feature-summary/email-builder.md)。 |
| **Webhook时间戳标准化** | Webhook有效负载的`data`对象中的所有日期和时间字段现在将秒数设置为`00`，提供与学习者成绩单报告一致的分钟级精度。 |
| **连接增强功能** | Azure数据湖存储(ADLS)连接器更新；对定期虚拟教室会话的持续教室名称支持；基于录制视图的出席情况跟踪。 |
| **播放器性能改进** | 流体课程播放器经过优化，缩短了加载时间，模块之间的转换更加流畅。 |
| **弃用课程/学习计划前出现影响警告** | 作者/管理员会先看到相关学习对象的警告列表，然后课程或学习路径才能停用。 通知作者组成学习对象已停用。 如果管理员编写了学习对象但没有编写者角色，则会收到错误消息。 |
| **CR/VC模块：预计持续时间** | 作者现在可以为教室和虚拟教室模块设置预期持续时间，与计划的会话时间分开。 该值显示在报告和面向学习者的课程信息中。 |
| **在编辑已获取的课程之前进行确认** | 配对帐户中的管理员现在可以在编辑通过目录共享获取的课程之前看到确认对话框，从而防止对共享内容进行意外更改。 |
| **实例ID为**&#x200B;的会话URL | Microsoft Teams、Adobe Connect和Zoom会话的会话启动URL现在包含实例ID，从而确保当存在多个实例时，将学习者路由到正确的会话。 |
| **针对大量受众公告的警告** | 当向超过可配置阈值的收件人发送临时公告电子邮件时，管理员现在会在发送前看到一个音量警告。 |
| **电子邮件模板：外部学习者的帐户URL** | 电子邮件通知模板现在可以包含专为外部学习者提供的单独帐户URL，从而引导他们获得正确的登录体验。 |
| **AEM Sites** | 现在，**您的配置文件** >您的兴趣领域部分中只有一个&#x200B;**编辑**&#x200B;按钮，可用于编辑您的产品首选项、角色首选项和技能首选项。 这也是Native Learning Manager的一部分。 |
| **AEM Sites** | 以前，系统提供两个&#x200B;**编辑**&#x200B;按钮，但现在，**编辑**&#x200B;按钮是一个统一按钮，可用于修改您的“产品”、“角色”和“技能”首选项。 |
| **时区** | 在已登录用户的“配置文件设置”中的“时区”字段正下方添加了一个新的搜索框。 搜索框可用于直接搜索时区，而不是滚动浏览整个可用时区列表。 如果要更改现有时区，请选择新时区，然后选择“保存”。 将保存新时区。 “保存”按钮仅在您选择时区时出现。 |

## 系统要求

详细了解[Adobe Learning Manager系统要求](/help/migrated/system-requirements.md)。

## 发行说明

请查看[发行说明](/help/migrated/release-note/release-notes.md)以了解最新发行更新。

## Adobe Learning Manager 的早期版本

* [Adobe Learning Manager 2026年4月版](/help/migrated/whats-new-april-2026.md)
* [Adobe Learning Manager 2025年10月版](/help/migrated/whats-new-october-2025.md)
