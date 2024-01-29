---
description: Microsoft TeamsAdobeLearning Manager应用程序
jcr-language: en_us
title: Microsoft TeamsAdobeLearning Manager应用程序
contentowner: saghosh
source-git-commit: 81dd3cecf7393c08434a70e15457d967a56df8d3
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---


# Microsoft TeamsAdobeLearning Manager应用程序

## 设置方式

在MS团队上设置ALM涉及三个步骤，需要ALM管理员和Microsoft Azure管理员的帮助。 在某些组织中，Azure管理员和MS团队管理员不同，因此还需要其他MS团队管理员。

**ALM管理员 — 集成管理员角色可审批团队应用程序**

在集成管理员批准MS Teams应用程序后，即可在MS Teams应用商店中使用AdobeLearning Manager应用程序，并且学习者可以访问它。 但是，应用程序将不包含通知、静默登录，并且不会为MS Teams中的学习者固定应用程序。

**Microsoft Azure管理员在Azure仪表板中批准ALM应用程序的权限**

Azure管理员必须批准ALM应用程序所需的权限。 这将允许该ALM应用程序向MS Teams发送通知并允许静默登录。 在静默登录中，用户无需单独登录即可在浏览器上AdobeLearning Manager。

**MS Teams管理员为ALM团队创建策略**

管理中心中的MS Teams管理员应为其所有用户固定ALM应用程序，并允许将其作为一项全局策略使用。 如果ALM仅由公司中的某个组使用，则MS团队管理员必须选择自定义策略并仅将该策略应用于该特定组。

## 集成管理员角色可审批团队应用程序

请执行以下步骤：

1. 在集成管理员应用程序上，选择 **[!UICONTROL 应用程序]** > **[!UICONTROL 特色应用程序]**，然后选择 **[!UICONTROL ALM Teams应用程序]**.

   ![](assets/featuredapps.jpg)
   *选择ALM Teams应用程序*

1. 在屏幕右上角，选择 **[!UICONTROL 批准]**.

   ![](assets/integration_admin_approval_form.jpg)
   *在应用程序设置页面上选择批准*

1. 选择 **[!UICONTROL 确定]** 在出现的对话框中，执行以下操作。

   ![](assets/integration_admin_approved_dialog_box.jpg)
   *批准后选择确定*

1. 获得批准后，即可在“外部应用程序”部分中看到“ALM Teams应用程序”。

   ![](assets/integration_admin_external_apps.jpg)
   *ALM Teams应用程序将显示在应用程序页面上*

现在，用户可以在MS Teams上访问ALM应用程序。

## Microsoft Azure管理员在Azure仪表板中批准ALM应用程序的权限

请执行以下步骤：

1. 以Azure管理员身份，导航到Azure仪表板中的“管理Azure Active Directory”部分。

   ![](assets/microsoft_azure.jpg)
   *启动Azure仪表板*

1. 将以下链接粘贴到单独的浏览器窗口中：

   `https://login.microsoftonline.com/<tenantIdTobeReplaced>/oauth2/authorize?client_id=8d349d9f-bf59-4ece-8022-a41e87d81903&response_type=code&redirect_uri=https://learningmanager.adobe.com`

1. 在上方链接中，将 `<tenantIdTobeReplaced>` 租户ID处于可用状态，请参阅下面的“概述”页面。 输入新的URL。

1. 将AdobeLearning Manager应用程序添加到您的Azure应用程序。

   ![](assets/microsoft_azure_dashboard.jpg)
   *添加到Azure*

1. 选择企业应用程序选项卡，然后选择所有应用程序。 您将看到此处列出了ALMTeamsApp。

   ![](assets/microsoft_azure_enterprise_applications.jpg)
   *查看ALM应用程序*

1. 单击该应用程序，然后导航到“权限”选项卡。

   ![](assets/microsoft_azure_ALMTeamsNonProdApp.jpg)
   *查看“权限”选项卡*

1. 在“权限”选项卡中，选择“ **[!UICONTROL 授予MSFT管理员许可]**&#39;以授予ALM Teams应用程序权限。

   ![](assets/microsoft_azure_ALMTeamsNonProdApp_permissions.jpg)
   *选择权限*

1. 选择 **[!UICONTROL 接受]**.

   ![](assets/microsoft_azure_ALMTeamsNonProdApp_permission_request.jpg)
   *选择接受*

1. 授予这些权限后，ALM应用程序将允许静默登录，并在MS Teams应用程序中将通知发送给学习者。

   ![](assets/microsoft_azure_ALMTeamsNonProdApp_permission_request_granted.jpg)
   *已授予访问权限*

## MS Teams管理员为Teams应用程序创建策略

请执行以下步骤：

1. 作为MS Teams管理员，请在管理中心创建用于将Teams应用程序添加到学习者Teams应用程序的策略。

   ![](assets/microsoft_teams_admin_center.png)
   *创建策略*

1. 导航至“设置策略”部分。 创建全局策略并选择 **[!UICONTROL 添加应用程序]** 在固定的应用程序子部分中。

   ![](assets/microsoft_teams_admin_center_add_installed_apps.png)
   *添加策略*

1. 在随后出现的对话框中，搜索 **[!UICONTROL AdobeLearning Manager]**，然后添加该应用程序。 此操作会在“已安装的应用程序”部分添加AdobeLearning Manager。

   ![](assets/microsoft_teams_admin_center_installed_apps.png)
   *安装应用程序*

1. 保存此策略。 这使该应用程序可供组织中的所有人使用。

或者，管理员可以创建自定义策略，而不是全局策略。 将AdobeLearning Manager添加到该自定义策略，然后仅将自定义策略应用于需要访问AdobeLearning Manager的用户组。
