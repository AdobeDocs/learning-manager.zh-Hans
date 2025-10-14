---
description: 在 Adobe Learning Manager 中安装 Microsoft Teams 连接器
jcr-language: en_us
title: 在 Adobe Learning Manager 中安装 Microsoft Teams 连接器
contentowner: saghosh
exl-id: 68092187-ac69-4727-a3dc-f3047a1e164d
source-git-commit: 6192559436074c3270644850b202589961e7b81b
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 17%

---

# 在 Adobe Learning Manager 中安装 Microsoft Teams 连接器

## 概述

Microsoft Teams®是基于持续聊天的协作平台，可完全支持文档共享、在线会议和其他业务沟通功能。

Adobe Learning Manager使用虚拟教室连接器与Microsoft Teams会议集成。

Microsoft Teams 连接器可连接 Adobe Learning Manager 和 Microsoft Teams 系统，实现虚拟会议自动同步。Microsoft Teams 连接器的功能如下所示：

**使用Microsoft Teams设置虚拟会话**

此连接器有助于将 Adob&#x200B;&#x200B;e Adobe Learning Manager 帐户与 Microsoft Teams 帐户集成。集成后，借助此连接器，Adobe Learning Manager 中的作者在创建虚拟教室模块时，可使用 Microsoft Teams 作为技术服务提供商。

**允许Microsoft Teams在学习者进入虚拟教室时对其进行身份验证**

此连接器可帮助您在创建会议时从Learning Manager设置Microsoft Teams会议组织者。 会议组织者可以管理大厅以决定是否允许用户进入会议，还可以控制 Microsoft Teams 提供的其他会议选项。

**使用自动用户完成同步**

通过Microsoft Teams完成情况自动同步流程，Learning Manager管理员可自动获取用户会议的完成记录和录制URL。

## Microsoft Teams 中的角色

如果您要组织具有多个参与者的会议，则可以为每个参与者分配角色，以便参与者了解他/她可以在会议中执行哪些操作。

有两种角色可供选择：**演示者**&#x200B;和&#x200B;**与会者**。

有关详细信息，请参阅[Teams会议中的角色 — Microsoft](https://support.microsoft.com/zh-cn/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。

## 设置 Microsoft Teams 连接器

>[!NOTE]
>
>下面标记为&lt;开发人员/可选>的项目为可选项，主要用于在用户没有生产租户的情况下设置Microsoft的试用/开发人员租户。 这些操作是可选的，因为它们大部分操作本应由团队管理员执行。

## 创建开发人员E5 Microsoft帐户&lt;开发人员/可选>

如果您有Office 365 E3或Office 365 E5，则可以访问Microsoft Teams连接器。 建议使用Office 365 E5。

* 访问[Microsoft计划页面](https://www.microsoft.com/en-in/microsoft-365/enterprise/compare-office-365-plans?&ef_id=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&OCID=AID2100137_SEM_CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&lnkd=Google_O365SMB_Brand&gclid=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE)。 在该网页上，您可以购买E3或E5帐户，也可以单击“免费试用”。
* 提供所需信息，创建帐户。

>[!NOTE]
>
>帐户必须使用格式`<username>@<company name>.onmicrosoft.com`。

## 为Microsoft Teams连接器创建应用程序

1. 访问[Microsoft Azure®门户](https://portal.azure.com/)。
1. 使用在上节中创建的Microsoft E5帐户登录。
1. 搜索&#x200B;**Azure Active Directory**。
1. 单击&#x200B;**[!UICONTROL 应用程序注册]**。
1. 单击&#x200B;**[!UICONTROL 新建注册]**，输入以下详细信息，然后注册应用程序：

   1. **名称** — 您选择的任何名称。
   1. **支持的帐户类型** — 任何组织目录（任何Azure Active Directory — 多租户）中的帐户。
   1. **重定向URI（可选）** — 表示回复URL的可选字段。

1. 在&#x200B;**Essentials**&#x200B;列中，请注意以下ID，集成过程中会进一步使用这些ID：

   1. **应用程序（客户端）ID**
   1. **目录（租户）ID**

1. 搜索客户端凭据，然后单击&#x200B;**[!UICONTROL 添加证书或密钥]**。
1. 单击&#x200B;**[!UICONTROL 新建客户端密钥]**&#x200B;并添加以下详细信息：

   1. **描述** — 输入任意名称。
   1. **过期** — 可设为任何值(建议设为24个月。 确保在前一个客户端凭据过期后生成新的凭据）。

请注意，集成过程中会进一步使用客户端密钥。

## 获取Microsoft Teams连接器的访问权限

1. 访问[Microsoft Azure门户](https://portal.azure.com/)。
1. 使用之前创建的Microsoft E5登录。
1. 搜索&#x200B;**Azure Active Directory**。
1. 单击&#x200B;**[!UICONTROL 应用程序注册]**。
1. 单击在上节中创建的应用程序。
1. 单击&#x200B;**[!UICONTROL API权限]**。
1. 单击&#x200B;**[!UICONTROL 添加权限]**。
1. 选择&#x200B;**[!UICONTROL Microsoft Graph]** > **[!UICONTROL 申请权限]**&#x200B;并添加以下权限：

   1. Chat.Read.All
   1. Directory.Read.All
   1. OnlineMeetingArtifact.Read.All
   1. OnlineMeetings.Read.All
   1. OnlineMeetings.ReadWrite.All
   1. User.Read.All
   1. OnlineMeetingRecording.Read.All

1. 单击&#x200B;**[!UICONTROL 授予管理员访问Adobe]**&#x200B;的权限。
1. 单击&#x200B;**[!UICONTROL 应用程序角色]** > **[!UICONTROL 创建应用程序角色]**。
1. 输入以下值：

   1. **显示名称** - API名称/权限名称（例如，Calendars.ReadWrite）。

   1. **允许的成员类型** — 同时指定用户和应用程序（用户/组+应用程序）。

   1. **值** - API名称/权限名称（例如，Calendars.ReadWrite）。

   1. **描述** - API名称/权限名称（例如，Calendars.ReadWrite）。

   1. **是否要启用此应用角色？** — 选中此复选框。

1. 对已添加的所有九个API/权限重复上述步骤。

## 使用PowerShell脚本配置访问策略

若要通过运行PowerShell脚本来配置Microsoft Teams连接器的应用程序访问策略，请按照此[文档](https://docs.microsoft.com/zh-cn/graph/cloud-communication-online-meeting-application-access-policy)中描述的步骤操作。

配置完成后连接器便可以访问 Microsoft Teams 在线会议。

>[!NOTE]
>
>执行上述文档中的第5步（可选）可确保当前所有活跃用户都可以从Learning Manager作者应用程序中获得组织者角色。 如果未执行此步骤，用户将没有成为组织者所需的访问权限，并且会议创建将失败(Microsoft API会将组织者视为Teams会议的创建者)。

## 在Learning Manager中设置Microsoft Teams连接器

1. 以&#x200B;**集成管理员**&#x200B;的身份登录Learning Manager。

1. 在“连接器”页面中，选择“Microsoft Teams”连接器并单击&#x200B;**[!UICONTROL 连接]**。

1. 输入以下值：

   1. **连接名称** — 提供作者在创建会话时可看到的名称。

   1. **Microsoft Teams租户ID** — 输入之前确定的值。

   1. **客户端ID** Microsoft Teams — 输入之前确定的值。

   1. **客户端密钥** Microsoft Teams — 输入之前确定的值。

   1. **Microsoft Teams管理员用户电子邮件** — 输入默认组织者电子邮件。 如果未从Learning Manager作者应用程序中明确选择组织者，则此用户（通常为服务用户）将成为会议创建者。

## 为用户分配许可证&lt;开发人员/可选>

1. 访问[https://admin.microsoft.com/#/homepage](https://admin.microsoft.com/#/homepage)。
1. 单击&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 活动用户]**。
1. 如果希望向某些用户提供Microsoft Teams访问权限，请单击&#x200B;**[!UICONTROL 更多用户操作]**。
1. 单击&#x200B;**[!UICONTROL 管理产品许可证]**。
1. 启用不含音频会议的Office 365 E5许可证。

<!--## Record a session

The API used for recording a session is a protected API. To access the API, you must request access from Microsoft. For more information, see this  [document](https://docs.microsoft.com/en-us/graph/teams-protected-apis).

In the document,

*"To request access to these protected APIs, complete the following  [request form](https://aka.ms/teamsgraph/requestaccess). We review access requests every Wednesday and deploy approvals every Friday, except during major holiday weeks in the U.S. Submissions during those weeks will be processed the following non-holiday week. To verify whether your request has been approved, test your application access on the next applicable Monday."*

For learners, the recording URL is displayed on the VC course overview page.

After 30 minutes of completing a course, the attendance for the learner gets marked. -->

## 常见问题解答

+++谁是组织者和演示者？

有关Microsoft Teams支持的各种角色和功能，请参阅Microsoft的[文档](https://support.microsoft.com/zh-cn/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。

+++

+++组织者是否应该同时注册Learning Manager和Microsoft Teams？

是的，组织者应该同时注册 Adobe Learning Manager 和 Microsoft Teams。此外，组织者必须属于集成管理员应用程序中配置的同一Microsoft租户。

+++

+++演示者是否应该同时注册Learning Manager和Microsoft Teams？

是的，演示者应该同时注册Learning Manager和Microsoft Teams。 演示者必须具有Azure Active Directory ID（可以与组织者属于同一租户，也可以属于任何其他租户）。 此外，即使是匿名用户（仅使用用户名而不是Active Directory登录的用户），也可以在会议期间由组织者或现有演示者指定为演示者。

+++

+++Microsoft Teams提供会议、网络研讨会和现场活动等功能。 Teams 连接器支持哪一种功能？

目前，Teams连接器仅支持Microsoft Teams中的会议。 有关详细信息，请参阅此[文档](https://docs.microsoft.com/zh-cn/microsoftteams/quick-start-meetings-live-events)。

+++
