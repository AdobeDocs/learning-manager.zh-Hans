---
description: 了解如何在 Adobe Learning Manager 中集成各种连接器
jcr-language: en_us
title: Adobe Learning Manager 连接器
contentowner: jayakarr
exl-id: 1f44934b-6a2b-484d-bc7f-d0f23e3008ca
source-git-commit: 4b6426f836b345421401103db0f14c353323c3fc
workflow-type: tm+mt
source-wordcount: '15848'
ht-degree: 59%

---

# Adobe Learning Manager 连接器

企业有其他应用程序和系统必须与 Adobe Learning Manager 集成。连接器是一种实用程序，可帮助执行基于数据的集成，例如从外部系统将数据导入Learning Manager。  也能够将数据从Learning Manager导出到外部系统。

Adobe Learning Manager 提供 Salesforce 和 FTP 连接器。 借助 Salesforce 连接器，公司的集成管理员可以将其 Salesforce 应用程序与 Adobe Learning Manager 集成。作为集成管理员，您还可以使用 FTP 连接器将一组用户自动导入到企业应用程序。

Adobe Learning Manager 还提供 Lynda、getAbstract 和 Havard 管理系统连接器。这些连接器使学习者能够访问并使用 Lynda.com、getAbstract 和 Harvard ManageMentor 的课程。

继续阅读，了解如何在 Adobe Learning Manager 中配置和使用以上连接器。

<!--
>[!NOTE]
>
>**Update:** December 2020 update of Learning Manager
>
>For **FTP**, **Box**, and **Custom FTP** connectors, while exporting Learner Transcript or xAPI, you can also export the data as a **zip** file, for:
>
>* Learner Transcripts
>* xAPI
-->

>[!NOTE]
>
>在2022年11月版Adobe Learning Manager中，Zoom已于2023年6月前弃用[JWT身份验证](https://marketplace.zoom.us/docs/guides/auth/jwt/)。 因此，带 JWT 的 Zoom 连接器将继续运行至 6 月，但我们建议用户创建服务器到服务器 OAuth 应用程序，以替换帐户中的功能。默认情况下，所有新连接都将拥有 Zoom OAuth 身份验证。

## Salesforce 连接器 {#sfconnector}

Salesforce 连接器可连接 Adobe Learning Manager 和 Salesforce 帐户以自动同步数据。Salesforce连接器的功能包括：

### 映射属性 {#map-attributes}

集成管理员可以选择 Salesforce 列并将其映射到相应的 Adobe Learning Manager 组属性。映射完成后，相同映射就能用在随后的用户导入中。如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

### 自动导入用户 {#automated-user-import}

用户导入操作能让 Adobe Learning Manager 管理员从 Salesforce 提取员工详细信息，并自动将其导入 Adobe Learning Manager。这一自动化流程让您无需在创建并将 CSV 上传到 Adobe Learning Manager 的过程中手动完成操作。

### 自动计划 {#auto-schedule}

结合使用自动计划功能以及自动用户导入功能可提高工作效率。Adobe Learning Manager 管理员可根据公司的需求制定计划。Learning Manager应用程序中的用户可以根据计划获得最新消息。 可以在 Adobe Learning Manager 应用程序中每天执行同步。

### 过滤用户 {#filtering-user}

Adobe Learning Manager 管理员可在导入用户前先对其使用过滤器。例如，Adobe Learning Manager 管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

### 配置 Salesforce 连接器 {#configuresalesforceconnector}

如要将Salesforce与Learning Manager集成，请学习相应操作过程

#### 先决条件 {#prerequisites}

确保您拥有 Salesforce 公司的 URL。例如，如果您的公司名称是&#x200B;**myorg**，则Salesforce URL可以是`https://myorg.salesforce.com`。 在将 Salesforce 帐户与 Adobe Learning Manager 连接时，这是唯一需要输入的内容。

此外，请确保您拥有相应的凭据以登录到帐户。

#### 创建连接 {#createaconnection}

1. 在 Adobe Learning Manager 主页，将鼠标悬停在 Salesforce 卡/缩略图上方。此时会显示菜单。单击菜单中的&#x200B;**[!UICONTROL “连接”]**&#x200B;条目。

   ![](assets/mouserover-salesforce.png)

   *连接选项*

1. 此时会显示一个对话框，提示您输入公司 URL。在提供URL后单击&#x200B;**[!UICONTROL 连接]**。
1. 连接成功后，将显示“概述”页面。

### 映射属性 {#mapattributes}

成功建立连接后，您可以将Salesforce列映射到Learning Manager的相应属性。 此步骤为必须操作。

1. 在映射页面中，您可以在左侧看见Learning Manager的列，在右侧看见Salesforce的列。 选择映射到Learning Manager列名称的相应列名称。

   ![](assets/sfdc-map-columns.png)
   *映射属性*

   >[!NOTE]
   >
   >左侧显示的Learning Manager列数据是从活动字段中获取的。 **管理器**&#x200B;字段必须映射到电子邮件地址类型的字段。 在能够使用连接器之前，必须映射所有列。

1. 完成映射后单击“**[!UICONTROL 保存]**”。
1. 连接器现在可以使用了。帐户已配置并在管理员应用程序中显示为数据源。管理员可以安排导入或用于按需同步。

## 使用 Salesforce 连接器 {#usingsalesforceconnector}

Salesforce 连接器连接至 Salesforce.com 来获取已配置用户，并将其添加到 Adobe Learning Manager。

### 从 Salesforce 联系人导入用户 {#import-salesforce-contacts}

Adobe Learning Manager 增强了 Salesforce 连接器，可获取联系人和 Salesforce 用户，并自动将他们导入 Adobe Learning Manager。

在Salesforce连接器页面上，输入Salesforce URL并完成身份验证。 通过身份验证后，您可以继续导入用户或联系人。 如果选择“联系人”选项，请指定要导入的联系人子集。

选择Salesforce列并将其映射到相应的Learning Manager组属性。 映射完成后，相同映射就能用在随后的用户导入中。

1. 登录到Salesforce。
1. 在连接页面上，单击&#x200B;**[!UICONTROL 导入内部用户]**。

   ![](assets/image048.png)
   *导入内部用户*

1. 在&#x200B;**导入用户**&#x200B;页面上，有一个新选项“联系人”。 单击单选按钮&#x200B;**联系人**，您将看到以下选项。

   ![](assets/image050.png)
   *映射联系人属性*

1. 如果单击“**[!UICONTROL 是]**”，则可以执行以下操作：

   * **选择“联系人”列：**&#x200B;选择要导入Learning Manager的字段。
   * **指定值：**&#x200B;选择表示所选字段的值。

   ![](assets/image053.png)
   *指定值*

   * 将Salesforce列与Learning Manager列进行映射。
   * 若要开始导入，请单击&#x200B;**[!UICONTROL 保存]**。

1. 如果您单击“**[!UICONTROL 否”。 导入所有联系人]**，您可以直接映射字段，无需筛选联系人。 此时，您将从Salesforce导入所有联系人。
1. 若要开始导入，请单击&#x200B;**[!UICONTROL 保存]**。

## 导出学习记录 {#export-learning-records}

Learning Manager支持将学习记录（如成绩单、用户报告、技能报告）导出到Salesforce。 您可以确定是否应将导出的数据与Salesforce中的“用户”表或“联系人”表进行关联。

![](assets/export-events-new.png)
*导出学习记录*

### Salesforce 中的自定义对象 {#custom-objects-in-salesforce}

在从Learning Manager中导出学习记录之前，您必须在Salesforce中创建自定义对象。 自定义对象是您为存储特定于您的公司或行业的信息而创建的对象。 详情请参阅 [Salesforce 自定义对象](https://trailhead.salesforce.com/en/content/learn/modules/data_modeling/objects_intro)。

如何创建对象：

1. 下载并安装程序包以创建自定义对象。

   * [程序包 1](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WPJ)
   * [程序包 2](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WPT)
   * [程序包 3](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WPi)

1. 在 Salesforce 中为自定义对象重命名。
1. 选择活动，然后单击&#x200B;**[!UICONTROL 保存]**。

>[!NOTE]
>
>请确保系统管理员已获得对软件包安装后添加的所有活动字段的访问权限。

**将活动与下列对象链接：**&#x200B;选择要导出的部分（“用户”或“联系人”）。 如果您选择“联系人”对象，则Learning Manager中存在、但不在Salesforce中的用户将在Salesforce中创建。

![](assets/link-events.png)
*链接事件选项*

>[!NOTE]
>
>您可以在一个帐户中创建多个连接。 在 Salesforce 中，单个连接最多可提供三个自定义对象。 如要为同一 Salesforce 帐户创建多个连接，则必须安装三个程序包。 我们最多提供三个程序包支持。
>
>要创建的连接数量必须与所安装的程序包数量一致。

>[!NOTE]
>
>在 Salesforce 的“执行状态”页面上，只能通过 Salesforce 检查已处理的记录数。 Learning Manager会将状态显示为“已完成”，即使对所有已处理的记录的导出操作为部分导出或失败也是如此。

## 安装 Salesforce 程序包 {#install-salesforce-package}

Learning Manager提供Salesforce应用程序包。 在 SFDC 中安装和配置程序包后，销售员工便可以在 SFDC 门户中开展培训活动。 SFDC 用户可利用此应用直接在 SFDC 门户中探索新培训、查看推荐内容及参加培训。 用户还可以直接在SFDC门户的应用中以刊头的形式收到管理员发送的公告。

### 在 Adobe Learning Manager 应用程序中设置 {#setup-in-learning-manager-app}

1. 以集成管理员身份登录 Adobe Learning Manager 管理员帐户。
1. 单击&#x200B;**[!UICONTROL 应用程序]** > **[!UICONTROL 特色应用程序]**。
1. 单击&#x200B;**[!UICONTROL Salesforce]**。
1. 在Salesforce应用程序页面上，请注意描述中提到的应用程序ID（也称为客户端ID）和客户端密钥。
1. 单击&#x200B;**[!UICONTROL 批准]**，您的应用必须成功获得批准。
1. 单击&#x200B;**[!UICONTROL 开发人员资源]** > **[!UICONTROL 用于测试和开发的访问令牌]**。
1. 在“获取OAuth代码”部分中，“客户端ID”和作用域必须设置为“admin：read，admin：write”。 单击&#x200B;**[!UICONTROL 提交]**。
1. 在“获取刷新令牌”中，输入“客户端 ID”和客户端密钥。 单击&#x200B;**[!UICONTROL 提交]**&#x200B;并记下刷新令牌。

### 在 Salesforce 应用中创建帐户 {#create-account-in-salesforce-app}

1. 在 Salesforce 注册页面创建帐户。 您必须在开发人员版或企业版中创建Salesforce帐户。  [开发人员注册URL](https://developer.salesforce.com/signup)。 确保必须使用在Learning Manager中使用的电子邮件ID注册Salesforce。
1. 通过验证电子邮件验证您的帐户。
1. 创建密码并登录 Salesforce。
1. 登录后记下Salesforce URL(例如site.lightning.force.com)

### 安装 Adobe Learning Manager 包 {#install-learning-manager-package}

要安装程序包，必须首先删除 Salesforce 中现有的程序包。 卸载前必须启用以下设置。 必须应用这些设置，否则无法安装程序包。

>[!NOTE]
>
>仅在Salesforce Lightning视图中支持Adobe Learning Manager应用程序。

1. 启动[Learning Manager包URL](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WOQ)。
1. 在&#x200B;**登录**&#x200B;页面中，单击&#x200B;**[!UICONTROL 使用自定义域]**。
1. 输入程序包URL，然后单击“**[!UICONTROL 继续]**”。 必须在安装页面选中“仅限管理员安装”选项。 请勿更改此选项。
1. 单击&#x200B;**[!UICONTROL 安装]**。 安装程序包后，单击&#x200B;**[!UICONTROL 完成]**。 系统将转至“已安装程序包”页面，您可以看到 Adobe Learning Manager 中已安装的程序包。
1. 转到 App Launcher（位于“设置”旁），然后搜索 Adobe Learning Manager。
1. 要配置应用，请单击&#x200B;**[!UICONTROL 配置]**。
1. 单击“**[!UICONTROL 新建]**”并添加以下详细信息：

   * **配置**：输入您选择的名称。
   * **ClientID**：输入从第一部分获取的值。
   * **ClientSecret：**&#x200B;输入从第一部分获取的值。
   * **RefreshToken：**&#x200B;输入从第一部分获取的值。
   * **LearningManagerBaseURL：** Learning Manager托管站点的URL。

### 添加远程站点设置 {#add-remote-site-settings}

1. 在页面右上角，单击&#x200B;**[!UICONTROL 设置]**。
1. 在&#x200B;**[!UICONTROL 快速查找]**&#x200B;中，搜索远程站点设置。
1. 单击&#x200B;**[!UICONTROL 新建远程站点]**。
1. 输入详细信息：

   * **远程站点名称**：输入您选择的名称。
   * **远程站点 URL**：托管 Adobe Learning Manager 的站点的 URL。

1. 启动 Adobe Learning Manager。

### 启用Learning Manager应用程序通知 {#enable-notifications-for-learning-manager-app}

1. 在右上角，单击&#x200B;**[!UICONTROL 设置]**。
1. 搜索自定义通知。
1. 单击&#x200B;**[!UICONTROL 新建]**。
1. 输入以下详细信息：

   1. **自定义通知名称：** LearningManagerNotification
   1. **API名称：** LearningManagerNotification

1. 选择&#x200B;**桌面**&#x200B;和&#x200B;**移动设备**&#x200B;作为支持的渠道。

1. 单击&#x200B;**[!UICONTROL “保存”]**。
1. 要为移动设备启用推送通知，请按以下步骤操作：

   1. 在手机中安装 Salesforce 移动应用。
   1. 使用凭据登录应用。
   1. 转到&#x200B;**设置** > **通知传递设置**。
   1. 添加适用于 iOS 和 Android 版本的 Salesforce。

### 从 Salesforce 中卸载 Adobe Learning Manager

1. 在Salesforce应用中，转到已安装的包。
1. 单击&#x200B;**[!UICONTROL 卸载]**。

## 为 Salesforce 用户配置 Adobe Learning Manager {#configure-learning-manager-for-salesforce-users}

Adobe Learning Manager 应用程序也适用于任何使用 Salesforce 帐户的用户。Salesforce 管理员可以根据配置文件添加用户。 Salesforce 配置文件与 Adobe Learning Manager 中的配置文件类似。例如，管理员、集成管理员、讲师等。 Salesforce 管理员还可以创建自定义配置文件。

作为 Salesforce 管理员，您可以将配置文件分配给用户或创建自定义配置文件。

![](assets/create-profile.png)

安装 Salesforce 程序包时，您可以将 Salesforce 配置文件分配给学习者。

安装 Salesforce 程序包后，您必须配置 Salesforce 配置文件。

单击“**[!UICONTROL 配置]**”>“**[!UICONTROL 新建]**”，然后添加以下内容：

* 配置名称
* 客户端 ID
* 客户端密码
* LearningManagerBaseURL
* 禁用重定向

>[!NOTE]
>
>若要让学习者查看Learning Manager应用程序，您必须为所有学习者启用该应用程序。

然后提供访问 Adobe Learning Manager 应用程序的权限。

![](assets/permission-set.png)

*设置访问Learning Manager应用程序的权限*

选择用户并为其分配相应权限。 学习者现在可以访问 Adobe Learning Manager 应用程序。

首先，选择一个配置文件（例如，用户的“标准配置文件”），然后单击该配置文件。 单击&#x200B;**[!UICONTROL “编辑”]**，在&#x200B;**“自定义应用程序设置”**&#x200B;部分中，启用&#x200B;**“Adobe Learning Manager”**&#x200B;复选框。 启用后用户便可访问该应用。

在&#x200B;**“自定义选项卡设置”**&#x200B;部分的&#x200B;**“学习者主页”**&#x200B;下拉列表中，选择&#x200B;**“默认启用”**&#x200B;选项。

您必须让应用对所有配置文件可见。

单击&#x200B;**[!UICONTROL “保存”]**，则属于所有配置文件中的学习者将可以访问Learning Manager应用程序。

### 学习路径相关更改 {#learning-path-changes}

#### 现有连接 {#existing-connections}

如果在管理员帐户中禁用了“学习路径”选项，则不会在报告中添加行和列。

如果在管理员帐户中启用了“学习路径”选项，则“类型”列将用“学习路径”进行填充，以防学习者注册。

>[!NOTE]
>
>如果启用了该标志，并且使用了现有连接，则部分记录可能会丢失。

#### 新连接 {#new-connections}

如果在管理员帐户中禁用了“学习路径”选项，则培训报告将包含以下列，但不会包含任何数据。

* **嵌入式路径**：显示学习计划的名称
* **嵌入式路径 ID**：显示学习计划的 ID。
* **嵌入式课程ID：**&#x200B;显示学习路径内的课程ID。

此外，对于帐户中启用了学习路径的新连接，将显示三个新列，并且所有数据都将流动。

此外，该报告将包含类型“学习路径（较高级别）”列，适用于注册学习路径的所有学习者。

在“类型”列中，“学习计划”将更名为“学习路径”。 现有连接将不会发生更改。

## Adobe Learning Manager FTP 连接器 {#ftpconnector}

借助 FTP 连接器，您可以将 Adobe Learning Manager 与任意外部系统集成以自动同步数据。需要外部系统能够以 CSV 格式导出数据，并将其放置在 Adobe Learning Manager FTP 帐户内相应文件夹下。FTP连接器的功能包括：

您还可以使用Box连接器进行数据迁移、用户导入和数据导出。 有关更多信息，请参阅Box连接器。

### 数据导入 {#data-import}

用户导入操作能让Learning Manager管理员从Learning Manager FTP服务获取员工详细信息，并自动将其导入Learning Manager。 使用此功能，您可以将这些系统生成的 CSV 放在 FTP 帐户下的相应文件夹中来集成多个系统。Learning Manager会拾取CSV文件，将其合并，并根据计划导入数据。 有关更多信息，请参阅计划功能。

**映射属性**

集成管理员可以选择CSV列并将其映射到Learning Manager的组属性。 映射需要花费一些时间。 映射完成后，相同映射就能用在随后的用户导入中。如果管理员想要针对导入用户使用不同的映射，则可以对映射进行重新配置。


#### 导出数据 {#export-data}

数据导出允许用户将用户技能和学习者成绩单导出到 FTP 位置，从而与任何第三方系统集成。

#### 计划 {#scheduling}

管理员可以根据公司要求设置计划任务，Learning Manager应用程序中的用户可以根据计划获得最新消息。 同样，集成管理员可以及时安排技能导出，以便与外部系统集成。 每天可以在Learning Manager应用程序中执行同步。

### 配置 Adobe Learning Manager FTP 连接器 {#configure-captivate-prime-ftp-connector}

如要将FTP连接器与Learning Manager集成，请学习相应操作过程。

#### 创建连接 {#Create-a-connection-1}

1. 在Learning Manager主页，将鼠标悬停在FTP卡/缩略图上方。 此时会显示菜单。选择菜单中的“连接”条目。

   ![](assets/mouseover-ftpconnector.png)

   *连接选项*

要使用FTP客户端连接到任何FTP服务器，您需要以下信息：

* **FTP域**：这是您要连接到的FTP服务器的地址。 例如，ftp.example.com
* **端口**：默认FTP端口为21，但出于安全原因，某些服务器可能使用不同的端口。 对于Adobe Learning Manager — 端口22
* **FTP用户名**：访问FTP服务器所需的用户名。
* **FTP密码**：与用户名关联的密码。

**FileZilla(Windows、macOS和Linux)**

**步骤1：下载并安装FileZilla**

如果您尚未安装FileZilla，请从以下官方网站下载它： [下载](https://filezilla-project.org/)并在您的计算机上安装它。

**步骤2：打开FileZilla**

安装后，在计算机上启动FileZilla。

**步骤3：收集FTP服务器信息**

**步骤4：在FileZilla**&#x200B;中输入FTP服务器信息

在顶部菜单中，选择&#x200B;**[!UICONTROL 文件]**，然后选择&#x200B;**[!UICONTROL 站点管理器]**（或使用快捷键Ctrl+S）。

**步骤5：添加新的FTP站点**

在“站点管理器”中，选择“**新建站点**”并键入名称（例如，“我的FTP服务器”）。

**步骤6：输入FTP详细信息**

键入以下信息：

* **主机**：键入FTP服务器的地址。
* **端口**：如果服务器使用的端口超过21，请输入正确的端口号。
* **协议**：选择&#x200B;**[!UICONTROL SFTP - SSH文件传输协议]**。
* **登录类型**：选择&#x200B;**[!UICONTROL 正常]**。
* **用户**：键入FTP用户名。
* **密码**：键入FTP密码。

**步骤7：连接到FTP服务器**

在站点管理器中选择&#x200B;**[!UICONTROL 连接]**&#x200B;按钮。 如果所有信息都正确，FileZilla将连接到FTP服务器。

**第8步：导航和传输文件**

连接后，您将在右侧看到远程文件，在左侧看到您的本地文件。 您可以在面板之间拖放目录来导航和传输文件。

>[!CAUTION]
>
>传输文件时，请避免更改服务器上的重要文件。

<!--1. A dialog appears prompting you to enter the email id. Provide the email id of the person responsible for managing the Learning Manager FTP account for the organization. Click **[!UICONTROL Connect]** after providing the email id. 
1. Learning Manager sends you an email prompting the user to reset the password before accessing the FTP for the first time. The user must reset the password and use it for accessing the Learning Manager FTP account.

   >[!NOTE]
   >
   >Only one Learning Manager FTP account can be created for a given Learning Manager account.

   In the overview page, you can specify the Connection Name for your integration. Choose what action you want to take  from  the following options:

   * Import Internal Users  
   * Import xAPI
   * Export User Skills - Configure a Schedule  
   * Export User Skills - OnDemand  
   * Export Learner Transcripts - Configure a Schedule
   * Export Learner Transcripts - OnDemand

   ![](assets/ftp-connector-dashboard.png)
   *Export options*-->

### 导入 {#import}

+++内部用户

通过“导入内部用户”选项，您可以按需或计划将用户从CSV中导入Learning Manager。

+++

+++映射属性

成功建立连接后，您便可以映射 CSV 文件中的各列。它被放置在 FTP 文件夹中，以对应 Adobe Learning Manager 的相应属性。此步骤为必须操作。

1. 在“映射属性”页面中，您可以在左侧看见Learning Manager的预期各列，在右侧看见CSV各列名称。 首先，您会在右侧看见一个空的选择框。单击&#x200B;**选择文件**，导入任何模板CSV。
1. 上述步骤会在右侧的选择下拉列表中填写所有 CSV 列名称。选择映射到Learning Manager列名称的相应列名称。

   >[!NOTE]
   >
   >经理字段必须映射到电子邮件地址类型的字段。在能够使用连接器之前，必须映射所有列。

1. 完成映射后选择&#x200B;**[!UICONTROL 保存]**。

   连接器现在可以使用了。已配置的帐户在管理员应用程序中显示为数据源，以便管理员安排导入或用于按需同步。

+++

+++使用Learning Manager FTP连接器

1. 必须将来自外部系统的CSV文件放在以下路径中：

   `code $OPERATION$/$OBJECT_TYPE$/$SUB_OBJECT_TYPE$/data.csv`

   >[!NOTE]
   >
   >在2016年7月版中，仅允许导入用户。 因此，如要使用FTP连接器，请确保已将CSV文件放入以下文件夹：

   `code Home/import/user/internal/*.csv`

1. FTP连接器从CSV文件中获取所有行。 重要的是，某 CSV 文件中某位用户对应的行不会出现在任何其他 CSV 中。
1. 所有CSV都必须包含映射中指定的列。
1. 在流程开始之前，文件夹中必须存在所有必需的CSV。

>[!NOTE]
>
>在将用户导入到 Adobe Learning Manager 时，管理员还必须了解如何在 Adobe Learning Manager 中管理用户。请参阅[用户管理帮助](migration-manual.md#usermanagement)以了解更多信息。

+++

+++导入xAPI

导入 xAPI 选项允许您根据需要安排将第三方服务的 xAPI 语句导入 Adobe Learning Manager。

+++

+++导入xAPI所需的配置

1. 在配置页面中，选择配置列表中可用的现有配置，以从CSV导入xAPI语句。 单击编辑或&#x200B;**添加新配置**&#x200B;链接以导航到“配置导入源”页面。

   **配置**

   * 在“配置导入源”页面中，填写两个字段，即“名称”和“源文件名”。源文件名应与 FTP 文件夹位置中提供的文件名匹配。
   * 单击&#x200B;**[!UICONTROL “保存”]**&#x200B;以保存更改。

   ![](assets/configurations.png)
   *配置*

   **过滤器**

   * 在左侧窗格中，单击&#x200B;**[!UICONTROL 过滤器]**。
   * 在“配置导入 - 过滤器”页面中，填写“名称”和“条件”字段以滤除记录。单击&#x200B;**[!UICONTROL “添加新过滤器”]**&#x200B;以添加其他过滤器。您可以单击“操作”列下的&#x200B;**“保存”**&#x200B;或&#x200B;**“删除”**&#x200B;选项来保存或删除过滤器。

   ![](assets/filter.png)
   *过滤器*

   **映射**

   * 在左侧窗格中，单击&#x200B;**[!UICONTROL “映射”]**。
   * 在“导入 xAPI 语句 - 配置 - 映射”页面的左侧，您可以看到需要与 CSV 列名称映射的 xAPI JSON 字段路径名。
   * 默认情况下，需要与 CSV 列名称映射的三个 JSON 路径字段名分别为 **actor.mbox**、**verb.id** 和 **object.id**。您可以单击&#x200B;**添加新映射**&#x200B;来添加要映射的其他字段。

   * 选择要与 Json 字段路径名映射的列名称类型（字符串、数字、布尔值或日期类型）。
   * 完成映射后单击“保存”。xAPI 现在可以按计划或按需导入。

   ![](assets/mapping.png)
   *映射*

1. 在左侧窗格中，单击&#x200B;**[!UICONTROL 配置计划]**。单击&#x200B;**[!UICONTROL 启用计划]**，以计划导入 xAPI 语句。

   您可以输入开始时间和日期，然后以天为单位输入 xAPI 导入计划的频率。例如，每 3 天启用一次 xAPI 导入。

   ![](assets/configure-schedule2x.png)
   *导入xAPI语句 — 配置计划*

1. 在左侧窗格中，单击&#x200B;**[!UICONTROL 按需执行]**。

   ![](assets/on-demand.png)
   *导入xAPI语句 — 按需*

1. 在左侧窗格中，单击&#x200B;**[!UICONTROL 执行状态]**，按时间顺序查看此连接器所有运行的摘要。您可以查看导入 xAPI 时的开始日期和持续时间，导入类型（按需或按计划）以及导入状态（xAPI 导入进行中、已完成或失败）。

   ![](assets/execution-status2x.png)
   *导入xAPI语句 — 执行状态*

+++

<!--### Export

+++Skills

There are two options to export User skill reports.

**[!UICONTROL User Skills - On Demand]**: You can specify the  start date and export the report using the option. The report is extracted from the date entered until present.

![](assets/export-on-demand2x.png)
*On demand export option*

**[!UICONTROL User Skills - Configure]**: This option let's you schedule the extraction of the report. Select the Enable Schedule check box and specify the start date and time. You can also specify the interval at which you want the report to be generated and sent.

![](assets/user-skills-configure.png)
*Configure export of report*

+++

To open the Export folder where the exported files are placed, open the link to FTP Folder provided in the User Skills page as shown below.

![](assets/ftp-folder.png)
*FTP folder to view files*

The auto-exported files are present in the location **Home/export/&#42;FTP_location&#42;**

The auto-exported files are available with the title, **skill_achievements_&#42;date from&#42;_to_&#42;date to&#42;.csv**

![](assets/exported-csvs.png)
*Exported .csv file*

+++Learner Transcript

![](assets/on-demand-report.png)

**Configure**: This option  let's  you schedule the extraction of the report. Select the Enable Schedule check box and specify the start date and time. You can also specify the interval at which you want the report to be generated and sent.

![](assets/configure-report.png)

+++

To open the Export folder where the exported files are placed in your FTP location, open the link to FTP Folder provided on the Learner Transcript page as shown below

The auto-exported files are present in the location **Home/export/&#42;FTP_location&#42;**

The auto-exported files are available with the title, **learner_transcript_&#42;date from&#42;_to_&#42;date to&#42;.csv**-->

### 支持手动 csv 字段 {#support-for-manual-csv-fields}

通过 FTP 导入用户数据时，管理员必须将系统中呈现的所有活动字段都映射到 csv 中的相应字段。

对于所有 csv 活动字段，这是必须的。 对于手动活动字段，集成管理员可以选择 **DontImportFromSource** 选项。

通过选择此选项，手动活动字段值不会使用 csv 导入来填充。 学习者提供的值保持不变。

>[!NOTE]
>
>在映射时，如果为csv活动字段选择了&#x200B;**DontImportFromSource**&#x200B;选项，则将从系统中删除此字段。

![](assets/ftp-conector-foractivefields.png)
*活动字段的FTP连接器*

## Lynda 连接器 {#lynda-connector}

Lynda 连接器：Lynda.com 的企业用户可使用此连接器供其学习者在 Adobe Learning Manager 内找到并学习 Lynda 课程。此连接器可以配置为使用您的 API 密钥定期从 Lynda.com 上提取课程。在 Adobe Learning Manager 中创建课程后，用户就能搜索和使用这些课程。随后就可以在 Adobe Learning Manager 中跟踪学习者的学习进度。

### 配置 Lynda 连接器 {#configure-the-lynda-connector}

1. 在集成管理员信息板中，单击 Lynda。

   您会看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置 Lynda 连接器，请单击“连接”。

   <!--Configure the Exavault FTP account before you configure this connector.-->

1. 在连接页面，为您的连接器指定名称。输入 Appkey 和您的连接的密钥。

   >[!NOTE]
   >
   >联系您的供应商，获取 Appkey 和密钥。

1. 单击“保存”。

   配置即会保存，并为您的帐户添加 Lynda 连接。现在，您可以从主页单击“管理连接” ，并随时编辑您的配置。

1. 如果已建立连接，请单击“管理连接”查看所有连接。

   >[!NOTE]
   >
   >在您配置此连接器之前，必须为您的帐户启用迁移功能。

1. 单击要编辑的连接。
1. 在左侧窗格中，单击&#x200B;**[!UICONTROL 配置]**。 执行以下任一操作：

   * 查看或编辑您帐户的详细信息，以及这个窗格中的同步计划。如果您要启用此帐户，请选择“启用连接”复选框。
   * 单击“编辑”并编辑您的凭据。如要撤消对此字段的更新，请单击“重置”
   * 单击“启用计划”以同步您的计划。您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。例如，启用每三天同步一次。

   单击&#x200B;**[!UICONTROL “保存”]**&#x200B;以保存更改。

   ![](assets/lynda.png)

   *为Learning Manager配置Lynda连接器*

1. 从左窗格中，单击“按需执行”。您可使用此选项从 Lynda 导入用户订阅源和其他相关数据。输入按需执行的“开始日期”，然后单击“执行”以执行同步。将导入从开始日期到现在的所有数据。

   * 如果同步过程中应用停机，则您可以单击“禁用同步过程中对 Adobe Learning Manager 的访问”。
   * 如果您点击了“启用同步过程中对 Adobe Learning Manager 的访问”，则同步期间服务不会中断。

   ![](assets/lynda-ondemand.png)

   *对Lynda连接器执行按需执行*

1. 您还可以随时从左侧窗格单击“执行状态”，按时间顺序查看此连接器所有运行的摘要。您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   >[!NOTE]
   >
   >删除并重新创建连接时，连接器的先前运行将再次出现。在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

   ![](assets/lynda-ondemand.png)

   *查看所有运行的摘要，单击“执行状态”*

## getAbstract 连接器 {#getabstractconnector}

getAbstract.com 的企业用户可使用 getAbstract 连接器供其学习者找到并使用 getAbstract 总结。连接器可以配置为定期提取使用情况数据，前提条件是要在 Adobe Learning Manager 中创建学习者完成情况记录。继续阅读，了解如何在 Adobe Learning Manager 中配置此连接器。

### 配置 getAbstract 连接器 {#configure-the-get-abstract-connector}

1. 在集成管理员信息板中，单击 getAbstract。

   您会看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置 getAbstract 连接器，请单击“连接”。

   <!--Configure the Exavault FTP account before you configure this connector.

   Ensure that you share this FTP credentials with your content provider to access the feeds.-->

1. 在“连接名称”字段中输入连接的名称。

   在“客户端 ID”和“客户端密钥”字段中输入相应的密钥。请与供应商联系以获取此连接器的相应密钥。

   需要密钥才能获取可在客户端使用的课程的课程元数据。

1. 如果已建立连接，请从主页单击 “getAbstract” > “管理连接”以查看和编辑您的现有配置。

   >[!NOTE]
   >
   >在您配置此连接器之前，必须为您的帐户启用迁移功能。

1. 单击要查看或编辑其配置的连接。

   ![](assets/getabstractschedulepage.png)

   *为Learning Manager配置getAbstract连接器*

1. 在左侧窗格中，单击“配置”。 执行以下任一操作：

   * 查看或编辑您帐户的详细信息，以及这个窗格中的同步计划。如果您要启用此帐户，请选择“启用连接”复选框。
   * 单击“编辑”并编辑您的凭据。如要撤消对此字段的更新，请单击“重置”
   * 单击“启用计划”以同步您的计划。您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。例如，启用每三天同步一次。

1. 单击&#x200B;**[!UICONTROL “保存”]**。

   配置即会保存，并为您的帐户添加 getAbstract 连接。

1. 从左窗格中，单击“按需执行”。您可使用此选项从 getAbstract 导入用户订阅源和其他相关数据。输入按需执行的“开始日期”，然后单击“执行”以执行同步。将导入从开始日期到现在的所有数据。

   * 如果同步过程中应用停机，则您可以单击“禁用同步过程中对 Adobe Learning Manager 的访问”。
   * 如果您点击了“启用同步过程中对 Adobe Learning Manager 的访问”，则同步期间服务不会中断。

1. 您还可以随时从左侧窗格单击“执行状态”，按时间顺序查看此连接器所有运行的摘要。您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   >[!NOTE]
   >
   >删除并重新创建连接时，连接器的先前运行将再次出现。在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

   要使任何类型的同步起作用，请确保 getAbstract FTP 文件夹中存在对应同步所指定日期的用户订阅源。

   请参阅以下 Excel 工作表，该工作表是 getAbstract 的用户订阅源文件的样本。文件名必须遵循以下格式&#x200B;**：report_export_年_月_日_时分秒.xlsx** 或&#x200B;**report_export_年_月_日.xlsx**。
   [getAbstract用户订阅源示例Excel表](assets/report-export-20170401175342.xlsx)

## Harvard ManageMentor 连接器 {#hmmconnector}

Harvard ManageMentor 的企业用户可以使用 Harvard ManageMentor 连接器供其学习者找到并学习 Harvard ManageMentor 课程。连接器能帮助在 Adobe Learning Manager 中创建课程，并可以配置为定期提取学习者学习进度数据。要配置此连接器，请执行以下步骤：

### 配置 Harvard ManagerMentor 连接器 {#configure-the-harvard-managermentor-connector}

1. 在集成管理员信息板中，单击 Harvard ManageMentor。

   您会看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置 Harvard ManageMentor 连接器，单击“连接”。

   <!--Configure the Exavault FTP account before you configure this connector.

   Ensure that you share this FTP credentials with your content provider to access the feeds.-->

1. 在“连接名称”字段中输入连接的名称。单击“连接”以保存此连接。
1. 如果已建立连接，请从主页单击 “Harvard ManageMentor” > “管理连接”。单击要为之编辑您现有配置的连接。

   >[!NOTE]
   >
   >在您配置此连接器之前，必须为您的帐户启用迁移功能。

   ![](assets/hmm.png)

   *为Learning Manager配置HarvardManage Mentor连接器*

1. 在左侧窗格中，单击“配置”。 执行以下任一操作：

   * 查看或编辑您帐户的详细信息，以及这个窗格中的同步计划。如果您要启用此帐户，请选择“启用连接”复选框。
   * 单击“启用计划”以同步您的计划。您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。例如，启用每三天同步一次。

1. 从左窗格中，单击“按需执行”。您可使用此选项从 Harvard ManageMentor 导入用户订阅源和其他相关数据。输入按需执行的“开始日期”，然后单击“执行”以执行同步。将为此连接导入从开始日期到现在的所有数据。

   * 如果同步过程中应用停机，则您可以单击“禁用同步过程中对 Adobe Learning Manager 的访问”。
   * 如果您点击了“启用同步过程中对 Adobe Learning Manager 的访问”，则同步期间服务不会中断。

   如果要每隔几天自动执行同步，请在“重复天数”字段中指定天数。同步可确保您的帐户使用 Harvard ManageMentor 的最新版摘要和总结进行更新。

1. 您还可以随时从左侧窗格单击“执行状态”，按时间顺序查看此连接器所有运行的摘要。您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   >[!NOTE]
   >
   >删除并重新创建连接时，连接器的先前运行将再次出现。在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

   要使同步成功，请确保 Harvard ManageMentor FTP 文件夹中至少存在以下文件中的一个：

   hmm12_metadata.csv：此文件提供Harvard ManageMentor连接器的课程元数据。 确保在上载文件时遵循命名约定。

   client_hmm12_20150125.csv：此文件是Harvard ManageMentor连接器的用户订阅源。 文件命名应遵循的约定是&#x200B;**client_hmm12_yyyyMMdd.csv.**

   请参阅以下两个用于此连接器的用户订阅源和课程订阅源文件样本：

   * [ Harvard ManageMentor连接器的课程元数据文件](assets/hmm12-metadata.csv)
   * [用于 Harvard ManageMentor 连接器的用户订阅源。](assets/client-hmm12-20170304.csv)

## Workday 连接器 {#workdayconnector}

借助 Workday 连接器，您可以将 Adobe Learning Manager 与 Workday 租户集成以自动同步数据。

### 导入 {#import-1}

#### 映射属性 {#map-attributes-1}

集成管理员可以选择Workday列并将其映射到相应的Learning Manager组属性。 映射完成后，相同映射就能用在随后的用户导入中。如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

#### 自动导入用户 {#automated-user-import-1}

用户导入操作能让 Adobe Learning Manager 管理员从 Workday 提取员工详细信息，并自动将其导入 Adobe Learning Manager。

#### 过滤用户 {#filtering-users}

Adobe Learning Manager 管理员可在导入用户前先对其过滤。例如，Adobe Learning Manager 管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

### 导出 {#export}

用户技能导出允许用户自动将用户技能导出到 Workday。

>[!NOTE]
>
>使用同一 Workday 帐户无法同时导出多个 Adobe Learning Manager 帐户中的技能。

#### 注意事项 {#points-to-note}

* 确保员工的UUID、电子邮件地址和姓名在多个Workday集成中是唯一的。 不正确的值将导致连接失败。
* 任何面向LMS管理员的客户端都不能删除通过Workday于填充的UUID字段。 如果要更改该值，请联系Adobe Learning Manager入门或支持团队。
* “用户清除”选项也可能不起作用，因为“用户清除”每次运行仅支持50个用户进行清除。 通过UUID上传用户时请格外谨慎。

### 计划 {#Scheduling-1}

管理员可以根据公司的要求计划相关任务，Adobe Learning Manager 应用程序中的用户可以根据计划获得最新消息。同样，集成管理员可以及时安排技能导出，以便与外部系统集成。可以在 Adobe Learning Manager 应用程序中每天执行同步。

### 配置 Workday 连接器 {#configure-workday-connector}

>[!PREREQUISITES]
>
>请求公司的Workday管理员创建具有ISU_Permissions文档中定义的权限的集成系统用户(ISU)。 从下面的链接下载的一个副本。

[下载集成系统用户(ISU)安全性的副本。](assets/isu-permissions-v1.pdf)如要将Workday连接器与Learning Manager集成，请学习相应操作过程。

1. 在Learning Manager主页中，将鼠标悬停在Workday磁贴上。 此时会显示菜单。单击菜单中的&#x200B;**[!UICONTROL “连接”]**&#x200B;条目。

   ![](assets/workday-tile.png)

   *Workday磁贴*

1. 此时会显示一个对话框，提示您输入新连接的凭据。在建立连接之前，请输入以下字段。

   * 连接名称：根据您的喜好提供一个连接名称。
   * 主机 URL：集成管理员可以从相应的 Workday 管理员获取主机 URL 详细信息。
   * 租户：租户是贵公司的内部人员。 您的 Workday 管理员为您提供租户详细信息。
   * 用户名和密码：Workday管理员创建具有所需安全权限的集成系统用户(ISU)，并将其共享给集成管理员。

>[!NOTE]
>
>   Learning Manager使用Workday API版本40.1。


![](assets/configure-connector.png)
*配置Workday连接器*

1. 在所有相关字段中输入信息后，单击“连接”。

   >[!NOTE]
   >
   >您也可以将多个 Workday 连接同步到您的 Adobe Learning Manager 帐户。

在“概述”页面中，您可以指定集成的连接名称。 选择您要采取的操作，您可从以下选项中选择：

* 导入内部用户
* 导出用户技能 - 配置计划
* 导出用户技能 - 按需

![](assets/overview.png)
*Workday概述*

### 导入 {#import-5}

#### 映射属性 {#map-attributes-4}

您可以使用 Workday 连接器来将 Adobe Learning Manager 与 Workday 集成以自动同步数据。您可以将当前所有用户从 Workday 导入到 Adobe Learning Manager。可以从各种数据源导入用户，包括 FTP 和 Salesforce。

在导入用户之前，必须对 Adobe Learning Manager 和 Workday 中的用户属性进行映射。在“概述”页面中，使用“导入”下的“内部用户”选项来映射属性。

在 Adobe Learning Manager 列下输入 Adobe Learning Manager 凭据。 使用下拉列表为 Workday 中各列选择正确的凭据。

>[!NOTE]
>
>目前，Adobe Learning Manager 支持从 Workday 导入 69 种用户属性。使用 Adobe Learning Manager 中的“活动字段”添加更多属性。

![](assets/workday.png)
*映射属性*

选中&#x200B;**排除临时工**&#x200B;复选框，以防止导入经理提供的临时工作人员。

Workday 有四个级别，而 Adobe Learning Manager 有两个级别。Workday中的四个级别是技能配置文件类别、技能配置文件、技能项目类别和技能项目。 您的技能名称以及Learning Manager的级别将一同映射到Workday的技能项目之下。

>[!NOTE]
>
>您可以添加其他 Workday 属性。 联系您的 CSAM 以添加属性。

+++支持的Workday属性列表

wd：User_ID
wd：Worker_ID
管理者
wd：Personal_Data.wd：Name_Data.wd：Preferred_Name_Data.wd：Name_Detail_Data。@wd：Formatted_Name
wd：Personal_Data.wd：Name_Data.wd：Legal_Name_Data.wd：Name_Detail_Data.@wd：Formatted_Name
wd：Personal_Data.wd：Name_Data.wd：Legal_Name_Data.wd：Name_Detail_Data.wd：Prefix_Data.wd：Title_Descriptor
wd：Personal_Data.wd：Name_Data.wd：Preferred_Name_Data.wd：Name_Detail_Data.wd：Prefix_Data.wd：Title_Descriptor
wd：Personal_Data.wd：Name_Data.wd：Preferred_Name_Data.wd：Name_Detail_Data.wd：First_Name
wd：Personal_Data.wd：Name_Data.wd：Preferred_Name_Data.wd：Name_Detail_Data.wd：Last_Name
wd：Personal_Data.wd：Name_Data.wd：Legal_Name_Data.wd：Name_Detail_Data.wd：First_Name
wd：Personal_Data.wd：Name_Data.wd：Legal_Name_Data.wd：Name_Detail_Data.wd：Last_Name
wd：Personal_Data.wd：Contact_Data.wd：Address_Data.0。@wd：Formatted_Address
wd：Personal_Data.wd：Contact_Data.wd：Address_Data.0.wd：Postal_Code
wd：Personal_Data.wd：Contact_Data.wd：Email_Address_Data.0.wd：Email_Address
wd：Personal_Data.wd：Contact_Data.wd：Address_Data.0.wd：Country_Region_Descriptor
wd：Personal_Data.wd：Contact_Data.wd：Phone_Data.0。@wd：Formatted_Phone
wd：Personal_Data.wd：Contact_Data.wd：Phone_Data.0.wd：Country_ISO_Code
wd：Personal_Data.wd：Contact_Data.wd：Phone_Data.0.wd：International_Phone_Code
wd：Personal_Data.wd：Contact_Data.wd：Phone_Data.0.wd：Phone_Number
wd：Personal_Data.wd：Primary_Nationality_Reference.wd：ID.1。$
wd：Personal_Data.wd：Gender_Reference.wd：ID.1。$
wd：Personal_Data.wd：Identification_Data.wd：National_ID.0.wd：National_ID_Data.wd：ID
wd：Personal_Data.wd：Identification_Data.wd：Custom_ID.0.wd：Custom_ID_Data.wd：ID
wd：User_Account_Data.wd：Default_Display_Language_Reference.wd：ID.1。$
wd：Role_Data.wd：Organization_Role_Data.wd：Organization_Role.0.wd：Organization_Role_Reference.wd：ID.1。$
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Position_Title
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Title
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Site_Summary_Data.wd：Name
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Site_Summary_Data.wd：Address_Data.@wd：Formatted_Address
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Job_Classification_Summary_Data.0.wd：Job_Classification_Reference.wd：ID.1。$
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Job_Classification_Summary_Data.0.wd：Job_Group_Reference.wd：ID.1。$
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Work_Space__Reference.wd：ID.1。$
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Job_Profile_Summary_Data.wd：Job_Family_Reference.0.wd：ID.1。$
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Job_Profile_Summary_Data.wd：Job_Profile_Name
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Job_Profile_Summary_Data.wd：Job_Profile_Reference.wd：ID.1。$
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Site_Summary_Data.wd：Address_Data.0.wd：Country_Reference.wd：ID.2。$
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Worker_Type_Reference.wd：ID.1。$
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Site_Summary_Data.wd：Address_Data.0。@wd：Formatted_Address
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Job_Profile_Summary_Data.wd：Management_Level_Reference.wd：ID.1。$
wd：Employment_Data.wd：Worker_Status_Data.wd：Active
wd：Employment_Data.wd：Worker_Status_Data.wd：Active_Status_Date
wd：Employment_Data.wd：Worker_Status_Data.wd：Hire_Date
wd：Employment_Data.wd：Worker_Status_Data.wd：Original_Hire_Date
wd：Employment_Data.wd：Worker_Status_Data.wd：Retired
wd：Employment_Data.wd：Worker_Status_Data.wd：Retirement_Date
wd：Employment_Data.wd：Worker_Status_Data.wd：已终止
wd：Employment_Data.wd：Worker_Status_Data.wd：Termination_Date
wd：Employment_Data.wd：Worker_Status_Data.wd：Termination_Last_Day_of_Work
wd：Organization_Data.wd：Worker_Organization_Data.0.wd：Organization_Data.wd：Organization_Code
wd：Organization_Data.wd：Worker_Organization_Data.0.wd：Organization_Data.wd：Organization_Name
wd：Organization_Data.wd：Worker_Organization_Data.0.wd：Organization_Data.wd：Organization_Type_Reference.wd：ID.1。$
wd：Organization_Data.wd：Worker_Organization_Data.0.wd：Organization_Data.wd：Organization_Subtype_Reference.wd：ID.1。$
wd：Qualification_Data.wd：Education.0.wd：School_Name
wd：Qualification_Data.wd：External_Job_History.0.wd：Job_History_Data.wd：Job_Title
wd：Qualification_Data.wd：External_Job_History.0.wd：Job_History_Data.wd：Company
wd：Management_Chain_Data.wd：Worker_Supervisory_Management_Chain_Data.wd：Management_Chain_Data.0.wd：Manager.Employee_ID
主要工作电子邮件
wd：Organization_Type_Reference_Cost_Center_ID
wd：Organization_Type_Reference_Cost_Center_Name
wd：Organization_Type_Reference_Company
wd：Organization_Subtype_Reference_Department
wd：Organization_Subtype_Reference_Division
wd：Universal_ID
wd：Integration_Field_Override_Data.3.wd：Value
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Site_Summary_Data.wd：Address_Data.0.wd：Country_Region_Descriptor
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Site_Summary_Data.wd：Address_Data.0.wd：Country_Region_Reference.wd：ID.2。$
wd：Personal_Data.wd：Contact_Data.wd：Address_Data.0.wd：Unsicillity

+++

### 导出 {#export-1}

您可以将出用户达成的全部技能从 Adobe Learning Manager 导出到 Workday。仅会导出所有活动用户技能，Adobe Learning Manager 不导出弃用的技能。您还可以连接多个Learning Manager\
连接到同一Workday连接器。 如果两个Learning Manager帐户中的技能名称相同，则它们会被映射到Workday中的相同技能。 在Workday中更新技能之前，如果两个Learning Manager帐户使用的是同一个Workday帐户，则建议对所有Learning Manager帐户中的技能名称进行更新。

+++用户技能 — 配置

您可利用此选项来计划安排报表提取。确保已选中“使用此连接启用用户技能导出”选框。选中“启用计划”选框，然后指定开始日期和时间。您还可以指定生成和发送报告的时间间隔。选择“启用日程安排”复选框，然后输入开始日期、时间和几天后重复。完成后，单击“保存”。

![](assets/configure-schedule.png)
*配置用户技能报告*

+++

+++用户技能 — 按需

您可以利用此选项来指定开始日期并导出报告。将提取从输入的日期中到现在的报告。输入您要开始生成报告的日期，然后单击“执行”。

![](assets/on-demand-report.png)
*按需用户技能报告*

+++

+++用户技能 — 执行状态

在这里，您可以查看所有任务的摘要并获取其状态报告。您可以通过单击错误报告链接下载错误报告。

![](assets/execution-status.png)
*用户技能执行报告*

+++

## miniOrange 连接器 {#mini-orange-connector}

借助 miniOrange 连接器，您可以将 Adobe Learning Manager 与 miniOrange 租户集成以自动同步数据。

### 导入 {#import-6}

#### 映射属性 {#map-attributes-5}

集成管理员可以选择miniOrange属性并将其映射到相应的Learning Manager组属性。 映射完成后，相同映射就能用在随后的用户导入中。如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

#### 自动导入用户 {#automated-user-import-3}

用户导入操作能让Learning Manager管理员从miniOrange获取员工详细信息，并自动将其导入Learning Manager。

#### 过滤用户 {#filtering-users-3}

Adobe Learning Manager 管理员可在导入用户前先对其过滤。例如，Adobe Learning Manager 管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

如要设置   miniOrange   连接器，请联系Learning Manager CSM团队。

### 配置 miniOrange 连接器 {#configure-mini-orange-connector}

1. 在Learning Manager主页，将鼠标悬停在miniOrange卡/缩略图上方。 此时会显示菜单。单击菜单中的&#x200B;**[!UICONTROL 连接]**&#x200B;选项。

   ![](assets/miniorange-tile.png)

   *miniOrange连接器磁贴*

1. 单击&#x200B;**[!UICONTROL 连接]**&#x200B;以建立新连接。 出现miniOrange连接器页面。 输入您要映射的帐户的详细信息。

   ![](assets/establish-connection.png)

   *创建连接*

1. 如果要直接将miniOrange用户导入成为Learning Manager内部用户，请使用&#x200B;**[!UICONTROL 导入内部用户]**&#x200B;选项。

   ![](assets/import-users.png)

   *导入内部用户*

1. 在映射页面的左侧   可在左侧和右侧看到Learning Manager的各列   你可以看到miniOrnage的各列。 选择映射到Learning Manager列名称的相应列名称。

   ![](assets/map-attributes.png)

   *映射属性*

1. 如要查看和编辑数据源，作为管理员，单击“**[!UICONTROL 设置”>“数据源”]**。

   已建立的miniOrange源将被列出。 如果需要编辑筛选器，请单击&#x200B;**[!UICONTROL 编辑]**。

   ![](assets/data-source.png)

   *查看和编辑数据源*

1. 完成导入后，您将收到一条通知。如要查看或编辑导入日志，请单击&#x200B;**[!UICONTROL 用户 > 导入日志。]**

<!-- #### Delete a connection {#deleteaconnection}

To delete an established  miniOrange  connection, follow these steps. -->

## Zoom连接器 {#zoom-connector}

您可以将Learning Manager与Zoom连接器集成，并使用它们来主持课程。  通过该连接器，您可以与学习者一起设置视频会议会议/课程。

如要设置和使用连接器，请按照下列步骤操作。

1. 在Learning Manager主页中，将鼠标悬停在“缩放”缩览图上。 此时会显示菜单。单击菜单中的&#x200B;**[!UICONTROL 连接]**&#x200B;选项。

   <!-- ![](assets/connectors.png)

   *Zoom connector tile* -->

1. Zoom连接器页面即会打开。 在相应字段中输入帐户的详细信息，以集成和同步用户订阅源。 您可以从您连接器帐户的管理员处获取这些详细信息。

   <!-- ![](assets/bluejeans-connecotrpage.png)
   *Connect to BlueJeans/ Zoom* -->

   >[!NOTE]
   >
   >作为学习者，启用连接器时，应使用您的 Adobe Learning Manager 帐户所用的电子邮件 ID 来启用将用户订阅源发送回 Adobe Learning Manager。

1. 建立连接后，作为作者，即可使用Zoom创建VC课程作为会议系统。

   <!-- ![](assets/vc.jpg)
   
   *Create a VC course* -->

1. 管理员、经理和学习者均可为已创建的课程注册学习者。 注册后，学习者会收到一封电子邮件。学习者便可登录其 Adobe Learning Manager 帐户来查看计划的详细信息，并参加课程学习。
1. 课程完成后，完成报告将被发送至 Adobe Learning Manager。管理员可查阅完成报告，检查学习者的出勤和得分。

   ![](assets/attendence-and-scoringreport.png)
   *出席和得分报告*

### 创建缩放服务器到服务器OAuth应用程序 {#create-a-zoom-server-to-server-oauth-app}

创建要在Adobe Learning Manager中使用的Zoom服务器到服务器OAuth应用程序时，必须在创建连接时添加Adobe Learning Manager所需的范围。

Adobe Learning Manager 需要获取以下范围，并且必须在 OAuth 应用中选择这些范围。

* 查看所有用户会议`/meeting:read:admin`
* 查看和管理所有用户会议`/meeting:write:admin`
* 查看报告数据`/report:read:admin`
* 查看所有用户信息`/user:read:admin`
* 查看用户信息并管理用户`/user:write:admin`

## Box 连接器 {#box_connector}

借助 Box 连接器，您可以将 Adobe Learning Manager 与任意外部系统集成以自动同步数据。需要外部系统能够以CSV格式导出数据，并将其放置在Learning Manager Box帐户内相应文件夹下。 Box连接器功能如下：

您还可以使用FTP连接器进行数据迁移、用户导入和数据导出。 有关更多信息，请查阅 [Adobe Learning Manager FTP 连接器。](connectors.md#main-pars_header_1427405935)

### 数据导入 {#data-import-1}

用户导入操作能让 Adobe Learning Manager 管理员从 Adobe Learning Manager Box 服务中提取员工详细信息，并自动将其导入 Adobe Learning Manager。使用此功能，您可以将这些系统生成的 CSV 放在 Box 帐户下的相应文件夹中来集成多个系统。Adobe Learning Manager 会拾取 CSV 文件，将其合并，并根据计划导入数据。请参见计划功能了解更多信息。

**映射属性**

集成管理员可以选择 CSV 列并将其映射到 Adobe Learning Manager 的组属性。映射只需进行一次。 映射完成后，相同映射就能用在随后的用户导入中。如果管理员想要针对导入用户使用不同的映射，则可以对映射进行重新配置。

## 数据导出 {#data-export}

数据导出允许用户将用户技能和学习者成绩单导出到 Box 位置，从而与任何第三方系统集成。

## 计划报告 {#schedule-reports}

管理员可以根据公司的要求计划相关任务，Adobe Learning Manager 应用程序中的用户可以根据计划获得最新消息。同样，集成管理员可以及时安排技能导出，以便与外部系统集成。可以在 Adobe Learning Manager 应用程序中每天执行同步。

## 配置 Box 连接器 {#boxconnector}

如要将Box连接器与Learning Manager集成，请学习相应操作过程。

1. 在Learning Manager主页，将鼠标悬停在Box卡/缩略图上方。 此时会显示菜单。单击菜单中的“连接”条目。

   ![](assets/screen-shot-2017-10-25at54426pm.png)

   *连接到Box*

1. 此时会显示一个对话框，提示您输入电子邮件 ID。提供负责管理公司Learning Manager Box帐户的人员的电子邮件ID。 提供电子邮件ID后，单击“连接” 。
1. Adobe Learning Manager 发送给您一封电子邮件，提示用户在第一次访问 Box 之前重置密码。用户必须重置密码，并使用此密码来访问Learning Manager Box帐户。

   >[!NOTE]
   >
   >一个Learning Manager帐户仅可创建一个Learning Manager Box帐户。

   在“概述”页面中，您可以指定集成的连接名称。 从以下选项中选择要执行的操作：

   * 导入内部用户
   * 导入 xAPI 活动报告
   * 导出用户技能 - 配置计划
   * 导出用户技能 - 按需
   * 导出学习者成绩单 — 配置计划
   * 导出学习者成绩单 — 按需

## 导入 {#import-7}

+++内部用户

您可使用内部用户选项来自动计划生成用户导入报告。生成的报告将作为 .CSV 文件发送给您。

+++

+++映射属性

成功建立连接后，您便可将Box文件夹中存放的CSV文件列映射到Learning Manager的相应属性。 此步骤为必须操作。

1. 在“映射属性”页面的左侧   可在右侧看到Learning Manager的预期列   一侧可看到CSV列名称。 首先，您会在右侧看见一个空的选择框。点击“选择文件”，导入任一模板CSV。
1. 上述步骤会在右侧的选择下拉列表中填写所有 CSV 列名称。选择映射到Learning Manager列名称的相应列名称。

   *经理字段必须映射到电子邮件地址类型的字段。 在能够使用连接器之前，必须映射所有列。*

1. 完成映射后单击“保存” 。

   连接器现在可以使用了。已配置的帐户在管理员应用程序中显示为数据源，以便管理员安排导入或用于按需同步。

+++

+++xAPI活动报告

xAPI 活动报告选项允许您生成对第三方服务 xAPI 语句的导入。这些文件保存为 .CSV 文件，然后在导入 Adobe Learning Manager 时会转换为 xAPI 语句。

+++

+++导入xAPI所需的配置

1. 在配置页面中，选择配置列表中可用的现有配置，以从CSV导入xAPI语句。 单击编辑或&#x200B;**添加新配置**&#x200B;链接以导航至“导入xAPI语句 — 配置 — 源文件”页面。

   ![](assets/artboard-11-2x.png)

   *编辑或添加新配置*

   **配置**

   * 在“配置导入源”页面中，填写两个字段，即“名称”和“源文件名”。源文件名应与 FTP 文件夹位置中提供的文件名匹配。
   * 单击&#x200B;**[!UICONTROL “保存”]**&#x200B;以保存更改。

   ![](assets/configurations-main2x.png)

   *配置*

   **过滤器**

   * 在左侧窗格中，单击过滤器。
   * 在“配置导入 - 过滤器”页面中，填写“名称”和“条件”字段以滤除记录。单击“添加新过滤器”以添加其他过滤器。您可以单击“操作”列下的“保存”或“删除”选项来保存或删除过滤器。

   ![](assets/box-filter-2x.png)

   *过滤器*

   **映射**

   * 在左侧窗格中，单击“映射”。
   * 在“配置导入 - 映射”页面的左侧，您可以看到需要与 CSV 列名称映射的 xAPI Json 字段路径名。
   * 默认情况下，需要与 CSV 列名称映射的三个 Json 路径字段名分别为 **actor.mbox**、**verb.id** 和 **object.id**。您可以单击“添加新映射”来添加要映射的其他字段。
   * 选择要与 Json 字段路径名映射的列名称类型（字符串、数字、布尔值或日期类型）。
   * 完成映射后单击“保存”。xAPI 现在可以按计划或按需导入。

   ![](assets/box-mapping-2x.png)
   *映射*

1. 在左侧窗格中，单击&#x200B;**[!UICONTROL 配置计划]**。单击“启用计划”，以计划导入 xAPI 语句。您可以输入开始时间和日期，然后以天为单位输入 xAPI 导入计划的频率。例如，每 3 天启用一次 xAPI 导入。

   ![](assets/configure-schedulebox2x.png)
   *导入xAPI语句 — 配置计划*

1. 在左侧窗格中，单击&#x200B;**[!UICONTROL 按需执行]**。

   ![](assets/box-on-demand-2x.png)
   *导入xAPI语句 — 按需*

1. 在左侧窗格中，单击&#x200B;**[!UICONTROL 执行状态]**，按时间顺序查看此连接器所有运行的摘要。您可以查看导入 xAPI 时的开始日期和持续时间，导入类型（按需或按计划）以及导入状态（xAPI 导入进行中、已完成或失败）。

   ![](assets/box-execution-status2x.png)
   *导入xAPI语句 — 执行状态*

+++

+++使用Learning Manager Box连接器

1. 必须将来自外部系统的CSV文件放在以下路径中：

   `code $OPERATION$/$OBJECT_TYPE$/$SUB_OBJECT_TYPE$/data.csv`

   >[!NOTE]
   >
   >在2016年7月版中，仅允许导入用户。 因此，如要使用Box连接器，请确保已将CSV文件放入以下文件夹：

   `code Home/import/user/internal/*.csv`

1. Box连接器从CSV文件中获取所有行。 重要的是，某 CSV 文件中某位用户对应的行不会出现在任何其他 CSV 中。
1. 所有CSV都必须包含映射中指定的列。
1. 在流程开始之前，文件夹中必须存在所有必需的CSV。

在将用户导入到 Adobe Learning Manager 时，管理员还必须了解如何在 Adobe Learning Manager 中管理用户。请参阅[用户管理帮助](migration-manual.md#usermanagement)以了解更多信息。

+++

## 导出 {#export-2}

+++技能

有两个选项可用于导出用户技能报告。

用户技能 - 按需：您可以使用该选项指定开始日期并导出报告。将提取从输入的日期到现在的报告

**[!UICONTROL 用户技能 - 配置]**：您可使用此选项来计划安排提取报告。选中“启用计划”选框，然后指定开始日期和时间。您还可以指定生成和发送报告的时间间隔。

+++

如要打开已导出文件位于Box中的“导出”文件夹，请打开“用户技能”页面中提供的“Box文件夹”链接，如下所示：

自动导出的文件出现在&#x200B;**Home/export/&#42;Box_location&#42;**&#x200B;中

自动导出文件的标题为&#x200B;**skill_achievements_&#42;开始日期&#x200B;&#42;_至_&#42;结束日期&#42;.csv**

>[!NOTE]
>
>客户负责管理访问权限和Learning Manager团队在Box文件夹中共享的内容。  文件夹中的内容也将物理存储在法兰克福地区。

### 支持手动 csv 字段 {#support-for-manual-csv-fields-1}

通过 Box 导入用户数据时，管理员必须将系统中呈现的所有活动字段都映射到 csv 中的相应字段。

对于所有 csv 活动字段，这是必须的。 对于手动活动字段，集成管理员可以选择 **DontImportFromSource** 选项。

通过选择此选项，手动活动字段值不会使用 csv 导入来填充。 学习者提供的值保持不变。

>[!NOTE]
>
>在映射时，如果为csv活动字段选择了&#x200B;**DontImportFromSource**&#x200B;选项，则将从系统中删除此字段。

![](assets/box-connector-foractivefields.png)
*活动字段的Box连接器*

>[!NOTE]
>
>对于任何使用 FTP/Box 作为数据源的连接器或迁移，所有处理过的 csv 文件都将删除。
>
>用于内容连接器（例如 LinkedIn）的 csv 将在七天后删除，而用于导入用户的 csv 将立即删除。

## LinkedIn 学习连接器 {#linkedinlearningconnector}

LinkedIn.com 的企业用户可使用 LinkedIn 学习连接器供其学习者在 Adobe Learning Manager 内找到并学习相关课程。此连接器可以配置为使用您的 API 密钥定期提取课程。在 Adobe Learning Manager 中创建课程后，用户就能搜索和使用这些课程。随后就可以在 Adobe Learning Manager 中跟踪学习者的学习进度。

>[!NOTE]
>
>对于从LinkedIn学习连接器导入到Adobe Learning Manager的所有课程，您将获得唯一学习对象ID。

>[!NOTE]
>
>在 LinkedIn 学习课程中花费的学习时间由 LinkedIn 内容/LinkedIn 平台传达给 Adobe Learning Manager 学习平台。如果 LinkedIn 学习不发送学习时间，则无法通过我们的学习平台进行记录。 在这种情况下，Learning Manager显示的学习时间为零。

### 配置 Linkedln 学习门户中的设置 {#configure-settings-in-linkedln-learning-portal}

1. 以管理员身份登录 Linkedln 学习 LMS。
1. 在顶部导航面板中单击&#x200B;**[!UICONTROL 管理员]**。
1. 在下一个窗口中点击&#x200B;**[!UICONTROL 设置]**&#x200B;选项卡。
1. 从左侧导航面板中选择&#x200B;**[!UICONTROL 播放集成]**，然后单击&#x200B;**集成**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL LMS内容启动设置]**&#x200B;以展开其设置。
1. 添加以下三个主机名：**learningmanager.adobe.com**、**learningmanagerlrs.adobe.com**、**cpcontents.adobe.com**
1. 选择&#x200B;**[!UICONTROL 启用 AICC 集成]**。

   ![](assets/linkedin-learning.png)

   *LinkedIn学习配置*

### 配置 LinkedIn 学习连接器 {#configure-linkedin-learning-connector}

1. 在集成管理员信息板中，单击[!UICONTROL LinkedIn学习]。 您会看到三个选项，“入门”、“连接”和“管理连接”。
1. 如果您是第一次配置LinkedIn学习连接器，请单击“[!UICONTROL 连接]”。

   <!--Configure the Exavault FTP account before you configure this connector.

   ![](assets/configure.jpg)
   *Configure connection*-->

1. 在连接页面，为您的连接器指定名称。输入 Appkey 和您的连接的密钥。

   >[!NOTE]
   >
   >企业管理员可以从LinkedIn学习管理门户生成一个新的应用程序，以获取Appkey和密钥。

1. 单击&#x200B;**[!UICONTROL “保存”]**。

   配置即会保存，并为您的帐户添加 LinkedIn 学习连接。您现在可以从主页单击&#x200B;**[!UICONTROL 管理连接]**，并随时编辑您的配置。

1. 如果已建立连接，请单击&#x200B;**[!UICONTROL 管理连接]**&#x200B;查看所有连接。

   >[!NOTE]
   >
   >在您配置此连接器之前，必须为您的帐户启用迁移功能。

1. 单击要编辑的连接。
1. 在左侧窗格中，单击“配置”。 执行以下任一操作：

   * 查看或编辑您帐户的详细信息，以及这个窗格中的同步计划。如果要启用此帐户，请选中&#x200B;**[!UICONTROL 启用连接]**&#x200B;复选框。
   * 单击&#x200B;**[!UICONTROL 编辑]**&#x200B;并编辑您的凭据。 如要撤消对此字段的更新，请单击“重置”。
   * 单击&#x200B;**[!UICONTROL 启用计划]**&#x200B;以计划同步。 您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。例如，启用每三天同步一次。

   单击&#x200B;**[!UICONTROL “保存”]**&#x200B;以保存更改。

1. 在左侧窗格中，单击&#x200B;**[!UICONTROL 按需执行]**。 您可使用此选项从 LinkedIn 导入用户订阅源和其他相关数据。输入按需执行的“开始日期”，然后单击“执行”以执行同步。 将导入从开始日期到现在的所有数据。

   * 如果同步过程中应用程序停机，则您可以单击&#x200B;**[!UICONTROL 禁用同步过程中对Learning Manager的访问]**。
   * 如果您在执行期间单击&#x200B;**[!UICONTROL 启用对Learning Manager的访问]**，则同步期间服务不会中断。

   ![](assets/ondemandexecution.jpg)

   *按需执行报表*

1. 您还可以随时从左侧窗格单击“执行状态”，按时间顺序查看此连接器所有运行的摘要。您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   ![](assets/executionstatus.jpg)

   *报告执行状态*

   >[!NOTE]
   >
   >删除并重新创建连接时，连接器的先前运行将再次出现。在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

### 筛选 LinkedIn 学习内容 {#filter-linkedin}

LinkedIn 连接器中附带筛选条件，会根据 LinkedIn 学习库中的数据划分相应内容。 此外，您还可以根据语言和库来筛选内容，并仅导入使用所需语言的课程。课程导入后，系统会根据导入配置将内容划分为多个目录。

筛选条件如下：

**所用的培训筛选条件：**&#x200B;从 LinkedIn 中筛选出对应的课程子集，并导入至 Adobe Learning Manager。

* **基于语言**

![](assets/filter-language.png)

*按语言筛选*

* **基于LinkedIn学习库**

![](assets/filter-catalog.png)

*按目录筛选*

**将培训导入至**

![](assets/iport-training.png)
*将培训导入目录*

**导入标签**

系统为您提供&#x200B;**“自定义标签”**&#x200B;的标签类型，您可借此为 LinkedIn 学习课程添加自定义标签。 您可以任意添加多个标签，并使用逗号分隔。

![](assets/add-custom-tags.png)

*添加自定义标签*

仅在迁移后才会保存内容。 相关内容将保存在相应的目录中。

## Power BI 连接器 {#powerbiconnector}

>[!NOTE]
>
>Adobe Learning Manager 仅支持与 Microsoft Power BI 的商业许可集成。不支持在 Government Cloud 上与 Microsoft Power BI 集成。

您可使用此连接器的集成功能来利用现有Power BI帐户在Power BI中分析及直观显示Learning Manager中的学习数据。 在配置期间，集成管理员可以将其 Power BI 工作区设置为使用两个实时数据集（学习者成绩单和用户技能报告）进行增量填充。 随后，您可以使用 Power BI 的所有功能和能力按照企业需求开发、部署并分配自定义信息板。

### 配置此连接器 {#configuring-the-connector}

若要配置连接器，请在&#x200B;**[!UICONTROL 连接器]**&#x200B;页面中，将鼠标悬停在&#x200B;**[!UICONTROL Power BI]**&#x200B;磁贴上，然后单击&#x200B;**[!UICONTROL 连接]**。 Power BI 页面即会打开。 如要建立连接，您需提供应用程序客户端 ID、应用程序客户端密钥、租户名称和工作区 ID（可选）。要获取这些凭据，请按照下列步骤操作。

![](assets/power-bi-configurepage.png)

*配置Power BI连接器*

1. 启动<https://app.powerbi.com/embedsetup>。
1. 单击&#x200B;**[!UICONTROL 为您的组织嵌入]**，然后登录到您的Microsoft帐户。
1. 输入应用程序的名称。
1. 在“应用程序类型”部分，选择“服务器端Web应用程序”选项。
1. 在&#x200B;**[!UICONTROL 重定向URL]**&#x200B;部分，选择选项&#x200B;**使用自定义URL**（如果您知道目标应用程序的URL，请选择此选项）。 输入以下URL：

   `https://learningmanager.adobe.com/ctr/app/azure/_callback` （根据环境更新域）

1. 在“主页URL”字段中，输入以下URL `https://learningmanager.adobe.com/`
1. 在权限部分中，选择&#x200B;**读取所有数据集**&#x200B;和&#x200B;**读取和写入所有数据集**。

   获取租户：联系您的 Power BI 管理员以获取租户名称。

   获取其工作场所 ID：仅 Power BI Pro 用户可创建工作场所。您可以在 Power BI 中创建工作场所，并从 URL 处获取 ID。

1. 单击&#x200B;**[!UICONTROL 注册应用]**&#x200B;并存储客户端ID和客户端密钥。

>[!NOTE]
>
>如果要再次授权连接，您必须创建另一个Power App，并指定更名的重定向URL。

您可以使用相同的方法导出学习者成绩单、用户技能和 xAPI 活动报告。从左侧面板中选择学习者成绩单/用户技能。“导出”页面即会打开。

启用&#x200B;**[!UICONTROL “使用此连接选框来启用用户技能/学习者成绩单导出”]**。保存更改。

**导出配置**：如果您要计划安排报告的提取。选中&#x200B;**[!UICONTROL 启用计划]**&#x200B;复选框并指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。

![](assets/power-bi-configureuserskillpage.png)

*导出配置以计划报告*

**按需导出：**&#x200B;您可以使用该选项指定开始日期并导出报告。 将提取从输入的日期到现在的报告。

![](assets/power-bi-userskillondemandpage.png)

*按需导出*

可以登录 Power BI 帐户来查看导出的数据。导出的数据在数据集一项下列出。

### 在 Adobe Learning Manager 中导出 xAPI 活动报告 {#export-xapi-activity-reports-in-captivate-prime}

在PowerBI-xAPI功能页面中，单击&#x200B;**[!UICONTROL 导出xAPI活动报告]**。

![](assets/powerbi-dashboard.png)
*PowerBI — 导出xAPI活动报告*

在左侧窗格中选择&#x200B;**配置**&#x200B;并执行以下步骤：

* 填写与列名和字符串类型匹配的 JSON 路径字段。
* 要添加更多 JSON 路径，请单击&#x200B;**[!UICONTROL “添加”]**。
* 您可以单击&#x200B;**[!UICONTROL 编辑]**&#x200B;以对 JSON 路径字段中的条目进行编辑。
* 单击&#x200B;**[!UICONTROL “保存”]**&#x200B;以保存更改。

**配置计划**

在左侧窗格中，单击&#x200B;**[!UICONTROL 配置计划]**&#x200B;并执行以下操作。

* 单击“启用使用此连接进行 xAPI 语句导出”。
* 单击&#x200B;**[!UICONTROL 启用计划]**&#x200B;复选框并指定开始日期和时间。您还可以指定要重复导出和发送的间隔天数。
* 单击&#x200B;**[!UICONTROL 保存]**&#x200B;按钮以保存配置计划设置。

![](assets/configure-schedule.png)
*xAPI导出配置计划*

**按需**

在左侧窗格中，单击&#x200B;**[!UICONTROL 按需]**&#x200B;并在“导出 xAPi 语句 - 按需”页面指定“开始日期”。

![](assets/on-demand-2.png)
*xAPI按需导出*

所有导出的数据都将进入 Adobe 在 Power BI 帐户中创建的数据集。

如果 LRS 中的少数 xAPI 语句没有配置用于导出的 json 路径，则 xAPI 导出到 Power BI 将会失败。对于无可用 json 路径的 xAPI 语句，应添加 N/A 常量值并在Power BI 中显示。

**执行状态**

选择&#x200B;**执行状态**，按时间顺序查看所有任务的摘要。在运行期间，警告标志表示失败。您可以单击错误报告链接，将错误报告下载为&#x200B;**CSV**。

![](assets/execution-status.png)
*xAPI导出执行状态*

### 统一报告 {#unified-reports}

Learning Manager可汇总用户数据、学习者成绩单、游戏、反馈报告等多份报告来创建导出内容，并将之作为一个数据集用于Power BI。

这使 Power BI 用户能够合并多份报告中的数据，从而在 Power BI 中展示十分强大的分析能力和可视化能力。

![](assets/unified-power-bireports.png)
*统一Power BI报告*

**按需导出**

使用该选项指定开始日期和结束日期并导出报告。 系统随即将提取指定日期范围内的报告。

![](assets/on-demand-export.png)
*按需导出*

**安排导出时间**

在要安排报告提取时间的情况下适用。选中&#x200B;**“启用计划”**&#x200B;选框，然后指定开始日期和时间。您还可以指定生成和发送报告的时间间隔。

![](assets/configure-schedule.png)
*配置计划*

您还可以将培训报告导出到Power BI。

培训报告可以作为“统一报告”功能的一部分导出到 Power BI。

培训报告包含两个附加字段：

* 已分享课程反馈的用户数量
* 课程的平均星级评分

### 筛选学习者成绩单的状态 {#lt-status}

在 Power BI 连接器的“统一报告”部分中，您可以通过相应选项并按照“学习对象”状态导出“学习者成绩单”。

* **全选：**&#x200B;导出指定日期范围内的所有记录或模块级活动。
* **已完成：**&#x200B;导出在日期范围内完成的所有记录。
* **进行中：**&#x200B;导出所有状态为“进行中”的记录。
* **未开始：**&#x200B;排除已于既定日期范围内注册但在报告生成时尚未开始的记录。

* **取消注册：**&#x200B;包括在日期范围内取消注册的所有记录。

![](assets/lt-filters.png)
*筛选学习成绩单的状态*

您可以导出所需列表，然后在稍后使用 Power BI 来分析报告。

### 下载 Power BI 模板 {#template}

Learning Manager还提供了现成的Power BI模板。 这些模板为Adobe Learning Manager帐户管理员提供了更出色的分析能力。

您可以下载模板、导出相关报告并使用这些可用模板轻松绘制报告。

![](assets/download-power-bi-template.png)
*下载Power BI模板*

这允许用户下载这些模板并应用在Power BI应用程序中，同时允许用户进一步自定义这些模板，使报告更具有信服力。

[**下载模板**](https://documentcloud.adobe.com/link/track?uri=urn:aaid:scds:US:842bb6a2-cd7d-4c3d-b968-da38bc1cc18a)

<!--<table> 
 <tbody>
  <tr> 
   <td><img src="assets/download.png"></td> 
   <td><p> </p> <p><a disablelinktracking="false" href="https://documentcloud.adobe.com/link/track?uri=urn:aaid:scds:US:842bb6a2-cd7d-4c3d-b968-da38bc1cc18a"><strong><em>Download the templates</em></strong></a></p></td> 
  </tr> 
 </tbody>
</table>-->

您还可以通过上面的链接手动下载模板。 使用模板并自定义相应的报表。

### 导出培训报告 {#export-training-report}

借助“统一报告”功能，您可将培训报告导出到 Power BI。

培训报告包含以下附加字段：

* 已分享课程反馈的用户数量
* 课程的平均星级评分

![](assets/export-training-report.png)
*导出培训报告*

### 学习路径相关更改 {#learning-path-related-changes}

#### 管理员：学习成绩单和统一报告 {#learning-transcripts-and-unified-reports}

**现有连接**

如果在管理员帐户中禁用了“学习路径”选项，则不会在报告中添加行和列。

如果在管理员帐户中启用了“学习路径”选项，则报告将包含类型“学习路径（较高级别）”列，适用于注册学习路径的所有学习者。

**新连接**

如果在管理员帐户中禁用了“学习路径”选项，则培训报告将包含以下列：

* 嵌入式路径：显示学习计划的名称
* 嵌入式路径 ID：显示学习计划的 ID。
* 嵌入式课程 ID：显示学习路径内的课程 ID。

此外，该报告将包含类型“学习路径（较高级别）”列，适用于注册学习路径的所有学习者。

在“类型”列中，“学习计划”将更名为“学习路径”。 现有连接将不会发生更改。 但是，对于新连接，更改将在30天后反映出来。

#### 培训报告：统一报告 {#training-report}

**现有连接**

如果在管理员帐户中禁用了“学习路径”选项，则不会在报告中添加行和列。

如果在管理员帐户中启用了“学习路径”选项，则报告将包含“类型”列。 该列包含新值“学习路径（较高级别）（如适用）”。

**新连接**

如果在管理员帐户中禁用了“学习路径”选项，则培训报告将包含以下列：

* **嵌入式路径**：显示学习计划的名称
* **嵌入式路径 ID**：显示学习计划的 ID。
* **嵌入式课程ID：**&#x200B;显示学习路径内的课程ID。

此外，该报告将包含类型“学习路径（较高级别）”列，适用于注册学习路径的所有学习者。

在“类型”列中，“学习计划”将更名为“学习路径”。 现有连接将不会发生更改。 但是，对于新连接，更改将在30天后反映出来。

## 自定义 FTP {#custom-ftp}

**先决条件**

>[!NOTE]
>
>要设置自定义 FTP，请与 CSM 联系。 CSM 将提供设置 FTP 所需的详细信息。
>
>设置FTP涉及前置时间，并且需要IT支持来允许IP和端口列表，以及在FTP服务器上创建具有特定权限的特定文件夹。

Adobe Learning Manager 提供连接到自定义 FTP 位置的功能。

您的 FTP 将支持以下功能：

### 数据导入 {#data-import-2}

用户导入操作能让 Adobe Learning Manager 管理员从 Adobe Learning Manager FTP 服务中提取员工详细信息，并自动将其导入 Adobe Learning Manager。使用此功能，您可以将这些系统生成的 CSV 放在 FTP 帐户下的相应文件夹中来集成多个系统。Adobe Learning Manager 会拾取 CSV 文件，将其合并，并根据计划导入数据。请参见计划功能了解更多信息。

**映射属性**

集成管理员可以选择 CSV 列并将其映射到 Adobe Learning Manager 的组属性。映射只需进行一次。映射完成后，相同映射就能用在随后的用户导入中。如果管理员想要针对导入用户使用不同的映射，则可以对映射进行重新配置。

### 数据导出 {#data-export-3}

数据导出允许用户将用户技能和学员成绩单导出到 FTP 位置，从而与任何第三方系统集成。

### 计划报告 {#schedule-reports-2}

管理员可以根据公司的要求计划相关任务，Adobe Learning Manager 应用程序中的用户可以根据计划获得最新消息。同样，集成管理员可以及时安排技能导出，以便与外部系统集成。可以在 Adobe Learning Manager 应用程序中每天执行同步。

要配置您自己的FTP，请以集成管理员身份登录，然后单击&#x200B;**[!UICONTROL 自定义FTP]** > **[!UICONTROL 连接]**。

身份验证有两种类型：

![](assets/custom-ftp-authenticationoptions.png)
*自定义FTP身份验证选项*

* **基本：**&#x200B;在基本身份验证中，您只需提供FTP域URL、用户名和密码。 提供详细信息后，单击“连接”。
* **认证：**&#x200B;如果客户FTP支持证书身份验证，则可以选择此选项。 单击“生成SSH密钥”后，SSH密钥将下载到您的本地计算机。 打开文件时，密钥显示如下，

![](assets/ssh-public-key.png)
*SSH公钥*

在添加以下详细信息之前，必须将此公钥放入FTP服务器。 在将给定密钥设置为FTP的公钥后，请提供FTP域URL和用户名，然后单击&#x200B;**连接**&#x200B;按钮以设置连接。

完成连接设置后，系统将在ftp位置自动创建用于导入和导出的文件夹。 此后，自定义FTP将提供导入/导出功能。

>[!NOTE]
>
>只能使用 SFTP 服务器配置自定义 FTP 连接器。

## ADFS 连接器 {#adfsconnector}

建立 ADFS 连接的先决条件：

* 在注册您的应用程序之前，请使用以下URL登录到您的Azure门户： [https://portal.azure.com/](https://portal.azure.com/)。
* 打开Azure Active Directory。

## 注册应用程序的步骤 {#steps-to-register-your-application}

* 单击 Azure Active Directory。 单击&#x200B;**[!UICONTROL 添加]** > **[!UICONTROL 应用程序注册]**。

  <!--![](assets/add-app-registration.png)-->
  <!-- *Add app registration*-->

* 输入应用程序名称。

  <!--![](assets/register-app.png)-->
  <!--*Enter the name of the application*-->

  单击&#x200B;**[!UICONTROL “注册”]**。

* 在右侧窗格中，选择&#x200B;**[!UICONTROL “证书和密钥”]**。

  <!--![](assets/add-client-secret.png)-->

  <!--*Select Certificates and Secrets*-->

* 添加客户端密钥。

  <!--![](assets/add-description.png)-->

  <!--*Add a client secret*-->

* 为密钥添加描述，并将其到期时间设置为 24 个月。

  <!-- ![](assets/copy-values.png)-->

  <!--*Add description*-->

* 例如，将值和密钥复制到记事本。

  <!-- ![](assets/copy-secret.png)-->

  <!--*Copy value and secret key*-->

* 选择&#x200B;**“API 权限”**。

  <!--![](assets/click-api-permission.png)-->

  <!-- *Left pane containing API Permissions*-->

* 选择&#x200B;**“添加权限”**。 此外，请启用选项&#x200B;**“授予管理员许可”**。

  ![](assets/add-permission.png)

  *添加权限*

* 选择&#x200B;**“Microsoft Graph”**。

  <!--![](assets/ms-graph.png)-->

  <!--*Select Microsoft Graph*-->

* 选择&#x200B;**“应用程序权限”**。

  ![](assets/request-api-permission.png)

  *选择应用程序权限*

* 搜索&#x200B;*“目录”*&#x200B;并选择&#x200B;**“读取目录数据”**。

  ![](assets/read-directory-data.png)

  *选择读取目录数据*

* 输入&#x200B;*“用户”*&#x200B;作为搜索词。

  ![](assets/search-user.png)

  *输入搜索词*

* 选择&#x200B;**“读取所有用户的完整个人资料”**。

  ![](assets/select-read-all.png)

  *选择“读取所有用户的完整个人资料”*

* 选择&#x200B;**“添加权限”**。

  <!--![](assets/select-add-permission.png)-->

  <!-- *Select Add Permissions*-->

### “ADFS配置”页面 {#adfs-configuration-page}

1. 在 Adobe Learning Manager 的 ADFS 配置页面中，输入先前获得的客户端 ID 和客户端密钥。

   单击&#x200B;**[!UICONTROL “连接”]**。

1. 登录到&#x200B;**portal.azure.com**。 这些值将填充到“租户ID”和“主域”字段中。

### 导入 {#import-8}

#### 映射属性 {#map-attributes-6}

集成管理员可以选择ADFS属性并将其映射到相应的Learning Manager组属性。 映射完成后，相同映射就能用在随后的用户导入中。如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

#### 自动导入用户 {#automated-user-import-4}

用户导入操作能让Learning Manager管理员从ADFS获取员工详细信息，并自动将其导入Learning Manager。

#### 过滤用户 {#filtering-users-4}

Learning Manager管理员可在导入用户前先对其过滤。 例如，Adobe Learning Manager 管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

要设置ADFS连接器，请联系Learning Manager CSM团队。

## 配置 ADFS 连接器 {#configure-adfs-connector}

1. 在Learning Manager主页，将鼠标悬停在ADFS卡片/缩略图上方。 此时会显示菜单。点击菜单中的连接条目。

   ![](assets/adfs1.jpg)

   *ADFS缩略图*

1. 单击“连接”以建立新连接。此时会显示ADFS连接器页面。 输入您要映射的帐户的详细信息。

   ![](assets/adfs2.jpg)

   *建立连接*

1. 如要直接将ADFS用户导入成为Learning Manager内部用户，请使用导入内部用户选项。

   ![](assets/adfs3.jpg)

   *将用户导入Learning Manager*

1. 在映射页面的左侧   可在左侧和右侧看到Learning Manager的各列   侧边可以看到ADFS的各列。 选择映射到Learning Manager列名称的相应列名称。

   ![](assets/adfs4.jpg)

   *映射属性*

1. 若要查看和编辑数据源，作为管理员，单击&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 数据源]**。

   已建立的ADFS源将被列出。 如果需要编辑筛选器，请单击&#x200B;**[!UICONTROL 编辑]**。

   ![](assets/datasource.jpg)
   *数据源设置*

1. 完成导入后，您将收到一条通知。要查看或编辑导入日志，请单击&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 导入日志]**。

### 删除连接 {#delete-a-connection-1}

要删除已建立的miniOrange连接，请执行以下步骤。

## Adobe Connect {#connect}

1. 在 Adobe Connect 上，点击卡上的三个点，然后选择&#x200B;**“连接”**。
1. 单击Adobe Connect配置部分中的&#x200B;**立即配置**&#x200B;链接。
1. 提供公司的 Adobe Connect 域名和登录凭据。

   Adobe Connect URL 示例：***mycompany.adobeconnect.com***

   您必须提供 Adobe Connect 帐户管理员的电子邮箱 ID。

   >[!NOTE]
   >
   >Adobe Learning Manager 仅支持 Adobe 托管的 Connect 帐户。示例：.adobeconnect.com。

1. 单击&#x200B;**[!UICONTROL 集成]**。

   验证电子邮件ID后，Learning Manager会显示消息“Connect成功集成”。 您可以使用 Adobe Connect 自动查看虚拟教室课程。

   **在 Connect 帐户管理员对其电子邮件 ID 进行身份验证后，系统会将请求交予 Adobe Connect 后端团队进行审批。通常需要一两天时间才能批准和设置集成。**

   >[!NOTE]
   >
   >Adobe Connect 帐户管理员应接受 Adobe Connect 的使用条款和条件。如果不接受，则登录身份验证会失败。创建 Adobe Connect 帐户后，请登录一次帐户。在首次登录时，会显示条款和条件页面。

### 添加虚拟教室会话信息 {#add-virtual-classroom-session-information}

如果虚拟教室课程的作者没有提供会话信息，那么管理员可提供会话详细信息。

以管理员身份登录，单击虚拟教室课程名称。单击左侧窗格中的“实例”和“会话详细信息”。  单击“会话详细信息”页面右上角的“编辑”图标以添加会话信息。

通过 Adobe Learning Manager 和 Adobe Connect 集成来创建虚拟教室模块或会话，您的 Connect 帐户应支持多个会议室，提供足够数量的会议室和在线用户同时使用。这些会议室用于支持 Adobe Learning Manager 虚拟教室模块。Adobe Learning Manager 会为其中每个虚拟教室模块或会话动态创建新的 Connect 会议室。

>[!NOTE]
>
>您必须在 Adobe Learning Manager 之外单独购买 Adobe Connect。

### Adobe Connect 长期会议室 {#persistent}

在 Adobe Connect 中，客户使用他们已在 Connect 中创建的现有会议室。 Connect 中的所有会议室都是长期的，且会议室模板会经过精心设置，以为所有长期会议室打造统一的体验。

您可以使用 Adobe Connect 中所创建的一个教室创建虚拟教室会话。

Adobe Learning Manager 现在还允许学习者通过身份验证进入 Connect 会议室加入虚拟会话。

![](assets/adobe-connect-authentication.png)
*Adobe Connect身份验证*

使用 Adobe Connect 创建虚拟教室模块时，可选择一个长期教室。如果选择&#x200B;**“无”**，则动态会议室的创建和以前一样。

![](assets/persistent-room-selection.png)
*长期教室选择*

学员通过 Adobe Connect 参加并完成课程后，会话的录制以及密码将显示在“学员”应用程序中。

![](assets/connect-recording.png)
*连接录音*

### 从 Adobe Connect 导入测验分数 {#quiz-adobe-connect}

将Connect测验数据导入Learning Manager并将其与现有报告工作流程集成，以便Learning Manager用户从报告内的Adobe Connect会话中获取测验数据、用户回答和分数情况，其方法类似于从具有测验功能的自学模块获取数据。

在 Connect 部分中，如果任何学习者参与了测验课程或开展了支持测验报告的任何交互，则除“完成”以外，系统还会追踪学习者的所有交互情况。 此课程必须为 Connect VC 培训。

以下为这一过程的工作流程概要。

**Adobe Connect - 主持人**

* Connect 中的主持人负责创建课程并上传包含测验的交互式内容。
* 主持人创建&#x200B;**“虚拟教室”**&#x200B;培训并保存 VC 培训。 主持人可以将上述所建课程链接至 VC，或者在会话期间使用 Connect 应用程序的&#x200B;**“共享课程”**&#x200B;选项来共享课程。

**Learning Manager — 作者**

* 作者在Learning Manager中创建模块类型为&#x200B;**虚拟教室**&#x200B;的课程。
* 从&#x200B;**“会议系统”**&#x200B;下拉列表中将 Connect 选为 VC 提供方。
* 选择“长期会议”课程，然后选择主持人在 Connect 中所创建的 VC 教室。 选择讲师。 保存并发布课程。

**Learning Manager — 学习者**

* 课程发布后，学习者便可加入课程。
* 获取 Connect 主持人授予的访问权限后，学习者便可重定向至 Connect VC 会话。

**Adobe Connect - 主持人**

* 在 VC 会话中，Connect 主持人会共享之前所共享的测验。

**Adobe Connect - 学习者**

* 学习者将接受测验，并在完成后关闭会话。

**Learning Manager — 学习者**

* 学习者将关闭会话，且系统会自动同步会话。

**Learning Manager — 管理员**

* 会话过期后，系统会在计划时段结束后触发导入测验的工作流程。
* 等待系统触发计划内容并完成处理流程。 如需从集成管理员端查看处理状态，您可以在 Adobe Connect 连接器中查看&#x200B;**“执行状态”**，从而了解进度。 执行成功后，状态将更改为&#x200B;**已完成**。

* 管理员随后选择之前创建的Learning Manager课程。 管理员可查看以下内容：

   * **考勤和评分** - 显示最终测验分数和考勤状态。
   * **L2 测验分数**

      * **按用户** — 以&#x200B;**分**&#x200B;和&#x200B;**百分比**&#x200B;显示最终测验分数。
      * **问题得分情况** - 以报告图表的形式展现测验信息。

## Marketo Engage 连接器 {#marketo}

Learning Manager可与营销自动化软件Marketo Engage集成，帮助开展营销活动。

在将新Marketo Engage添加到Learning Manager帐户后，便可通过Marketo Engage连接器为Learning Manager数据库添加（或更新）潜在客户。 其还会将Learning Manager中用户的学习行为（课程注册、课程完成、技能分配和技能成就）与Marketo Engage中相应的潜在客户相关联，并将之作为自定义对象。 营销人员可使用此类信息，根据在Learning Manager中捕获的用户学习行为以及Marketo Engage功能（如“智能列表”）来定位受众。

作为集成管理员，您可以将 Adobe Learning Manager 与 Marketo Engage 实例集成，以自动执行数据同步。您可以导出内部用户、培训注册人数以及技能完成事件。 您可以按计划执行上述操作，并可按需配置上述内容。

如需将Learning Manager与您的Marketo帐户集成，您的Marketo帐户需要能够通过API创建架构。

您可以从 Marketo 应用程序下载以下 3 份报告：

* 用户报告
* 学习成绩单
* 用户技能报告

创建Marketo Engage连接时，必须提供以下详细信息：

* 连接名称
* 客户端 ID
* 客户端密钥
* Marketo Engage域

![](assets/marketo-creds.png)

*输入Marketo的凭据*

>[!NOTE]
>
>您可以从 Marketo Engage 应用程序中获取客户端 ID 和密钥。在Marketo应用程序上，您可以从&#x200B;**LaunchPoint**&#x200B;部分获取客户端ID和密钥，并可从&#x200B;**WebServices**&#x200B;部分获取Marketo域。

在Learning Manager应用程序的Marketo Engage连接的&#x200B;**统一报告**&#x200B;部分，您可以根据以下内容创建营销活动：

* 新用户已添加到Learning Manager
* 新用户已注册一门课程
* 新用户已完成一门课程
* 学习者已开始学习一种技能
* 学习者已掌握一种技能

与任何其他连接器一样，您可以在本连接器中按需整理并导出数据。

### Marketo Engage中的列映射 {#column-mapping-in-marketo-engage}

Marketo 中的数据库分为两种：

* 潜在客户数据库
* 自定义对象数据库

列映射可用于创建潜在客户数据库。 潜在客户即您从“用户报告”中导出的用户。

“用户报告”中的字段皆列于 Adobe Learning Manager 列下方。Marketo 列下的字段皆由 Marketo 提供。 您可以使用这两列将Learning Manager中的任何字段映射到Marketo中的字段。 您可以从Marketo的Learning Manager列加入相关列。 加入列后，您便可开始创建潜在客户数据库。

然后，您可以在 Marketo 中查看导出的所有用户。

在 Marketo 应用程序的&#x200B;**“Marketo 自定义对象”**&#x200B;部分中，所有三份报告（“学习者成绩单”、“用户技能”以及“用户报告”）皆列于此。 每份报告的名称前都预设了字符串&#x200B;**“cp_”**。 我们会将每位导出至 Marketo 的新用户视作潜在客户。

### 事件

将Learning Manager事件中的数据导出至Marketo Engage实例。 选择要按需或按计划导出到 Marketo Engage 数据库的事件。

* 新用户添加
* 更新用户元数据
* 更新用户活动
* 培训注册
* 自助注册
* 技能完成

<!--## BlueJeans Events {#bj-events}

BlueJeans Events connector connects Learning Manager and BlueJeans systems to automate data synchronization. Using this connector, you can:

* **Set up virtual sessions using BlueJeans Events:** Configure a new event in BlueJeans and setup a VC session in Learning Manager by selecting the appropriate BlueJeans event. Date and time details are picked automatically from the BlueJeans events.
* **Automated User Completion Syncing:** An Automated user completion syncing process allows the Learning Manager Administrator to fetch completion records for BlueJeans events automatically.

This new connector requires a separate set of credentials to configure the connector. The credentials of the existing BlueJeans Meetings connector will not work for BlueJeans Events connector.

![](assets/bj-event-connector.png) 
*Credentials for BlueJeans Event Connector*

### Workflow {#workflow}

1. The BlueJeans Event moderator creates an event from within BlueJeans.
1. The author creates BlueJeans event course using the BlueJeans event url, which is created in future dates.
1. Since BlueJeans events have a similar title for multiple events, the author must append the event attendee url to the room name, so that he/she can choose the appropriate event.

   The format to enter event url: ***event name--event attendee url***

   For Dynamic rooms, the behavior is similar to that of Adobe Connect.

   ![](assets/bj-eventname.png)
   *BlueJeans Events configuration*

1. Once the author enters the BlueJeans event url, the date and time will be auto populated.
1. Add an instructor to the event. The instructor will now have elevated privileges as a Presenter in a BlueJeans event.

Administrators, managers, and learners can enroll learners to the created course. Upon enrollment, the learner receives an email. The learner can sign in to their Learning Manager account to view the program details and take the course.

When the course is complete, the completion report gets triggered after a scheduled duration. The administrator can see the completion report to check the attendance and score of the learners.

If the BlueJeans Event moderator enables the recording during the session, after session ends, the recording is available in the learner app.

![](assets/bluejeans-event-configure.png)
*BlueJeans Events configuration*

When you enable the check-box **Fetch Events created by the other users**, you can then add the list of BlueJeans event creators in the **Additional Event Creators** field. In the Author app, only events created by these users are searchable via the type-ahead field.

If the **Additional Event Creators** field is left blank, all events created in BlueJeans will be available for searching in the Author App.

The Author, in the Author app, then selects an event from the list of available events. In addition, the Author can add instructors to the event. These instructors in Learning Manager would become the presenters within BlueJeans events.

>[!NOTE]
>
>All users must belong to the same enterprise in BlueJeans Events App.

>[!NOTE]
>
>We've added a caching mechanism that improves the overall user experience. It is applicable when you select additional event creators. In this mode, the events are fetched the first time when an author searches for an event. The cache persists for 30 mins so that authors know how long they must wait to fetch the new events.-->

## Microsoft Teams 连接器 {#microsoft-teams-connector}

Microsoft® Teams® 是基于持续聊天的协作平台，可支持文档共享、在线会议和其他业务沟通功能。

Adobe Learning Manager 使用虚拟教室连接器与 Microsoft Teams 会议集成。

Microsoft Teams 连接器可连接 Adobe Learning Manager 和 Microsoft Teams 系统，实现数据自动同步。Microsoft Teams 连接器的功能如下所示：

**使用Microsoft Teams设置虚拟会话**

此连接器有助于将 Adob&#x200B;&#x200B;e Adobe Learning Manager 帐户与 Microsoft Teams 帐户集成。集成后，借助此连接器，Adobe Learning Manager 中的作者在创建虚拟教室模块时，可使用 Microsoft Teams 作为技术服务提供商。

**允许Microsoft Teams在学习者进入虚拟教室时对其进行身份验证**

会议组织者可允许会议大厅限制用户进入会议，并可控制由 Microsoft Teams 提供的其他会议选项。

**使用自动用户完成同步**

通过用户完成情况自动同步流程，Adobe Learning Manager 管理员可自动获取 Teams 会议的完成记录和录制 URL。

有关详细信息，请参阅&#x200B;[**在Adobe Learning Manager中安装Microsoft Teams连接器**](install-microsoft-teams-connector.md)。

## 培训数据访问连接器 {#training-data-access}

>[!IMPORTANT]
>
>仅当Adobe Learning Manager作为Adobe Experience Manager的插件出售时，此特定功能才可用。 课程数据将在24小时后失效。

>[!NOTE]
>
>本节重点介绍基础架构的工作原理，但如果您需要构建无头或基于AEM的非登录体验，请联系我们。 我们将根据您的用例建议正确的方法。 此功能目前无法作为自助服务使用。

使用&#x200B;**[!UICONTROL 培训数据访问]**&#x200B;连接器可以创建无头体验。 此体验可以是独立的，也可以是基于AEM Sites的自定义用户界面。 它可以帮助检索并向学习者显示培训信息，同时允许搜索和过滤。 启用数据连接器后，将有一组公共API可用于构建界面，其中课程/学习路径信息将面向学习者显示。

### 配置连接器 {#configure-training-data-connector}

使用&#x200B;**[!UICONTROL 培训数据访问]**&#x200B;连接器将您的Adobe Learning Manager帐户与数据存储和搜索系统集成。 这有助于基于AEM Sites的界面获取培训数据、显示网页并为学习者提供更好的搜索选项。

使用API将培训元数据从Adobe Learning Manager导出到数据检索和搜索支持服务。 您还可以创建计划来自动执行这些导出操作。

要配置培训数据访问连接器，请执行以下步骤：

1. 在集成管理员应用中，选择&#x200B;**[!UICONTROL 培训数据访问]** > **[!UICONTROL 入门]**。
1. 在&#x200B;**[!UICONTROL 入门]**&#x200B;页面中选择&#x200B;**[!UICONTROL 下一步]**。
1. 键入连接名称和列入允许列表的域。

   ![](assets/connection-name-and-domain-name.png)
键入连接名称和域名

1. 从以下选项中选择&#x200B;**[!UICONTROL 接口类型]**：

   * **[!UICONTROL Native Learning Manager]**：这是标准产品，仅适用于原生界面。
***[!UICONTROL 无头界面]**：这是公开API以构建未登录体验的高级产品。

   ![](assets/types-of-interface.png)
接口类型

1. 选择&#x200B;**[!UICONTROL 连接]**。 基本URL和CDN URL将自动生成。
您可以使用这些URL通过API检索数据。

   >[!NOTE]
   >
   >使用高级产品的客户将获得与使用标准产品的客户不同的URL。


1. 在连接器页面上选择&#x200B;**[!UICONTROL 导出培训元数据]**。
1. 选择&#x200B;**[!UICONTROL 使用此连接启用培训元数据导出]**&#x200B;以导出培训数据。
1. 在您启用连接后，所有课程、学习路径和证书的图像都将迁移至CDN。
1. 将课程、学习路径和证书的元数据导出到搜索和检索服务中。
1. 您可以通过选择启用计划选项来计划元数据导出。 对于高级计划，计划每3小时自动执行一次。
1. 对于按需报告，请转到&#x200B;**[!UICONTROL 按需]**，选择&#x200B;**[!UICONTROL 开始日期]**，然后&#x200B;**[!UICONTROL 单击]**执行。
您可以在**[!UICONTROL 执行状态]**&#x200B;页面上检查报表执行状态。

### 在 AEM 中创建网站 {#create-website-in-aem}

**先决条件：**&#x200B;从&#x200B;[**GitHub存储库**](https://github.com/adobe/adobe-learning-manager-reference-site/releases/tag/1.0.0)安装AEM包。

1. 使用基础和检索 URL、客户端 ID、客户端密钥和管理员刷新令牌，并在 AEM 中创建配置。
1. 使用 AEM 组件创建网站。
1. 发布网站。

有关详细信息，请参阅此&#x200B;[**文档**](../../adobe-learning-manager-integration-aem.md)。

### 学习者 {#learners}

已发布的网站会显示从面向未登录学习者的搜索服务中检索到的所有迁移课程、证书和学习路径的列表。

学习者单击“课程”、“证书”或“学习路径”后，“概述”页面即会启动。 在该页面上，学习者注册后，必须先登录才能参加课程。

### 未登录体验 {#non-logged-in-experience}

利用未登录体验，您可以为未登录用户创建实时体验。 例如，未登录体验可充当营销活动的登陆页面，以鼓励注册。

Adobe Learning Manager中的未登录体验可使用&#x200B;**[!UICONTROL 培训数据访问]**&#x200B;连接器进行配置。 连接器提供以下产品：

* 标准产品
* 高级产品

**标准产品**

标准产品是构建Adobe Learning Manager的本机版本。 用户可以构建仅演示、未登录的无头体验。 演示无头体验不可扩展，不应在生产环境中使用。

**高级产品**

高级产品可帮助用户构建由&#x200B;**[!UICONTROL 培训数据访问]**&#x200B;连接器配置的无头界面。 如此一来，用户可以实时获取课程和学习路径的相关数据，如姓名、描述、作者、技能、持续时间等。 对于混合式学习情景，您还可以获得实时名额限制、已占用名额、轮候表限制和轮候表数量。 客户可以使用这些API创建搜索和筛选功能，并为未登录学习者创建完整的课程摘要。

客户可以购买高级计划来构建这种高度可扩展的非登录体验。

>[!NOTE]
>
>请联系支持团队或CSM以购买高级计划。

用户购买计划后，CSM团队将为他们激活高级计划。 使用培训数据访问连接器，用户可以使用前面提到的功能设置未登录体验。

## Adobe Commerce 连接器 {#adobe-commerce-connector}

>[!NOTE]
>
>仅当Adobe Learning Manager作为Adobe Experience Manager的附加项出售时，此特定功能才可用。

>[!NOTE]
>
>还可为试用帐户启用此连接器。

Adobe Learning Manager 现提供与 Adobe Commerce 的集成，B2B 和 B2C 客户可以通过该平台打造电子商务体验。

Adobe Commerce 是一款可扩展且可扩容的商务支持解决方案，可让您在单个平台上为 B2B 和 B2C 客户打造多渠道商务体验。 使用 Adobe Commerce 连接器将您的 Adobe Learning Manager 帐户与 Adobe Commerce 连接，并在学习平台上实现电子商务功能。

启用此连接器并利用 Adobe Commerce 功能将学习方案作为付费培训提供。注意，您需要先单独购买 Adobe Commerce，然后才能使用此连接器将其与 Adobe Learning Manager 集成。

连接器将培训数据发送到 Commerce 平台，以便与 Adobe Commerce 集成，然后学习者就可以在该平台上付款并购买培训。

除了发起购买之外，连接器还从 Adobe Commerce 收集购买详细信息，Adobe Learning Manager 会使用此信息来验证购买并解锁培训访问权限。

**先决条件**

1. 启用[RabbitMq](https://devdocs.magento.com/cloud/project/services-rabbit.html)或任何其他消息代理。
1. 启用[CRON](https://devdocs.magento.com/cloud/env/variables-deploy.html#cron_consumers_runner)。
1. 为实行步骤 1 和步骤 2，请编辑以下文件：

   1. .magento.app.yaml
   1. .magento/services.yaml
   1. .magento.env.yaml

1. 通过自定义模块覆盖选项限制。 此为可选步骤，但强烈建议在处理大型数据集时使用此步骤。
1. 启用页面上的所有异步 API。 由于可能有大量数据，因此导出操作是异步进行的。 来自Adobe Commerce的API被调用，同时请求负载也已发送。 请求会将消息推送到队列，且此队列中有一个使用者，该使用者会处理这些消息并在Commerce端创建产品。 默认情况下，Adobe Commerce 不提供这种异步处理。 因此必须启用此选项。
1. 在付款成功页面上添加用于返回到 ALM 的链接。 必须在 Adobe Commerce 中配置此返回 URL。 用于链接的URL。- `https://learningmanager.adobe.com/app/learner#/postPayment`
1. 将索引从“正在保存”更改为“已计划”。  有关详细信息，请参阅此[KB](https://support.magento.com/hc/en-us/articles/360040227191)。
1. 应用以下修补程序。 有关详细信息，请参阅[应用修补程序](https://devdocs.magento.com/cloud/project/project-patch.html)。
1. 快速配置。  云基础架构上的Adobe Commerce需要快速配置，并在预发布环境和生产环境中使用。 有关更多信息，请参阅[快速设置](https://devdocs.magento.com/cloud/cdn/configure-fastly.html)。

### 配置连接器 {#configure-connector}

以集成管理员的身份，在 Adobe Commerce 连接器中单击&#x200B;**[!UICONTROL “连接”]**。

在配置页面中，输入以下详细信息。可在 Adobe Commerce 中获取这些详细信息（授权密钥）。在Adobe Commerce中创建集成后，可在此处获得凭据。

![](assets/adobe-commerce-configuration.png)
*配置Adobe Commerce连接器*

启用 Adobe Commerce 连接器连接后，作者可以设置课程、学习路径或证书的价格。

发布课程、学习路径或证书后，学习者可以在学习者应用程序中购买课程。

* **本机 Adobe Learning Manager：**&#x200B;学习者可以在 Adobe Learning Manager 内购买课程、学习计划或证书。 仅适用于作者已添加价格的情况。
* **使用 AEM 站点进行自定义：**&#x200B;学习者可以从 AEM 站点购买课程。

### 工作流 {#workflow}

Adobe Commerce 管理员将 Adobe Learning Manager 配置为集成。

作者将课程、学习路径或证书标记为高级并指定价格。 为帐户启用了电子商务时，才会出现此选项。 有关更多信息，请参阅[创建课程](../../authors/feature-summary/courses.md)。

在 Adobe Commerce 中同步数据后，才能购买课程或学习路径。

### 将课程导出到 Adobe Commerce {#export-commerce}

作者为各种课程、学习路径或认证设置价格后，您可以用集成管理员的身份，将课程、学习路径或认证导出到 Adobe Commerce。

>[!NOTE]
>
>在2024年3月版Adobe Learning Manager中，我们引入了对[Adobe Commerce 2.4.6](https://experienceleague.adobe.com/docs/commerce-operations/release/notes/adobe-commerce/2-4-6.html?lang=en)的支持。


1. 单击&#x200B;**[!UICONTROL 导出培训元数据]** > **[!UICONTROL 按需]**。

1. 选择日期。

1. 单击&#x200B;**[!UICONTROL “执行”]**。 执行成功后，所有定价的课程或学习路径都将移至 Adobe Commerce。 然后，学习者可以从Learning Manager购买课程。

### 原生学习管理器和Adobe Commerce {#learning-manager-with-commerce}

#### 学习者无法注册此类课程。 {#learner}

作为学习者，您必须登录才能购买课程、证书或学习路径。

要购买课程，请单击“立即购买”。 您将重新转至 Adobe Commerce 以完成购买。 支付成功后，您会看到一条消息，提示您返回Learning Manager并开始课程。 您还必须单独登录Adobe Commerce以完成购买。

从 ALM 本机版或 AEM 购买课程、证书或学习路径时，您会收到 ALM 以及 Adobe Commerce 发送的电子邮件。

此外，您还可以启用/禁用Adobe Commerce中的电子邮件。

### 带有Adobe Commerce的AEM站点 {#aem-sites-with-adobe-commerce}

启用“使用 AEM 站点自定义”选项后，学习者可以从自定义 AEM 站点购买课程。

AEM 站点将包含 Adobe Learning Manager 中的所有元数据，用于启用 Adobe Commerce 进行搜索。 在未登录的情况下，可在 Adobe Commerce 上获取课程。

可以同时提供登录体验和非登录体验。 未登录的用户可以搜索和浏览课程目录、学习计划和证书。 但是，如果您想购买课程，则必须登录到 AEM 站点。

与本机 Adobe Learning Manager 一样，登录后，您可以将课程添加到购物车中，然后预览或购买课程。

### 设置 Adobe Commerce 连接器 {#setup-commerce-connector}

#### 先决条件 {#pre-requisites}

管理员必须在管理应用程序的&#x200B;**“设置”>“常规”**&#x200B;中，选中&#x200B;**“为培训启用定价”**&#x200B;的复选框。 如果启用此选项，作者可以指定培训的价格。 当您添加 Adobe Commerce 连接时，将自动选中并执行此复选框。

Adobe Learning Manager 支持电子商务买卖培训。 在此处，用户可以通过销售培训来推广其产品的向上销售和交叉销售。

通过集成 Adobe Commerce，Adobe Learning Manager 可以支持购买和销售培训，以便在客户合作伙伴教育情景中提供更完整的客户体验。

此集成的主要目标如下：

* 用户可以通过在Adobe Learning Manager或无头学习界面上销售课程来创造收入。
* 启用与平台的Adobe Commerce集成，以使用Learning Manager的本机应用程序和AEM销售课程。
* 允许Learning Manager的客户以付费课程的形式提供正式学习。
* 学习者可以在决定购买培训之前预览课程。

#### Adobe Learning Manager 本机版 {#native-learning-manager}

**集成管理员**

1. 在“集成管理员”页面上，添加 Adobe Commerce 连接器。 从通过 Adobe Commerce 创建的应用程序中获取身份验证。
1. 启用 Adobe Commerce 后，即在 Adobe Learning Manager 中启用电子商务。 从 Adobe Learning Manager 到 Adobe Commerce 的数据将按照计划进行同步。数据包括所有培训（付费培训）以及元数据（用户、技能、作者姓名、价格等）。

>[!NOTE]
>
>AdobeLearning Manager和Adobe Commerce的登录方式不同。

### AEM {#aem}

在此模式下，学习者将课程从基于 AEM 的站点中移除，该站点是使用基于 AEM 的模板和组件构建的。

在AEM站点上，学习者可以使用购物车、添加到购物车按钮、从购物车中删除课程等。

如果用户未登录，他们仍然可以搜索课程目录以及查看课程详细信息，但不能购买课程。 作为学习者，您必须登录才能购买课程。

学习者购买课程后，将被重定向到注册状态的课程概述页面，在该页面中，他们可以参加已购买的培训。

#### 无头 - 未登录 {#headless-non-logged-in}

学习者可以：

* 在搜索栏中搜索任何培训。
* 按价格范围筛选所有培训。

学习者不能：

* 从“概述”页面购买课程。
* 预览付费内容。

#### 无头 - 登录 {#headless-logged-in}

学习者可以：

* 浏览、查看、搜索和筛选付费或免费培训课程。

* 将课程添加到购物车中，然后结帐购买。
* 在购物车中添加、更新或删除培训课程。
* 同时购买多个培训课程。
* 在播放器中预览付费课程。
* 查看付款出错的消息。

* 购买课程后，可在电子邮件中查看以附件形式发送的发票。

#### 按需同步 {#on-demand-sync}

系统每天会执行两次 Learning Manager 与 Adobe Commerce 之间的同步。 管理员为电子商务启用帐户后，若启用&#x200B;**“使用此连接启用培训元数据导出”**&#x200B;选项，系统将在公共CDN中存储课程、学习路径和证书的图像。

如果数据保持不同步，则系统不会为学习者显示定价信息。

对于本机Learning Manager，如果启用了电子商务并完成了Learning Manager与Adobe Commerce之间的同步，则学习者可以查看或搜索免费或付费培训。

对于AEM，没有“立即购买”选项，只有&#x200B;**添加到购物车**&#x200B;按钮。 如果未执行同步，此按钮也将保持禁用状态。

#### 常见问题解答 {#faqs}

+++哪些课程无法购买？

学习者无法购买重复认证、内容市场培训、已获取的培训、连接器培训、工作辅助和经理批准/指定的课程等课程。
+++

+++“学习者成绩单”和“培训报告”是否有任何更改？

这些报告会显示帐户中所有已购买培训的价格和购买日期。
+++

+++学习者是否可以注册免费培训？

是的，学习者可以注册免费培训。 免费培训在“培训概述”页面上显示“预览并注册”按钮。
+++
