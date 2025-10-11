---
description: 了解Adobe Learning Manager 2025年10月版的新增功能和增强功能
jcr-language: en_us
title: Adobe Learning Manager 2025年10月版的新增功能
source-git-commit: 5d50bd56b6663b26fc6db0ff33d19ad809e9bf6a
workflow-type: tm+mt
source-wordcount: '5638'
ht-degree: 0%

---


# Adobe Learning Manager 2025年10月版的新增功能

Adobe Learning Manager 2025年10月版引入了重要的增强功能，旨在提高报告准确性、扩展集成功能并增强管理员、作者和学习者的学习体验。

* Experience Builder：根据您组织的需求设计完全品牌化、基于角色的学习门户。 使用小组件、菜单和页面创建品牌化、基于角色的学习门户。
* 学习讨论区中的社交标记：学习者现在可以在帖子和评论中使用@username标记同行，从而在社交学习社区中实现有针对性的协作和通知。
* 规定范围的公告权限：自定义管理员可以创建仅限于其分配的用户组或目录的公告，从而确保有针对性通信并减少信息过载。
* 基于语言的进度跟踪：现在，学习者进度会针对每个区域设置单独保存，以便能够在语言之间无缝切换，而不会丢失进度。
* 增量自定义角色管理：管理员现在可以在Adobe Learning Manager中通过支持增量和多增量导入，更高效地管理自定义角色。
* 增强的用于分析和迁移的API：新的和改进的API提供了更好的测验性能跟踪、迁移状态监控以及对社交学习中用户标记的支持。

## Experience Builder

>[!IMPORTANT]
>
>我们很高兴宣布，Experience Builder是用于创建可自定义学习门户的创新工具，将在Adobe Learning Manager 2025年10月版后推出。
>
>随着发布日期的临近，敬请关注更多更新。 我们期待看到您如何使用Experience Builder转变学习门户。
>
>如有任何问题或其他信息，请联系您的客户成功经理。

Experience Builder是Adobe Learning Manager中的一种无代码/低代码工具，可帮助您创建自定义学习门户。 它允许您设计品牌化、用户友好的学习门户，而无需具备技术技能或丰富的编码知识。
使用Experience Builder，管理员可以轻松创建页面、菜单和小组件，以根据受众提供定制的个性化学习体验。

使用Experience Builder之前，企业面临以下挑战：

1. **有限自定义**：门户网站修复了设计，几乎没有选项可用于反映您的品牌。 管理员只能进行基本更改，例如修改页眉、页脚或颜色，这限制了您创建独特体验的能力。
2. **成本**：构建自定义门户网站需要花费大量的开发人员和较长的时间，通常需要6至9个月才能完成。 这一做法增加了总体拥有成本和延迟部署。
3. **一般体验**：每个人都看到相同的内容，即使这与他们的角色或需求无关。 个性化的缺乏降低了学习者的参与度和满意度。
4. **技术障碍**：非技术管理员难以创建或更新门户，因为他们需要编码知识或外部支持。

Experience Builder通过提供用于创建个性化、品牌化门户的简单、无代码/低代码解决方案解决了这些问题。

它使管理员能够设计满足其组织需求的门户，而无需依靠技术专业知识或外部开发人员。

**用例**

* **品牌化门户**：创建将贵公司的网站与徽标、颜色和布局相匹配的门户。 例如，医疗保健公司可以设计一个门户，在提供学习内容的同时反映其企业品牌。
* **基于角色的学习**：针对特定角色构建页面。 销售团队可以查看产品培训，而工程师可以访问技术课程。
* **产品培训**：为不同的产品(例如Photoshop或Illustrator)设置专用页面，并使用显示课程、认证和相关资源的小组件。

有关使用小组件创建自定义页面的更多信息，请查看[Experience Builder](/help/migrated/administrators/feature-summary/experience-builder/overview.md)。

## 基于语言的学习者进度

目前，Adobe Learning Manager仅跟踪选定区域设置语言的学习者进度，从而在播放器中切换语言/区域设置时导致进度严重丢失。 此限制可能会导致用户体验不佳，因为学习者在访问不同语言的内容时可能会失去进度。 在用户和模块级别跟踪播放器中每个模块的进度。 这会导致在用户切换回同一模块之前使用的区域设置时，其进度被覆盖。

例如，如果学习者在区域设置A（英语）中获得75%的进度，然后切换到区域设置B（西班牙语），在返回到区域设置A时，其进度会重置为0%，而不是从75%恢复。

要解决这些限制，增强了该功能，以支持特定于区域设置的进度跟踪：

* **特定于区域设置的存储**：当学习者在播放器内切换区域设置（例如，从区域设置A切换到区域设置B）时，Adobe Learning Manager现在会为内容的每个区域设置单独保存进度状态。
* **进度恢复**：当用户切换回以前使用的区域设置（从区域设置B切换回区域设置A）时，内容会从该特定区域设置中用户停止的位置恢复。
* **独立的进度跟踪**：每个区域设置均保持其自身的进度状态，允许学习者探索多种语言的内容，而不会丢失每种语言的单个进度。

基于语言的学习者进度不支持以下内容类型：

* 不支持视频和音频内容。
* 不支持第三方内容，包括Go1、LinkedIn Learning、getAbstract和Harvard ManageMentor。
* 不将数据发送到“学习记录存储区”(LRS)的内容将不跟踪或保存进度。
* 处于脱机模式时，移动应用程序用户无法跟踪此功能的进度。

有关基于语言的学习者进度的更多信息，请查看[我的学习](/help/migrated/learners/feature-summary/courses.md#language-based-progress-management)。

## 对自定义角色的增量和多增量支持

Adobe Learning Manager现在支持增量和多增量导入，用于自定义角色和角色分配。 使用增量导入，管理员只能上传用户的新记录、更新记录或删除的记录，而不能重新上传整个CSV文件。

多增量导入允许大型组织按地区或部门（例如，美国、欧盟、亚太地区）拆分增量文件并并行处理它们，从而扩展了此功能。 Adobe Learning Manager还支持多达20个增量用户CSV及其相应的自定义角色CSV，使其能够扩展到大型操作。

管理员现在可以逐步上传角色和用户角色文件（role.csv和user_role.csv）以及用户文件(user.csv)，而不是始终执行完整上传。 每个用户导入(user1.csv)均链接到其自己的角色和角色映射文件(user1_role.csv、user1_user_role.csv)，并存储在单独的FTP文件夹中。

以下CSV中添加了以下三个附加列：

* 用户注册状态(user.csv)：表示用户在系统中的当前注册状态（例如，活动、非活动或已删除）。
* 角色状态(role.csv)：指示帐户中的自定义角色当前是处于活动状态还是非活动状态。
* 用户角色状态(user_role.csv)：定义用户和角色之间映射的状态，显示分配是处于活动状态还是已删除。

Adobe Learning Manager现在可捕获用户审核和自定义角色报告中的添加、更新和删除操作，从而让管理员更好地了解更改。

>[!NOTE]
>
>这些更改仅适用于使用增量用户的帐户。

有关自定义角色的增量和多增量支持的详细信息，请查看[自定义角色的增量和多增量支持](/help/migrated/integration-admin/feature-summary/configure-role-csv-files.md#incremental-and-multi-incremental-support-for-custom-roles)。

## Go1集成增强功能

Go1集成得到增强，允许直接监管在Adobe Learning Manager中创建学习计划(LP)的Go1课程。 此更新支持在重复认证中纳入Go1课程，并引入新版本的Go1内容中心体验，可实现更高效的课程监管。

* 使用AI聊天帮助或手动选择直接在Go1中创建和管理播放列表。
* 使用自动进度重置功能在循环认证周期中加入Go1课程。 有关创建证书的详细信息，请查看[证书](/help/migrated/administrators/feature-summary/certifications.md)。
* 升级的内容发现界面改进了浏览和内容监管。

**重要说明**

* 所有Go1功能都需要有效的Go1许可证。
* 先前的免费Go1内容将停用。 组织必须预览和购买所需的内容捆绑包。
* 管理员和作者可以创建和管理播放列表；学习者保持仅查看访问权限。

有关将Go1课程添加到学习路径的更多信息，请参阅[策划Go1课程到学习路径](/help/migrated/administrators/feature-summary/content-marketplace/curate-go1-playlist.md)。

## 活动模块中支持vimeo URL

活动模块现在支持嵌入Vimeo URL，与YouTube嵌入的内容类似。 此增强功能允许管理员直接将Vimeo视频链接添加到活动模块中。 作者创建课程并添加“活动”模块时，现在会看到包含Vimeo URL的选项。 与添加YouTube链接的方式类似，作者可以将Vimeo链接直接粘贴到模块设置中。 发布后，学习者可以在学习者应用程序中无缝播放Vimeo视频，无需在平台外部重定向。

有关向课程添加模块的详细信息，请查看[添加模块](/help/migrated/authors/feature-summary/courses.md#add-modules)。

## CR/VC模块的时区信息

现在，“课程概述”页面、“实例”页面、“学习者预览”页面和“日历构件”中会显示教室(CR)和虚拟教室(VC)模块的时区详细信息。 学习者和管理员可以跨关键页面和日历邀请清楚地看到与已调度会话关联的时区。 学习者可以更好地计划和加入会话，而不会有时区误解。 此增强功能仅在沉浸式学习者应用程序中可用。

不同地区的学习者可以确认正确时区的会话时间。 清晰显示时区有助于防止会话错过并确保日历安排的准确性。

## 创建课程时自动填充作者姓名

在创建课程期间，**[!UICONTROL 作者]**&#x200B;字段现在会自动填充正在创建课程的作者的姓名。 作者不再需要手动输入自己的姓名。 仍可根据需要添加或更新其他作者。

对于具有严格内容所有权规则的组织，自动填充可确保始终正确归属“作者”。 编辑现有课程时，作者可以更新或添加共同作者，而不会丢失自动填充的条目。

有关创建课程的更多信息，请查看[创建课程](/help/migrated/authors/feature-summary/courses.md#create-a-course---advanced-workflow)。

## 更改配置文件时搜索外部配置文件

以前，管理员滚动浏览整个外部个人资料列表，并在重新分配学习者时手动选择所需的个人资料。 这使得该过程非常耗时，尤其是对于拥有多个配置文件的帐户。 借助此增强功能，管理员和自定义管理员现在可以在更改配置文件工作流程期间直接在选项卡中搜索外部配置文件。

**用例**

* 在拥有数百个外部个人资料（如加盟位置、合作伙伴公司或地区组）的帐户中，管理员现在可以使用搜索功能立即找到确切的个人资料，从而减少错误并节省时间。
* 在组织变革（如合并或部门调整）期间，可能需要将学习者批量转移到新的外部个人资料。 基于搜索的重新分配使此任务更流畅、更准确。

有关更改个人资料的详细信息，请查看[更改外部个人资料](/help/migrated/administrators/feature-summary/add-users-user-groups.md#change-profile)。

## 为Microsoft Teams会话添加联合组织者

以前，作者只能为Microsoft Teams会话分配单个组织者。 借助此增强功能，管理员现在可以向会话中添加共同组织者。 Microsoft Teams会话中引入了新字段&#x200B;**[!UICONTROL Co-Organizer]**，作者可以在主要组织者旁边分配其他组织者。

作者可以为每个Microsoft Teams会话指定多个共同组织者。 共同组织者与主要组织者具有相同的访问权限和权限。 作者对每个会话最多可以添加10个组织者，这提供了更大的灵活性并改进了会话管理。

**用例**

在与许多学习者进行大规模会话时，共同组织者可以帮助管理出席情况、缓和讨论并监控聊天，而主要组织者侧重于提供培训。

有关向课程添加CR/VC会话的详细信息，请查看[添加模块](/help/migrated/authors/feature-summary/courses.md#add-modules)文章。

## 下载感兴趣的学习者报告

当管理员弃用所有课程实例（例如，在课程生命周期结束时）时，**[!UICONTROL “课程概述”]**&#x200B;页面上的&#x200B;**[!UICONTROL “注册”]**&#x200B;按钮将替换为[!UICONTROL “注册感兴趣的内容”]选项。 学习者可以选择此选项以表达参加课程的兴趣。 管理员现在可以查看和导出已注册感兴趣课程的学习者列表。

然后，管理员可以访问此列表并将其作为报告下载。 当无活动实例可用时，已向课程页面添加&#x200B;**[!UICONTROL 感兴趣的学习者]**&#x200B;按钮。 此时会在管理员UI中显示学习者姓名以及他们注册的日期。

管理员可以选择&#x200B;**[!UICONTROL 操作]**，然后选择&#x200B;**[!UICONTROL 导出报告]**&#x200B;以导出&#x200B;**[!UICONTROL 感兴趣的学习者报告]**。

![](assets/register-interest.png)
_学习者可以查看“注册感兴趣内容”选项的课程概述部分_

查看[下载感兴趣的学习者](/help/migrated/administrators/feature-summary/courses.md#download-the-interested-learner-report)，了解更多信息。

## 在Salesforce应用程序中重置推荐

以前，使用Adobe Learning Manager Salesforce应用程序的学习者只能选择角色和推荐首选项一次。 如果他们更改了角色，则他们必须切换到本机的Adobe Learning Manager应用程序，才能更新其配置文件并接收相关课程建议。 通过最新的增强功能，学习者现在可以在工作角色、团队或职责发生变化时，直接在Salesforce应用程序中快速重置首选项。

这一简化的流程可确保他们在不离开Salesforce的情况下，继续收到更新且相关的课程建议。 管理员可以从更高的学习完成率和用户角色与推荐内容之间更好的协调中获益，所有这些都无需在交换平台上提供额外的支持或指导。

Adobe Learning Manager现在在Salesforce应用程序中提供&#x200B;**[!UICONTROL 重置兴趣]**&#x200B;按钮。 学习者现在可以重置其角色和学习首选项，而无需离开Salesforce或登录到本机Adobe Learning Manager应用程序。

有关Salesforce应用中的重置建议的更多信息，请查看[Salesforce应用中的重置建议](/help/migrated/learners/feature-summary/sfdc-app.md#reset-recommendations-in-salesforce-app)。

## 日历小组件增强功能

学习者现在可以在“日历”小组件中查看过去和即将开始的会话。 他们可以在日历中移动到任何日期并查看会话详细信息。 这意味着他们可以查看已进行的会议，帮助他们跟踪错过或出席的内容。 他们还可以查看未来24个月的所有即将开始的会话（包括当月），从而更轻松地提前计划和管理其日程安排。

查看[日历](/help/migrated/learners/feature-summary/learner-home-page.md#calendar)，了解有关日历小组件的详细信息。

## 在社交讨论区中为用户添加标签

社交讨论区现在支持用户标记功能，支持更具针对性的讨论，并改进了学习社区内的协作。 可以通过学习者应用程序、API和Adobe Learning Manager参考站点，在社交学习帖子和评论中为学习者添加标签。

无法标记讨论区范围之外的用户，从而防止出现不需要的通知。 如果从系统中删除了已标记用户，其提及内容将显示为“匿名”。 不允许标记用户组或“@all”来防止通知垃圾邮件。

* **@username标记**：用户可以使用“@username”格式标记其他讨论区成员。
* **范围受限标记**：只能标记有权访问特定讨论区的用户，从而确保隐私和相关性。
* **多渠道通知**：标记的用户会收到应用程序内通知和电子邮件通知，其中包含指向相关帖子或评论的直接链接。

**用例**

* 寻求特定同事对医疗案例提供投入的医疗保健专业人员：标签功能允许医生和护士快速通知合适的专家，确保对复杂的患者案例提供及时和准确的建议。
* 就专门专题咨询专题专家：通过为专家加标签，团队可以直接让适当的人参与，缩短反应时间，改进技术查询或专门查询的决策。
* 需要特定利益相关方提供投入的团队讨论：标记利益相关方可确保相关决策者了解最新信息，并能提供投入，使项目与业务目标保持一致和同步。

有关在社交讨论区中标记用户的详细信息，请查看[社交讨论区中的用户标记](/help/migrated/learners/feature-summary/social-learning-web-user.md#tag-users-in-social-board-posts)。

## 自定义管理员的限定范围的公告权限

自定义管理员现在可以创建公告，但只能为其分配的用户组或目录创建公告。 这可以防止跨组织边界的意外通信。 自定义管理员只能为其分配范围内的用户创建公告。 公告的范围可以限定为特定的用户组或目录。 完全管理员可维护对所有公告的可见性和控制，包括由规定范围的自定义管理员创建的公告。

**主要优点**

* 有针对性的沟通，确保公告仅面向相关受众。
* 通过防止不相关的通知到达意外用户来减少信息过载。
* 保持组织界限并防止意外交叉通信。

**重要说明**

* 如果自定义管理员的作用域发生更改，则受影响的公告会显示一个警告图标，并要求重置各个作用域。
* 当范围发生更改时，必须单独更新每个公告。
* [通知公告](/help/migrated/administrators/feature-summary/announcements.md)报告仅显示自定义管理员分配范围内的学习者。

**用例**

* 特许经营组织，其中区域管理人员只需要与其特许经营人沟通。
* 具有区域或部门管理员的大型组织将发布目标定位到其团队。

有关为分配的作用域创建公告的详细信息，请查看[为分配的作用域创建公告](/help/migrated/administrators/feature-summary/announcements.md#create-announcement-for-the-assigned-scope)。

## 从Adobe Captivate发布内容时选择自定义角色

将内容从Adobe Captivate发布到Adobe Learning Manager时，如果用户具有多个自定义角色，系统将提示他们选择特定的自定义角色，以便根据特定的自定义角色发布课程。 这可确保对已发布的课程应用正确的角色所有权和权限。

有关为用户创建自定义角色的更多信息，请查看[自定义角色](/help/migrated/administrators/feature-summary/custom-role.md)。

## “由我保存”小部件的增强功能

以前，选择&#x200B;**[!UICONTROL 由我保存]**&#x200B;条会显示目录中可用的所有课程。 现在，学习者仅在学习者主页上的&#x200B;**[!UICONTROL 由我保存]**&#x200B;栏中看到已添加书签的课程。 选择此条带会将学习者引导至目录页面，仅会显示他们已保存的课程。

学习者可以在目录中应用其他过滤器，以缩小搜索范围。 应用过滤器后，系统仅显示符合选定条件的课程。 以前添加书签的课程仅在其与应用的过滤器匹配时显示。

有关AEM站点中已保存课程小组件的更多信息，请查看[配置AEM站点中已保存的课程小组件](/help/migrated/integrate-aem-learning-manager.md#configure-my-saved-courses-widgets-in-aem-sites)。

## 支持显示共享课程中的作者姓名

以前，将课程与[配对帐户](/help/migrated/administrators/feature-summary/peer-account.md)共享时，作者显示为外部作者。 现在，课程会显示作者姓名，无论他们是主帐户的内部用户还是旧版作者（即，在创建课程期间，在“作者”字段中输入的任何姓名作为字符串）。 选择“作者”会显示他们与配对帐户共享的课程数量；但是，这些作者不是配对帐户中的实际用户。

如果从主帐户中删除了用户，则该用户的数据将从主帐户中删除，但作者信息将保留在已共享其内容的任何配对帐户中。

>[!NOTE]
>
>这是一个基于标记的功能，请联系我们的客户支持团队[learningmanagersupport@adobe.com](mailto:learningmanagersupport@adobe.com)以启用此选项。

有关将内容共享到配对帐户的详细信息，请查看[配对帐户](/help/migrated/administrators/feature-summary/peer-account.md)。

## 低阶学习对象的搜索可见性

以前，当搜索结果属于高阶学习对象（如学习路径或认证）时，它们无法一致地显示各个课程。 如果学习者仅注册了学习路径或认证，则搜索仅返回高阶结构，而不返回单个课程。

通过此增强功能，学习者现在可以在搜索结果中查看各个课程，即使这些课程是学习路径或认证中的内容也是如此。 引入了新的管理员设置&#x200B;**[!UICONTROL “在搜索结果中显示所有已注册的课程”]**。 启用此设置后，在搜索特定课程时，系统始终会显示课程本身以及任何相关的“学习路径”或“认证”。

有关常规设置的详细信息，请查看[设置](/help/migrated/administrators/feature-summary/settings.md#general-settings)。

## API 更改

### 迁移API增强功能

Adobe Learning Manager现在支持通过迁移过程将各种数据对象迁移至帐户。 此过程可通过API和用户界面启动。 迁移失败时，可以通过界面下载错误。 这些错误在调试迁移错误和管理迁移运行时非常有用。

在此版本中，您还可以通过API下载错误日志，以便高效地、以编程方式跟踪和调试错误。

**API更改**

新的迁移API `runStatus`允许集成管理员检查通过API触发的迁移运行状态，这在以前版本的Adobe Learning Manager中是不可能实现的。

此外，`runStatus` API现在提供了一个直接链接，可用于下载已完成运行的错误日志(CSV)。 请注意，该链接的有效期仅为七天，并且日志会保留一个月。

`startRun` API的响应已更新，包含了迁移项目ID、Sprint ID和Sprint运行ID，这些都是查询新状态终结点所必需的。

#### runStatus API

**描述**

检索现有迁移运行的状态。

**端点**

```
GET /bulkimport/runStatus
```

**参数**

* **migrationProjectId**： （必需）。 迁移项目的唯一标识符。 迁移项目用于将数据和内容从现有学习管理系统(LMS)传输到Adobe Learning Manager。 每个迁移项目可以由多个Sprint组成，它们是较小的迁移任务单元。

* **sprintId**： （必需）。 迁移项目中Sprint的唯一标识符。 Sprint是迁移任务的子集，其中包括要从现有LMS迁移到Adobe Learning Manager的特定学习项目（如课程、模块、学习者记录）。 每个Sprint都可以独立执行，从而允许分阶段迁移。

* **sprintRunId**： （必需）。 一个唯一标识符，用于跟踪迁移项目中特定Sprint的执行情况。 它与Sprint中定义的项目的实际迁移过程相关联。 sprintRunId有助于监视、故障排除和管理迁移作业。

**响应**

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

`startRun` API响应已更新为包括三个附加字段 — migrationProjectId、sprintId和sprintRunId。 这些字段允许用户使用新的runStatus API跟踪和查询特定迁移运行的状态。

```
curl -X GET --header 'Accept: text/html' 'https://learningmanager.adobe.com/primeapi/v2/bulkimport/runStatus?migrationProjectId=001&sprintId=10001&sprintRunId=7'
```

生成以下响应。 响应包含：

* `migrationId`
* `sprintId`
* `sprintRunId`

**响应**

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

有关从现有LMS迁移内容的详细信息，请查看[迁移手册](/help/migrated/integration-admin/feature-summary/migration-manual.md)。

### 社交API更改（用户标记、评论和回复）

Adobe Learning Manager现在支持社交讨论区中的@user标记功能，学习者可以在帖子、评论和回复中提及和通知同行。 此功能增强了跨平台的协作和内容发现。

此版本引入了新的API功能以支持用户提及，包括增强的POST和GET端点，并且为标记用户引入了新的搜索功能。

**API更改概述**

* 更新了POSTAPI，用于创建包含用户提及的帖子/评论/回复
* 更新了响应中包含GET提及数据的API

**用户提及的格式**

使用以下格式提及用户： @(user:userId)

#### 创建提及帖子

**端点**

```
POST /primeapi/v2/posts
```

**描述**

创建包含用户提及的新社交学习帖子。

**请求正文**

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

**响应**

_userMentions_&#x200B;关系中包含提及数据的标准帖子创建响应。

#### 创建包含提及的评论

**端点**

```
POST /primeapi/v2/comments
```

**描述**

在有用户提及的帖子中添加评论。

**请求正文**

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

#### 创建包含提及的回复

**端点**

```
POST /primeapi/v2/replies
```

**描述**

回复包含用户提及的评论。

**请求正文**

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

#### 检索包含提及的帖子

**端点**

```
GET /primeapi/v2/posts/{id}
```

**描述**

检索帖子详细信息，包括提及的用户。

**响应**

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

### 社交API更改（用户搜索）

**端点**

```
GET /primeapi/v2/users/search?q={searchTerm}&context=tagging
```

**描述**

根据社交范围设置搜索可用于添加标签的用户。

**请求参数**


* q（必填）：搜索词（最少3个字符）。
* 上下文：设置为“标记”以使用户有资格被提及。
* 讨论区ID（可选）：根据访问权限筛选用户的讨论区ID。

**响应**

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

### 针对测验性能跟踪的学习者API增强

`GET /loResourceGrades` API已得到增强，可提供详细的测验性能数据，从而支持更复杂的分析和自动化决策。

API响应现在包括两个附加字段：

* **[!UICONTROL 最高分数]**：学习者在所有测试尝试中获得的最佳分数
* **[!UICONTROL maxScore]**：测验可能的总分数

**API响应示例**

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

作为响应，**课程:15067_30122_41715_1_3400468**&#x200B;是要为其请求信息的学习对象资源级别的ID。 可从`learningObjectResourceGrad` API获取`GET /enrollments/{id}`e ID。

### API响应支持区分作者姓名的大小写

现在，API响应会提供在课程创建或更新期间输入的旧版作者姓名的确切案例。 这可确保姓名在学习者UI和公共API中的显示一致。

* 添加新的作者姓名后，案例将完全按照输入的信息进行存储和返回。
* 如果删除现有作者姓名，然后使用其他案例重新添加该姓名，则更新后的案例将得到遵循并反映在所有使用该作者姓名的课程中。
* 不会对以前存储的名称执行自动迁移；只有新添加或更新后的名称才会遵循此行为。

### 日历API增强功能

现在，日历会加载用户所选月份的会话。 为了通过API获取过去和即将开始的会话，已将新`year`参数添加到学习者端点`GET /users/{id}/calendar`。 必须同时提供`month`和`year`参数才能检索会话详细信息。

**卷曲示例**

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth a4ae04eb9f06f4bf88abcde17' 'https://abc.adobe.com/primeapi/v2/users/12345678/calendar?month=7&year=2025&currentMonthOnly=false&filter.allSessions=false'
```

### 通过管理员API支持标记完成

以前，公共API不支持在多注册场景中进行基于实例的完成标记。 通过此增强功能，您现在可以将课程实例ID包含在`POST /users/{userId}/userModuleGrade`的请求正文中，并且管理员可以标记特定实例的完成情况。

### 设置SCORM报告的用户ID首选项

某些客户需要学习者的UUID（通用唯一标识符）而不是默认的user_id才能完成SCORM内容。 使用UUID可更准确地跟踪学习计划，并防止MAU（每月活动用户）帐户中许可证使用情况的重复。

为了支持此功能，添加了一个新的帐户级别设置`reporting_userid_preference`。 启用后，每当学习者完成SCORM内容时，此设置都会发送UUID而不是user_id。

>[!NOTE]
>
> 请联系我们的客户支持团队[learningmanagersupport@adobe.com](mailto:learningmanagersupport@adobe.com)以配置此设置。

新属性`reportingUserIdPreference`已引入`get /account`，用于跟踪用户ID首选项。

### 共享课程中的作者信息

在学习对象API中，作者信息的返回方式已更新，以区分主帐户课程和与配对帐户共享的课程：

* 共享课程（配对帐户）：作者详细信息现在返回新属性`authorDetails`下。 即使课程源自其他帐户，此属性也会提供作者姓名。

* 主帐户课程：作者信息将继续在现有`authors`属性下返回，而不更改当前行为。

此更改可确保通过API公开主课程和共享课程作者数据的一致性，同时还可保持现有集成的兼容性。

## 对Webhook的更改

### 使用连接器注册LinkedIn Learning Webhook

以前，管理员必须通过API手动将LinkedIn学习Webhook注册到Adobe Learning Manager。 借助此增强功能，LinkedIn学习(LIL)连接器现在支持在ALM中建立新连接期间自动注册Webhook。 将在LinkedIn学习配置页面上自动填充&#x200B;**OAuth服务器URL**&#x200B;和&#x200B;**租户服务器URL**。

有关LinkedIn学习集成的详细信息，请查看[LinkedIn学习](/help/migrated/integration-admin/feature-summary/connectors.md#linkedin-learning-connector)。

### linkedIn学习中MAU许可证使用情况的更改

以前，对于MAU（每月活动用户）帐户，当学习者直接在LinkedIn学习平台上完成LinkedIn学习课程时，Adobe Learning Manager不计算许可证用量。 仅通过Adobe Learning Manager播放器学习的课程会触发许可证使用，导致对每月活动用户(MAU)的跟踪不准确。

借助此增强功能，Adobe Learning Manager现在会在学习者在LinkedIn学习平台中使用课程时生成外部Webhook。 当Adobe Learning Manager收到此Webhook时，它将计算许可证用量，以确保跨两个平台准确跟踪。

## 报告更改

### “学习者成绩单”中由讲师标记的完成数

现在，即使会话日期之后已记录出席情况，增量学习者成绩单也会捕获由讲师标记的完成情况。
此增强功能解决了增量学习者成绩单中的一个关键差距，即如果在原始会话日期之后记录出勤情况，那么讲师标记的完成内容之前会被错过。

增量学习者成绩单是计划报告，仅捕获在指定期间内发生的更改（如完成或进度更新），而不是提供完整的历史数据转储。 它们常用于自动化、信息板和集成，允许用户高效地跟踪最近的学习活动，而无需每次处理整个成绩单历史记录。

* **标记完成日期（UTC时区）列**：新的时间戳列，可捕获讲师将会话或模块标记为完成时的确切日期和时间。
* **增强的完成源跟踪**：跟踪记录完成情况的特定讲师和模块（例如，“教室”）。

这些更改可确保会话日期之后标记的完成情况准确反映在增量学习者成绩单中。

**用例**

* 在教室授课中，讲师可以在实际授课后标记出勤情况。
* 自动化系统或信息板，依赖增量学习者成绩单实现合规性或报告功能。

![在Adobe学习中，学习者成绩单报告显示了已标记的完成日期（以黄色高亮显示）用于课程完成跟踪](/help/migrated/assets/mark-completion-column.png)
_学习者成绩单报告会以黄色显示一个新列，突出显示所有用户的各个完成日期_

查看[学习者成绩单](/help/migrated/administrators/feature-summary/learner-transcripts.md)，了解有关学习者成绩单报告的更多信息。

### 增强型用户报告及扩展数据字段

用户报告现在包含其他字段，以增强用户跟踪和组织映射。 这些更新简化了用户识别，支持与下游用户管理工作流程的集成，提高了对报告关系的理解，并维持了组织界限以防止意外的交叉通信。

* 内部用户ID列：提供唯一的内部标识符，以便跨不同系统和API端点顺畅地跟踪用户。
* “经理电子邮件”列：包括用于组织层次结构跟踪的直接经理联系人信息。

![显示内部用户ID和经理电子邮件列并以黄色突出显示的用户报告](/help/migrated/assets/user-report-columns.png)
_用户报告，重点介绍内部用户ID和经理电子邮件地址，以简化用户管理_

有关用户报告的详细信息，请查看[下载用户报告](/help/migrated/administrators/feature-summary/add-users-user-groups.md#download-the-user-report)。

### FTP、自定义FTP和Box中的用户报告

**概述**

除了现有的作业API之外，用户报告现在可用于Box、FTP和自定义FTP连接器。 这些报告提供有关内部用户ID、用户电子邮件、姓名、经理电子邮件、用户类型等方面的详细信息。

可以按需或按计划生成报告，并将数据存储在相应的连接器中，以便于访问和分析。 此增强功能改进了用户活动的监控和审核，从而支持更好的安全性和合规性跟踪。

这些报告可与现有报告（例如用户注册、登录访问、游戏和培训）一起提供，使管理员能够从单个位置访问所有基本报告，以简化数据管理和分析。

有关FTP、自定义FTP和Box连接器的详细信息，请查看[连接器](/help/migrated/integration-admin/feature-summary/connectors.md)。

### 在学习者成绩单中包括暂停的用户

**概述**

公司现在可以在学习者成绩单中包含挂起用户（具有已禁用的外部配置文件的用户），从而确保全面的历史学习数据保留。

* 用于配置挂起用户可见性的帐户级别标志，允许挂起用户显示在学习者成绩单中。
* 即使在停用挂起的外部配置文件后，仍会保留历史数据。

**实现要求**

* 请联系您的客户成功经理(CSM)以启用帐户级别标志。

>[!NOTE]
>
>默认情况下，现有帐户禁用此标志，对于新帐户，必须明确请求使用此标志。

查看[学习者成绩单](/help/migrated/administrators/feature-summary/learner-transcripts.md)文章详细信息。

### 包含直接访问链接的工作辅助报告

**概述**

工作辅助报告已得到增强，包含指向工作辅助的直接下载链接，从而简化了管理员和作者的内容管理和审核流程。 此增强功能可从报告中直接下载文件并访问URL。 无需手动查找和下载工作辅助以进行法规遵从性或辅助功能审核。

* 工作辅助链接列：从报告中直接访问工作辅助文件和外部URL。
* 基于角色的访问控制：链接辅助功能取决于用户角色和目录权限。
* 已删除的工作辅助仍可访问已激活的课程。

**用例**

* 作者或管理员会根据大型组织的要求定期对工作辅助进行辅助功能审核。
* 任何需要快速、基于角色访问工作辅助文件的情景，以供审核或合规。

![](/help/migrated/assets/job-aid-report.png)
_工作辅助报告显示直接下载链接，可以轻松访问和下载Adobe Learning Manager中的工作辅助_

有关工作辅助报告的详细信息，请查看[工作辅助报告](/help/migrated/administrators/feature-summary/reports.md#job-aids-report)。

## 本次更新中修复的错误

* 现在可以正确生成非互动测验的L2测验分数，包括完成测验的用户的详细信息。
* 现在，当在连接配置期间将身份验证机制设置为“签名”时，会将签名正确发送到目标主机。
* 在会话完成后，未删除在Adobe Connect会话期间创建的虚拟用户。 SnapLogic管道现在可正确删除这些用户，即使`principals-delete` API以前返回了200个响应而没有删除这些用户。
* API响应中的`null`个`eventDetail`对象不再导致异常。 系统现在会跳过空条目并处理整个阵列，从而确保完成录制。
* 反馈报告中的“反馈日期”列现在显示正确的日期。 以前，秒错误地传递给Date构造函数（预期为毫秒），导致日期显示为1970年1月。 此问题现已解决，以确保在生成反馈报告时准确显示日期。
* 即使其中一个课程实例已弃用，学习者现在也可以更新Flex学习路径的注册内容。 以前，选择新实例会导致控制台错误（无法读取未定义的属性）并阻止更新。
* 学习路径中的资源名称现在可以正确显示，而不会中断中间字。
* 现在，在为新用户创建连接时，将从LIL连接器启用LinkedIn Learning Webhook。 系统还会通过专用API注册帐户，并在LinkedIn学习配置页面上显示其他配置信息（OAuth URL和租户URL）。
* 通过SAML工作流(`UpdateUserWorkerTask`)更新的用户属性值现在与其原始大小写一起保存，而不是转换为小写。
* 对课程中的模块进行重新排序后，必修模块数量不会再重置为“全部”；数量现在保持不变。
* Go1管道现在通过将两个字母的代码映射到四个字母的代码来一致地处理语言代码，类似于LinkedIn学习管道。
* 在弃用帐户中，学习者在取消认证注册后启动学习路径课程时，之前会看到“此课程不存在”。 注册源现已正确更新，学习路径中的课程可正常启动。
* 当module_version.csv文件包含空值或null值的contentType字段时，课程创建现在没有任何问题。
* 按“目录”或“目录标签”筛选时，课程现在可以正确显示。 以前，在课程页面上应用这些过滤器时，即使课程与目录相关联，也不会显示课程。
* 在学习者应用程序中，流体播放器中的TAB键卡在“进入全屏”按钮上。 键盘导航现在可在所有屏幕元素中正确移动。
* 将鼠标悬停在经理应用程序合规性信息板中的长课程名称上，现在会显示已注册或合规课程的全名。
* module.csv中的模块可见性列只接受“共享”或“隐藏” 。 任何其他值都将在迁移期间触发错误，从而防止后端失败。
* 禁用UUID后，使用大小写混合的电子邮件创建新管理员时，不再生成重复的用户条目。 系统现在会持续处理电子邮件大小写，以防止出现重复邮件。
* 现在，阿拉伯语、希腊语、希伯来语、印地语、泰语和乌克兰语等语言的课程可正确显示NotesPDF。 以前，即使字符在播放器中正确显示，它们也会在下载的PDF中显示扭曲。

## 系统要求

查看[Adobe Learning Manager系统要求](/help/migrated/system-requirements.md)。

## 发行说明

请查看[发行说明](/help/migrated/release-note/release-notes.md)以了解最新发行更新。

## Adobe Learning Manager 的早期版本

* [Adobe Learning Manager 2025年5月版](/help/migrated/whats-new-may-2025.md)
* [Adobe Learning Manager 2025年11月版](/help/migrated/whats-new-nov-24.md)
