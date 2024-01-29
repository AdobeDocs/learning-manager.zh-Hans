---
description: 在AdobeLearning Manager中安装Microsoft Teams连接器
jcr-language: en_us
title: 在AdobeLearning Manager中安装Microsoft Teams连接器
contentowner: saghosh
source-git-commit: ab6737e8b43222a6538921b0628a504a5f15859d
workflow-type: tm+mt
source-wordcount: '1258'
ht-degree: 0%

---



# 在AdobeLearning Manager中安装Microsoft Teams连接器

## 概述

Microsoft® Teams®是基于持续聊天的协作平台，可完全支持文档共享、在线会议和其他业务沟通功能。

AdobeLearning Manager使用虚拟教室连接器与Microsoft Teams会议集成。

Microsoft Teams连接器可连接Learning Manager和Microsoft Teams系统，实现虚拟会议自动同步。 以下列表介绍了Microsoft Teams连接器的功能：

**使用Microsoft Teams设置虚拟会话**

此连接器可帮助将您的AdobeLearning Manager帐户与Microsoft Teams帐户集成。 集成后，借助此连接器，Learning Manager中的作者在创建虚拟教室Microsoft Teams时，可使用“模块”作为技术服务提供商。

**允许Microsoft Teams在学习者进入虚拟教室时对其进行身份验证**

此连接器可帮助您在创建会议时从Learning Manager设置Microsoft Teams会议组织者。 会议组织者可以管理大厅以限制或允许其进入会议，还可以控制Microsoft Teams提供的其他会议选项。

**使用用户完成情况自动同步**

通过Microsoft Teams完成情况自动同步流程，Learning Manager管理员可自动获取用户会议的完成记录和录制URL。

## Microsoft Teams中的角色

如果您要组织具有多个参与者的会议，则可以为每个参与者分配角色，以便参与者了解他/她可以在会议中执行哪些操作。

有两个角色可供选择： **演示者** 和 **与会者**.

有关详细信息，请参阅  [Teams会议中的角色 — Microsoft](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

## 设置Microsoft Teams连接器

>[!NOTE]
>
>已标记的项目 &lt;developer optional=&quot;&quot;> 以下是可选的，主要用于在用户没有生产租户的情况下设置Microsoft的试用/开发人员租户。 这些操作是可选的，因为它们大部分操作本应由团队管理员执行。

## 创建开发人员E5 Microsoft帐户 &lt;developer optional=&quot;&quot;>

如果您有Office 365 E3或Office 365 E5，则可以访问Microsoft Teams连接器。 建议使用Office 365 E5。

* 访问 [Microsoft计划页面](https://www.microsoft.com/en-in/microsoft-365/enterprise/compare-office-365-plans?&amp;ef_id=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&amp;OCID=AID2100137_SEM_CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&amp;lnkd=Google_O365SMB_Brand&amp;gclid=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE) . 在该网页上，您可以购买E3或E5帐户，也可以单击“免费试用”。

* 提供所需信息并创建帐户。

>[!NOTE]
>
>帐户必须使用格式 `<username>@<company name>.onmicrosoft.com`.

## 为Microsoft Teams连接器创建应用程序

1. 访问  [Microsoft Azure®门户](https://portal.azure.com/).
1. 使用在上节中创建的Microsoft E5帐户登录。
1. 搜索 **Azure Active Directory**.
1. 点击 **[!UICONTROL 应用程序注册]**.
1. 点击 **[!UICONTROL 新注册]**，输入以下详细信息，并注册应用程序：

   1. **名称**  — 随意输入名称。
   1. **支持的帐户类型**  — 任何组织目录（任何Azure Active Directory — 多租户）中的帐户。
   1. **重定向URI（可选）**  — 表示回复URL的可选字段。

1. 在 **基本** 列中，请注意以下ID，集成过程中会进一步使用这些ID：

   1. **应用程序（客户端）ID**
   1. **目录（租户）ID**

1. 搜索客户端凭据，然后单击 **[!UICONTROL 添加证书或密钥]**.
1. 点击 **[!UICONTROL 新客户端密钥]** 并添加以下详细信息：

   1. **描述**  — 输入任意名称。
   1. **过期**  — 设置为任何值(建议设为24个月。 确保在前一个客户端凭据过期后生成新的凭据)。

请注意，集成过程中会进一步使用客户端密钥。

## 获取Microsoft Teams连接器的访问权限

1. 访问  [Microsoft Azure门户](https://portal.azure.com/).
1. 使用之前创建的Microsoft E5登录。
1. 搜索 **Azure Active Directory**.
1. 点击 **[!UICONTROL 应用程序注册]**.
1. 单击在上节中创建的应用程序。
1. 点击 **[!UICONTROL API权限]**.
1. 点击 **[!UICONTROL 添加权限]**.
1. 选择 **[!UICONTROL Microsoft Graph]** > **[!UICONTROL 应用程序权限]** 并添加以下权限：

   1. Chat.Read.All
   1. Directory.Read.All
   1. OnlineMeetingArtifact.Read.All
   1. OnlineMeetings.Read.All
   1. OnlineMeetings.ReadWrite.All
   1. User.Read.All

1. 点击 **[!UICONTROL 向Adobe授予管理员访问权限]**.
1. 点击 **[!UICONTROL 应用程序角色]** > **[!UICONTROL 创建应用程序角色]**.
1. 输入以下值：

   1. **显示名称** - API名称/权限名称（例如，Calendars.ReadWrite）。

   1. **允许的成员类型**  — 同时指定用户和应用程序（用户/组+应用程序）。

   1. **值** - API名称/权限名称（例如，Calendars.ReadWrite）。

   1. **描述** - API名称/权限名称（例如，Calendars.ReadWrite）。

   1. **是否要启用此应用程序角色？**  — 选中此复选框。

1. 对已添加的所有九个API/权限重复上述步骤。

## 使用PowerShell脚本配置访问策略

要通过运行PowerShell脚本来配置Microsoft Teams连接器的应用程序访问策略，请按照以下步骤操作  [文档](https://docs.microsoft.com/en-us/graph/cloud-communication-online-meeting-application-access-policy).

这样连接器便可以访问Microsoft Teams联机会议。

>[!NOTE]
>
>执行上述文档中的第5步（可选）可确保当前所有活跃用户都可以从Learning Manager作者应用程序中获得组织者角色。 如果未执行此步骤，用户将没有成为组织者所需的访问权限，并且会议创建将失败(Microsoft API会将组织者视为Teams会议的创建者)。

## 在Learning Manager中设置Microsoft Teams连接器

1. 以集成管理员身份登录Learning Manager。

1. 在连接器页面中，选择Microsoft Teams连接器，然后单击 **[!UICONTROL Connect]**.

1. 输入以下值：

   1. **连接名称**  — 提供作者在创建会话时可看到的名称。

   1. **Microsoft Teams租户ID**  — 输入之前确定的值。

   1. **Microsoft Teams客户端ID**  — 输入之前确定的值。

   1. **Microsoft Teams客户端密钥**  — 输入之前确定的值。

   1. **Microsoft Teams管理员用户电子邮件**  — 输入默认组织者电子邮件。 如果未从Learning Manager作者应用程序中明确选择组织者，则此用户（通常为服务用户）将成为会议创建者。

## 将许可证分配给用户 &lt;developer optional=&quot;&quot;>

1. 访问 [https://admin.microsoft.com/#/homepage](https://admin.microsoft.com/#/homepage).
1. 点击 **[!UICONTROL 用户]** > **[!UICONTROL 活动用户]**.
1. 点击 **[!UICONTROL 针对用户的更多操作]** ，用于要向其提供Microsoft Teams访问权限的用户。
1. 点击 **[!UICONTROL 管理产品许可证]**.
1. 启用不含音频会议的Office 365 E5许可证。

## 录制会话

用于录制会话的API是受保护的API。 要访问该API，您必须向Microsoft请求访问权限。 有关更多信息，请参阅此文档  [文档](https://docs.microsoft.com/en-us/graph/teams-protected-apis).

在文档中，

*“要请求访问这些受保护的API，请完成以下操作  [请求表单](https://aka.ms/teamsgraph/requestaccess). 我们会在每周三审查访问请求，每周五进行审批，美国主要节假日周除外。在这些周中提交的请求会在下一个非节假日周进行处理。 要验证您的请求是否已获批，请在下一个相应的周一测试应用程序访问权限。”*

学习者可在“VC课程概述”页面上看到录制URL。

完成课程30分钟后，系统即会标记学习者的出勤情况。

## 常见问题解答

+++谁是组织者和演示者？

请参见  [文档](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019) 从Microsoft获得Microsoft Teams支持的各种角色和功能。

+++

+++组织者是否应该同时注册Learning Manager和Microsoft Teams？

是的，组织者应该同时注册Learning Manager和Microsoft Teams。 此外，组织者必须属于集成管理员应用程序中配置的同一Microsoft租户。

+++

+++演示者是否应该同时注册Learning Manager和Microsoft Teams？

是的，演示者应该同时注册Learning Manager和Microsoft Teams。 演示者必须具有Azure Active Directory ID（可以与组织者属于同一租户，也可以属于任何其他租户）。 此外，即使是匿名用户（仅使用用户名而不是Active Directory登录的用户），也可以在会议期间由组织者或现有演示者指定为演示者。

+++

+++Microsoft Teams提供会议、网络研讨会和现场活动等功能。 Teams连接器支持哪一种功能？

目前，Teams连接器仅支持Microsoft Teams中的会议。 有关更多信息，请参阅此文档  [文档](https://docs.microsoft.com/en-us/microsoftteams/quick-start-meetings-live-events).

+++
