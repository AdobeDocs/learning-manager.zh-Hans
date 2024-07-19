---
description: 公司可利用本文档中提供的推荐方法设置和配置 Adobe Learning Manager。要想快速入门，Adobe Learning Manager 团队建议分阶段进行。您不必按照特定顺序执行所有阶段。
jcr-language: en_us
title: Adobe Learning Manager 设置最佳实践指南
contentowner: jayakarr
preview: true
source-git-commit: 46afb6603456ced9d7e2aaf98d07ec92fee30c0b
workflow-type: tm+mt
source-wordcount: '3387'
ht-degree: 70%

---



# Adobe Learning Manager 设置最佳实践指南

公司可利用本文档中提供的推荐方法设置和配置 Adobe Learning Manager。要想快速入门，Adobe Learning Manager 团队建议分阶段进行。您不必按照特定顺序执行所有阶段。

这些阶段可以由三个不同的角色执行，根据公司设置由一人或多人执行。 三个角色如下：

1. **IT管理员** - IT管理员负责执行公司中与Learning Manager应用程序关联的激活或集成相关活动。 IT 管理员还可以添加单个/多个用户，并担任集成管理员的角色。
1. **作者** — 作者负责创建公司学习要求所需的学习内容。 公司的培训或学习内容作者可以开始创建Learning Manager应用程序所需的基本内容。
1. **Learning Manager管理员** - Learning Manager应用程序管理员负责执行配置和设置活动。 在某些公司中，IT 管理员也可以充当 Adobe Learning Manager 应用管理员的角色。

您可以浏览下面提供的信息图，大致了解各个阶段及其对应的任务。

![](assets/learning-manager-getting-started.jpg)

在此阶段，我们假定公司已收到许可证密钥，并且您已激活 Adobe Learning Manager 帐户。如信息图所示，三条轨道的解释如下：

## 第 1 阶段 - 技术设置（IT 管理员） {#phase1technicalsetupitadministrator}

在轨道1中，公司的IT管理员可以切换为Learning Manager应用程序中的集成管理员角色，并执行一些激活和集成操作，如下所示：

### 启用/添加活动字段（Adobe Learning Manager 管理员） {#enableaddactivefieldscaptivateprimeadministrator}

除了用户在注册过程中提供的活动字段外，管理员还可以添加更多活动字段。 管理员还可以启用/禁用用户字段。 这些活动字段的值根据与用户帐户关联的各种数据源的元数据生成。 有关详细信息，请参阅[活动字段帮助](feature-summary/add-users-user-groups.md#active-fields)。

### 单点登录 (SSO) {#singlesignonsso}

您可以使用 Adobe ID 或单点登录，访问 Adobe Learning Manager 应用程序。单点登录机制允许用户仅进行一次身份验证即可多次访问多个应用程序。此项配置对企业并非必需配置。如果公司有基于 SAML 2.0 的 SSO 提供程序，可以用来配置 Adobe Learning Manager 应用程序。此项配置应在公司级别和 Adobe Learning Manager 应用程序级别进行配置。如果您选择使用SSO，请联系Adobe支持以获取配置说明。 有关详细信息，请参阅[设置帮助](feature-summary/settings.md)。

### 批量导入用户 {#bulkimportofusers}

当公司有大量用户时，您可以使用 .CSV 文件将所有用户批量导入 Adobe Learning Manager 应用。在执行此任务之前，我们建议您从公司HR应用程序中以.CSV格式导出用户列表。 即使在此阶段不用批量导入用户，您也可以熟悉 CSV 格式。 要开始在Learning Manager中执行导入流程，请上传.CSV文件，并将应用程序数据字段映射到公司的CSV列。 有关详细信息，请参阅[批量导入帮助](add-users-in-bulk.md)。

### FTP 连接器集成 {#ftpconnectorintegration}

如果您需要不断添加或删除公司员工，则可以选择使用 FTP 连接器自动批量导入用户。 您必须先建立连接，然后上传 CSV 并将 CSV 的属性映射到相应的 Adobe Learning Manager 字段。您可以安排自动导入流程，并在需要时同步。 有关详细信息，请参阅[FTP连接器帮助](../integration-admin/feature-summary/connectors.md#ftpconnector)。

### Salesforce 连接器集成 {#salesforceconnectorintegration}

如果公司拥有 Salesforce 帐户，则可以自动将所有用户从 Salesforce 导入 Adobe Learning Manager 应用。如果要使用此功能，可以使用 Salesforce 连接器将 Adobe Learning Manager 与 Salesforce 帐户集成以自动同步数据。使用自动计划功能定期执行自动导入用户。 您还可以每天执行同步。 有关更多信息，请参阅 [Salesforce 连接器帮助](../integration-admin/feature-summary/connectors.md#sfconnector)。

### Adobe Connect 集成 {#adobeconnectintegration}

如果公司使用 Adobe Connect，则可以将其与 Adobe Learning Manager 应用集成，为学习者提供无缝的用户体验。集成之后，学习者只需单击一下，即可访问 Adobe Learning Manager 应用中的虚拟教室，而无需再次登录 Adobe Connect。学习者还可以通过此功能在 Adobe Learning Manager 应用中使用录制的虚拟教室会话。要进行集成，请首先集成设置。 使用&#x200B;**“设置”>“Adobe Connect”>“立即配置”**&#x200B;提供 Connect URL 和登录凭据，然后集成。 有关更多信息，请参阅 [Adobe Connect 集成帮助](feature-summary/adobeconnect-integration.md)。

### Salesforce 应用注册 {#salesforceappregistration}

公司中的学习者可以在其 Salesforce 帐户中无缝访问 Adobe Learning Manager 应用。学习者可以在 Salesforce 应用程序中访问已指定的学习内容，如课程、学习计划和工作辅助。用户还可以从 Salesforce 中的 Adobe Learning Manager 应用访问通知和公告。要使用此功能，您必须在 Adobe Learning Manager 应用中注册 Salesforce 特色应用。有关安装和使用说明的信息，请参阅 [Salesforce 应用帮助](../integration-admin/feature-summary/sfdc-app.md)。

## 第 2 阶段 - 站点配置（Adobe Learning Manager 管理员） {#phase2siteconfigurationcaptivateprimeadministrator}

公司中的 Adobe Learning Manager 应用管理员必须先配置或设置某些功能，然后才能开始为学习者实施这些功能。

### 品牌推广 {#branding}

公司可能希望在Learning Manager应用程序中显示公司徽标、在URL中拥有自己的域、显示公司名称以及与公司品牌匹配的颜色方案。 公司可以利用 Adobe Learning Manager 使用所有上述功能。如果要自定义设置并使用自己的品牌推广，请单击左侧窗格中的“品牌推广”部分。 单击上述所有选项旁边的“编辑”，并根据您的需求进行自定义。 有关更多信息，请参阅[品牌推广和主题帮助](feature-summary/themes.md)。

### 添加用户/用户组 {#addusersusergroups}

学习者是学习内容的主要用户，因此在学习管理系统中添加用户是第一步。 将用户添加到 Adobe Learning Manager 应用，然后为其分配角色。您可以通过以下方式添加用户：

#### 添加用户（内部） {#addusersinternal}

* **作为单一用户** - 您可以先在 Adobe Learning Manager 应用中以单一用户形式添加部分用户，然后再批量添加。此外，当您希望在批量导入用户后根据需要添加更多单个用户时，此选项非常有用。
* **自行注册** — 管理员可利用此选项允许其员工自行注册Learning Manager。
* **批量导入**（使用CSV上传） — 您可以使用此选项将用户批量导入Learning Manager应用程序。 先决条件是您必须在使用此功能之前以CSV格式准备好用户列表。

#### 添加用户（外部配置文件） {#addusersexternalprofiles}

* 通过外部注册 - 您可以使用此选项将公司外部的部门成员或外部员工注册到应用程序。

#### 添加用户组 {#addusergroups}

Adobe Learning Manager 应用会根据相似属性生成默认用户组。除默认用户组外，您还可以根据职务、位置等参数生成自定义用户组，以便在游戏和报告中使用这些组。 有关更多信息，请参阅[添加用户帮助](feature-summary/add-users-user-groups.md)。

### 分配角色 {#assignroles}

在向 Adobe Learning Manager 中添加用户后，管理员可以开始根据公司要求向用户分配作者、管理员或集成管理员角色。要向用户分配角色，请在管理员登录页面的左侧窗格中单击&#x200B;**[!UICONTROL 用户]**，选中各个用户名对应的复选框，然后单击&#x200B;**[!UICONTROL 操作]**&#x200B;下拉列表选择要分配的角色。 Adobe Learning Manager会根据公司在CSV文件中提到的角色/权限，向用户分配经理角色。 您还可以使用“编辑用户”工作流程，将用户角色更改为“经理”。 有关更多信息，请参阅[添加用户帮助](feature-summary/add-users-user-groups.md)。

### 通知模板 {#notificationtemplates}

如果学习管理系统中的用户希望了解自己的状态或获知事件/活动，那么通知非常有用。 在创建课程、配置功能或使用课程时，用户会经历多个事件，这些事件会触发特定通知，并发送至学习者、其经理、管理员或作者。 Adobe Learning Manager 在应用中提供了各种电子邮件通知模板。作为管理员，您可以根据公司要求自定义模板。 要创建电子邮件通知，请在左侧窗格中选择&#x200B;**“电子邮件模板”**，然后单击模板名称。 有关更多信息，请参阅[电子邮件模板帮助](feature-summary/email-templates.md)

**关闭电子邮件通知（推荐）**

默认情况下，Adobe Learning Manager 应用中的通知处于启用状态。如果您不想通知公司员工，可以在此阶段关闭通知。

### 徽章 {#badges}

徽章是一种成就度量，员工在完成课程后即可获得。 全球各地的专业人士可将这些徽章用于表现其掌握了特定技能或学习成就。您可以创建徽章集合，以便在学习者完成学习内容后将其分配给学习者。 要开始创建徽章，可以单击左侧窗格中的&#x200B;**[!UICONTROL “徽章”]**&#x200B;功能。 有关更多信息，请参阅[徽章帮助](feature-summary/badges.md)。

### 反馈 {#feedback}

反馈是 LMS 中衡量学习者学习进度并确保学习内容质量的重要因素之一。 Adobe Learning Manager 为用户提供两类反馈选项。

* L1 反馈是学习者在完成课程后提供的反馈。
* L3反馈是经理根据课程对学习者行为和日常活动的影响向学习者提供的反馈。

公司可以选择性使用此功能。 管理员可以根据公司要求自定义反馈模板。 要使用此功能，管理员必须在课程实例级别启用 L1 和 L3 反馈选项。 要配置反馈，请选择任何课程，单击左侧窗格中的“实例默认值”，然后启用反馈选项。 有关更多信息，请参阅[反馈帮助](feature-summary/courses.md)。

### 游戏 {#gamification}

确保学习者在使用内容时参与其中是公司面临的挑战之一。 游戏吸引和激励学习者使用游戏技巧完成其目标，从而提高课程的完成率。 学习者可以与其同事进行竞争，在多个学习活动中获得点数，并获得铜、银、金和白金等级。管理员可以启用/禁用各个游戏任务，并修改任务的点数分配。 Adobe Learning Manager 的部分游戏功能为默认设置。您可以在使用具有默认设置的功能一段时间之后，选择自定义。 配置/更改此功能的设置为可选项。 如果公司中有主题专家，则建议在使用此功能之前先配置设置。 有关更多信息，请参阅[游戏帮助](feature-summary/gamification.md)。

### 创建学习对象 {#createlearningobjects}

这是三条轨道（轨道 1、轨道 2 和轨道 3）交汇的必经阶段，便于您采取下一步行动。

此时，在创建模块和课程后，您可以开始创建更高级别的学习对象（如认证、学习计划或工作辅助等），以继续下一步。 在开始创建学习对象之前，请确保已在 Adobe Learning Manager 应用中添加部分用户、创建部分模块和课程。

#### 创建认证 {#createcertifications}

认证是对学习者一次性或周期性完成学习内容的证明或成绩证明。 在课程完成后向学习者提供认证，可以让更多学习者注册学习内容。 作为管理员，您可以创建内部托管或第三方执行的认证计划。在内部认证中，指定学习者需完成后才能获得认证的课程。在创建认证之前，请确保您的帐户中有一些可用课程。 有关如何创建认证的更多信息，请参阅[认证帮助](feature-summary/certifications.md)。

#### 创建工作辅助 {#createjobaids}

工作辅助是一个培训内容知识库，可供学习者访问，无需任何注册或完成标准。 学习者可以在工作时参考这些工作辅助，获取在公司内执行任何活动或任务的相关协助。尽管在创建课程的过程中并未强制要求使用工作辅助，但 Adobe Learning Manager 团队建议您创建工作辅助，使之成为公司最佳做法。有关如何创建工作辅助的信息，请参阅[工作辅助帮助](../authors/feature-summary/job-aids.md)。

#### 创建学习计划 {#createlearningprograms}

学习计划是一组专门设计的课程，旨在满足特定的学习者目标。在创建学习计划之前，请确保您已经创建部分课程，或者您的帐户中有可用的现有课程。  虽然公司可以选择性使用此功能，但Learning Manager团队建议您使用此功能，向员工灌输专注学习的理念。 要开始使用学习计划，请单击左侧窗格中的“学习计划”，从目录中选择一组课程并发布。 有关具体说明，请参阅[学习计划帮助](feature-summary/learning-programs.md)。

### 创建目录 {#createcatalogs}

您可以使用公司目录创建目标内容或将内容分类到定义的学习者集合。 在 Adobe Learning Manager 中，目录是学习对象（如课程、认证或学习计划）的集合。在创建目录时，您可以根据自己的喜好选择学习对象。 在创建目录之前，请确保您已创建一组课程、认证或学习计划。 如果要将一组学习对象分配给任何内部或外部用户组，则可以使用这些对象自定义创建目录。 有关目录的详细信息，请参阅[目录帮助](feature-summary/catalogs.md)。

### 打开电子邮件通知/用户访问权限 {#turnonemailnotificationsuseraccess}

在此阶段，您可以为应用程序的用户打开电子邮件通知，并启用用户访问权限。

## 第 3 阶段 - 创作课程（作者） {#phase3authoringcoursesauthor}

公司中的内容开发人员或作者可以开始创建学习内容。 模块和课程是构成Learning Manager应用程序中所有学习内容的基础，必须创建。

### 创建模块 {#createmodules}

模块是 Adobe Learning Manager 应用的基本构建块。要整理学习内容，请以作者身份开始创建模块。 您可以从 Adobe Learning Manager 提供的四类课程模块（即教室模块、自学模块、活动模块和虚拟教室模块）中任选一类。请参阅[模块帮助](../authors/how-to-choose-modules.md)，了解最适合公司需求的课程模块类型。

### 创建课程 {#createcourses}

管理员可以在 Adobe Learning Manager 应用中担任作者角色并创建课程。在 Adobe Learning Manager 应用中，课程是具有一组模块的基本单元，且可以分配给学习者。学习者使用课程。 您可以通过以下方式开始创建课程：选择先前创建的模块，关联您希望学习者从课程中习得的技能，将级别、积分和徽章与课程关联，根据自己的喜好选择工作辅助、先决条件和资源，然后发布课程。 您还可以为课程创建多个实例，以便将课程实例分配给状态不同（如处于不同时区、日程安排各异等）的多名学习者。 有关如何创建课程的更多信息，请参阅[课程帮助](../authors/feature-summary/courses.md)。

### 创建学习对象 {#Createlearningobjects-1}

这是三条轨道（轨道 1、轨道 2 和轨道 3）交汇的必经阶段，便于您采取下一步行动。

此时，在创建模块和课程后，您可以开始创建更高级别的学习对象（如认证、学习计划或工作辅助等），以继续下一步。 在开始创建学习对象之前，请确保已在 Adobe Learning Manager 应用中添加部分用户、创建部分模块和课程。

#### 创建认证 {#Createcertifications-1}

认证是对学习者一次性或周期性完成学习内容的证明或成绩证明。 在课程完成后向学习者提供认证，可以让更多学习者注册学习内容。 作为管理员，您可以创建内部托管或第三方执行的认证计划。在内部认证中，指定学习者需完成后才能获得认证的课程。在创建认证之前，请确保您的帐户中有一些可用课程。 有关如何创建认证的更多信息，请参阅[认证帮助](feature-summary/certifications.md)。

#### 创建工作辅助 {#CreateJobaids-1}

工作辅助是一个培训内容知识库，可供学习者访问，无需任何注册或完成标准。 学习者可以在工作时参考这些工作辅助，获取在公司内执行任何活动或任务的相关协助。尽管在创建课程的过程中并未强制要求使用工作辅助，但 Adobe Learning Manager 团队建议您创建工作辅助，使之成为公司最佳做法。有关如何创建工作辅助的信息，请参阅[工作辅助帮助](../authors/feature-summary/job-aids.md)。

#### 创建学习计划 {#Createlearningprograms-1}

学习计划是一组专门设计的课程，旨在满足特定的学习者目标。在创建学习计划之前，请确保您已经创建部分课程，或者您的帐户中有可用的现有课程。  虽然公司可以选择性使用此功能，但Learning Manager团队建议您使用此功能，向员工灌输专注学习的理念。 要开始使用学习计划，请单击左侧窗格中的“学习计划”，从目录中选择一组课程并发布。 有关具体说明，请参阅[学习计划帮助](feature-summary/learning-programs.md)。

## 第 4 阶段 - 管理 LMS（Adobe Learning Manager 管理员） {#phase4managingyourlmscaptivateprimeadministrator}

### 公告 {#announcements}

如果公司希望一次性向帐户中所有学习者分发重大信息，那么公告非常有用。 在 Adobe Learning Manager 应用中，公告是一种多媒体消息（文本、图像或视频），由管理员起草并向一组特定用户组和学习对象进行广播。您可以立即发送公告，也可以安排在特定日期自动触发公告。 如果要在 Adobe Learning Manager 应用中使用此功能，请从左侧窗格中选择“公告”，然后单击“添加”以创建公告。有关详细信息，请参阅[公告帮助](feature-summary/announcements.md)。

### 用户注册 {#userenrollment}

用户注册是 LMS 应用程序的重要一步。 在此阶段，您可以开始将学习者注册到 Adobe Learning Manager 应用中的各种学习对象。您可以使用学习方案，手动或自动注册学习者。

#### 手动注册 {#manualenrollment}

* **自行注册 —**&#x200B;如果在创建学习对象时启用此选项，则学习者可以自行注册到学习对象。
* **经理批准** — 如果在创建课程时在注册类型中选择此选项，则学习者需要经理批准才能完成注册。
* **经理指派** — 如果在创建课程的过程中选择此注册类型，则此类课程必须由经理指派。
* **管理员注册** — 在这种情况下，管理员可以根据组织要求注册部分学习者。

有关详细信息，请参阅[用户注册帮助](feature-summary/courses.md)内容。

要手动将学习者注册到学习对象，可以采用如下四种方式：

### 自动注册 {#automatedenrollment}

使用学习方案自动将学习者注册到学习对象。

#### 学习方案（基于触发器） {#learningplansbasedontriggers}

您可以根据某些事件的发生情况，通过学习计划自动向学习者分配课程、学习计划或认证。 例如，

* 添加新用户
* 用户更改用户组
* 学习者完成学习对象
* 用户完成技能

有关更多信息，请参阅[学习计划帮助](feature-summary/learning-plans.md)内容。

### 创建报告 {#createreports}

在此阶段，您可以开始创建并管理各类报告。

您可以利用 Adobe Learning Manager 创建各种报告来跟踪、监控和控制学习者活动。您可以使用以下三种类型的报告功能来生成报告：

* **报告信息板** — 根据不同类别（用户组、效果、学习者上课时间等）创建总结报告，便于深入了解学习者对学习内容的使用情况。
* **学习者成绩单** — 创建以学习者为中心的报告，其中包含学习者自注册之日起到目前为止的完整历史记录。
* **课程报告** — 根据各个课程创建学习者课程使用情况统计数据。 您还可以在课程级别创建测试报告。

有关报告生成过程的详细信息，请参阅[报告帮助](feature-summary/reports.md)。

有关Learning Manager应用程序功能使用的任何其他信息，请根据相应角色参阅[Learning Manager帮助](../topics.md)。
