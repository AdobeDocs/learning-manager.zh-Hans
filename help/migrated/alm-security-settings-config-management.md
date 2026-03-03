---
title: Adobe Learning Manager — 安全设置和配置管理
description: 本文档概述了Adobe Learning Manager的管理帐户类型、安全相关设置、推荐的安全默认值、API功能、导出功能、配置比较方法、发布实践和版本历史记录。 它提供了有关特权帐户如何操作、其安全含义以及如何在整个平台上支持配置管理的详细指导。
jcr-language: en-us
exl-id: a2e34104-c417-407f-af85-9f3f4b2a9fcb
source-git-commit: 84d74761c95ac670a93d65a844caebd42e4e4d41
workflow-type: tm+mt
source-wordcount: '1940'
ht-degree: 0%

---

# 简介

本指南提供对Adobe Learning Manager (ALM)的FedRAMP建议（FRR-RSC-03至FRR-RSC-08）的详细回复。 它概述了安全最佳实践、推荐的安全默认值以及用于审核、导出和管理特权帐户设置的工具。 本文档专为管理员和合规性团队而设计，旨在确保ALM帐户的安全配置和管理。

它还突出显示了ALM满足或部分满足FedRAMP标准的领域，并引用了Adobe Experience League上的支持文档和资源。

+++Adobe Learning Manager中的自定义管理员或集成管理员只能操作哪些与安全相关的设置？它们会对安全产生哪些影响？

Adobe Learning Manager的两个特权帐户类型 — 自定义管理员和集成管理员。 每个系统都有一组明确的安全相关设置，并附带有文件规定的含义。

**自定义管理员 — 他们可以操作哪些内容**：

* 自定义角色由完整管理员在“ALM管理员”>“用户”>“自定义角色”中配置。 自定义管理员可以获准访问以下一个或多个权限类别：帐户权限（公告、游戏、技能、用户管理）、功能权限（目录、报告、标签）和学习对象权限（课程、认证、学习路径）。
* 范围是安全性最敏感的设置：自定义角色可以限制为特定用户组和/或特定目录。 在不限制范围的情况下，自定义角色可在整个平台范围内有效地访问其授予的功能，接近一个完整管理员的足迹。
* 如果在“帐户权限”下向自定义角色授予“设置”访问权限，则该自定义管理员可以修改登录方法、通知设置和帐户级别配置 — 这是一个影响重大的权限，只能通过明确的业务合理性来授予该权限。

**集成管理员 — 他们可以操作哪些内容**：

* 集成管理员在集成管理员>应用程序>注册中管理OAuth 2.0应用程序注册。 他们可从六个OAuth范围中选择一个，范围从学习者读取权限到管理员角色读取/写入权限。 管理员读/写范围通过API授予已注册应用程序与完全管理员相同的权限。
* 集成管理员可以配置FTP、SFTP、Salesforce、Workday和其他连接器，它们可以导入用户记录、角色分配和课程完成，并将平台数据导出到外部系统。
* 集成管理员配置Webhook，以将实时ALM事件数据（注册、完成、角色更改）推送至外部URL。 已泄露或配置错误的Webhook端点存在数据导出风险。
* 集成管理员可以配置LTI集成。 启用后，无法禁用LTI。

**引用**：

* [自定义角色 | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)
* [通过CSV管理自定义角色 | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/configure-role-csv-files)
* [应用程序开发人员手册 | Adobe Learning Manager][https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual]
* [Adobe Learning Manager连接器](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/connectors)

+++

+++对于Adobe Learning Manager中的顶级管理和特权帐户，建议采用哪些安全默认值？这些帐户在何处配置？

Adobe Learning Manager记录了“管理员”角色和特权帐户类型的特定建议安全默认值。

* **顶层管理员帐户默认值（在首次设置时配置）**：

* 内部用户的登录方法：通过SAML 2.0单点登录(SSO)：在“ALM管理员”>“设置”>“登录方法”中配置。 员工或管理员不得使用Adobe ID。
* 两步验证(2FA)：对所有用户强制执行：在Adobe Admin Console > “设置” > “隐私和安全” > “身份验证设置”中配置。
* 最长会话寿命：8小时（或根据组织策略）：在Adobe Admin Console > “设置” > “隐私和安全” > “高级设置”中配置。
* 最长空闲时间：30分钟（或根据组织策略）：与上述位置相同。
* 非活动用户自动删除：启用时具有组织定义的保留期（例如，90天非活动）：ALM“管理员”>“设置”>“常规”。
* 外部用户配置文件过期：在创建时针对每个外部配置文件设置：ALM管理员>用户>外部。 没有不确定的外部个人资料。
* IP访问限制：在可行的情况下，限制为批准的IP范围：Admin Console>设置>高级设置。

**自定义管理员角色默认值（创建每个角色时配置）**：

* 已注册应用程序的OAuth范围：所需的最低范围。 除非绝对必要，否则绝不要授予管理员角色读/写访问权限。
* 自定义角色范围：限制为特定用户组和特定目录。 不要创建作用域为“所有用户”和“所有目录”的自定义角色，除非该功能真正需要它。
* 自定义角色中的设置访问权限：考虑到权限提升风险，除非特定功能需要，否则请勿授予权限。

**集成管理员默认值**：

* API OAuth范围：选择满足集成要求的最严格的范围。 请勿将读/写权限授予仅需要学习者阅读权限的应用程序。
* 连接器凭据、LTI凭据和Webhook URL：视为敏感机密 — 从不通过电子邮件共享或提交到源代码管理。

**引用**：

* [设置 | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)
* [安全的用户身份验证和密码 | Adobe Admin Console](https://helpx.adobe.com/enterprise/using/authentication-settings.html)
* [自定义角色 | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)

+++

+++Adobe Learning Manager是否为管理员提供了一种将当前帐户设置与建议的安全默认设置进行比较的方法？

Adobe Learning Manager没有专用的比较仪表板，无法自动显示当前设置和推荐的安全默认值。

**自定义角色报告：当前特权角色分配**：

* 在ALM中，导航到“管理员”>“用户”>“自定义角色”，然后单击“下载”（右上角）以导出所有自定义角色、其权限集及其范围分配的CSV。
* 将此导出与FRR-RSC-02第8部分中的推荐默认值进行比较 — 具体检查是否有任何自定义角色具有“设置”访问权限、“所有用户”范围或“所有目录”范围，但无文档说明。

**ALM REST API：编程配置检索**：

* GET/account终结点以JSON格式返回帐户级别配置数据，可使用OAuth作用域中的管理员角色进行访问。 客户可以通过编程方式调用此端点，并将响应与从FRR-RSC-02第8节中的建议默认值派生的基线进行比较。
* GET/users端点（使用include=role筛选器）返回所有用户的当前角色分配，从而能够自动检测意外的角色分配。

>[!NOTE]
>
>Adobe Learning Manager不提供本机并排比较UI。 需要自动进行配置合规性检查的客户应将ALM REST API与其现有工具集成。

**引用**

* [应用程序开发人员手册 | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual)

+++

+++管理员能否以计算机可读的格式从Adobe Learning Manager导出当前与安全相关的设置和配置？

Adobe Learning Manager支持通过多种机制导出与安全相关的配置数据。 没有单个导出一次生成所有安全设置的完整快照，但以下导出内容共同涵盖了安全相关数据的完整范围。

**ALM REST API：当前角色分配和帐户配置的JSON导出**：

* GET/account：返回JSON中的帐户级别设置，包括活动登录配置数据和帐户元数据。
* GET/users？include=role：返回当前在JSON中分配了角色的所有用户。
* GET/userGroups — 返回与审核自定义角色范围相关的所有用户组及其成员资格。
* 所有API响应均为JSON (vnd.api+json)。 身份验证使用具有管理员角色读/写范围的OAuth 2.0。

**自定义角色CSV导出：当前特权角色定义**：

* ALM管理员>用户>自定义角色>下载将导出包含所有自定义角色定义、其权限类别和范围分配的CSV。
* 此导出可以用作当前特权帐户配置的计算机可读快照。
**

**作业API：批量用户和角色数据**：

* ALM作业API支持按需生成CSV格式的用户报告（包括角色分配）。 外部合规性或SIEM工具可以计划和使用这些内容。

**引用**

* [应用程序开发人员手册 | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual)

+++

+++Adobe Learning Manager是否提供可通过其以编程方式查看和调整与安全相关的设置的API？

Adobe Learning Manager提供了完整的REST API v2，允许使用OAuth 2.0身份验证以编程方式查看和调整与安全性相关的设置。 下面是与安全设置相关的特定API功能：

**身份验证和作用域**：

* 应用程序由集成管理员在集成管理员>应用程序>注册中注册。 OAuth 2.0客户端ID和密钥按应用程序颁发。
* 有六个作用域可用。 对于安全设置管理，需要具有管理员角色的读取/写入权限。 这将授予应用程序与完整管理员通过API的相同访问权限。
* 访问令牌是通过标准OAuth授权代码或客户端凭据流获取的。 基本URL： https://learningmanager.adobe.com/primeapi/v2/

**通过API进行用户和角色管理**：

* GET/users：检索所有用户及其当前角色
* POST/users：以编程方式设置新用户
* PATCH/users/{id}：更新用户属性，包括角色分配
* /users/{id}DELETE：禁用用户帐户
* POST/users/{id}/purge：永久清除用户和所有相关记录

帐户配置检索：

* GET/account：返回JSON格式的帐户级配置，包括帐户设置数据，包括complianceLabelDefaultID、showComplianceLabel和custom_injustions等字段。

+++

+++Adobe Learning Manager是否以OSCAL、JSON或YAML等机器可读格式发布其安全配置指南？

Adobe Learning Manager目前不以计算机可读的格式发布其《安全配置指南》。 [FRR-RSC-01](/help/migrated/alm-administrative-lifecycle.md)和[FRR-RSC-02](/help/migrated/alm-secure-administration-guide.md)中的指南已作为人类可读文档在Adobe Experience League上发布，采用HTML和可下载的文档格式。

没有公开可用的OSCAL组件定义、YAML基线或JSON策略文件编码为Adobe Learning Manager建议的安全默认值。

需要自动将当前设置与推荐基线进行比较的客户应使用[ALM REST API](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual)以JSON格式检索当前配置数据。

+++

+++Adobe Learning Manager的《安全配置指南》是否可以公开提供，而无需登录或特殊访问？

**公开可用的内容**：

* [FRR-RSC-01：安全管理指南](/help/migrated/alm-administrative-lifecycle.md)：顶层管理帐户的完整生命周期指南。
* [FRR-RSC-02：管理安全设置和含义](/help/migrated/alm-secure-administration-guide.md)：所有安全相关的设置、其含义和建议的默认值。
* FRR-RSC-03-10（本文档） — 对所有8个FedRAMP SHOULD建议的问答响应。

+++

+++Adobe Learning Manager是否提供版本控制和发布历史记录，使机构可跟踪一段时间以来对安全相关设置和推荐默认值的更改？

Adobe Learning Manager会为每次产品更新保留一个公开可用的详细版本历史记录。 每个版本都记录了对管理设置、身份验证功能、API端点和角色管理功能进行的与安全相关的更改。

**ALM发行说明：编号、累积的更改历史记录**：

* Adobe会为每个Adobe Learning Manager更新（例如，更新100、更新99）发布带编号的发行说明。 这些会在Experience League时发布，并记录所有新增功能、现有设置更改、API添加和移除、连接器更改以及已弃用的功能。
* 每个发行说明都有一个专用的API更改部分，其中列出了与安全性相关配置功能直接相关的新端点、修改的响应字段以及弃用项。

**新增功能页面：每个版本功能摘要**：

* 每个主要版本都有一个专用的“新增功能”页面，其中记录了上下文相关的全新安全功能。 例如，发行说明包括对自定义角色权限处理的更改、为自定义角色增加CSV创建的权限可见性以及API速率限制更改。

**API弃用列表：已删除API功能的权威记录** s：

* Adobe维护着一个专用的“API弃用”页面，其中列出了所有已弃用和已删除的ALM API端点以及其中每次发生弃用的发行版本。

**引用**：

* [Adobe Learning Manager发行说明](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/release-notes)
* [Adobe Learning Manager的新增功能](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/whats-new-july-2024)
* [Adobe Learning Manager中的API弃用](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/api-deprecations-list)

+++
