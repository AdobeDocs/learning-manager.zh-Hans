---
description: 了解Adobe Learning Manager 2026年4月版的新增功能和增强功能，包括API和Webhook更改
jcr-language: en_us
title: Adobe Learning Manager 2026年4月版的新增功能
exl-id: da46f186-3ff3-422a-af49-31c7405fd584
source-git-commit: 971a9c79fc2b831b990e30a44a2eeab5d5c5ce63
workflow-type: tm+mt
source-wordcount: '1768'
ht-degree: 0%

---

# Adobe Learning Manager 2026年4月版的新增功能

**对于学习者：**&#x200B;流体播放器现在会显示下一个模块名称和清除“退出”按钮。 可以通过LTI设置播放器语言，以便跨平台获得一致的体验。 自定义参数名称为“locale”，它接受区域设置代码。 例如， locale=fr-FR。 Captivate内容包括统一的目录、幻灯片级别的完成刻度以及可靠的备注导出。 为工作辅助、清单问题和视频文本轨道(VTT)提供多语言支持。 AI Assistant可帮助学习者在学习体验中获取答案。

**对于管理员和作者：** Zoom连接器支持多个并发VILT会话。 配对帐户中的共享课程会显示真实作者，而不是“外部作者”。 管理员可以限制模块可以启动的时间。 学习者API中会显示学习对象到期日期。 清单模块支持加权评分、多语言问题文本和可选的审阅者评论。 自定义证书提供了一个具有动态字段和AI生成背景的拖放编辑器。 利用未登录的Experience Builder，您无需登录即可构建公共学习页面。

**对于讲师：**&#x200B;为实例注册和会话出席情况生成二维码。 在清单评估期间添加评论或反馈。

**报告和分析：** SCORM内容现在可以在L2报告中报告多次测试尝试。 “学习者成绩单”中的计算所花费的学习时间得到改进。 管理员的学习成绩单报告已更新。 提供了高级搜索增强功能。

**登录方法：**了解OpenID Connect如何在Adobe Learning Manager中为学习者、作者和管理员登录。 OpenID Connect (OIDC)是基于Web标准构建的通用登录方法。 许多组织使用
员工和合作伙伴的身份提供方（例如Okta、Google Workspace或Microsoft Entra ID）。

有关详细信息，请查看[使用OIDC登录](/help/migrated/oidc.md)。

## 替代项和等效项中的Webhook和迁移

### Webhook

学习者通过替代或关系完成课程时，ALM会触发与标准课程完成Webhook分离的Webhook事件。 这可确保集成在需要时以不同方式响应替代完成。 当发生追溯完成或追溯完成时，还会触发Webhook事件，包括历史更新以及关系更改。

有关详细信息，请查看[Webhook](/help/migrated/integration-admin/feature-summary/webhooks.md#webhooks-for-alternates)。

### 迁移

[Webhook](/help/migrated/integration-admin/feature-summary/migration-manual.md#migration-for-alternates-and-equivalents)中概述了用于在系统中引入学习对象(LO)等价性的基于CSV的数据模型和迁移行为。

## 自动清除已删除的用户

自动清除已删除用户功能可清除已在ALM中删除的用户的数据。 清理在可配置的保留期之后进行，侧重于批量操作，以便在不影响性能的情况下高效地处理大型客户帐户。

有关详细信息，请查看[自动清除已删除的用户](/help/migrated/administrators/feature-summary/purge-users.md#auto-purge-of-deleted-users)。

## 设置模块访问时间控制

这项增强功能可让作者和管理员在Adobe Learning Manager中定义允许学习者启动模块的时间范围。 在配置的开始/结束窗口之外，模块在课程结构中仍然可见，但学习者无法启动它。

有关详细信息，请查看[设置模块访问时间控制](/help/migrated/administrators/feature-summary/module-access-time-control.md)。

## “学习者成绩单”的更改

此版本增强了学习成绩单(LT)报告，并提供了更清晰的可审核性和合规性支持。

* 管理LT中新增的“完成方法”列会显示完成是直接、替代还是撤销，而替代完成现在会使用来源培训中的继承日期来影响状态、完成日期和完成来源，并在撤销来源或发生直接完成时进行更新。
* 在启用了追溯未完成的情况下删除所有合格关系时，撤销的替代会自动调整状态、完成日期和完成来源。
* 在管理员和学习者学习对象以及所有导出渠道中，清单模块的审阅者反馈在重命名的审阅者注释列下实现标准化。
* 最后，学习时间计算现在可以更好地区分活动时间与空闲时间，从而提高参与和合规性报告的准确性。

有关详细信息，请查看[学习者成绩单报告](/help/migrated/administrators/feature-summary/reports/changes-in-learner-transcript.md)中的更改。

## 包含审阅者注释功能的清单

使用此功能，审阅者可以在清单评估期间添加评论或反馈。 您可以为每个学习者提供个性化、可操作的反馈。 您还可以选择显示姓名并添加注释，以提高透明度。 所有备注均会保存在学习者的成绩单中，并包含在清单报告中。

有关详细信息，请查看[配置包含注释的清单](/help/migrated/authors/feature-summary/courses.md#checklist-with-commenting)。

## 对清单的多语言支持

使用此功能，您可以用多种语言创建和管理清单模块。 每个清单问题、说明和评估标准都可以翻译，以便审阅者和学习者使用他们首选的语言与清单进行交互。 系统以用户选定的内容语言显示清单，这提高了全球团队的可访问性和合规性。

查看[在模块中创建多语言清单](/help/migrated/authors/feature-summary/courses.md#create-a-multi-language-checklist)

## 针对讲师评估的核对表问题权重

利用此功能，您可以为每个清单问题指定不同的最高分数（权重）。 您可以反映每个问题的不同重要性或难度，从而支持更准确和有意义的评估。 系统根据您的输入计算总分，并根据您设置的标准确定学习者通过还是失败。

查看[创建加权清单问题](/help/migrated/authors/feature-summary/courses.md#how-to-create-a-weighted-checklist)

## 自定义证书

Adobe Learning Manager (ALM)中的自定义证书可让管理员和作者设计、管理和为学习者颁发个性化证书。

该功能包括拖放编辑器、动态字段、多语言支持和AI生成的背景，使组织无需技术专业知识即可创建品牌证书。

查看[设计自定义证书](/help/migrated/administrators/feature-summary/create-customize-certificate.md)

## Experience Builder中的未登录体验

Experience Builder中的未登录体验允许组织向所有访问者（包括未登录访问者）显示其学习内容和门户页面。 此功能旨在通过提供流畅的品牌预览来吸引、通知和吸引潜在学习者，然后再要求他们登录或注册。

在Experience Builder中查看[未登录体验](/help/migrated/administrators/feature-summary/experience-builder/non-logged-in-experience.md)

## 高级搜索增强功能

“高级搜索”中的搜索结果现在更加准确和相关。 在内容搜索和元数据中，完全匹配的关键字的排名都较高，这使得学习者可以更轻松地准确找到他们想要的内容。

学习者现在还可以在搜索结果中看到已注册的学习对象，即使它们不属于辅助目录，从而确保不会错过任何相关内容。 此外，工作辅助排名在高级搜索和内容内搜索中得到了改进，可以更快地显示最相关的资源。

## 多语言工作辅助

Adobe Learning Manager (ALM)中的多语言工作辅助允许作者和管理员在单个工作辅助条目中提供多种语言的支持文档、指南或资源。 不同区域的学习者可以访问其首选语言的相关材料，这可以提高理解、合规性和用户体验。

查看[添加多语言工作辅助](/help/migrated/authors/feature-summary/job-aids.md#create-a-multilingual-job-aid)以了解更多信息。

## 多语言视频文本轨道(VTT)支持（适用于作者）

Adobe Learning Manager对多语言视频文本轨道(VTT)的支持使作者能够为多语言视频和音频内容提供字幕和字幕。 此功能可简化本地化，使培训面向全球受众，并确保遵守辅助功能标准。 作者可以直接在平台内自动生成、翻译、审阅和编辑VTT文件。

有关详细信息，请查看[多语言VTT支持](/help/migrated/authors/feature-summary/content-library.md#multi-lingual-vtt-support)。

## 显示配对帐户中共享课程的原始作者

当通过目录将课程共享到配对帐户时，Adobe Learning Manager目前在接收帐户的“学习者”、“管理员”和“作者”视图中，将作者标记为“外部作者”。 这可能会给学习者和管理员带来挑战，尤其是在大型企业中，因为出现问题或疑问时，很难确定并联系相应的内容所有者。

这项增强功能可确保配对帐户中共享课程的作者信息得到保留和呈现，而不是被通用占位符替代。

### 新增功能

显示配对帐户中共享课程的实际作者姓名

对于通过外部或配对目录共享的课程，源帐户中的原始作者姓名现在显示在接收帐户中，而不是“外部作者”。

这适用于：

* 学习者应用程序（课程卡或课程详细信息）。
* 以学习者身份预览时，管理员和作者视图。

查看[共享课程的作者姓名显示](/help/migrated/administrators/feature-summary/peer-account.md#author-name-display-for-shared-courses-including-previously-acquired-courses)，了解更多信息。

## 等效项和替代项

使用ALM中的对应项和替代项，提供顺畅的学习体验并消除冗余培训。 此新功能允许管理员配置单向（替代）或双向（等效）规则，其中完成一项培训会自动授予另一项培训的替代完成。 此功能旨在简化大型学习生态系统，确保学习者绕过他们已经掌握的内容，组织大幅减少管理员支持票证，消除手动覆盖，并维护更清晰、更准确的学习者记录。

有关详细信息，请查看[对等项和替代项](/help/migrated/administrators/feature-summary/alternates-equivalence.md)。

## 实例注册和会话出席的讲师二维码

讲师可以自行生成二维码用于：

* 课程实例注册、
* 会话出席情况，或
* 同时注册+出席情况

在会话级别。 专为学习者进入物理或混合教室并要求快速、自助服务选项使用二维码注册和记录出勤情况而设计。

有关详细信息，请查看[下载学习者注册和出席的二维码](/help/migrated/instructors/feature-summary/learners.md#download-qr-codes-for-learner-enrollment-and-attendance)。

## 带有会话链接的日历邀请(ICS)

Adobe Learning Manager在发送给学习者和讲师的日历邀请（ICS文件）**中直接包含**&#x200B;会话加入链接。 这允许参与者直接从他们的日历加入会话，而无需搜索会话电子邮件。

此增强功能改进了日历客户端（如&#x200B;**Gmail**&#x200B;和&#x200B;**Outlook**）的体验。

有关详细信息，请查看[包含会话链接的日历邀请](/help/migrated/instructors/feature-summary/learners.md#joining-a-session-from-gmail)。

## 面向学习者的AI助理

学习者的AI Assistant (Beta)可帮助他们从指定的学习内容中快速查找答案，而无需浏览整个课程。 您可以用浅显的语言提出问题，并获得准确、重点突出的答复，并提供指向相关课程内容的源链接。

功能、支持的场景和限制可能会随功能的变化而改变。 AI Assistant是Adobe Learning Manager中的生成式AI聊天助手，可使用您信任的学习内容提供快速、准确的答案。 其中包括引用，以便您始终了解信息的来源。

查看[学习者的AI Assistant](/help/migrated/learners/feature-summary/learner-ai-assistant.md)


## 此版本中的API更改

2026年4月版Adobe Learning Manager引入了针对以下内容的公共API的增强功能：替代项和对等项、对内容的时间窗口访问、内容驱动的测试尝试、未登录体验和工作辅助处理。 这些更改旨在实现大致向后兼容，同时实现更精确的集成。

查看4月版中的[API更改](/help/migrated/api-changes-alm.md)

## 系统要求

查看[Adobe Learning Manager系统要求](/help/migrated/system-requirements.md)。

## 发行说明

请查看[发行说明](/help/migrated/release-note/release-notes.md)以了解最新发行更新。

## Adobe Learning Manager 的早期版本

* [Adobe Learning Manager 2025年10月版](/help/migrated/whats-new-october-2025.md)
* [Adobe Learning Manager 2025年5月版](/help/migrated/whats-new-may-2025.md)
