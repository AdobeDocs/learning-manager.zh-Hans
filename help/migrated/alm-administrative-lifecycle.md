---
title: Adobe Learning Manager管理帐户生命周期
description: 本文档提供了有关在Adobe Learning Manager (ALM)中安全管理顶级管理帐户的综合指导，以满足FedRAMP合规性和最佳安全实践的要求。
jcr-language: en-us
source-git-commit: db3ed4dc44da75b418e923999bdf3776bf81b11f
workflow-type: tm+mt
source-wordcount: '2122'
ht-degree: 0%

---


# Adobe Learning Manager中的管理帐户类型

## ALM角色映射

在Adobe Learning Manager中，顶级管理帐户是管理员角色。 本指南每次使用FedRAMP术语“顶级管理帐户”时，都会提及此角色。 自定义管理员和集成管理员被视为特权（范围）帐户。

下表将FedRAMP帐户层映射到Adobe Learning Manager中使用的特定角色：

| FedRAMP术语 | ALM角色名称 | 描述 |
|--------------------------------------|----------------------------|-------------|
| 顶级管理帐户 | 管理员 | ALM中的最高权限角色。 完全控制用户、角色、学习内容、报告、集成和所有系统配置。 直接映射到FedRAMP顶级管理帐户定义。 |
| 特权帐户（范围） | 自定义管理员 | 管理员权限的一个定义的子集，范围涵盖特定的功能（例如，报告、目录管理）。 没有完全的帐户级别控制。 |
| 特权帐户（集成） | 集成管理员 | 管理ALM和外部系统之间的集成以及基于API的访问。 提升的权限范围仅限于集成管理。 |


Adobe Learning Manager使用基于角色的访问控制(RBAC)模型来管理管理访问权限。 管理角色仅由授权管理员分配。

有关详细信息，请参阅[Adobe Learning Manager中的自定义角色](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)

## 身份类型和推荐的身份验证

Adobe Admin Console支持管理员帐户的三种身份类型。 身份类型的选择具有直接的安全影响：

| 身份类型 | 描述 | 安全建议 |
|---------------------------|-----------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| Adobe ID（个人ID） | 默认类型；由Adobe管理。 任何人都可以创建一个。 | 不建议管理员使用。 组织无法控制此帐户类型。 |
| Enterprise ID | 组织拥有的帐户，由Admin Console系统管理员管理。 | 如果Federated ID/SSO不可用，则接受。 强制执行2FA。 |
| Federated ID(SSO) | 组织所有；与SAML 2.0 SSO集成。 组织完全控制身份验证。 | 推荐。 通过组织的IdP进行身份验证；支持在身份提供者级别执行MFA。 |

有关更多信息，请参阅以下内容：

* [身份类型](https://helpx.adobe.com/enterprise/using/admin-console.html)
* [安全的用户身份验证和密码](https://helpx.adobe.com/enterprise/using/authentication-settings.html)

## 角色分配和访问控制

现有管理员通过明确的[角色分配](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/user-management/add-users-user-groups)来控制对Adobe Learning Manager中管理帐户的访问。 安全管理访问的关键特性包括：

* 管理角色仅由授权管理员分配。
* 访问是基于角色的，并根据分配的权限划分范围。
* 组织负责限制具有合法业务需求的用户的管理访问权限。

Adobe建议客户定期审查管理访问权限，以确保遵守最低权限原则。

## 强制执行多重身份验证(MFA)

Adobe强烈建议管理员在整个企业范围内强制执行两步验证(2FA)。 MFA适用于Enterprise ID和Adobe ID用户。 Federated ID用户应在其组织的身份提供者处强制执行MFA。

要在Adobe Admin Console中实施2FA，请执行以下操作：

1. 登录到Adobe Admin Console。
2. 导航至“设置”>“隐私和安全”>“身份验证设置”。
3. 启用两步验证并选择强制选项以防止用户禁用它。
4. 可以选择配置基于IP的访问限制和高级会话设置（最长会话寿命/最长空闲时间）。

>[!IMPORTANT]
>
>Adobe建议强制实施2FA，而不是为用户保留可选功能。 2FA最多可能需要24小时才能应用。 对于Federated ID用户，请在您的身份提供方强制实施MFA。

有关详细信息，请参阅[安全用户身份验证](https://helpx.adobe.com/enterprise/using/authentication-settings.html)。


## 以管理员身份登录

ALM [管理员](https://experienceleague.adobe.com/en/docs/learning-manager/using/get-started/getting-started-admin)使用通过Admin Console管理的组织凭据直接登录到ALM平台。

### 分配管理员角色

在ALM平台中，管理员可通过创建和管理角色、为用户分配权限以及根据操作责任定义权限范围来配置管理访问权限。

要在ALM中分配管理员角色，请执行以下操作：

1. 以现有管理员身份登录Adobe Learning Manager.
2. 导航到“用户” > “内部” 。
3. 搜索或选择目标用户。
4. 选择操作>分配角色>设为管理员。

自定义管理角色使客户能够委派管理任务，同时保持对帐户级别权限的集中控制。 自定义管理员的范围可以限定为特定的用户组或目录。

有关详细信息，请参阅[添加用户和用户组](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/user-management/add-users-user-groups)。

## 配置登录方法和SSO

ALM管理员通过“设置”>“登录方法”（一个与安全性相关的关键配置）控制所有用户可用的登录方法：

* **内部用户**：将登录模式设置为Adobe ID或单点登录(SSO)。 强烈建议通过SAML 2.0进行SSO。
* **外部用户**：将登录模式设置为Adobe ID、SSO或Learning Manager ID。 将所选方法与您组织的安全策略保持一致。

Adobe建议使用Federated ID/SAML 2.0 SSO作为所有内部用户的登录方法。 这可确保身份验证完全由您组织的身份提供者控制，从而实现集中式MFA强制以及在用户离开时立即撤销帐户。

有关详细信息，请参阅[设置](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/settings)。

## 建议的安全设置默认值

首次设置ALM帐户时，Adobe建议在授予任何管理用户操作访问权限之前验证以下默认设置：

| 设置 | 推荐的安全默认值 | 配置位置 |
|------------------------------|------------------------------------------------------------------|-------------------------------------------------|
| 登录方法 — 内部用户 | 单点登录(SSO)/Federated ID | ALM >设置>登录方法 |
| 两步验证(2FA) | 强制（对于任何用户不是可选的） | “Admin Console”>“设置”>“隐私和安全” |
| 最长会话寿命 | 8小时或每个组织策略 | “Admin Console”>“设置”>“高级设置” |
| 最长空闲时间 | 30分钟或每个组织策略 | “Admin Console”>“设置”>“高级设置” |
| 管理员角色范围 | 最低权限；尽可能使用自定义管理员角色 | ALM >用户>自定义角色 |
| 外部用户到期 | 在每个外部用户个人资料上设置到期日期 | ALM >用户>外部 |

### 新管理员的初始设置核对清单

在设置新的顶级管理员帐户时，请在授予操作访问权限之前完成以下操作：

* 确认身份类型为Enterprise ID或Federated ID — 不是个人Adobe ID。
* 在Admin Console级别强制执行2FA（“设置”>“身份验证设置”）。
* 配置SSO/Federated ID（如果尚未启用）。
* 在Admin Console>设置>高级设置中设置最长会话寿命和最长空闲时间。
* 限制管理员角色范围 — 仅分配用户责任所需的权限。
* 验证管理员帐户是否已绑定到您的IT团队控制的组织电子邮件地址。
* 在贵组织的特权访问注册表中记录该帐户。

## 管理帐户的操作

### 日常管理任务

管理帐户用于执行日常操作任务，包括：

* **用户生命周期管理**：创建用户、更新配置文件和更改角色。
* **学习内容管理**：管理课程、学习计划、认证和目录。
* **报告和分析**：生成和审阅有关学习者进度和平台使用情况的报告。
* **集成和系统配置**：管理连接器、基于API的访问和系统级别设置。

执行管理操作时，管理员应遵循其组织的内部访问控制和更改管理策略。

请参阅[Adobe Learning Manager管理员常见问题解答](https://experienceleague.adobe.com/en/docs/learning-manager/using/faq/frequently-asked-questions-for-administrators)


### 角色层次结构和委派

Adobe Admin Console使用分层管理结构。 系统管理员可以将责任委派给较低权限的角色，以减少顶层管理员帐户的攻击面：

* 产品管理员：管理对特定Adobe产品(例如Adobe Learning Manager)的访问。
* 产品配置文件管理员：管理特定产品配置文件中的用户会员资格。
* 用户组管理员：管理用户组成员资格。
* ALM自定义管理员：ALM内具有每个目录和用户组可配置权限的限定范围的管理员。

### 持续的治理做法

持续运行ALM管理员帐户的组织应遵循以下惯例：

* **定期访问查看**：定期审核Admin Console（“用户”>“管理员”）中的系统管理员和ALM管理员（“用户”>“内部”）的列表，以确保只有当前授权的人员担任这些角色。
* **审核日志监视**：Admin Console审核日志记录管理员所做的所有更改。 系统管理员具有完全可见性。 定期查看日志，了解未经授权的更改。
* **最小静态访问权限**：避免将顶级管理员帐户用于例行任务。 为特别需要的任务保留完全管理员访问权限。
* **会话安全性**：在“Admin Console”>“设置”>“高级设置”中配置“最长会话寿命”和“最长空闲时间”，以限制无人参与会话的暴露情况。

有关详细信息，请参阅[Admin Console概述](https://helpx.adobe.com/enterprise/using/admin-console.html)。

### 在管理员控制下管理用户帐户

ALM管理员管理内部和外部用户帐户。 与安全相关的操作包括：

* 用户自动删除：在“设置”中，管理员可以将非活动内部用户配置为在指定天数后自动删除，从而减少休眠帐户风险。
* 外部用户过期：管理员在创建外部用户配置文件时设置过期日期。 过期的帐户将自动移动到非活动状态。
* 用户删除：管理员可通过“用户”>“内部”>“操作”>“删除用户”手动删除用户。
* 用户清除：删除后，管理员可以永久清除用户记录，以遵守数据保留策略，并防止未经授权访问陈旧的用户数据。

有关更多信息，请参阅以下内容：

* [添加用户和用户组](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/user-management/add-users-user-groups)
* [清除用户](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/purge-users)

## 行政账户解除

如果不再需要管理访问权限，则必须将其删除。 停止运行管理帐户可能包括：

* 撤销用户的管理角色。
* 在不再需要完全管理访问权限时减少权限。
* 在适当的时候从系统中删除用户。

定期查看并删除不必要的管理访问权限有助于保持最低权限的访问。

### 删除系统管理员权限(Admin Console)

当系统管理员离开组织或更改角色时，必须立即撤销权限：

1. 以系统管理员身份登录Adobe Admin Console 。
2. 导航到“用户” > “管理员” 。
3. 选择要删除的管理员。
4. 单击“更多选项(...)”图标>编辑管理员，然后删除系统管理员角色，或选择删除用户以从组织完全删除用户。
5. 如果管理员担任其他角色（产品管理员、支持管理员等），则同时撤销这些角色。

>[!IMPORTANT]
>
>如果离职管理员是组织的合同负责人，则必须将“合同负责人”角色转移给其他人员，然后才能删除他们。 如有需要，请联系Adobe支持。

有关更多信息，请参阅以下内容：

* [在Admin Console上创建、更新或删除用户帐户](https://helpx.adobe.com/enterprise/using/manage-users-individually.html)
* [如何退出您组织拥有的帐户](https://helpx.adobe.com/enterprise/using/leave-organization.html)

### 删除ALM管理员角色

要撤销ALM管理员访问权限而不删除用户的帐户（例如，当人员仍然是学习者时），请执行以下操作：

1. 以管理员身份登录Adobe Learning Manager。
2. 导航到“用户” > “内部” 。
3. 搜索并选择用户。
4. 选择操作>删除角色>删除管理员。

用户将恢复为“学习者”角色。 他们的学习历史记录和课程注册信息将得以保留。

有关详细信息，请参阅[添加用户和用户组](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/user-management/add-users-user-groups)。

### 删除和清除用户

当用户完全离开组织时，应从平台中删除其帐户：

* 删除用户：用户>内部>选择用户>操作>删除用户。 这将禁用帐户并删除活动访问权限。
* 清除用户：删除后，转到“用户”>“用户清理”，选择删除月份，选择用户，然后选择“操作”>“清除用户”。 清除操作将永久删除所有用户记录。

有关详细信息，请参阅[清除用户](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/purge-users)。


## 安全和共同责任

Adobe Learning Manager采用共享责任模式：

* Adobe负责保护基础ALM平台和基础设施。
* 客户负责管理其ALM帐户中的管理访问权限、角色分配和用户生命周期活动。

有关Adobe Learning Manager安全实践的其他信息，请参见[Adobe Learning Manager安全概述(PDF)](https://experienceleague.adobe.com/docs/learning-manager/assets/alm-security-whitepaper-2024.pdf)

## 文档维护

本文档可能会定期更新，以反映Adobe Learning Manager功能或管理最佳实践中的更改。 版本和上次更新日期保存在文档元数据和FedRAMP授权包中。 客户应参考Adobe Experience League上的公开版本，以确保他们使用的是最新指南。

## 增强的安全功能覆盖范围

### SCG-ENH-CMP

Adobe维护记录在案的组件库存、所有权和生命周期管理流程，以确保跨系统组件的受控配置和法规遵从性。

### SCG-ENH-API

Adobe强制实施标准化的API安全控制，包括身份验证、授权和监控，并有文档记录的管理和平台保护措施作为支持。

### SCG-ENH-MRG

Adobe应用正式的更改和合并管理流程（包括审查和批准控制），以维护系统完整性和减少部署风险。

### SCG-ENH-VRH

Adobe遵循已定义的漏洞管理和补救流程，包括识别、确定优先级、跟踪和及时解决。
