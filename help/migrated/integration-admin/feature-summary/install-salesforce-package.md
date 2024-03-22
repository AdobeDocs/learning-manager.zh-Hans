---
jcr-language: en_us
title: 安装 Salesforce 程序包
description: Learning Manager提供Salesforce应用程序包。 在 SFDC 中安装和配置程序包后，销售员工便可以在 SFDC 门户中开展培训活动。 SFDC 用户可利用此应用直接在 SFDC 门户中探索新培训、查看推荐内容及参加培训。 用户还可以直接在SFDC门户的应用中以刊头的形式收到管理员发送的公告。
contentowner: saghosh
exl-id: 2b1c32e7-81af-4c13-a2bd-66684cde084e
source-git-commit: 970c5f46d6af49bfcca09f88f3d0ece1168fe442
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 51%

---

# 安装 Salesforce 程序包

## 概述

Learning Manager提供Salesforce应用程序包。 在 SFDC 中安装和配置程序包后，销售员工便可以在 SFDC 门户中开展培训活动。 SFDC 用户可利用此应用直接在 SFDC 门户中探索新培训、查看推荐内容及参加培训。 用户还可以直接在SFDC门户的应用中以刊头的形式收到管理员发送的公告。

### 在 Adobe Learning Manager 应用程序中设置

1. 以集成管理员身份登录 Adobe Learning Manager 管理员帐户。
1. 点击 **[!UICONTROL 应用程序]** > **[!UICONTROL 特色应用程序]**.
1. 点击 **[!UICONTROL Salesforce]**.
1. 在Salesforce应用程序页面上，请注意描述中提到的应用程序ID（也称为客户端ID）和客户端密钥。
1. 点击 **[!UICONTROL 批准]** 并且必须成功批准您的应用程序。
1. 点击 **[!UICONTROL 开发人员资源]** > **[!UICONTROL 用于测试和开发的访问令牌]**.
1. 在“获取OAuth代码”部分中，“客户端ID”和作用域必须设置为“admin：read，admin：write”。 点击 **[!UICONTROL 提交]**.
1. 在“获取刷新令牌”中，输入“客户端 ID”和客户端密钥。 点击 **[!UICONTROL 提交]** 并记下刷新令牌。

### 在 Salesforce 应用中创建帐户

1. 在 Salesforce 注册页面创建帐户。 您必须在开发人员版或企业版中创建Salesforce帐户。  [开发人员注册URL](https://developer.salesforce.com/signup). 确保必须使用在Learning Manager中使用的电子邮件ID注册Salesforce。
1. 通过验证电子邮件验证您的帐户。
1. 创建密码并登录 Salesforce。
1. 登录后记下Salesforce URL(例如site.lightning.force.com)

### 安装 Adobe Learning Manager 包

要安装程序包，必须首先删除 Salesforce 中现有的程序包。 卸载前必须启用以下设置。 必须应用这些设置，否则无法安装程序包。

![](assets/uninstall-package.png)

*安装Learning Manager包*

>[!NOTE]
>
>仅在Salesforce Lightning视图中支持AdobeLearning Manager应用程序。

1. 启动  [Learning Manager程序包URL](https://test.salesforce.com/packaging/installPackage.apexp?p0=04tDb000000LRvP).
1. 在 **登录** 页面，单击 **[!UICONTROL 使用自定义域]**.

1. 输入程序包URL，然后单击 **[!UICONTROL 继续]**. 必须在安装页面选中“仅限管理员安装”选项。 请勿更改此选项。
1. 点击 **英寸高**. 安装程序包后，单击 **[!UICONTROL 完成]**. 系统将转至“已安装程序包”页面，您可以看到 Adobe Learning Manager 中已安装的程序包。

1. 转到 App Launcher（位于“设置”旁），然后搜索 Adobe Learning Manager。
1. 要配置应用程序，请单击 **[!UICONTROL 配置]**.
1. 点击 **[!UICONTROL 新]** 并添加以下详细信息：

   * **配置**：输入您选择的名称。
   * **客户端ID**：输入从第一部分获取的值。
   * **客户端密码：** 输入从第一部分获取的值。
   * **刷新令牌：** 输入从第一部分获取的值。
   * **学习管理器基本网址：** Learning Manager托管站点的URL。
   * **禁用重定向**：禁用重定向至 Adobe Learning Manager 中的学习者主页。

>[!NOTE]
>
>您只能创建单个配置。 如果您尝试添加其他配置，系统将显示错误消息。 配置可将 Salesforce 帐户映射到学习者帐户。

### 添加远程站点设置

1. 在页面右上角，单击 **[!UICONTROL 设置]**.
1. 向内 **快速查找**，搜索远程站点设置。
1. 点击 **[!UICONTROL 新建远程站点]**.
1. 输入详细信息：

   1. **远程站点名称**：输入您选择的名称。
   1. **远程站点 URL**：托管 Adobe Learning Manager 的站点的 URL。

1. 启动 Adobe Learning Manager。

### 启用 Adobe Learning Manager 应用程序的通知

1. 在右上角，单击 **设置**.
1. 搜索自定义通知。
1. 点击 **[!UICONTROL 新]**.
1. 输入以下详细信息：

   1. **自定义通知名称：** LearningManagerNotification
   1. **API名称：** LearningManagerNotification

1. 选择两者 **桌面** 和 **移动版** 作为支持的渠道。

1. 单击&#x200B;**[!UICONTROL “保存”]**。
1. 要为移动设备启用推送通知，请按以下步骤操作：

   1. 在手机中安装 Salesforce 移动应用。
   1. 使用凭据登录应用。
   1. 转到“ ” **设置** > **通知传递设置**.
   1. 添加适用于 iOS 和 Android 版本的 Salesforce。

### 从 Salesforce 中卸载 Adobe Learning Manager

1. 在Salesforce应用中，转到已安装的包。
1. 点击 **[!UICONTROL 卸载]**.

## 为 Salesforce 用户配置 Adobe Learning Manager

Adobe Learning Manager 应用程序也适用于任何使用 Salesforce 帐户的用户。Salesforce 管理员可以根据配置文件添加用户。 Salesforce 配置文件与 Adobe Learning Manager 中的配置文件类似。例如，管理员、集成管理员、讲师等。 Salesforce 管理员还可以创建自定义配置文件。

### 配置文件

作为 Salesforce 管理员，您可以将配置文件分配给用户或创建自定义配置文件。

>[!NOTE]
>
>用户必须同时存在于Salesforce和Learning Manager中。

![](assets/create-profile.png)

*为学习者分配配置文件*

添加学习者时，必须为该学习者分配特定配置文件。 然后前往该配置文件，授予所需的访问权限。

若要让学习者查看Learning Manager应用程序，您必须为所有学习者启用该应用程序。

然后提供访问 Adobe Learning Manager 应用程序的权限。

![](assets/permission-set.png)

*添加访问Learning Manager应用程序的权限*

当您安装程序包时，系统将创建新的权限集， **AdobeLearning Manager用户**. 前往该权限集，然后添加用户。

选择用户并为其分配相应权限。 学习者现在可以访问 Adobe Learning Manager 应用程序。

首先，选择一个配置文件（例如，用户的“标准配置文件”），然后单击该配置文件。 点击 **[!UICONTROL 编辑]** 在 **自定义应用程序设置** 部分，启用该复选框 **AdobeLearning Manager**. 启用后用户便可访问该应用。

在&#x200B;**“自定义选项卡设置”**&#x200B;部分的&#x200B;**“学习者主页”**&#x200B;下拉列表中，选择&#x200B;**[!UICONTROL “默认启用”]**&#x200B;选项。

您必须让应用对所有配置文件可见。

点击 **[!UICONTROL 保存]** 并且属于所有配置文件的学习者可以访问Learning Manager应用程序。
