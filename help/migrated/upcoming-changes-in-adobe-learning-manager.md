---
title: Adobe Learning Manager 2026年4月版的新增功能
description: 了解Adobe Learning Manager 2026年4月版的新增功能、改进和重要更新。
exl-id: 4d2129c4-42d8-446f-8837-879b5c2f42bf
source-git-commit: bff4227db5cb1d419d66c59688989de1406b0458
workflow-type: tm+mt
source-wordcount: '7458'
ht-degree: 1%

---

# Adobe Learning Manager中即将推出的更改

<!-- >>[!IMPORTANT]
>
>The Adobe Learning Manager October 2025 release is now live. View [What's New](/help/migrated/whats-new.md) for more information on the latest features and enhancements. This page will be updated with the new features and enhancements for the next release. Stay tuned for more updates. -->

## 版本概述

2026年4月版Adobe Learning Manager引入了一系列改进，使学习者学习更顺畅，管理员更易于管理，讲师更灵活，包括使用“下一模块”标签和专用退出按钮在流体播放器中更清晰地导航，支持多个并发Zoom会话，因此团队无需手动设置即可运行并行虚拟课程，以及通过显示真实作者而不是配对帐户中的“外部作者”来更好地查看共享课程。 此更新还公开了学习者API中的学习对象到期日期，以帮助LXP突出显示时效性培训，为工作辅助添加多语言支持，使一个工作辅助可以携带所有语言版本，并允许管理员通过定义对群组或定时计划有用的开始/结束窗口来限制模块何时可以开始。

使用LTI的外部系统现在可以自动设置播放器语言，为学习者提供跨平台的一致语言体验。 此外还有几项清单升级，包括加权评分、多语言问题文本和可选的审阅者评论以获得更丰富的反馈。 ALM现在可捕获SCORM内容中控制的多次测验尝试，并在L2报告中以干净的方式报告每次尝试。 讲师还可以自行生成二维码，以便在面对面会话期间即时跟踪注册和出席情况，而且借助统一的目录、幻灯片级别的完成时间表和可靠的笔记导出功能，Captivate内容的播放会更加干净。 总体而言，该版本侧重于清晰度、一致性、多语言就绪性、管理效率和更灵活的培训交付。

## 流体播放器导航 — 显示下一个模块的名称

### 概述

此增强功能已包含在Adobe Learning Manager的2025年11月版中。

播放器中的“下一个”操作会显示下一个模块或课程的名称，并在学习者准备退出播放器时明确发出信号，从而指示单击后会发生什么。

### 新增功能

播放器&#x200B;**中的{ModuleName}“下一个模块：**”标签

现在，流体播放器中的“下一步”图标会显示课程中下一个模块的名称。 例如，下一模块：第2课 — 快速入门。

这适用于学习者在同一课程中从一个模块转到下一个模块的情况。

**清除最后一个模块上的退出操作**

当学习者位于课程的最后一个模块中时，系统会显示一个新的退出操作按钮，表示单击该按钮将关闭播放器并将其返回到课程上下文。

**移动和PDF内容的响应行为**

在较小的视口上（例如，约320 px宽度），“下一个”标签可能会缩短或隐藏，仅显示图标，以避免与PDF控件重叠。

对于PDF模块，播放器将控件调整为单独的行，因此导航标签和PDF控件不会相互干扰。

**更新的管理员>品牌推广>播放器预览**

“管理员”>“品牌推广”中的播放器预览现在反映新标签，例如，下一模块：第2课。 管理员可利用此视图查看更新的导航行为。

### 主要优点

**让学习者导航更清晰**

学习者不必再猜测选择“下一步”时会发生什么。 标签会明确说明后续内容，是模块还是课程。 这种模糊性的减少有助于缓解犹豫和困惑，特别是在许多学习者可能不熟悉LMS界面的大型客户教育受众中。

**较高的课程完成率**

明确说明下一步（下一个模块： {ModuleName}）并为最终模块添加明确的退出操作，可降低学习者放弃课程或忽略最后一个完成步骤的可能性。

**跨设备实现更可预测的用户体验**

更新的标签与桌面、平板电脑和移动设备上的“下一个”或“上一个”行为和图标保持一致。 在设备和PDF流之间考虑布局约束，以使控件保持可用并可访问。

这对于将流体播放器嵌入自定义学习体验的无头实现尤其重要。

### 用例

**客户和合作伙伴教育门户(无头门户或AEM集成门户)**

在完全无头设置中使用Adobe Learning Manager的帐户，引导学习者从外部营销渠道进行营销。 这些学习者：

* 经常按长序列使用视频内容。

* 系统可明确指示下一节/模块时的课程式体验。

在这些环境中，**下一个模块：{ModuleName}**&#x200B;标签：

* 强化了这次旅程的向导性质。

* 最小化模块之间的流失。

**包含有序模块的合规性和认证课程**

在受管控或法规遵从性要求较高的情形中：

* 学习者必须完成严格的模块序列。

* 作者通常会禁用目录以避免跳过。

此处显示&#x200B;**下一个模块：{ModuleName}**：

* 向学习者确认他们遵循的顺序正确。

* 这降低了他们误解下一步行动并提前退出的可能性。

**课程相互跟随的学习路径**

其中，学习路径或等价课程链接了多个课程。 在为大量受众构建课程风格序列时，此功能非常有用。

**移动优先使用**

对于主要使用手机或平板电脑的学习者：

* 更新了标签和响应式行为，确保导航保持可读性，而无需依赖小的关闭图标或隐藏控件。

* 这对于可能会在移动设备上短时间会话中访问内容的客户教育、零工或一线学习者非常重要。

## Zoom连接器 — 创建多个并发Zoom会话

### 概述

即将升级的Zoom连接器将显着增强Adobe Learning Manager管理虚拟讲师指导培训(VILT)的方式。 以前，用户一次只能创建一个Zoom会话。 使用新的更新，管理员和作者可以使用标准集成同时计划多个Zoom会话。

### 新增功能

#### 通过连接器支持多个并发缩放会话

* Zoom连接器现在允许从ALM在同一日期/时间创建多个VILT会话。

* 计划逻辑不再在帐户/连接器级别强制实施“一次一个Zoom会议”约束。

* 管理员和作者可以配置重叠的VILT会话（例如，区域课堂、平行轨道或不同合作伙伴组的重复会话），无需解决方法。

#### 使用讲师的Zoom身份（而非Zoom超级管理员）创建会议

为了安全地支持并发会议，已更新连接器，以便：

* Zoom会议现在使用讲师的电子邮件地址而非Zoom超级管理员电子邮件创建。

* 根据现有Zoom计划的限制，每位讲师的Zoom帐户可以与其他讲师并行主持自己的会议。

**注释**：

* 每个会议仍然仅支持一名讲师。

* 如果讲师的电子邮件后来在Adobe Learning Manager中更新，则现有会议仍与创建时使用的原始电子邮件关联。

#### 不再手动为并发会话粘贴Zoom URL

以前，当第二个或第三个缩放会话必须同时运行时：

* 作者必须在ALM之外手动创建Zoom会议，然后将Zoom加入URL粘贴到课程实例配置中。

* 这很容易出错，并且无法从出席情况跟踪等连接器功能中获益。

使用更新后的连接器：

* 可以使用Zoom连接器直接从ALM UI创建所有会话，即使它们在时间上重叠。

* 会话生命周期（创建/取消）继续通过集成进行集中管理。

### 主要优点

#### 更好的VILT大规模调度

组织现在可以：

* 同时运行多个基于Zoom的虚拟教室（例如，虚拟峰会的平行轨道、区域组群或单独的合作伙伴培训课程）。

* 避免以前强制管理员序列化会话或依赖手动缩放管理的瓶颈。

#### 减少管理员和作者开销

增强功能消除了：

* 在Adobe Learning Manager之外手动创建Zoom会议。

* 将缩放URL复制粘贴到各个课程实例中以进行重叠会话。

* 链接配置错误、附加错误的会议或错过出席跟踪的风险。

管理员和作者可以使用熟悉的工作流程从Adobe Learning Manager管理所有Zoom会话。

#### 更好地与Zoom配置和讲师角色保持一致

通过将会议与个别讲师Zoom帐户关联：

* 每位讲师可以在各自的Zoom许可证限制内操作。

* 组织可以使用其现有的缩放配置模型（每个培训师、每个BU等各一个帐户），同时仍可与Adobe Learning Manager完全集成。

* 它避免了单点瓶颈：为所有会话使用共享超级管理员Zoom用户。

### 用例

#### 多轨虚拟活动和峰会

举办大型活动（例如，产品促销营、合作伙伴峰会或认证周）的客户教育团队可以：

* 在同一时隙中配置多个基于缩放的会话（针对不同的轨道或主题）。

* 在Adobe Learning Manager的课程和学习路径下将所有这些模块作为VILT模块进行管理。

* 在连接器处理所有基础Zoom会议创建时，为学习者提供统一的体验。

#### 全球合作伙伴和客户培训

跨地区培训客户和合作伙伴的组织可以：

* 在重叠的时间为欧洲、中东和非洲、亚太以及美洲地区运行单独的Zoom会话，以匹配本地工作时间。

* 避免为其他同类组强制使用单个全局时隙或手动缩放设置。

#### 内部启用

内部实施团队（销售、支持等）可以：

* 在ALM中安排并行入门课程或基于角色的分类（例如，为开发人员、管理员和业务利益相关者安排单独的Zoom会议室）。

* 将所有会话保留在ALM的VILT模型中以用于报告和合规性目的，而不是部分过渡到非托管的Zoom会议。

## 显示配对帐户中共享课程的原始作者

### 概述

当通过目录将课程共享到配对帐户时，Adobe Learning Manager目前在接收帐户的“学习者”、“管理员”和“作者”视图中，将作者标记为“外部作者”。 这可能会给学习者和管理员带来挑战，尤其是在大型企业中，因为出现问题或疑问时，很难确定并联系相应的内容所有者。

这项增强功能可确保配对帐户中共享课程的作者信息得到保留和呈现，而不是被通用占位符替代。

### 新增功能

显示配对帐户中共享课程的实际作者姓名

对于通过外部或配对目录共享的课程，源帐户中的原始作者姓名现在显示在接收帐户中，而不是“外部作者”。

这适用于：

* 学习者应用程序（课程卡或课程详细信息）。

* 以学习者身份预览时，管理员和作者视图。

### 主要优点

#### 共享内容的直接所有者可见性

配对帐户中的学习者和管理员现在可以：

* 查看课程作者，即使课程是通过共享目录获取的。

* 避免使用通用且无用的“外部作者”标签。

#### 更一致的多租户和配对帐户体验

对于运行多租户或扩展企业方案的客户：

* 这门课程在各个帐户中显示了一致的作者品牌标记。

* 学习者体验与主客户的期望一致（例如，看到“Cloud Academy团队”而非“外部作者”）。

### 用例

#### 具有配对帐户的大型企业

企业将ALM用于：

* 拥有标准课程的主科目，以及

* 通过共享目录获取内容的配对帐户。

配对帐户中的学习者需要了解哪个企业团队编写了课程，才能正确路由问题或改进建议。

借助此增强功能：

* 现在，共享课程会在配对帐户中显示正确的企业作者姓名。

* 企业的内部支持工作量减少，因为学习者和本地管理员知道该联系谁。

#### 内部多BU共享

如果一个业务部门为他人安排学习活动：

* 可以在所有使用帐户的作者字段中标识所属BU。

* 本地L&amp;D管理员可以快速查看课程是在本地维护还是由其他BU维护，并相应地开展协作。

## 在学习者API中显示学习对象到期（自动弃用）日期

### 概述

此增强功能可直接通过Adobe Learning Manager面向学习者的API提供学习对象(LO)的自动弃用日期。 为课程、学习路径或认证配置到期或自动弃用日期后，该信息现在会包含在关键学习者端点返回的学习对象数据中。

### 新增功能

#### 学习者学习对象API中新增“到期/自动弃用”字段

* 学习者学习对象API（例如，将学习对象返回到学习者体验和外部平台的端点）现在包含学习对象到期日期（为该学习对象配置的自动弃用日期）。

* 该字段作为学习对象实体的一部分在以下响应中返回：

   * 获取学习对象（学习对象详细信息）。

   * 学习对象数据，用于填充学习者主页、目录和搜索结果。

* 该字段是对实例级别上已存在的现有completionDeadline的补充；新字段专门针对学习对象级别的自动弃用日期。

#### 提供以搜索为基础的学习者体验

由于到期日期作为搜索支持的学习对象表示的一部分显示，因此它现在可在ALM或外部平台使用的任何位置使用：

* 搜索API或

* 搜索驱动的目录以及构建学习者视图的建议。

**范围和排除项**

此增强功能仅适用于学习者API。

### 主要优点

#### 自定义LXP中的到期感知学习者体验

对于大中型企业，其自定义LXP现在可以直接从ALM获取学习对象到期信息，从而使他们：

* 在课程卡和详细信息页面上显示“即将于{date}过期”或“即将过期”标签。

* 更明确地表达紧迫感，以便学习者优先考虑即将停用的培训。

这对于合规性或有时限的产品培训尤其重要，因为在这些培训中，学习对象会定期刷新，而旧版本会停用。

#### 为学习者提供更好的指导，立即开始培训

通过公开学习对象到期，学习者体验可以：

* 高亮显示仍然有效的课程和即将停用的课程。

* 帮助学习者避免参加近期将不再有效或可用的培训。

#### 与现有完成截止日期数据的一致性

之前，学习者API会显示实例级别completionDeadline，但不会显示学习对象级别的自动弃用日期。 进行此更改后：

培训的以下方面可用：

* “我必须在何时完成此实例？” （完成截止日期）。

* “到什么时候才会提供培训？” （自动停用/到期日期）。

### 用例

#### 具有严格的课程生命周期管理的全球企业

定期弃用并替换课程（例如更新法规、产品或方法）的企业可以：

* 避免学习者对是否正在逐步取消培训感到困惑。

* 推动学习者使用最新且生命周期较长的产品。

其自定义门户和内部工具现在可以通过学习者API直接从ALM中读取到期日期。

#### 外部客户或合作伙伴学院

对于客户和合作伙伴培训，营销页面和门户通常强调最新培训。

通过学习对象API中的到期日期，体验构建者可以：

* 隐藏或弱化接近退休年龄的内容。

* 构建“完成活动的最后机会”活动。

## 工作辅助的多语言支持

### 概述

增强功能将Adobe Learning Manager的本地化模型扩展到工作辅助，允许作者将每种语言的不同内容文件附加到单个工作辅助。 作者现在可以将所有本地化版本作为一个逻辑工作辅助进行管理，而不是为每种语言创建单独的工作辅助。

### 新增功能

#### 工作辅助的特定语言内容上传

作者可以将每种受支持语言的不同文件附加到单个工作辅助，例如课程和其他学习对象。

工作辅助创建/编辑体验现在支持：

* 选择语言。

* 在同一个工作辅助实体中上传该语言的特定语言文件。

#### 播放器和学习者UI中的统一语言处理

更新了流体播放器，以便学习者打开工作辅助时，显示与学习者语言对应的内容变体（如果可用）。

管理员和作者可将工作辅助视为具有语言变体的单个对象，而不是按语言显示单独的项目。

### 主要优点

#### 所有语言的单个工作辅助

作者可以避免为每个语言创建单独的工作辅助。

同一工作辅助的所有语言变体(例如，程序、SOP、清单PDF或参考指南)都可以在一个位置进行管理。

#### 为全球学习者带来更好的体验

学习者会自动看到其首选语言的工作辅助，这表示：

* 不要混淆要打开的版本。

* 访问区域外副本或过期副本的风险较低。

这在必须提供多种语言的相同流程或产品文档的多语言组织中尤为有用。

### 用例

#### 参考内容的全球推广

企业需要向世界各地的学习者提供多种语言的工作辅助，例如：

* 产品参考表。

* 处理检查列表。

* 支持行动手册

他们无需创建单独的工作辅助，如“产品快速入门 — EN”、“产品快速入门 — DE”、“产品快速入门 — JP”等，而是可创建一个工作辅助、为每个语言附加本地化文件并让ALM根据语言设置为每个学习者提供正确的版本。

#### 适用于多个市场的面向客户或合作伙伴的文档

对于客户和合作伙伴学院，工作辅助可能包括：

* 产品备忘单

* 集成指南

* 支持工作流程

借助多语言工作辅助：

* 每个合作伙伴都可以看到本地化版本，而不必在语言特定的条目之间进行选择。

* 营销和支持团队可以在所有区域设置中为每个主题管理一个工作辅助。

## 对模块启动时间设置限制

### 概述

这项增强功能可让作者和管理员在Adobe Learning Manager中定义允许学习者启动模块的时间范围。 在配置的开始/结束窗口之外，模块在课程结构中仍然可见，但学习者无法启动它。

如果用户需要更严格地控制特定内容何时可用或应停止启动（例如，在定时计划、基于团队的培训或时间紧迫的练习中），此功能非常重要。

### 新增功能

作者现在可以在课程模块级别配置开始日期/时间和结束日期/时间，以控制何时允许学习者启动该模块。 在该窗口中，模块行为与往常一样；在开始时间之前或结束时间之后，学习者可以看到课程大纲中的模块，但不能启动。

该配置显示在课程创作用户界面中，作为对特定模块类型（如自学内容、测验或活动）的附加计划控件。 管理员可以使用这些控件创建分阶段打开的模块，或防止在规定时间范围内使用内容的程序延迟启动。

#### 主要优点

主要优点是能够控制模块何时可访问。 培训团队可以将模块可用性与真实事件（如新产品发布、监管截止日期和内部计划）保持同步。 这确保学习者先完成必备内容，然后才能访问后续模块。

例如，第1组学生只能在第2周访问模块2，而模块3将保持锁定状态直到第3周，无需手动隐藏和取消隐藏内容或创建单独的课程版本。

此举可以提升学习者体验：学习者看到的课程结构不是面向技术上可访问但不应在该时（或应已经完成）访问的模块，而是允许他们开始的模块明显与预期的时间表一致。

#### 用例

* **基于同类群组的启用计划**：在此计划中，每周都会解锁一个新模块。 第1周的内容立即可用，第2周可见，但直到指定日期才能开始。 第3周遵循相同的门控过程。 学习者可以查看整个学习路径，但系统控制他们何时可以开始每个步骤。

* **有时限的产品或营销活动培训**：营销或产品团队可以创建培训模块，该模块只能在营销活动有效或特定版本的产品仍可用时访问。 此指定的开始窗口可确保学习者在指定的结束时间后，不会开始关于已停产产品版本的模块。

* **评估或考试环境**：组织可以打开一个模块（如测试）以创建一个定义明确的简短窗口（例如，“您可以在给定日期9:00到12:00之间的任何时间开始考试”）。 学习者无法在该窗口之外开始考试，这支持跨时区和同类群组的公平安排。

## 通过自定义LTI参数控制播放器语言

### 概述

增强功能允许使用LTI（学习工具互操作性）的外部平台在启动时指定Adobe Learning Manager内容的语言。 LTI消费者可以通过自定义LTI参数发送语言代码，而不是依靠学习者在流体播放器中更改语言。 然后，Adobe Learning Manager将使用此代码选择适当的语言变体。

### 新增功能

现在，作为LTI使用者的外部平台可以在启动ALM内容时传递自定义语言参数（和相关播放器设置）。 ALM读取此参数并：

* 设置相应的播放器语言。

* 配置多语言内容时，启动模块的相应语言变体。

这意味着首次学习者在外部平台中选择法语时，将看到ALM播放器和模块直接以法语启动，而无需调整ALM中的任何内容。

增强功能还适应外部平台将ALM视为无头内容播放器的情况。 例如，它允许通过发送额外的自定义参数来调整某些用户界面设置来隐藏导航元素和目录(TOC)。 这些设置与语言参数结合使用，使外部平台能够提供流畅的品牌化体验，同时仍利用ALM进行播放和跟踪。

### 主要优点

* **跨系统的一致语言体验**：当学习者在外部门户中选择一种语言时，该选择会立即反映在ALM中。 这可确保学习者不会遇到门户语言与课程语言不匹配的情况。 因此，他们不必在播放器中搜索语言切换。

* **特定于语言的报告**：在其平台上，语言选择与ALM一致，这提高了其分析和学习者跟踪的准确性。 此对齐方式还支持这样的配置：对于特定课程，ALM自己的语言控件在流体播放器中被有意禁用或隐藏。 在这些情况下，外部平台是语言的单一真实来源。

### 用例

* 一个重要的用例涉及使用基于LTI的集成的大型企业。 学习者首先在平台上注册并选择语言。 然后，他们通过LTI启动ALM培训课程。 借助此增强功能，当学习者选择西班牙语时，ALM模块会自动以西班牙语打开。 这意味着学习者无需调整ALM中的语言设置。 此外，基于语言的报告仍与学习者在ALM中看到的内容和体验保持一致。

* 另一个应用是在客户或合作伙伴门户中提供无头课程体验。 在此设置中，门户可以使用iframe嵌入ALM内容，而所有导航和语言用户体验(UX)在ALM之外进行管理。 通过使用自定义LTI参数，门户可以确保ALM播放器以正确的语言显示，并隐藏任何不必要的用户界面元素（如目录和导航按钮）。 如此一来，学习者便可感知到单个连贯的应用程序，而不是不连贯的工具集合。

* 对于使用其他LMS或学习平台以多种语言进行大规模培训的组织来说，这是有益的。 他们可以标准化该平台的使用以管理学习者配置文件、选择区域设置和显示目录。 同时，ALM是一个可靠的内容和跟踪引擎，在每次启动LTI时均尊重外部系统指定的语言偏好和用户交互。

## 针对讲师评估的核对表问题权重

### 概述

这项增强功能引入了加权清单，让讲师和管理人员使用分级评分和总分来评估学习者，而不是将每个清单问题都视为相等。 目标是通过对问题进行加权评价来促进清单的编制，这样可以在一个清单中反映不同行动或技能的相对重要性。

### 新增功能

核对清单将支持以下类型：

1. 是/否
行为与今天相同：每个问题为“是/否”，通过标准基于“是”响应的数量。

2. 相同权重的问题

   * 提问以数值刻度（默认为0-10）计分，其中：

      * 该量表上的最大/最小值可在清单级别自定义。

      * 比例表现在可以从0开始（之前的最低分数为1）。

   * 所有问题的最高分相同，因此清单的行为与每个问题的统一评分表相同。

3. 不同权重问题

   * 每个问题都有它自己的最高分数（权重）。

   * 通过标准取决于学习者在清单中可能获得的总分的百分比(例如，“如果学习者获得≥70%的可用总分，则通过”)。

对于所有清单类型：

* **审阅者**（讲师或经理）会根据配置的清单类型对学习者进行评估：

   * 选择“是/否”。

   * 根据定义的等级选择分数。

* **清单**&#x200B;报告已更新，以针对不同权重的问题包括：

   * 每个问题的最高分数。

   * 每个学习者在该问题中获得的分数。

这样，就可以根据预期的权重来分析整体性能和特定于问题的性能。

### 主要优点

* **更丰富、更现实的评估**：讲师可以通过对关键行为给予更多的点数，减少对次要行为的点数，从而反映现实世界的优先级，同时仍然使用适合观察任务或实际任务的核对表工作流程。

* **基于总分的通过/失败**：评估可以基于整体百分比分数，而不仅仅是多少个问题通过了阈值，更符合典型能力或评分计划。

* **更好的报告**：更新的清单报告会公开每个问题的最高分数和已实现分数，从而让计划所有者和质量团队识别具体的弱点并改进培训或评估指导。

### 用例

* **企业技能评估**：通过基于情景的实用核对表评估工程师，其中某些诊断或沟通步骤比表面步骤或低风险步骤更重要。 加权问题和总分通过标准使得这些评估更加可信并能预测真实世界的表现。

* **安全和合规性观察**：在医疗保健、制造业或外勤服务行业，关键安全步骤的最高得分可能较高，从而确保错过安全关键操作对总得分的影响大于错过一个次要的程序性步骤。

* **辅导和校准**：借助报告中每个问题得分的最大值和已获得的最大值，经理可以准确地看到学习者表现不佳的区域，并对讲师进行关于如何获得一致得分的校准。

## 对清单问题的多语言支持

### 概述

增强功能引入了对于清单问题的多语言支持，允许审阅者使用其首选语言对清单进行评估和评分。 此功能在多语言区域和全球部署中尤其有用，因为它允许作者为每个支持的内容语言创建本地化的清单问题，同时维护单个清单模块和一致的评估流程。

现在，在Adobe Learning Manager中：

* 所有面向学习者的模块(SCORM、PDF、HTML等)均以多种Content Language提供，允许学习者选择其首选的语言。

* 在清单模块中，审阅者（讲师/经理）会根据清单中定义的问题对学习者进行评估。

### 新增功能

**创作**

* 作者现在可以使用在课程级别选择的所有语言添加清单问题。

* 对于每个清单：

   * 作者应使用课程中提供的每种内容语言提供对应的问题文本。

   * 作者有责任确保每个问题的含义在不同语言之间保持一致。

**查看体验**

* 审阅者将看到以所选内容语言显示的清单问题和评估UI。

* 用一种语言评估问题时：

   * 逻辑上所有语言的评估（分数、是/否、状态）都相同。 它是一种包含多种语言视图的单一清单，而不是每种语言的单独清单。

**报告的角色**

清单报告将以用户的内容语言显示问题文本：

* 以每种语言运行报告的管理员或审阅者将看到该语言的本地化问题名称。

* 基本回答和分数保持不变；仅翻译问题标签。

### 主要优点

* **更好的审阅者体验**：审阅者可以完全用自己的语言工作，阅读问题和记录评估，而不会出现语言障碍。

* **法规和政策调整**：在语言平等要求的地区（例如，比利时的荷兰语/法语），检查清单现在可以符合与其他学习材料相同的标准，从而降低合规风险。

* **一致的评估逻辑**：在本地化文本时，评估和评分将共享到所有语言，从而确保结果具有可比性，并可集中管理。

### 用例

* 以多种语言开展业务的多国特许经营机构可部署单个课程和清单，同时仍可在每个地区提供本地化的审查者体验。

* 任何拥有本地讲师的全球企业（例如，欧洲、中东和非洲、拉美和亚太地区）都可让审阅者使用本地语言工作，同时共享相同的全球检查清单设计和报告。

## 包含审阅者注释功能的清单

### 概述

增强功能为清单评估引入了一项评论功能，允许讲师和经理等审阅者在提供数字分数的同时提供质量反馈。 学习者可在必要时看到此反馈。

目标是支持基于清单的评估，其中指导者的反馈与数字结果一样重要。 这包括突出显示特定优势、需要改进的领域或提供给定分数的上下文。

如今，审阅者可以：

* 按问题评估每个学习者的清单。

* 查看结果并重新评估失败的学习者。

在航空等现实场景中，外地培训员对车间代理和机场工作人员进行评估。 同样，中小企业的讲师和导师通常使用核对表来评估工作绩效。 但是，这些检查清单通常不包括用于获取与评估相关的叙述性反馈的结构化部分。

### 新增功能

#### 创作选项

作者可将每个清单配置为：

* 启用或禁用审阅者的注释功能。

* 决定是否应向学习者显示审阅者的姓名及注释。

这使组织能够根据其文化和隐私要求定制评论可见性。

#### 审阅者体验

启用注释时：

* 审阅者（讲师/经理）可以在评估清单时添加可选评论。

* 学习者可以根据清单设置选择注释是否对学习者可见。

如果他们重新评估学习者，则可以更新或更改评论以反映最新的评估。

#### 报告和通知

* 核对清单报告新增了一列审阅者评论栏，捕获了评估期间提供的评论。

* 每当进行清单评估时，学习者都会收到通知（平台内和电子邮件）。 这些通知包括：

   * 注释和

   * 审阅者的姓名（如果配置为可见）。

这样不仅可以存储反馈，还可以主动向学习者显示反馈。

### 主要优点

* **更丰富、类似指导的反馈**：数字分数辅之以上下文备注，使核对表成为指导的更有效工具，而不仅仅是合规性。

* **可跟踪性和可审计性**：组织会获得由谁来评估谁、何时以及他们说了什么（在受监管的环境和高风险角色中非常重要）的持久记录。

* **提高学习者参与度**：学习者会收到与特定评估相关的明确指导，这可以提高他们对期望和后续步骤的理解。

### 用例

* 拥有受监管环境的组织可以利用评论记录临床判断或程序反馈，以供在现场观察的工作人员使用。

* 航空和地勤组织可以附加有关运行绩效、安全实践和客户行为的详细注释，将核对表变成结构化的汇报工具。

* 在导师指导和SME评估中，讲师可以捕获到一些微妙而不仅不适合分数的情况，例如，“已妥善处理升级，但需要改进时间管理”或“出色的故障排除流程；错过了记录步骤”。

## 内容级多次尝试和测验报告

### 概述

>[!IMPORTANT]
>
>请注意，只有在帐户中启用该功能后，才能使用该功能。 联系ALM支持或客户成功经理。


目前，ALM支持在LMS级别通过多次测验尝试(MQA)功能进行多次尝试：

* 作者可以在课程级别（适用于课程中所有测验模块）或模块级别（每个测验模块）配置尝试次数。

* 尝试可以是：

   * 特定数字（例如，3次尝试），或

   * 无限次尝试，在LMS级别控制。

* 当学习者通过流体播放器使用某个模块，然后关闭播放器或完成模块时，会将该会话视为一次LMS尝试。

* 每次LMS尝试都会在L2测验报告中捕获为新行。

但是，如果内容文件本身（例如，清晰的SCORM测验）实施其自己的多次尝试逻辑，则ALM的L2测验报告目前无法正确区分或跟踪这些内部尝试。

此增强功能引入了内容级的多次尝试跟踪测验，允许Adobe Learning Manager在L2测验报告中准确地捕获内容本身内的每次尝试。 它适用于内容创作工具（如“清晰表达SCORM”）独立管理测验尝试的情况。 使用此功能，尝试操作将正确反映在ALM报告中，而不依赖于LMS级别的多重测验尝试(MQA)设置。

### 新增功能

#### 用于内容级别尝试的作者标志

* 当将内容上传到内容库时，作者现在可以指示特定内容文件中有多次嵌入的尝试。

* 这是按内容的设置，用于指示ALM将内容内定义的尝试视为真理来源。

#### 课程/模块行为

在课程中使用此类内容时：

* 模块会从内容而不是从LMS MQA导出其尝试。

* 学习者将仅看到一次LMS级别的尝试：

   * 课程概述和模块视图不会显示该模块的LMS“重新尝试”按钮。

   * 尝试处理（例如，测验中的重试）受内容本身管辖。

#### 报告

L2测验报告将更新，以将每次内容级别尝试视为单独的尝试行：

* 内容中配置的每一次内部测验尝试在L2测验报告中均显示为单独的行，就像今天的LMS级尝试一样。

* 每行的格式与L2报告中现有的多次尝试行的格式相同（相同的列、结构和语义）。

* 这样可提供一致的报告体验：

   * 无论尝试是由LMS MQA控制还是由内容控制，L2测验报告都会为每个尝试显示一行。

#### 主要优点

* 准确的SCORM尝试历史记录会测验尝试是否由工具（如Articulate ）在内部控制，而不强制执行LMS级别的MQA配置。

* 更干净的学习者体验：对于内容控制的尝试，学习者会看到LMS级别的单个插槽，无需与LMS重新尝试控件交互；所有重试都将在他们已了解的测试UI中处理。

* 灵活的体系结构：用户可以选择ALM MQA或内容级别尝试是否应驱动每个模块的行为，具体取决于其内容的创作方式以及他们更喜欢管理尝试的方式。

* 一致的报告模型：L2测验报告的下游使用者可以将每一行视为“一次尝试”，而不管尝试逻辑从何处开始。

#### 用例

* 使用清晰的SCORM的组织可以在SCORM包中保留独立的测验逻辑，同时无需额外的LMS配置即可在ALM中实现精确的尝试级别报告。

* 使用供应商提供的SCORM内容的组织可以避免修改或实施额外的尝试和使用LMS级别MQA的重试逻辑。

## 实例注册和会话出席的讲师二维码

### 概述

此增强功能增加了讲师自行生成二维码的功能，以便：

* 课程实例注册、

* 会话出席情况，或

* 同时注册+出席情况

在会话级别。 专为学习者进入物理或混合教室并要求快速、自助服务选项使用二维码注册和记录出勤情况而设计。

### 新增功能

#### 讲师生成的二维码

* 讲师可以在会话级别为以下项生成二维码：

   * 实例注册：学习者可进行扫描，以注册包含当前会话的实例。

   * 标记会话出席情况：学习者在会话期间/之后扫描，以记录该特定会话的出席情况。

   * 注册实例+标记会话出席情况：面向尚未注册但需要一步标记出席情况的访客的组合二维码。

* 讲师可以根据场景（注册、出勤或两者）导出所需的二维码。

#### 二维码打包

导出的二维码PDF将包括：

* 课程名称

* 实例名称

* 会话名称

这样，讲师和协调员可以轻松地为每次会话确定并打印正确的二维码。

### 主要优点

* **讲师自主权**：讲师无需再等待管理员创建二维码。 它们可以直接为每次会话生成它们，提高了灵活性，减少了协调开销。

* **更好的课堂物流**：对于上门或现场访问的受众（例如现场工作人员、车间工作人员或外部与会者），讲师可以使用二维码现场管理注册和出勤情况。

* **减少了管理员工作负载**：管理员团队可以专注于配置和治理，而不是处理每个会话的例行QR代码生成请求。

### 用例

* 如果组织有大量现场会话（例如，对专业人士的产品培训），讲师则可以打印特定于会话的二维码，只需一次扫描即可注册并标记出勤情况。

* 在零售、制造业和医疗保健培训中，学习者通常直接从教室参加会议，或不预先注册，可以在门口放置“注册+出席”二维码。 如此一来，学习者就可以通过手机自助服务注册和出席情况。

* 通过合作伙伴或客户的培训活动，现场培训师可以轻松适应会议室、其他会议或其他与会者的变化，而无需咨询管理员获取新的二维码。

## Captivate和ALM播放器改进

### 概述

此增强功能改进了在Adobe Learning Manager (ALM)播放器中播放Adobe Captivate内容的体验，尤其是在最近对Captivate的体系结构进行了更改之后。 目标是使学习者能够在ALM中本地使用Captivate模块，同时确保导航、完成跟踪和笔记记录清晰、一致且可靠。

### 新增功能

#### 统一目录体验

* 播放器的左侧将仅显示ALM目录。

* 在ALM中播放Captivate时，将隐藏模块自己的目录。

* 这样可消除重复，确保导航的单一真实来源，并释放屏幕空间。

#### 视觉完成反馈

* ALM目录将显示指示幻灯片级别完成的绿色刻度线（或等效视觉提示）。

* 学习者浏览Captivate幻灯片时，ALM目录会反映已完成的幻灯片，符合学习者对现代课程玩家的期望。

#### 上下文进度控件

* 播放器控件将根据幻灯片类型进行调整：

   * 对于视频幻灯片：

      * 显示时间进度条，反映视频播放。

* 对于非视频幻灯片：

   * 显示幻灯片导航控件（下一张/上一张幻灯片等）而不是无法正常工作的时间栏。

      * 这样可以避免显示某些幻灯片类型上不相关或不有效的控件。

#### 简化的导航

* 单独的模块导航栏(ALM)和课程导航栏将合并为一个直观的栏。

* 此统一导航：

   * 清楚区分了在Captivate模块中移动与返回课程/模块级别的移动。

   * 减少由具有重叠目的的多个条引起的混淆。

#### 可靠的注释链接

* 备注将链接到幻灯片编号而不是时间戳。

* 此更改：

   * 修复了由于缺少时间戳或不正确时间戳而导致导出失败的问题。

   * 确保可以将备注一致地导出为PDF，并在备注与其所属的幻灯片上下文之间具有可靠的映射。

### 主要优点

* 更干净的单人体验：学习者使用同一个目录和一个导航模型进行互动，减少混乱和认知负荷。

* 准确的完成和进度指示：幻灯片级别的勾选标记和上下文控件可帮助学习者了解自己的位置以及剩余内容。

* 更强大的笔记记录和导出功能：通过将笔记绑定到幻灯片而不是脆弱的时间戳，即使包含基于幻灯片的PDF内容，用户也可以重新获得可靠的笔记到Captivate工作流程。

* 保留作者工作流程：作者保留了Captivate直接发布到ALM的简单性，而学习者将获得现代、集成的播放体验，且没有额外的创作负担。

### 用例

* 依赖Captivate进行交互式模拟的支持计划可以将内容部署到ALM中，确保学习者的导航、完成跟踪和笔记功能一致。

* 使用Captivate作为主要内容创作工具的企业可以保持一键发布，避免混淆双目录和学习者无法正常工作的控件。

* 依赖于从ALM中的Captivate内容导出的注释（用于指导、合规性或记录）的企业可以访问以下内容：

   * 备注正确链接到幻灯片。

   * PDF按预期生成。

## 改进了“学习者成绩单”中花费的计算时间

### 概述

Adobe Learning Manager在2026年4月版中修订了“学习者成绩单”中计算学习时间的方式。 以前，如果学习者在未参与内容的情况下打开播放器，则报告逻辑可能会导致不准确的时间，从而导致差异。 现在，新方法根据用户参与来跟踪活动时间，特别是当选项卡处于焦点以及存在用户活动时。 此更改会产生更准确的数据。

此更新改进了报告和信息板，可帮助管理员更好地确保合规性并跟踪学习者进度。 发布后，请查看您的学习者成绩单以查看这些增强功能。

更新的计算方法侧重于实际参与，例如活动选项卡焦点和最近的用户交互，从而提高了以下领域时间报告的准确性：

* 学习者成绩单(UI)
* 管理员信息板指标
* 课程注册报告
* API和连接器

### 更改的内容

学习者成绩单中的&#x200B;**学习时间**&#x200B;列现在使用改进的逻辑来更准确地计算时间。 系统现在可以根据用户参与来区分活动期间和空闲期间，而不是简单地跟踪播放器的打开/关闭时间。

* **活动时间**：学习者处于活动状态的时间（例如，在正确的选项卡上，执行滚动或观看视频等操作）。
* **空闲时间**：学习者未参与的时间（例如，切换Tab键，10分钟后无活动），不包括在总数中。

这适用于大多数模块类型，但SCORM、Captivate和XAPI模块除外，它们会保留原始逻辑。

### 工作原理

新的计算方式因模块类型而异：

* **视频和音频模块**：播放内容时处于活动状态，即使学习者切换到其他选项卡也是如此。 跟踪回放时间不需要制表符焦点。
* **静态模块(PDF、PPT、Excel等)**：如果在过去10分钟内点击选项卡并执行活动（鼠标移动、滚动、单击、键盘输入），则处于活动状态。 如果连续10分钟没有活动，则变为空闲。
* **SCORM和Captivate**&#x200B;保留原始打开/关闭逻辑。
* **xAPI**&#x200B;现在使用基于选项卡的活动时间检测，其中仅在选项卡处于活动状态时计算时间。 请注意，不支持AICC内容&#x200B;****。
* **HTML、LTI和其他内容**：可能有所不同；请查看学习者成绩单以了解准确性。

扣除空闲时间，确保仅报告真正的参与时间。

>[!NOTE]
>
>如果您的笔记本电脑进入睡眠模式，则可能无法正确跟踪学习时间。 这是因为活动跟踪会在系统睡眠时暂停，仅在唤醒笔记本电脑时恢复。


### 摘要表

| **模块类型** | **活动时间（计数）** | **空闲时间（已排除）** |
| --- | --- | --- |
| **视频/音频** | 播放时间 | 未开始；已结束；已暂停&#x200B;**\>10分钟** |
| **静态(PDF/PPT/DOC)** | 过去&#x200B;**10分钟**&#x200B;内选项卡活动的&#x200B;**和**&#x200B;活动 | 无活动&#x200B;**\>10分钟**；选项卡处于非活动状态 |
| **SCORM** | 内容运行时报告的时间 | 无法检测到空闲 |
| **Captivate** | 基于幻灯片的计时 | 无法检测到空闲 |
| **** | 选项卡处于活动状态 | 选项卡处于非活动状态 |
| **HTML** | 选项卡处于活动状态的播放器打开时间 | 选项卡处于非活动状态 |
| **LTI制作者/使用者** | 如果LTI内容在ALM的播放器中播放（即，ALM使用在另一台充当制作者的LMS上托管的LTI内容），则应用此花费时间的逻辑。<br><br>但是，如果内容在LMS之外播放（即，内容托管在ALM中，则ALM是制作者，但播放发生在外部播放器中），则这部分时间计算逻辑不适用。  <br>**注意**：Adobe Learning Manager不支持LTI Consumer。 | 选项卡处于非活动状态 |

**注释**：

* **审阅和并行会话**：当满足上述条件时，计为活动。
* **所有设备、浏览器、语言**：已包含；同步后添加脱机移动设备使用。

### 新计算的好处

* **准确的报告**：消除无人值守的玩家的膨胀时间，提供逼真的学习持续时间。
* **更好的合规性**：支持准确跟踪强制培训（例如，一家公司要求每月5小时）。
* **改进的信息板**：用户活动图表和花费的时间报告现在反映了实际参与情况。
* **学习者见解**：帮助管理员识别正版进度并解决不参与的学习者。

### 报告和分析影响

* **学习者成绩单：**“花费的学习时间”现在反映了&#x200B;**实际参与情况**。
* **管理员信息板：**&#x200B;包含时间的指标（例如，“花费的时间”磁贴、趋势）将在之前空闲时间膨胀的情况下显示&#x200B;**更低但更逼真的**&#x200B;值。
* **课程注册报告：**&#x200B;与时间相关的字段在启动后采用&#x200B;**新计算**。
* **可比性说明：**&#x200B;由于未重新计算历史数据，因此跨发布日期的时间系列分析可能会显示&#x200B;**步骤更改**。 考虑在分析工具中按日期进行批注或分段。

### API和连接器

* **没有对报告所用时间的现有端点/字段进行架构更改**。
* **字段语义**&#x200B;已更新，以反映在功能启动&#x200B;_后_&#x200B;会话的&#x200B;**活动时间计算**。
* **消耗时间的连接器和导出**&#x200B;字段将在以后自动接收更新的值。

### 向后兼容性和数据迁移

* **历史会话：**&#x200B;未重新计算。
* **新会话：**&#x200B;使用&#x200B;**新**&#x200B;活动时间计算。
* **混合期间：**&#x200B;对于审核或纵向报告，请划分为&#x200B;**启动前/启动后**，以避免误读。

### 已知限制

* **交互式内容** (SCORM/Captivate)继续依赖内容提供的定时；无法检测内容中的空闲时间。
* **基于Iframe的内容**(HTML/xAPI)限制了细粒度交互的检测；请改用Tab键焦点。

### 常见问题解答

**此更新是否更改了历史记录？**

讨论区创建的帖子数这项更改仅适用于功能启动后的会话。

**如何验证更改？**

查看学习者成绩单中最近的模块；将时间与预期持续时间进行比较。

**这是否影响所有帐户？**

是的，这是针对所有Adobe Learning Manager帐户的全球更新。

**学习者是否需要执行操作？**

讨论区创建的帖子数更改是自动的，并且对学习者透明。

**如果学习者让内容保持打开状态该怎么办？**

现在将排除空闲时间，从而防止过度报告。

**当选项卡处于非活动状态时，视频/音频会话是否会自动暂停？**

讨论区创建的帖子数播放行为保持不变。 当暂停时间超过10分钟或者没有主动播放时，会排除时间。

**是否将反映脱机移动活动？**

是。设备同步时包括离线使用。

**如果仪表板现在显示较低的平均值，我该怎么办？**

在空闲时间先前已导致结果膨胀的情况下，预计会出现这种情况。 根据需要批注面板和调整目标。

**是否有任何先决条件？**

无；更改是自动进行的。























<!-- See this [article](/help/migrated/administrators/feature-summary/reports/learner-transcripts.md) for more information on Learner Transcript report.

The downloaded Learner Transcript report contains the new column: Mark Completed Date (UTC TimeZone).

![Learner Transcript reports showing marked completed dates (highlighted in yellow) for course completion tracking in Adobe Learning](/help/migrated/assets/mark-completion-column.png)
_Learner Transcript report displays a new column in yellow highlighting individual completion dates for each user_

## Enhanced User Report with extended data fields

**Overview**

The User Report now includes additional fields to improve user tracking and organizational mapping.

**What's new**

* Internal User ID column: Provides unique internal identifiers for smooth user tracking across different systems and API endpoints.
* Manager Email column: Includes direct manager contact information for organizational hierarchy tracking.

**Key benefits**

* Simplified user identification and eliminates issues when mapping users across multiple systems.
* Supports downstream user management workflows through integration capabilities.
* Improved organizational mapping and better understanding of reporting relationships.
* Maintains organizational boundaries and prevents accidental cross-communication.

### User Report with the new column

See this [article](/help/migrated/administrators/feature-summary/reports.md#user-activity-dashboards) to learn how to download the User Report. 

The downloaded User Report file contains the new columns: Internal User ID and Manager Email.

![User Report showing the internal user ID and manager email columns highlighted in yellow](/help/migrated/assets/user-report-columns.png) 
_User Reports highlighting internal user IDs and manager email addresses to streamline user management_

## FTP User Report with Internal User ID support

**Overview**

The FTP-based User Report now includes Internal User ID support, providing a unified approach to data export and integration for headless implementations.

**What's new**

* User Reports are now available through [Custom FTP](/help/migrated/integration-admin/feature-summary/connectors.md#custom-ftp) alongside existing reports (Gamification Transcripts, Learner Transcripts, Trainings Report).
* The Internal User ID column is now consistent across all export methods (FTP, Jobs API, and UI).

**Key benefits**

* Simplified data management with a single source for all necessary reports.
* Better data consistency by ensuring uniform user identification across reporting periods.
* Automated workflow support by enabling bulk operations and analytics workflows with consistent identifiers.
The User Report downloaded from FTP folder contains the new column, Internal User ID.

## Include suspended users in Learner Transcripts

**Overview**

Organizations can now include suspended users (those with disabled external profiles) in Learner Transcripts, ensuring comprehensive historical learning data retention.

**What's new**

* Configurable suspended user visibility with an account-level flag to include suspended users in the Learner Transcripts.
* Historical data retention even after deactivation of suspended external profiles.

**Implementation requirements**

* Contact your Customer Success Manager (CSM) to enable the account-level flag.

>[!NOTE]
>
>This flag is disabled by default for existing accounts and must be explicitly requested for new accounts.

## Scoped announcement permissions for custom administrators

**Overview**

Custom administrators can now create announcements, but only for their assigned user groups or catalogs. This prevents unintended communication across organizational boundaries.

**What's new**

* Custom administrators can only create announcements for users within their assigned scope.
* Announcements can be scoped to specific user groups or catalogs.
* Full administrators maintain visibility and control over all announcements, including those created by scoped custom administrators.

**Key benefits**

* Targeted communication ensuring announcements reach only relevant audiences.
* Reduced information overload by preventing irrelevant notifications from reaching unintended users.
* Maintains organizational boundaries and prevents accidental cross-communication.

**Important considerations**

* If a custom administrator's scope changes, affected announcements display a warning icon and require individual scope resets.
* Each announcement must be updated individually when scope changes occur.
* The Notification Announcement report shows only learners within the custom administrator's assigned scope.

**Use cases**

* Franchise organizations where regional managers need to communicate only with their franchisees.
* Large organizations with regional or departmental administrators targeting announcements to their teams.

### Create announcement for the assigned scope

A custom administrator can create announcements limited to their assigned user groups and catalogs, ensuring messages reach the right audience and preventing unnecessary notifications.

To create an announcement for the assigned scope:

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Announcement]** in the left navigation pane.
3. Select **[!UICONTROL Add]**. 
   
   ![](/help/migrated/assets/create-add-announcement.png)
   _Announcements page in Adobe Learning Manager, where administrators can create and manage announcements for targeted user groups_

4. Select the **[!UICONTROL Announcement Type]** from the dropdown menu.
        a. **[!UICONTROL As Notification]**
        b. **[!UICONTROL As Masthead]**
        c. **[!UICONTROL As Recommendation]**
        d. **[!UICONTROL As Email]**
5. Select **[!UICONTROL As Masthead]**. 
6. Select the language and upload an image for the masthead. 
7. Optionally, add a URL for the action button. 
   
   ![](/help/migrated/assets/announcement-screen.png)
   _Create Announcement screen allowing administrators to set announcement type, upload attachments, and add action buttons_

    The assigned scope is pre-selected in the **[!UICONTROL Scope]** section and cannot be modified by administrators.
    
    >[!NOTE]
    >
    >**[!UICONTROL For Notification]** and **[!UICONTROL Email]** announcements, they can include additional user groups and catalogs if these overlap with their assigned scope.

8. Select **[!UICONTROL Save]**.

Only learners within the custom administrator's scope will be able to view the announcement. See this [article](/help/migrated/administrators/feature-summary/announcements.md) to learn how to create multiple types of announcements. 

### Reset the scope by Custom administrators

Custom administrators can reset the scope of their published announcements if an administrator has changed the scope of them. Once the scope is reset, the updated scope will be applied to the announcement, and only learners within the new scope will be able to see the announcement.

To reset the scope:

1. Log in to Adobe Learning Manager as a custom administrator.
2. Select **[!UICONTROL Announcement]** in the left navigation pane.
3. Select **[!UICONTROL Published]** tab.
4. Select any announcement and then select setting icon. 
5. Select **[!UICONTROL Edit]**. 

   ![](assets/select-edit-published-announcement.png)
   _Announcement screen showing the published announcements with edit, publish and other options_

6. Select **Reset**. 

   ![](assets/reset-the-scope.png)
   _Announcement showing a scope change notification, with an option for custom administrators to reset and update the scope selection to reflect new access permissions_

The scope will be updated, and only users within the updated scope will be able to view the announcement.

### Edit the announcement through administrator UI

Administrators can view announcements created by custom administrators through their interface. They have the ability to edit these announcements only by modifying or removing the assigned scope. If scope changes are not made, administrators cannot make further edits to the announcement.

To edit the announcement through administrator UI:

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Announcement]** in the left navigation pane.
3. Select **[!UICONTROL Published]** tab.
4. Select any announcement and then select setting icon.
5. Select **[!UICONTROL Edit]**. 

   ![](assets/select-edit-published-announcement.png)
   _Announcement screen showing the published announcements with edit, publish and other options_

6. Select **[!UICONTROL Remove]**. 
   
   ![](assets/remove-the-scope.png)
   _Announcement screen indicating that scope must be removed to allow administrators to edit announcements created for scoped user groups_

Administrator can edit the announcement after removing the scope.

## Tag users in social boards

**Overview**

Social learning boards now support user tagging functionality, enabling more targeted discussions and improved collaboration within learning communities. Learners can be tagged in social learning posts and comments through the learner app, APIs, and Adobe Learning Manager reference site.

**What's new**

* **@username tagging**: Users can tag other board members using the "@username" format.
* **Scope-restricted tagging**: Only users with access to the specific board can be tagged, ensuring privacy and relevance.
* **Multi-channel notifications**: Tagged users receive both in-app and email notifications with direct links to relevant posts or comments.

**Key features**

* Users outside the board's scope cannot be tagged, preventing unwanted notifications.
* If a tagged user is deleted from the system, their mention appears as "anonymous".
* Tagging user groups or "@all" is not permitted to prevent notification spam.

**Use cases**

* Healthcare professionals seeking input from specific colleagues on medical cases.
* Subject matter experts being consulted on specialized topics.
* Team discussions requiring input from specific stakeholders.
* Knowledge sharing sessions with targeted expert involvement.

### Tag users in social board posts

Learners can now tag specific board members in posts or comments using @username. Tagging is limited to members with access to that board.

To tag users in a social board:

1. Log in to Adobe Learning Manager as a learner. 
2. Select **[!UICONTROL Social Learning]** in the left navigation pane.
   
   ![](/help/migrated/assets/select-social-learning-admin.png)
   _Enable collaborative learning by selecting Social Learning to access discussion boards, share insights, and tag users for interactive engagement_

3. Select **[!UICONTROL New Post]**.
   
   ![](assets/select-new-post.png)
   _Start a new discussion by selecting New Post in Social Learning to share knowledge with the tagged users_

4. Before tagging users, select the board from the **[!UICONTROL Post this to a Discussion Board]** option.

   ![](assets/select-boards-in-social-board.png)
   _Select a discussion board to post and tag users, enabling targeted collaborative conversations in Social Learning_

5. Type your post details, then tag a user by entering the @ symbol followed by their name (for example, @andrew). When you type @ followed by the first three letters of the user's name, it displays a list of matching users.
 
   ![](assets/type-a-user-tag.png)
   _Tag users in your discussion post by typing @ followed by the username to enable targeted collaboration within Social Learning boards_

6. Select the desired user from the list.
7. Select **[!UICONTROL Post]**. 

The tagged users receive both in-app and email notifications with a direct link to the post, making discussions more targeted and collaborative.

### Tag users based on the board's scope

Scope-restricted tagging allows users to tag only those learners who have permission to access a specific board. This helps maintain privacy by preventing tagging of users outside the scope. 

If you try tagging learners who are outside the board's scope, no suggestions will appear, and you won't be able to tag them. Refer to this [article](/help/migrated/administrators/feature-summary/social-learning-configurations-as-an-admin.md) to learn more about Social Learning Scope. 

## Tag deleted users in comments

If a user who has been deleted is tagged in a Social Learning post, their name will show as Anonymous in the post. The comment and tag remain visible for context, but profile link or details are not shown.

![](assets/deleted-users-tagged.png) 
_Social Learning post highlighting how a deleted user appears as Anonymous when tagged_

## Job Aids report with direct access links

**Overview**

The Job Aids report has been enhanced to include direct download links to job aids, streamlining content management and audit processes for administrators and authors.

**What's new**

* Job Aid Link column: Direct access to job aid files and external URLs from within the report.
* Role-based access control: Link accessibility depends on user roles and catalog permissions.
* Deleted job aids remain accessible if still linked to active courses.

**Key benefits**

* Direct file downloads and URL access from within the report.
* Eliminates manual effort in locating and downloading job aids for compliance or accessibility audits. 

**Use cases**

* Authors or administrators conduct regular accessibility audits on job aids, as required by large organizations.
* Any scenario where quick, role-based access to job aid files is needed for review or compliance.

### Job Aids Report with the new column

See this [article](/help/migrated/administrators/feature-summary/reports.md#job-aids-report) to learn how to download Job Aids Report.

The Job Aids Report can be downloaded from the Reports section and now includes direct download links for each job aid.

![](assets/job-aid-report.png) 
_Job Aids Report displays direct download links, making it easy to access and download job aids in Adobe Learning Manager_

## API updates

### Learner API enhancements for quiz performance tracking

**Overview**

The `GET /loResourceGrades` API has been enhanced to provide detailed quiz performance data, enabling more sophisticated analytics and automated decision-making.

**What's new**

The API response now includes two additional fields:

* **[!UICONTROL highestScore]**: The best score achieved by a learner across all quiz attempts
* **[!UICONTROL maxScore]**: The total possible score for the quiz

**API response example**

```
{
    "links": {
        "self": "https://learningmanagerstage1.adobe.com/primeapi/v2/loResourceGrades/course:15067_30122_41715_1_3400468"
    },
    "data": {
        "id": "course:15067_30122_41715_1_3400468",
        "type": "learningObjectResourceGrade",
        "attributes": {
            "completed": false,
            "duration": 0,
            "hasPassed": false,
            "highestScore": 0,
            "maxScore": 0,. 
            "progressPercent": 0,
            "score": 0
        },
        "relationships": {
            "loResource": {
                "data": {
                    "id": "course:15067_30122_41715_1",
                    "type": "learningObjectResource"
                }
            }
        }
    }
}
```

In response, **course:15067_30122_41715_1_3400468** is the ID of the Learning Object resource grade for which the information is being requested. The `learningObjectResourceGrad`e id can be obtained from the `GET /enrollments/{id}` API.  

**Key benefits**

* Enables detailed quiz performance analysis for learning effectiveness measurement.
* Supports progression rules based on highest achievement rather than most recent attempts.
* Provides complete picture of learner quiz performance over time.

**How the API works**

1. A user attempts a quiz multiple times; each attempt is recorded.
2. The API provides both the highest score achieved and the maximum possible score for the quiz.
3. External systems can use this data to trigger automated actions, such as enrolling users in new courses based on their best performance.

**Use cases**

* Headless learning systems require automated enrollment decisions.
* Learning analytics platforms tracking learner achievement patterns.
* Compliance systems with performance-based progression requirements.

### Migration API enhancements

**Overview**
Adobe Learning Manager now supports the migration of various data objects into an account via the migration process. This process can be initiated via both APIs and the User Interface. When a migration fails, errors are available for download via the interface. These errors are useful in debugging migration errors and managing the migration runs. 

With this release, the error logs will also be available to download via the APIs for efficient, programmatic error tracking and debugging.

**API changes**

There is a new migration API, `runStatus`, which allows integration administrators to check the status of migration runs triggered via the API, something not possible in previous versions of Adobe Learning Manager. 

Additionally, `runStatus` API now provides a direct link to download error logs (CSV) for completed runs. Note that the link is valid for seven days only, and the logs are retained for one month.

The `startRun` API's response has been updated to include the migration project ID, sprint ID, and sprint run ID, which are required to query the new status endpoint. 

#### runStatus API

**Description**

Retrieves the status of an existing migration run.

**Endpoint**

```
GET /bulkimport/runStatus
```

**Parameters**

* **migrationProjectId**: (Required). A unique identifier for a migration project. A migration project is used to transfer data and content from an existing Learning Management System (LMS) to Adobe Learning Manager. Each migration project can consist of multiple sprints, which are smaller units of migration tasks.

* **sprintId**: (Required). A unique identifier for a sprint within a migration project. A sprint is a subset of migration tasks that includes specific learning items (e.g., courses, modules, learner records) to be migrated from an existing LMS to Adobe Learning Manager. Each sprint can be executed independently, allowing for phased migration.

* **sprintRunId**: (Required). A unique identifier used to track the execution of a specific sprint within a migration project. It's associated with the actual migration process for the items defined in a sprint. The sprintRunId helps in monitoring, troubleshooting, and managing the migration job.

**Response**

```
{
  "sprintId": 2510080,
  "sprintRunId": 2740845,
  "migrationProjectId": 2509173,
  "startTime": 1746524711052,
  "endTime": 1746524711052,
  [
    {
      "id": 2609923,
      "lastHeartbeatTime": 1746524711052,
      "objectName": "content",
      "jobState": "COMPLETED",
      "errorCsvLink": "",
      "errorLogLink": "migration/5830/2509173/2510080/2740845/content_err.csv",
      "sequenceNumber": 1
    },
    {
      "id": 2609922,
      "lastHeartbeatTime": 1746524713577,
      "objectName": "course",
      "jobState": "WAITING_IN_QUEUE",
      "errorCsvLink": "",
      "errorLogLink": null,
      "sequenceNumber": 2
    }
  ]
}
```

#### startRun API

The `startRun` API response was updated to include three additional fields- migrationProjectId, sprintId, and sprintRunId. These fields allow users to track and query the status of specific migration runs using the new runStatus API.

```
curl -X GET --header 'Accept: text/html' 'https://learningmanager.adobe.com/primeapi/v2/bulkimport/runStatus?migrationProjectId=001&sprintId=10001&sprintRunId=7'
```

Produces the following response. The response contains:

* migrationId
* sprintId
* sprintRunId

**Response**

```
{
  "status": "OK",
  "title": "BULKIMPORT_RUN_INITIATED_SUCCESSFULLY",
  "source": {
    "info": "Success",
    "migrationInfo": {
      "migrationProjectId": "001",
      "sprintId": "10001",
      "sprintRunId": "7"
    }
  }
}
```

### Social API changes (user tag, comments, and replies)

**Overview**

Adobe Learning Manager now supports @user tagging functionality in Social Learning boards, enabling learners to mention and notify peers within posts, comments, and replies. This feature enhances collaboration and content discovery across the platform.

This release introduces new API capabilities to support user mentions, including enhanced POST and GET endpoints, as well as a new search functionality for tagged users.

**API changes overview**

* Updated POST APIs for creating posts/comments/replies with user mentions
* Updated GET APIs with user mention data in responses

**Format of user mentions**

A user is mentioned using the format: @(user:userId)

#### Create post with mentions

**Endpoint**

```
POST /primeapi/v2/posts
```

**Description**

Create a new social learning post with user mentions.

**Request body**

```
{
  "data": {
    "type": "post",
    "attributes": {
      "boardId": 13282,
      "accountId": 11152,
      "text": "<p>This is a new post mentioning @[user:11257229]</p>",
      "createdByUserId": 11257228,
      "postType": "discussion"
    },
    "id": null
  }
}
```

**Response**

Standard post creation response with mention data included in the _userMentions_ relationship.

#### Create comment with mentions

**Endpoint**

```
POST /primeapi/v2/comments
```

**Description** 

Add a comment to a post with user mentions.

**Request body**

```
{
  "data": {
    "type": "comment",
    "attributes": {
      "postId": 20746,
      "accountId": 11152,
      "text": "<p>Test Comment @[user:11257229]</p>",
      "createdByUserId": 11257228,
      "commentLevel": 0
    },
    "id": null
  }
}
```

#### Create reply with mentions

**Endpoint**

```
POST /primeapi/v2/replies
```

**Description**

Reply to a comment with user mentions.

**Request body**

```
{
  "data": {
    "type": "reply",
    "attributes": {
      "postId": 20746,
      "accountId": 11152,
      "text": "<p>Thanks for the update @[user:11257229]</p>",
      "createdByUserId": 11257228,
      "commentLevel": 1,
      "parentCommentId": 55621
    },
    "id": null
  }
}
```

#### Retrieve posts with mentions

**Endpoint**

```
GET /primeapi/v2/posts/{id}
```

**Description**

Retrieve post details, including mentioned users.

**Response**

```
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/posts/7522"
  },
  "data": {
    "id": "7522",
    "type": "post",
    "attributes": {
      "commentCount": 3,
      "dateCreated": "2025-06-10T11:33:29.000Z",
      "dateUpdated": "2025-06-25T14:52:04.000Z",
      "downVote": 0,
      "postingType": "DEFAULT",
      "richText": "<p>my updated fourth post @[user:14707776] second mention my first post</p>",
      "state": "ACTIVE",
      "text": "my updated fourth post @[user:14707776] second mention my first post",
      "upVote": 0,
      "viewsCount": 0
    },
    "relationships": {
      "createdBy": {
        "data": {
          "id": "14707776",
          "type": "user"
        }
      },
      "parent": {
        "data": {
          "id": "3971",
          "type": "board"
        }
      },
      "userMentions": {
        "data": [
          {
            "id": "14707776",
            "type": "user"
          }
        ]
      }
    }
  },
  "included": [
    {
      "id": "14707776",
      "type": "user",
      "attributes": {
        "avatarUrl": "https://cpcontents.adobe.com/public/images/default_user_avatar.svg",
        "binUserId": "45664b87-75a3-43ec-b0b7-5064958eac6f",
        "email": "user@example.com",
        "enrollOnClick": false,
        "fields": {
          "Location": "BLR"
        },
        "gamificationEnabled": true,
        "lastLoginDate": "2025-06-27T11:21:17.000Z",
        "name": "John Doe",
        "pointsEarned": 1690,
        "pointsRedeemed": 0,
        "preferredResolution": "AUTO",
        "profile": "admin",
        "roles": [
          "Learner",
          "Admin",
          "Author",
          "Instructor",
          "Integration Admin",
          "Manager"
        ],
        "state": "ACTIVE",
        "userType": "Internal"
      },
      "relationships": {
        "account": {
          "data": {
            "id": "9238",
            "type": "account"
          }
        }
      }
    }
  ]
}
```

### Social API changes (user search)

**Endpoint**

```
GET /primeapi/v2/users/search?q={searchTerm}&context=tagging
```

**Description**

Search for users available for tagging based on social scope settings.

**Request parameters**


* q (required): Search term (minimum 3 characters).
* context: Set to "tagging" to get users eligible for mentions.
* boardId (optional): Board ID to filter users based on access permissions.

**Response**

```
{
  "data": [
    {
      "id": "11257229",
      "type": "user",
      "attributes": {
        "name": "Jane Smith",
        "email": "jane.smith@example.com",
        "avatarUrl": "https://cpcontents.adobe.com/public/images/default_user_avatar.svg",
        "userType": "Internal",
        "state": "ACTIVE"
      }
    }
  ]
}
```

### Implementation guidelines

#### Character limits

* Posts: 4000-character limit applies, with each tagged user reducing available characters by a fixed amount.
* Comments: 1000-character limit.

#### Mention validation

* Users can only be tagged by username or email (not UUID).
* Internal users cannot tag external users and vice versa.
* Tagging availability follows existing social scope settings.
* Board permissions determine tagging eligibility (Public/Private).

#### Notifications

* Multiple mentions of the same user in one post result in a single notification.
* Original post owner receives notifications only when specifically tagged.

#### Error handling

* Invalid user IDs in mentions return validation errors.
* GDPR and soft-deleted users appear anonymous in tagged content.

### Language-based learner progress

Currently, learner progress is tracked only for the selected locale language, causing significant progress loss when switching languages/locales in the player. This limitation creates poor user experience where learners lose their learning progress when exploring content in different languages.

**Current issues**

* **Progress override**: The progress for each module in the player is tracked at both the user and module levels. This leads to a situation where a user's progress is overridden when they switch back to a previously used locale for the same module.
* **Progress reset**: For instance, if a learner achieves 75% progress in Locale A (English) and then switches to Locale B (Spanish), upon returning to Locale A, their progress resets to 0% instead of resuming from 75%.

To resolve these limitations, the API has been enhanced to support locale-specific progress tracking:

* **Locale-specific storage**: When a learner switches locales (for example, from Locale A to Locale B) within the player, the system now saves the progress state separately for each locale of the content.
* **Progress resumption**: When the user switches back to a previously used locale (from Locale B back to Locale A), the content resumes from where they left off in that specific locale.
* **Independent progress tracking**: Each locale maintains its own state of progress, allowing learners to explore content in multiple languages without losing their individual progress in each language.

#### API changes

The following APIs have been enhanced to support the new locale parameter:

* GET Player State API
* POST Player State API

#### GET Player State API

**Endpoint**

```
GET /primeapi/v2/users/{userId}/playerState
```

**Description**

Retrieves the current state of a learning object for a specific user and locale.

**Parameters**

|Parameter |Type |Location |Required |Description |
|---|---|---|---|---|
|userId |String |Path |Yes |Unique identifier of the user |
|loId |String |Query |Yes |Learning Object identifier in format lo:{id} |
|loResourceId |String |Query |Yes |Learning Object resource identifier in format course:{loId_loInstanceId_moduleId_moduleVersion}|
|csrf_token |String |Query |Yes |CSRF protection token |
|locale |String |Query |Optional |Locale identifier for language-specific progress (e.g., "en-US", "es-ES") |

**Example request**

```
GET /primeapi/v2/users/12345/playerState?loId=lo:67890&loResourceId=course:67890_1_mod123_v2&csrf_token=abc123&locale=en-US
```

**Response behavior**

* If the locale parameter is provided and a locale-specific state exists, the API returns the progress for that locale.
* If the locale parameter is provided but no locale-specific state exists, the API performs a fallback search for the default state.
* If the locale parameter is omitted, the API returns the default state (maintains backward compatibility).
* For headless requests where the locale is null, the API falls back to the default state lookup.

#### POST Player State API

**Endpoint**

POST /primeapi/v2/users/{userId}/playerState

**Description**

Updates or creates the current state of a learning object for a specific user and locale.

**Parameters**

|Parameter |Type |Location |Required |Description |
|---|---|---|---|---|
|userId |String |Path |Yes |Unique identifier of the user |
|loId |String |Query |Yes |Learning Object identifier in format lo:{id} |
|loResourceId |String |Query |Yes |Learning Object resource identifier in format course:{loId_loInstanceId_moduleId_moduleVersion} |
|csrf_token |String |Query |Yes |CSRF protection token |
|locale |String |Query |Optional |Locale identifier for language-sp|

**Request body**

The request body contains the Learning Object state data specific to the locale.

**Example request**

```
POST /primeapi/v2/users/12345/playerState?loId=lo:67890&loResourceId=course:67890_1_mod123_v2&csrf_token=abc123&locale=en-US
```

```
{
  "progress": 75,
  "completionStatus": "incomplete",
  "timeSpent": 1800,
  "lastAccessedPage": 5,
  // Additional state data
}
```

The API creates or updates the Learning Object state for the specified locale.

## Go1 integration enhancements

**Overview**

Go1 integration is enhanced to allow direct curation of Go1 courses for creating Learning Programs (LP) within Adobe Learning Manager. This update supports the inclusion of Go1 courses in recurring certifications and introduces a new version of the Go1 content hub experience, enabling more efficient course curation.

**What's new**

* Create and manage playlists directly within Go1 using AI chat assistance or manual selection.
* Include Go1 courses in recurring certification cycles with automatic progress reset.
* Upgraded content discovery interface for improved browsing and content curation.

**Key benefits**

* AI-assisted playlist creation significantly speeds content grouping and delivery.
* Enables use of Go1 content for recurring regulatory training requirements.
* Clear preview-and-purchase model supports informed content investment decisions.
* Improved discovery and curation tools for better content management.

**Important notes**

* All Go1 features require an active Go1 license.
* Previous free Go1 content will be decommissioned. Organizations must preview and purchase required content bundles.
* Administrators and authors can create and manage playlists; learners maintain view-only access.

**Use cases**

* Organizations requiring extensive external content libraries for comprehensive training programs.
* Compliance-focused training programs needing regular content updates and delivery cycles.
* Learning teams are seeking to reduce content curation overhead through AI assistance.

### Add Go1 playlist to a Learning Path

Administrators can create a learning path that includes a Go1 playlist, so learners can access selected third-party courses as part of their training.

To create a learning path:

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Learning Paths]** in the left navigation pane. 
3. Select **[!UICONTROL Add]**. 

   ![](assets/select-add-to-lp.png)
   _Select Add in the Learning Paths section to create and organize new structured training programs for your learners_

4. Type the required details and select **[!UICONTROL Save]**. See this [article](/help/migrated/administrators/feature-summary/learning-paths.md) for more information. 
5. Select **[!UICONTROL Add Go1 Courses]**.

   ![alt text](assets/select-go1-courses.png)
   _Add Go1 courses to your Sales Engineers Skill Development playlist to expand learning options with curated third-party content_

6. In the **[!UICONTROL Library]**, search for and select **[!UICONTROL Create playlist]** and choose from one of the following:
    a. **[!UICONTROL with AI]**: Create a playlist with the help of AI.
    b. **[!UICONTROL by myself]**: Create a playlist by manually adding courses to it. 

**Create a playlist with AI**

Administrators can type the playlist description in the AI prompt. The AI will curate the related courses and create a playlist based on the requirements. AI generates playlists by interpreting the learning goal or prompt provided by the user. When creating a playlist, admins can select to curate content 'with AI' which allows the system to use large language models to understand the specified learning objectives and content preferences like duration and type. The AI then searches the content library for relevant learning objects that match these criteria.

To create a playlist with AI:

1. Select **[!UICONTROL Create playlist]** and then select **[!UICONTROL with AI]**.
   
   ![](assets/select-by-AI-playlist.png)
   _Create curated playlists with AI, which enables automated course recommendations tailored to learner needs_

2. Type a short description about your playlist in the **[!UICONTROL Enter your learning goal]** text field.
3. Select **[!UICONTROL Next]**. 
   
   ![](assets/type-a-prompt.png)
   _Type your learning goal to create a custom playlist, helping Adobe Learning Manager recommend targeted courses tailored to your learners' needs_

4. Choose the skills from the list.
   
   ![](assets/select-skills.png)
   _Choose the skills from the list to curate the courses for the Sales Engineer_
5. Select the course duration and type for your playlist.
6. Select **[!UICONTROL Generate playlist]**. The playlist is created with 10 courses, and administrators can use it to create a Learning Path.
   
   ![](assets/created-playlist.png)
   _Review your curated Sales Engineer Skills Enhancement Playlist in Adobe Learning Manager_
7. Select **[!UICONTROL Add to Library]**.
8. Select **Yes** in the confirmation prompt.
9. Select the playlist from the **[!UICONTROL Select playlist to import prompt]**. 

   ![](assets/add-playlist-to-lp.png)
   _Select and import the Sales Engineer Skills Enhancement Playlist from the Go1 Library in Adobe Learning Manager_

10. Select **[!UICONTROL Add Playlists to Learning Path]** and then **[!UICONTROL Publish]**. 

The courses in the playlist will be added to the Learning Path. Administrators can then enroll learners, who can immediately begin taking the courses.

**Create a playlist manually**

Manually select courses that best match learners' requirements and curate additional relevant courses.

To create a playlist manually:

1. Select **[!UICONTROL Create playlist]** and then select **[!UICONTROL by myself]**.
   
   ![](assets/select-manual-playlist.png)
   _Manually create a playlist giving administrators full control to curate courses based on specific learner needs_

2. Type the title and description of your playlist.
 
   ![](assets/type-title-and-description.png)
   _Add a title and description to your playlist in Adobe Learning Manager to clearly define its purpose and help guide learners toward targeted skill development_

3. Select **[!UICONTROL Create]**. 
4. Select **[!UICONTROL Add item]** to add the related courses. 
   
   ![](assets/add-items.png)
   _Add items to your Sales Engineers Skill Development playlist in Adobe Learning Manager to curate targeted courses_

5. Search and select the required courses. 

The playlist has been created with related courses, and administrators can use it to create a learning path. 

## Save player state progress for languages

**Overview**

The Fluidic Player now saves your progress separately for each language within a module. This means you can switch between languages and pick up exactly where you left off in each one, instead of losing your progress and starting over.

**Key benefits**

* Jump between languages and resume from your exact position in each one.
* Perfect for learners who need to access content in multiple languages during their learning journey.
* Complete the module in any language while maintaining progress in all languages you've accessed.

**Use cases**

* Global organizations with employees who speak multiple languages and may need to reference content in their native language and English.
* Compliance training where learners might start in one language but need to complete in another for certification purposes.
* Technical training programs where learners might understand concepts better in their native language but need English terminology for their work.

**Important notes**

* The Fluidic Player's language preference is retained within a session. If a learner changes the language and moves to another module, the new language is used for subsequent modules, as long as the player remains open.
* The grade (completion status) is still tracked at the module level, not per locale. The first locale in which the completion criteria are met will update the grade for the module. If a learner completes the module in one language and then switches to another, any further grade updates will be overwritten from the previous grade, but progress for each locale is still preserved.

## Custom roles import support in incremental user import

Adobe Learning Manager now supports custom role imports in the existing multi-incremental user import workflow (regular full user import + incremental enabled flow). This enhancement allows role.csv and user_role.csv files to be uploaded and processed incrementally, without requiring full data uploads each time.

Previously, role.csv and user_role.csv files could only be uploaded in full mode, meaning administrators had to include all previously added role definitions and assignments in every upload. With this new incremental support, only new or modified role data needs to be uploaded, reducing overheads and improving efficiency.

**What's new**

1. Incremental support for custom roles and role assignments:

    * role.csv  and  user_role.csv can now be processed incrementally in the multi-file incremental workflow.
    * No need to upload all existing role and user role data with every import.

2. Enhanced multi-incremental workflow implementation:

    * Create separate folders in FTP for each uploaded user import file.
    * Each folder contains:

        * The user import file- (File1.csv)
        * Corresponding role and role assignment files- (File1_role.csv, File1_user_role.csv)

    For example, user1.csv corresponds to user1_role.csv (custom roles) and user1_user_roles.csv (user-role mapping).

    **Example FTP structure before processing:**

    ```
    import/user/internal/  
         File1.csv  
         File2.csv  
        File3.csv  

    UserRole/  
        File1_role.csv  
        File1_user_role.csv  
        File2_role.csv  
        File2_user_role.csv  
        File3_role.csv  
        File3_user_role.csv  
    ```
 
3. Adobe Learning Manager also supports up to 20 incremental user CSVs and their corresponding custom roles CSVs, making it suitable for large-scale operations.

**Use cases**

* Global companies manage regional teams by uploading multiple incremental user files for each region (EU, America, Asia), allowing administrators to update users and assign new roles for each region in a single workflow.
* Large enterprises automate onboarding and permissions by regularly ingesting incremental user updates from HR systems. This supports seamless updates to user profiles and granular role assignments without manual intervention.

### New columns added to CSV files

Three new columns have been introduced to enhance the data captured in user, role, and user-role CSV exports/imports:

* **User Registration State (user.csv)**: Indicates the current registration status of the user.
* **Role State (role.csv)**: Indicates the current status of roles within the system.
* **User Role State (user_role.csv)**: Indicates the status of the user-role association. 

>[!NOTE]
>
>The above CSV changes apply only to the accounts that use incremental users.

Download the [sample CSVs](assets/sample-csv-Incremnetal.zip) here. 

## Reset recommendations in Salesforce app

**Overview**

Previously, learners using the Adobe Learning Manager Salesforce app could only select roles and recommendation preferences once. If their role changed, they were required to access the native Adobe Learning Manager app to update their profile and receive relevant course recommendations. This made the learning experience and contributed to lower engagement within the Salesforce environment.

**What's new**

Adobe Learning Manager now features a  **[!UICONTROL Reset Interests]** button within the Salesforce app. Learners can now reset their roles and learning preferences without needing to leave Salesforce or sign in into the native Adobe Learning Manager app. This enhancement streamlines access to personalized learning content, ensuring recommendations remain relevant as users' roles evolve.

**Use cases**

* Learners who change job roles, teams, or responsibilities can quickly reset their preferences to receive updated and relevant course recommendations all within the Salesforce app.
* By removing the need to switch to the native Adobe Learning Manager app, the learning journey is smoother, encouraging ongoing engagement and consumption of recommended content through Salesforce.
* Administrators benefit from higher rates of learning completion and better alignment between user roles and recommended content, without extra support or guidance on switching platforms.

### Reset interest in the Salesforce app

To reset the interests and recommendations from the Salesforce app:

1. Log in to Adobe Learning Manager app for Salesforce as a learner.
2. Select **[!UICONTROL Reset Interests]** option at the bottom.

The learner's recommendation or interest will be reset from the Adobe Learning Manager Salesforce app. 

## Create learning portals with Experience Builder

>[!IMPORTANT]
>
>We are excited to announce that Experience Builder, the innovative tool for creating customizable learning portals, will be available following the October 2025 release of Adobe Learning Manager.
>
>Stay tuned for more updates as we approach the release date. We look forward to seeing how you use Experience Builder to transform your learning portals.
>
>For any questions or additional information, contact your Customer Success Manager.

**Introduction**

Experience Builder is a no-code/low-code tool in Adobe Learning Manager that helps you create customized learning portals. It allows you to design branded, user-friendly learning portals without needing technical skills or extensive coding knowledge.
With Experience Builder, you can create new pages, menus, and widgets to deliver personalized learning experiences for your audience quickly and easily. With Experience Builder, you can quickly create new pages, menus, and widgets to deliver personalized learning experiences for your audience.

**Problem statement**

Before Experience Builder, organizations faced several challenges:

1. **Limited customization**: Portals had fixed designs with few options to reflect your brand. Administrators could only make basic changes, such as modifying headers, footers, or colors, which limited the ability to create unique experiences.
2. **Cost**: Building custom portals required expensive developers and long timelines, often taking 6 to 9 months to complete. This approach increased the total cost of ownership and delayed deployment.
3. **Generic experiences**: Everyone saw the same content, even if it wasn't relevant to their role or needs. This lack of personalization reduced learner engagement and satisfaction.
4. **Technical barriers**: Non-technical administrators struggled to create or update portals because they needed coding knowledge or external support.

Experience Builder solves these problems by providing a simple, no-code/low-code solution for creating personalized, branded portals.

It allows administrators to design portals that meet their organization's needs without relying on technical expertise or external developers.

**Key benefits**

**Easy customization**

* Design portals that match your brand with custom headers, footers, logos, and layouts.
* Use widgets to add dynamic content like courses, categories, and HTML elements.
* Create pages and menus tailored to specific audiences, ensuring learners see relevant content.

**No-code/low-code solution**

* Administrators can create and manage portals without coding knowledge, making it accessible to non-technical users.
* Drag-and-drop functionality simplifies the process of building pages and menus.

**Personalized learning**

* Configure pages and menus to display content relevant to specific user groups, such as sales teams, designers, or engineers.
* Use hidden pages to provide exclusive content accessible only through direct links.

**Global reach**

* Create multilingual pages to support learners around the world.
* Localize content to cater to diverse audiences and improve accessibility.

**Mobile-friendly**

* Learners can access content on any device, including phones and tablets.
* Preview pages in both desktop and mobile views to ensure a smooth experience.

**Real-world use cases**

**Branded portals**

* Create a learning portal that looks like your company's website, complete with logos, colors, and layouts.
* For example, a healthcare company can design a portal that matches its corporate branding while integrating learning content.

**Role-based learning**

* Build pages for specific roles, like engineers, sales teams, or designers.
* For instance, sales teams might see product training, while engineers access technical courses.

**Product training**

* Set up separate pages for different products, such as Photoshop, Illustrator, or other offerings.
* Each page can include widgets displaying courses, certifications, and resources related to the product.

**Employee and customer training**

* Use the portal for onboarding new employees, training external partners, or educating customers about your products.
* For example, a software company can create a portal for customer tutorials and troubleshooting guides.

**Localized content**

* Offer content in multiple languages for global learners.
* For instance, a multinational company can create pages in English, Spanish, and French to cater to its diverse workforce.

### Building blocks of Experience Builder

The main components and building blocks of Experience Builder are structured to provide flexibility, ease of use, and targeted learning experiences. Below is a detailed breakdown:

#### Pages

Pages are the foundation of building a learning portal in Experience Builder. Administrators can create new pages tailored to specific audiences or purposes. Additionally, administrators can:

* Create custom pages with flexible layouts (rows and columns).
* Add widgets to populate pages with content.
* Manage page lifecycle with draft and published states.
* Hide pages from menus while keeping them accessible via direct links.

For example, a page for sales training might include widgets displaying relevant courses, testimonials, and a calendar of upcoming sessions.

#### Menus

Menus organize pages into navigable structures for learners. Administrators can:

* Create custom menus to group pages for specific user groups.
* Add hierarchy and ordering to prioritize visibility for specific audiences.
* Include submenus for grouping related pages.

For example, a menu called Resources might include pages for eBooks, videos, and FAQs.

#### Widgets

Widgets allow administrators to add dynamic content and functionality to pages. The following widgets are available:

* Calendar
* Categories
* Compliance Status
* Courses & Paths
* Content Box
* Gamification
* HTML
* Iframe
* My Learning
* Social Learning

For example, a page might include a Courses & Paths widget to display recommended courses and a Calendar widget for upcoming training sessions.

#### Branding tools

Experience Builder provides tools to customize the appearance of the portal. Administrators can:

* Customize headers, footers, and layouts to match corporate branding.
* Use CSS and JavaScript for advanced styling.

For example, a healthcare company might use branding tools to create a portal that matches their corporate website's look and feel.

### Get started with Experience Builder

A software company wants to build a training portal for its customers. The portal will have pages for different products like Photoshop and Illustrator, organized in menus. It will include widgets that show courses, certifications, and upcoming training sessions.

#### Create a page

To create a page in Adobe Learning Manager:

1. Log in to Adobe Learning Manager as an administrator. 
2. Select **[!UICONTROL Branding]** in the left navigation pane. 
3. Select **[!UICONTROL Custom Pages]**.
4. Select **[!UICONTROL Create page]**.

   ![](assets/select-create-page.png)
   _Custom Pages screen showing the Create page option to design new custom learning experiences_

5. Type the **[!UICONTROL Page name]** (for example, Photoshop training).
6. Type the **[!UICONTROL Page description]** (for example, Learn how to use Photoshop effectively). 
7. Select the page type from the following:

    * **[!UICONTROL Build using ALM widgets]**: Administrator can create a page using the existing Adobe Learning Manager widgets.
    * **[!UICONTROL External page]**: The administrator can add a URL for the external page. If you select the page type as external, add the URL in the Page URL text field.

8. Select the **[!UICONTROL Change icon]** to change the page's icon.
 
   ![](assets/create-page-screen.png)
   _Courses page creation screen displaying options to type the page name, description, type, and icon for a customized learner page_
9. Select **[!UICONTROL Add New Language]** to add the default language for the page. 
10. Select **[!UICONTROL Save]**. 

The page has been created and saved as a draft in the Custom Pages section. Administrators can edit and design the drafted pages using the widgets. 

#### Design page in Experience Builder

Adobe Learning Manager enables administrators to design pages tailored to their requirements using customizable widgets.
To design the page in Experience Builder:

1. Log in to Adobe Learning Manager as an administrator. 
2. Select **[!UICONTROL Branding]** in the left navigation pane. 
3. Select **[!UICONTROL Custom Pages]** and then select the required page. 
4. Select **[!UICONTROL Page Design]**.  
5. Select **[!UICONTROL Edit]**. 
 
   ![](assets/edit-the-page.png)
   _Edit mode allows administrators to design course pages by organizing sections and adding widgets in their preferred language_

6. Choose the options from **[!UICONTROL Select section layout]** dropdown.
7. Select a section from the following based on the number and size of the widgets you want to add in the section:

    * **[!UICONTROL 1 column-Full section width]**: Content spans the entire section width for maximum space.
    * **[!UICONTROL 2 columns-1/2 section width each]**: Two equal-width columns split the section evenly.
    * **[!UICONTROL 2 columns-2/3 and 1/3 section width respectively]**: Main content takes two-thirds, side content one-third.
    * **[!UICONTROL 2 columns-1/3 and 2/3 section width respectively]**: Side content takes one-third, main content two-thirds.
    * **[!UICONTROL 3 columns-1/3 section width each]**: Three equal-width columns divide the section into thirds.
 
   ![](assets/select-section-layout.png)
   _Section layout selection dialog allows administrators to choose single or multi-column widget arrangements for custom page design_

8. Select **[!UICONTROL Proceed]**.
9. Select **[!UICONTROL Add widget]**.
 
   ![](assets/select-add-widgets.png)
   _The page design screen allows administrators to select and add widgets to customize their course pages_

10. Choose the required widget and then select **[!UICONTROL Proceed]**. 
11. Configure the widget and select **[!UICONTROL Add widget]**. See this [section](#add-and-configure-widgets) for adding and configuring the widgets.
12. Select **[!UICONTROL Save]** and choose from the following options:

    * **[!UICONTROL Save as Draft]**: The page will be saved as a draft. The administrator can edit the page later.
    * **[!UICONTROL Save & Publish]**: The page will be published, and the administrator can add this page to the Menu. 
   
   ![](assets/select-save-options.png)
   _Save options allow administrators to choose between saving a page as a draft for future editing or publishing it for learner access_

The page can be saved as a draft or published. Administrators can edit drafts before publishing and can also update and republish published pages.

#### Add and configure widgets

**Calendar widget**

This widget visually presents courses and schedules in calendar format. It supports filters by catalog, enrollment status, location, product, and role. The responsive design adapts to various grid sizes.

To configure the Calendar widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder). 
2. Select **[!UICONTROL Calendar]** and then select **[!UICONTROL Proceed]**.
 
   ![](assets/select-calendar.png)
   _Widget selection screen highlighting the Calendar widget option to display training sessions in a calendar_

3. Type a **[!UICONTROL Widget title]** and **[!UICONTROL Widget description]**.
 
   ![](assets/configure-calendar-widget.png)
   _Calendar widget customization screen, where administrators can set the widget title, description, and select catalogs_

4. Select a catalog by searching to display its courses and learning paths within the **[!UICONTROL Calendar]** widget.
5. Select **[!UICONTROL Add Widget]**.

The Calendar widget will be added to the page. Administrator can add other widgets and publish the page.

**Categories widget**

This widget displays categories (e.g., roles, catalogs) as tiles, leading to filtered views or specific pages.

To configure the Categories widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder).  
2. Select **[!UICONTROL Categories]** and then select **[!UICONTROL Proceed]**. 
 
   ![](assets/select-categories-widget.png)
   _Widget selection screen highlighting the Categories widget option to organize learning content by catalog, product, or role for easy navigation_

3. Select the details to display on the category cards:

    * **[!UICONTROL Category Image]**
    * **[!UICONTROL Category Description]**

4. Type a **[!UICONTROL Widget title]** and **[!UICONTROL Widget description]**.
5. Search for and choose a catalog from the **[!UICONTROL Category source]**.
 
   ![](assets/configure-calendar-widget.png)
   _Configure Categories widget options to set widget title and description, and select the category source_

6. Select **[!UICONTROL Add Widget]**.

The Categories widget will be added to the page. Administrators can add other widgets and publish the page.

**Compliance widget**

This widget supports filtering similar to a calendar, but is focused on compliance-related learning objects. It allows learners to modify or remove compliance label filters dynamically.

To configure the Compliance widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder).  
2. Select **[!UICONTROL Compliance Status]** and then select **[!UICONTROL Proceed]**.
 
   ![](assets/select-compliance-status.png)
   _Widget selection screen highlighting the Compliance Status widget used to display learner enrollments with deadlines and status indicators_

3. Type a **[!UICONTROL Widget title]** and **[!UICONTROL Widget description]**.
 
   ![](assets/configure-compliance.png)
   _Compliance Status widget screen, where administrators can set the widget title and description to display enrollment deadlines and status for learners_

4. Select **[!UICONTROL Add widget]**.

The Compliance status widget will be added to the page. Administrators can add other widgets and publish the page.

**Courses and paths widget**

This widget displays a strip of course or path tiles, customizable to show different details. 

To configure the Courses and Paths widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder). 
2. Select **[!UICONTROL Courses & Paths]**.
 
   ![](assets/select-course-path.png)
   _Widget selection screen highlighting the Courses & Paths widget for displaying courses, learning paths, certifications, and job aids as interactive cards for learners_

3. Select **[!UICONTROL Proceed]**. 
4. Type **[!UICONTROL Widget title]** and **[!UICONTROL Widget description]**. 
5. Select the catalogs or manually choose up to 25 courses to display.
    
   ![](assets/configure-course-paths.png)
   _Courses & Paths widget where administrators set the widget title, description, and select courses or learning paths to display as interactive cards_

6. Select **[!UICONTROL Add widget]**. 

The Courses & Paths widget will be added to the page. Administrators can add other widgets and publish the page.

**Content Box widget**

This widget allows creating sections with titles, descriptions, images, and CTAs. 

To configure Content Box widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder).
2. Select **[!UICONTROL Content Box]** and then select **[!UICONTROL Proceed]**. 
 
   ![](assets/select-content-box.png)
   _Widget selection screen highlighting the Content Box widget for displaying custom images, text, and action buttons to enhance learner engagement_

3. Type the **[!UICONTROL Title]** and **[!UICONTROL Description]**.
4. Type the text into the **[!UICONTROL Action button label]** and provide a link. 
5. Select any of the options for Background fill:

    * **[!UICONTROL Color]**: Select the color from the color picker or type the color code in the text field.
    * **[!UICONTROL Image]**: Browse and upload a picture.

6. Adjust the box height using the **[!UICONTROL Content box height]** option. 
7. Select the text formatting options.
 
   ![](assets/configure-content-box.png)
   _Content Box widget customization screen, where administrators can enter a title, description, action button label, and link_

8. Select **[!UICONTROL Add widgets]**. 

The Content Box widget will be added to the page. Administrators can add other widgets and publish the page.

**Gamification widget**

This widget shows gamification and points earned by learners in a leaderboard format. It has been updated for Experience Builder with a name, description, and localization customization.

To configure the Gamification widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder).
2. Select **[!UICONTROL Gamification]** and then select **[!UICONTROL Proceed]**. 
 
   ![](assets/select-gamification.png)
   _Widget selection screen highlighting the Gamification widget used to display learning activities and achievements on the leaderboard_

3. Type the **[!UICONTROL Widget title]** and **[!UICONTROL Widget description]**. 
4. Select **[!UICONTROL Add widgets]**. 

The Gamification widget will be added to the page. Administrators can add other widgets and publish the page.

**HTML widget**

This widget allows custom HTML, CSS, and JS code to be embedded, providing flexibility for static content like testimonials. 

To configure the HTML widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder).
2. Select **[!UICONTROL HTML]** and then select **[!UICONTROL Proceed]**. 
 
   ![](assets/select-html.png)
   _Widget selection screen highlighting the HTML widget for customizing pages using HTML, CSS, and JavaScript code_

3. Type your **[!UICONTROL HTML]**, **[!UICONTROL CSS]**, and **[!UICONTROL JavaScript]** code in the respective fields. 
4. Select **[!UICONTROL Add widget]**. 

The HTML widget will be added to the page. Administrators can add other widgets and publish the page.

**IFrame widget**

This widget allows embedding external web applications or webpages directly within the page. Includes options to name, describe, and localize the iframe content.

To configure the Iframe widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder).
2. Select **[!UICONTROL Iframe]** and then select **[!UICONTROL Proceed]**. 
 
   ![](assets/select-iframe.png)
   _Widget selection screen highlighting the Iframe widget for embedding external applications or web pages within a selected section_

3. Type the URL in the **[!UICONTROL Page linked to Action button]** option.
4. Adjust the Iframe height using the **[!UICONTROL Iframe height]** option.     
 
   ![](assets/configure-iframe.png)
   _Iframe widget customization screen, where administrators can enter a page URL and specify iframe height to embed external content_

5. Select **[!UICONTROL Add widget]**. 

The Iframe widget will be added to the page. Administrators can add other widgets and publish the page.

**My Learning widget**

This widget is similar to the Courses and Paths widget, but filters content specifically for each learner, showing their personalized set of enrolled learning objects.

To configure the My Learning widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder). 
2. Select **[!UICONTROL My Learning]** and then select **[!UICONTROL Proceed]**. 
 
   ![](assets/select-my-learning.png)
   _Widget selection screen, highlighting the My Learning widget used to display the learner's personalized list of enrolled courses_

3. Type the **[!UICONTROL Widget title]** and **[!UICONTROL Widget description]**.
4. Select **[!UICONTROL Add widget]**.

My Learning widget will be added to the page. Administrators can add other widgets and publish the page.

**Social Learning widget**

This widget enables social collaboration functionalities such as posts, comments, and user tagging within the platform. It is enhanced for Experience Builder with customization options, including name and localization.

To configure the Social Learning widget:

1. Follow steps 1-9 from the [Design page in Experience Builder](#design-page-in-experience-builder). 
2. Select **[!UICONTROL Social Learning]** and then select **[!UICONTROL Proceed]**. 
 
   ![](assets/select-social-learning.png) 
   _Widget selection screen highlighting the Social Learning widget for displaying a posts to encourage collaboration and engagement_

3. Type the **[!UICONTROL Widget title]** and **[!UICONTROL Widget description]**.
4. Select **[!UICONTROL Add widget]**. 

The Social Learning widget will be added to the page. Administrators can add other widgets and publish the page.

#### Organize pages into a menu

Menus help organize and link pages in Experience Builder, making it easy for learners to navigate your learning portal. Administrators can create menus, add pages to them, and customize which menus are shown to specific audiences. 

**Create a menu**

To create a menu:

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Branding]** in the left navigation pane.
3. Select **[!UICONTROL Menu]** and then select **[!UICONTROL Create]**.
 
   ![](assets/select-create-menu.png)
   _Menu screen showing options to view, organize, and create customized menus for different learner groups_

4. Type the **[!UICONTROL Menu name]** (for example, Product Training) and select the user group in the **[!UICONTROL Visible to]** option.
   
   ![](assets/type-menu-name.png)
   _Create menu screen, where administrators can enter a menu name for internal use and specify user groups to control menu visibility_

5. Choose the custom page from the **[!UICONTROL Select pages]** option. 
 
   ![](assets/select-custom-pages.png)
   _Page selection screen, highlighting the option to include the custom page for user groups and customize the menu order_

6. Select **[!UICONTROL Preview menu]** to view the menu before saving it. 
7. Select **[!UICONTROL Save]**.

The created menu will be visible for the selected learners. They can access the custom pages through their Learner UI. 
 
![](assets/view-the-custom-pages.png)
_Learner UI displaying the custom page with featured training modules and easy navigation from the sidebar menu_

#### Manage pages lifecycle

Administrators can use the Custom Pages section to edit, delete, and duplicate the pages.

**Edit the page**

To edit the custom pages:

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Branding]** in the left navigation pane.
3. Select **[!UICONTROL Custom Pages]**.
4. Select the required page and then select **[!UICONTROL Edit]**. 
5. Select **[!UICONTROL Save]**.

The page will be updated with the changes. 

![](assets/edit-the-page-custom.png)
_Edit the custom page, allowing administrators to update the page name, description, and type_

**Delete the page**

To delete the page:

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Branding]** in the left navigation pane.
3. Select **[!UICONTROL Custom Pages]**.
4. Select the required page.
5. Select **[!UICONTROL Action]** and then select **[!UICONTROL Delete]**. 
 
![](assets/duplicate-the-page.png)
_Custom Pages screen displaying options to delete custom pages created for product training_

**Duplicate the page**

To duplicate the page:

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Branding]** in the left navigation pane.
3. Select **[!UICONTROL Custom Pages]**.
4. Select the required page.
5. Select **[!UICONTROL Action]** and then select **[!UICONTROL Duplicate]**. 
 
![](assets/duplicate-the-page.png)
_Custom Pages screen displaying options to duplicate the custom pages created for product training_

#### Preview the pages

To preview the pages:

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Branding]** in the left navigation pane.
3. Select **[!UICONTROL Custom Pages]**.
4. Select the required page and then select **[!UICONTROL Page Design]**
5. Select **[!UICONTROL Edit]** and then select **[!UICONTROL Preview page]** to view the portal's preview. 

![](assets/preview-page.png)
_Page preview showing a custom page layout with a banner, featured courses_

#### Localize the pages

When an admin adds multiple languages to the custom pages, add the widget details for each language in the corresponding language tab next to the default language tab.

![](assets/localize-pages.png) 
_Administrators can add widget details for additional languages, such as French, alongside the default language_

#### Set up hidden pages

The hide pages option allows administrators to keep the Learner UI clean by showing fewer pages. Administrators can hide pages from the menu so learners don't see them in learner UI, but learners can still reach those pages in other ways. For example, the Catalog page can be hidden from the menu but accessed through other navigation paths.
 
![](assets/select-hidden-pages.png)
_Menu configuration screen showing hidden pages such as Catalog, Social Learning, Skills, and Badges_ -->





<!-- We're excited to share several important updates coming to Adobe Learning Manager with the upcoming releases. These enhancements aim to streamline admin workflows, improve data reporting accuracy, and strengthen role-based controls.

These changes are designed to reduce manual effort, support automation, and improve governance across training operations.

## Capture instructor-marked completions in Learner Transcript

### Audience  

Administrator and automation owners 

### Overview 

In Adobe Learning Manager, when using incremental Learner Transcripts (LT) for automation workflows, instructor-marked completions made after the session date are not captured. The completion timestamp reflects the original session end time (not the time the instructor marked the completion). Since these updates fall outside the one-day change window used for incremental LT generation, as a result, learners' attendance and completion data are excluded from reports, leading to inaccurate or incomplete downstream reporting and potential compliance gaps. 

### What has changed 

Learner Transcript (LT) reports include completions marked by instructors after the session date. This ensures that any delayed attendance marking is correctly reflected in the transcript export. 

Attendance states like "Attended with pass/fail" will appear automatically in incremental LT exports. 

### What's new 

* New column: Mark Completed Date (UTC TimeZone). 
* Completion Source is available at module level. 
* Compatible with connector-based or job API-generated LT reports. 

![](assets/capture-instructor.png)

**Action required**

* If your automation depends on column positions, ensure logic accounts for the new column. 
* If using column names, no changes are required. 
* Retrofitted completions (manual imports) are not included. 

## Download links in Job Aids report

### Audience 

Administrator, custom administrator, and automation owners 

### Overview 

The Job Aids report includes a direct download link for each job aid, allowing quick access from the report itself. 

### What's new  

A new column, **[!UICONTROL Job Aid Link]**, has been added to the third position in the report. It links directly to the job aid if it's a file or shows the external URL provided by the author. 

Users with access (admin/authors and custom roles) can download the job aid using this link. 

![](assets/download-links-for-job-aid.png) 

### Action required 

* Review automated workflows using Job Aids reports (using Jobs API). 
* If the script is based on column position, update scripts accordingly. 
* No action is needed if using column names. 

## Internal User ID and Manager Email columns added to User Report

### Audience 

Administrators (and custom administrators) using the **[!UICONTROL User Report]** (**[!UICONTROL Admin]** > **[!UICONTROL Users]** > **[!UICONTROL Internal]** > **[!UICONTROL Export User data]**) downloaded from the administrator User Interface. 

### Overview 

To assist in user identification and integration workflows, two columns, **[!UICONTROL Internal User ID]** and **[!UICONTROL Manager Email]** have been added to the User report, exported via the User Interface. 

### What's new 

The User report includes a user's internal user ID and their manager's email address, to map them uniquely across different tools or API endpoints. 

### Action required 

* If using this report in automated flows, then this newly added column should be taken care of in automation.  
* No changes are needed if workflows are not impacted. 

## Scoped announcement permissions for custom administrators

### Audience 

Custom administrators 

### Overview 

Custom administrators can create announcements only for the user groups or catalogs within their defined scope. 

### What's new 

* Scoping rules allow custom administrators to create announcements for specific user groups or catalogs only. 
* When defining a custom role, administrators can assign announcement permissions with scope on user groups or catalogs. 
* Custom administrators are limited to creating announcements within their given scope. 
* The notification announcement report for custom administrators will display learners only within their assigned scope. 

### Action required 

* The format of the report will remain unchanged. If custom administrators download it from the User Interface, the content of the report will be subject to their scope. 
* No modifications are necessary if this report is not utilized in any automated or downstream workflow.

See the [Release notes](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/release-notes) article for a cumulative list of new features and changes to Adobe Learning Manager.-->
