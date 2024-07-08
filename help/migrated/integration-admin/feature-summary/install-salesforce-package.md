---
jcr-language: en_us
title: 安装 Salesforce 程序包
description: Learning Manager 提供了一个 Salesforce 应用程序包。 在 SFDC 中安装和配置程序包后，销售员工便可以在 SFDC 门户中开展培训活动。 SFDC 用户可利用此应用直接在 SFDC 门户中探索新培训、查看推荐内容及参加培训。 用户还可以在 SFDC 门户内的应用程序内以刊头的形式获得管理员发送的公告。
contentowner: saghosh
exl-id: 2b1c32e7-81af-4c13-a2bd-66684cde084e
source-git-commit: dffa765061b35d4559388e4120e51943768c8db8
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 47%

---

# 安装 Salesforce 程序包

## 概述

Learning Manager 提供了一个 Salesforce 应用程序包。 在 SFDC 中安装和配置程序包后，销售员工便可以在 SFDC 门户中开展培训活动。 SFDC 用户可利用此应用直接在 SFDC 门户中探索新培训、查看推荐内容及参加培训。 用户还可以在 SFDC 门户内的应用程序内以刊头的形式获得管理员发送的公告。

### 在 Adobe Learning Manager 应用程序中设置

1. 以集成管理员身份登录 Adobe Learning Manager 管理员帐户。
1. 单击“应用程序&#x200B;]**”**[!UICONTROL >**[!UICONTROL “特色应用程序]**”。
1. 单击 **[!UICONTROL Salesforce]**。
1. 在 Salesforce 应用程序页面上，记下说明中提到的应用程序 ID（也称为客户端 ID）和客户端密码。
1. 单击“批准&#x200B;]**”**[!UICONTROL ，您的应用必须成功获得批准。
1. 单击“开发人员资源&#x200B;]**”**[!UICONTROL >**[!UICONTROL “用于测试和开发的]**&#x200B;访问令牌”。
1. 在“获取 OAuth 代码”部分中，客户端 ID 和范围必须设置为 - admin：read，admin：write。 单击“ **[!UICONTROL 提交]**”。
1. 在“获取刷新令牌”中，输入“客户端 ID”和客户端密钥。 单击“提交&#x200B;]**”**[!UICONTROL &#x200B;并记下刷新令牌。

### 在 Salesforce 应用中创建帐户

1. 在 Salesforce 注册页面创建帐户。 您必须在开发人员版或企业版中创建 Salesforce 帐户。  [开发人员注册 URL](https://developer.salesforce.com/signup)。 确保必须使用电子邮件 ID 来注册已用于学习管理器的 Salesforce。
1. 通过验证电子邮件验证您的帐户。
1. 创建密码并登录 Salesforce。
1. 在登录后记下 Salesforce URL（例如，site.lightning.force.com）

### 安装 Adobe Learning Manager 包

要安装程序包，必须首先删除 Salesforce 中现有的程序包。 卸载前必须启用以下设置。 必须应用这些设置，否则无法安装程序包。

![](assets/uninstall-package.png)

*安装学习管理器程序包*

>[!NOTE]
>
>Adobe Learning Manager 应用程序仅在 Salesforce Lightning 视图中受支持。

1. 启动  [学习管理器程序包 URL](https://test.salesforce.com/packaging/installPackage.apexp?p0=04tDb000000LRvP)。
1. 在 **“登录** ”页面中，单击“ **[!UICONTROL 使用自定义域]**”。

1. 输入程序包 URL，然后单击“继续&#x200B;]**”。**[!UICONTROL &#x200B;安装页面必须选中“仅为管理员安装”选项。 请勿更改此选项。
1. 单击“ **英寸高**”。 安装包后，单击“完成&#x200B;]**”。**[!UICONTROL &#x200B;系统将转至“已安装程序包”页面，您可以看到 Adobe Learning Manager 中已安装的程序包。

1. 转到 App Launcher（位于“设置”旁），然后搜索 Adobe Learning Manager。
1. 要配置应用程序，请单击配置&#x200B;****。
1. 单击“新建&#x200B;]**”**[!UICONTROL &#x200B;并添加以下详细信息：

   * **配置**：输入您选择的名称。
   * **客户端 ID**：输入从第一部分中获取的值。
   * **客户端机密：** 输入从第一部分中获取的值。
   * **刷新令牌：** 输入从第一部分中获取的值。
   * **LearningManagerBaseURL：** 托管学习管理器的站点的 URL。
   * **禁用重定向**：禁用重定向至 Adobe Learning Manager 中的学习者主页。

>[!NOTE]
>
>您只能创建一个配置。 如果您尝试添加其他配置，系统将显示错误消息。 配置可将 Salesforce 帐户映射到学习者帐户。

### 添加远程站点设置

1. 在页面的右上角，单击“ **[!UICONTROL 设置]**”。
1. 在“快速查找”中&#x200B;****，搜索“远程站点设置”。
1. 单击“ **[!UICONTROL 新建远程站点]**”。
1. 输入详细信息：

   1. **远程站点名称**：输入您选择的名称。
   1. **远程站点 URL**：托管 Adobe Learning Manager 的站点的 URL。

1. 启动 Adobe Learning Manager。

### 将 Adobe 域添加到 Salesforce 受信任的 URL

要将 Adobe 域添加到受信任的 URL，请执行以下步骤：

1. 在 Salesforce 控制台中，转到 **[!UICONTROL “设置]** ”> **[!UICONTROL “快速查找]**”。
1. 搜索“ **[!UICONTROL 受信任的]** URL”，然后选择“ **[!UICONTROL 新建受信任的 URL]**”。
1. 在“API 名称&#x200B;]**”**[!UICONTROL &#x200B;字段中键入名称。
1. 将该 URL 添加为 `{}.adobe.com{*}`.
1. 选中 CSP 指令&#x200B;**中的所有**&#x200B;复选框并保存更改。
1. 编辑 Salesforce 应用程序的刷新令牌并保存。
1. 重新启动 Salesforce 应用程序。

### 启用 Adobe Learning Manager 应用程序的通知

1. 在右上角，单击“设置&#x200B;**”。**
1. 搜索自定义通知。
1. 单击“新建&#x200B;]**”。**[!UICONTROL 
1. 输入以下详细信息：

   1. **自定义通知名称：** 学习管理器通知
   1. **API 名称：** 学习管理器通知

1. **选择桌面**&#x200B;和&#x200B;**移动设备**&#x200B;作为支持的频道。

1. 单击&#x200B;**[!UICONTROL “保存”]**。
1. 要为移动设备启用推送通知，请按以下步骤操作：

   1. 在手机中安装 Salesforce 移动应用。
   1. 使用凭据登录应用。
   1. 转到 **设置** > **通知传递设置**。
   1. 添加适用于 iOS 和 Android 版本的 Salesforce。

### 从 Salesforce 中卸载 Adobe Learning Manager

1. 在 Salesforce 应用程序中，转到“已安装的包”。
1. 单击“卸载&#x200B;]**”。**[!UICONTROL 

## 为 Salesforce 用户配置 Adobe Learning Manager

Adobe Learning Manager 应用程序也适用于任何使用 Salesforce 帐户的用户。Salesforce 管理员可以根据配置文件添加用户。 Salesforce 配置文件与 Adobe Learning Manager 中的配置文件类似。例如，管理员、集成管理员、讲师等。 Salesforce 管理员还可以创建自定义配置文件。

### 配置文件

作为 Salesforce 管理员，您可以将配置文件分配给用户或创建自定义配置文件。

>[!NOTE]
>
>用户必须同时存在于 Salesforce 和 Learning Manager 中。

![](assets/create-profile.png)

*将配置文件分配给学习者*

添加学习者时，您必须为学习者分配特定的配置文件。 然后转到该配置文件并授予所需的访问权限。

若要让学习者查看学习管理器应用程序，您必须为所有学习者启用该应用程序。

然后提供访问 Adobe Learning Manager 应用程序的权限。

![](assets/permission-set.png)

*添加权限以访问学习管理器应用*

安装包时，会创建一个新的权限集，即 **Adobe Learning Manager User**。 转到权限集，然后添加用户。

选择用户并为其分配相应权限。 学习者现在可以访问 Adobe Learning Manager 应用程序。

首先，选择一个配置文件（例如，用户的“标准配置文件”），然后单击该配置文件。 单击“编辑&#x200B;]**”，然后在“**&#x200B;自定义应用程序设置”**[!UICONTROL **&#x200B;部分，启用“Adobe Learning Manager **”复选框**。启用后用户便可访问该应用。

在&#x200B;**“自定义选项卡设置”**&#x200B;部分的&#x200B;**“学习者主页”**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL “默认启用”]**&#x200B;选项。

您必须让应用对所有配置文件可见。

单击“保存&#x200B;]**”**[!UICONTROL ，属于所有配置文件的学习者将访问学习管理器应用程序。
