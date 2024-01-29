---
description: 了解如何在Learning Manager中集成各种连接器
jcr-language: en_us
title: Learning Manager连接器
contentowner: jayakarr
source-git-commit: ab6737e8b43222a6538921b0628a504a5f15859d
workflow-type: tm+mt
source-wordcount: '15880'
ht-degree: 0%

---



# Learning Manager连接器

企业有其他应用程序和系统必须与Learning Manager集成。 连接器是一种实用程序，可帮助执行基于数据的集成，例如从外部系统将数据导入Learning Manager。  也能够将数据从Learning Manager导出到外部系统。

Learning Manager提供Salesforce和FTP连接器。 借助Salesforce连接器，公司的集成管理员可以将其Salesforce应用程序与Learning Manager集成。 作为集成商，您还可以使用FTP连接器将一组用户自动导入到企业应用程序中。

Learning Manager还提供Lynda、getAbstract和Harvard Management System连接器。 学习者可通过这些连接器访问和学习Lynda.com、getAbstract和Harvard ManageMentor中的课程。

继续阅读以了解如何在Learning Manager中配置和使用各连接器。

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
>在2022年11月版AdobeLearning Manager中，Zoom已弃用 [2023年6月之前进行JWT身份验证](https://marketplace.zoom.us/docs/guides/auth/jwt/). 因此，带JWT的Zoom连接器将继续运行至上述日期，但我们建议用户创建服务器到服务器OAuth应用程序，以替换帐户中的功能。 默认情况下，任何新连接都将拥有Zoom OAuth身份验证。

## Salesforce连接器 {#sfconnector}

Salesforce连接器可连接Learning Manager和Salesforce帐户，从而自动同步数据。 Salesforce连接器的功能包括：

### 映射属性

集成管理员可以选择Salesforce列并将其映射到相应的Learning Manager组属性。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

### 自动导入用户

用户导入操作能让Learning Manager管理员从Salesforce获取员工详细信息，并自动将其导入Learning Manager。 这一自动化操作在创建并将CSV上传到Learning Manager的过程中能避免手动工作。

### 自动计划

结合使用自动计划功能以及自动用户导入功能可提高工作效率。 Learning Manager管理员可根据公司的需求设置计划。 Learning Manager应用程序中的用户可以根据计划获得最新消息。 可在Learning Manager应用程序中每天执行同步。

### 过滤用户

Learning Manager管理员可在导入用户前先对其过滤。 例如，Learning Manager管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

### 配置Salesforce连接器 {#configuresalesforceconnector}

如要将Salesforce与Learning Manager集成，请学习相应操作过程

#### 先决条件 {#prerequisites}

确保您拥有Salesforce公司的URL。 例如，如果您的公司名称是 **myorg**，Salesforce URL可以是 `https://myorg.salesforce.com`. 这是将Salesforce帐户与Learning Manager连接所需的唯一输入。

此外，请确保您拥有相应的凭据以登录到帐户。

#### 创建连接 {#createaconnection}

1. 在Learning Manager主页，将鼠标悬停在Salesforce信息卡/缩略图上方。 此时会显示一个菜单。 点击 **[!UICONTROL Connect]** 菜单中的项。

   ![](assets/mouserover-salesforce.png)

   *连接选项*

1. 此时会显示一个对话框，提示您输入组织URL。 点击 **[!UICONTROL Connect]** 在提供URL后。
1. 连接成功后，将显示“概述”页面。

### 映射属性 {#mapattributes}

成功建立连接后，您可以将Salesforce列映射到Learning Manager的相应属性。 此步骤为必须操作。

1. 在映射页面中，您可以在左侧看见Learning Manager的列，在右侧看见Salesforce的列。 选择映射到Learning Manager列名称的相应列名称。

   ![](assets/sfdc-map-columns.png)
   *映射属性*

   >[!NOTE]
   >
   >左侧显示的Learning Manager列数据是从活动字段中获取的。 该 **管理者** 字段必须映射到电子邮件地址类型的字段。 在可以使用连接器之前，必须映射所有列。

1. 点击 **[!UICONTROL 保存]** 完成映射后。
1. 连接器现在可以使用了。 已配置并显示为管理员应用程序内的数据源的帐户。 管理员可以安排导入或用于按需同步。

## 使用Salesforce连接器 {#usingsalesforceconnector}

Salesforce连接器会连接到Salesforce.com来获取已配置用户，并将其添加到Learning Manager。

### 从Salesforce联系人导入用户 {#import-salesforce-contacts}

Learning Manager增强了Salesforce连接器，可获取联系人和Salesforce用户，并自动将他们导入Learning Manager。

在Salesforce连接器页面上，输入Salesforce URL并完成身份验证。 通过身份验证后，您可以继续导入用户或联系人。 如果选择“联系人”选项，请指定要导入的联系人子集。

选择Salesforce列并将其映射到相应的Learning Manager组属性。 映射完成后，相同映射就能用在随后的用户导入中。

1. 登录到Salesforce。
1. 在连接页面上，单击 **[!UICONTROL 导入内部用户]**.

   ![](assets/image048.png)
   *导入内部用户*

1. 在 **导入用户** 页面，有一个新选项，联系人。 单击单选按钮 **联系人** 您会看到以下选项。

   ![](assets/image050.png)
   *映射联系人属性*

1. 如果您单击 **[!UICONTROL 是]**，您可以执行以下操作：

   * **选择“联系人”列：** 选择要导入Learning Manager的字段。
   * **指定值：** 选择表示所选字段的值。

   ![](assets/image053.png)
   *指定值*

   * 将Salesforce列与Learning Manager列进行映射。
   * 要开始导入，请单击 **[!UICONTROL 保存]**.

1. 如果您单击 **[!UICONTROL 不行。 导入所有联系人]**，您可以直接映射字段，无需筛选联系人。 此时，您将从Salesforce导入所有联系人。
1. 要开始导入，请单击 **[!UICONTROL 保存]**.

## 导出学习记录

Learning Manager支持将学习记录（如成绩单、用户报告、技能报告）导出到Salesforce。 您可以确定是否应将导出的数据与Salesforce中的“用户”表或“联系人”表进行关联。

![](assets/export-events-new.png)
*导出学习记录*

### Salesforce中的自定义对象

在从Learning Manager中导出学习记录之前，您必须在Salesforce中创建自定义对象。 自定义对象是您为存储特定于您的公司或行业的信息而创建的对象。 有关详细信息，请参阅 [Salesforce自定义对象](https://trailhead.salesforce.com/en/content/learn/modules/data_modeling/objects_intro).

创建对象的方法如下：

1. 下载并安装包以创建自定义对象。

   * [程序包1](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WPJ)
   * [程序包2](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WPT)
   * [程序包3](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WPi)

1. 在Salesforce中重命名自定义对象的名称。
1. 选择事件并单击 **[!UICONTROL 保存]**.

**将活动与下列对象链接：** 选择要导出的部分（“用户”或“联系人”）。 如果您选择“联系人”对象，则Learning Manager中存在、但不在Salesforce中的用户将在Salesforce中创建。

![](assets/link-events.png)
*链接事件选项*

>[!NOTE]
>
>您可以在一个帐户中创建多个连接。 在Salesforce中，单个连接最多可提供三个自定义对象。 如果要为同一Salesforce帐户创建多个连接，则必须安装三个程序包。 我们最多提供三个程序包支持。
>
>要创建的连接数量必须与所安装的程序包数量一致。

>[!NOTE]
>
>在Salesforce的“执行状态”页面上，只能通过Salesforce检查已处理的记录数。 Learning Manager会将状态显示为“已完成”，即使对所有已处理的记录的导出操作为部分导出或失败也是如此。

## 安装Salesforce包

Learning Manager提供Salesforce应用程序包。 在SFDC中安装和配置程序包后，销售员工便可以在SFDC门户中开展培训活动。 SFDC用户可利用此应用直接在SFDC门户中探索新培训、查看推荐内容及参加培训。 用户还可以直接在SFDC门户的应用中以刊头的形式收到管理员发送的公告。

### 在Learning Manager应用程序中设置

1. 以集成管理员身份登录Learning Manager管理员帐户。
1. 点击 **[!UICONTROL 应用程序]** > **[!UICONTROL 特色应用程序]**.
1. 点击 **[!UICONTROL Salesforce]**.
1. 在Salesforce应用程序页面上，请注意描述中提到的应用程序ID（也称为客户端ID）和客户端密钥。
1. 点击 **[!UICONTROL 批准]** 并且必须成功批准您的应用程序。
1. 点击 **[!UICONTROL 开发人员资源]** > **[!UICONTROL 用于测试和开发的访问令牌]**.
1. 在“获取OAuth代码”部分中，“客户端ID”和作用域必须设置为“admin：read，admin：write”。 点击 **[!UICONTROL 提交]**.
1. 在“获取刷新令牌”中，输入客户端ID和客户端密钥。 点击 **[!UICONTROL 提交]** 并记下刷新令牌。

### 在Salesforce应用中创建帐户

1. 在Salesforce注册页面上创建一个帐户。 您必须在开发人员版或企业版中创建Salesforce帐户。  [开发人员注册URL](https://developer.salesforce.com/signup). 确保必须使用在Learning Manager中使用的电子邮件ID注册Salesforce。
1. 通过验证电子邮件验证您的帐户。
1. 创建密码并登录Salesforce。
1. 登录后记下Salesforce URL(例如site.lightning.force.com)

### 安装Learning Manager程序包

如果要安装程序包，必须首先删除Salesforce中现有的程序包。 卸载之前，必须启用以下设置。 必须应用这些设置，否则无法安装程序包。

>[!NOTE]
>
>仅在Salesforce Lightning视图中支持AdobeLearning Manager应用程序。

1. 启动 [Learning Manager程序包URL](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WOQ).
1. 在 **登录** 页面，单击 **[!UICONTROL 使用自定义域]**.
1. 输入程序包URL，然后单击 **[!UICONTROL 继续]**. 必须在安装页面选中“仅限管理员安装”选项。 请勿更改此选项。
1. 点击 **[!UICONTROL 安装]**. 安装程序包后，单击 **[!UICONTROL 完成]**. 系统将转至“已安装程序包”页面，您可以看到AdobeLearning Manager中已安装的程序包。
1. 转到App Launcher（位于“设置”旁），然后搜索AdobeLearning Manager。
1. 要配置应用程序，请单击 **[!UICONTROL 配置]**.
1. 点击 **[!UICONTROL 新]** 并添加以下详细信息：

   * **配置：** 输入您选择的名称。
   * **客户端ID**：输入从第一部分获取的值。
   * **客户端密码：** 输入从第一部分获取的值。
   * **刷新令牌：** 输入从第一部分获取的值。
   * **学习管理器基本网址：** Learning Manager托管站点的URL。

### 添加远程站点设置

1. 在页面右上角，单击 **[!UICONTROL 设置]**.
1. 向内 **[!UICONTROL 快速查找]**，搜索远程站点设置。
1. 点击 **[!UICONTROL 新建远程站点]**.
1. 输入详细信息：

   * **远程站点名称：** 输入您选择的名称。
   * **远程站点URL：** Learning Manager托管站点的URL。

1. 启动Learning Manager

### 启用Learning Manager应用程序通知

1. 在右上角，单击 **[!UICONTROL 设置]**.
1. 搜索自定义通知。
1. 点击 **[!UICONTROL 新]**.
1. 输入以下详细信息：

   1. **自定义通知名称：** LearningManagerNotification
   1. **API名称：** LearningManagerNotification

1. 选择两者 **桌面** 和 **移动版** 作为支持的渠道。

1. 点击 **[!UICONTROL 保存]**.
1. 要为移动设备启用推送通知，请执行以下步骤：

   1. 在手机中安装Salesforce移动应用程序。
   1. 使用您的凭据登录应用。
   1. 转到“ ” **设置** > **通知传递设置**.
   1. 添加适用于iOS和Android的Salesforce。

### 从Salesforce中卸载Learning Manager

1. 在Salesforce应用中，转到已安装的包。
1. 点击 **[!UICONTROL 卸载]**.

## 为Salesforce用户配置Learning Manager

任何Salesforce帐户中的用户也可使用Learning Manager应用程序。 Salesforce管理员可以根据配置文件添加用户。 Salesforce配置文件与Learning Manager中的配置文件类似。 例如，管理员、集成管理员、讲师等。 Salesforce管理员还可以创建自定义配置文件。

作为Salesforce管理员，您可以将配置文件分配给用户或创建自定义配置文件。

![](assets/create-profile.png)

安装程序包时，您可以为学习者分配Salesforce配置文件。

安装包后，必须配置配置文件。

点击 **[!UICONTROL 配置]** > **[!UICONTROL 新]**，然后添加以下内容：

* 配置名称
* 客户端ID
* 客户端密码
* LearningManagerBaseURL
* 禁用重定向

>[!NOTE]
>
>若要让学习者查看Learning Manager应用程序，您必须为所有学习者启用该应用程序。

下一步是提供访问Learning Manager应用程序的权限。

![](assets/permission-set.png)

*设置访问Learning Manager应用程序的权限*

选择用户并分配相应的权限。 学习者现在可以访问Learning Manager应用程序。

现在，选择一个配置文件，例如，用户的“标准配置文件”，然后单击该配置文件。 点击 **[!UICONTROL 编辑]** 在 **自定义应用程序设置** 部分，启用该复选框 **AdobeLearning Manager**. 这样用户就可以访问该应用程序。

在 **自定义选项卡设置** 部分，在 **学习者主页** 从下拉列表中，选择选项 **默认打开**.

您必须使应用程序对所有配置文件可见。

点击 **[!UICONTROL 保存]** 并且属于所有配置文件的学习者可以访问Learning Manager应用程序。

### 学习路径相关更改

#### 现有连接

如果在管理员帐户中禁用了“学习路径”选项，则不会在报告中添加行和列。

如果在管理员帐户中启用了“学习路径”选项，则“类型”列将用“学习路径”进行填充，以防学习者注册。

>[!NOTE]
>
>如果启用了该标志，并且使用了现有连接，则部分记录可能会丢失。

#### 新连接

如果在管理员帐户中禁用了“学习路径”选项，则培训报告将包含以下列，但不会包含任何数据。

* **嵌入式路径：** 显示学习计划的名称
* **嵌入式路径ID：** 显示学习计划的ID。
* **嵌入式课程ID：** 显示学习路径内的课程ID。

此外，对于帐户中启用了学习路径的新连接，将显示三个新列，并且所有数据都将流动。

此外，该报告将包含类型“学习路径（较高级别）”列，适用于注册学习路径的所有学习者。

在“类型”列中，“学习计划”将更名为“学习路径”。 现有连接不会发生更改。

## Learning Manager FTP连接器 {#ftpconnector}

借助FTP连接器，您可将Learning Manager与任意外部系统集成以自动同步数据。 需要外部系统能够以CSV格式导出数据，并将其放置在Learning Manager FTP帐户内相应文件夹下。 FTP连接器的功能包括：

您还可以使用Box连接器进行数据迁移、用户导入和数据导出。 有关更多信息，请参阅Box连接器。

### 数据导入 {#dataimport}

用户导入操作能让Learning Manager管理员从Learning Manager FTP服务获取员工详细信息，并自动将其导入Learning Manager。 使用此功能，您可以将这些系统生成的CSV放在FTP帐户下的相应文件夹中来集成多个系统。 Learning Manager会拾取CSV文件，将其合并，并根据计划导入数据。 有关更多信息，请参阅计划功能。

**映射属性**

集成管理员可以选择CSV列并将其映射到Learning Manager的组属性。 映射只需进行一次。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以重新配置该映射。

#### 导出数据 {#exportdata}

数据导出允许用户将用户技能和学习者成绩单导出到FTP位置，从而与任何第三方系统集成。

#### 计划 {#scheduling}

管理员可以根据公司的要求设置计划任务，Learning Manager应用程序中的用户可以根据计划获得最新消息。 同样，集成管理员可以及时安排技能导出，以便与外部系统集成。 可在Learning Manager应用程序中每天执行同步。

### 配置Learning Manager FTP连接器 {#configurecaptivateprimeftpconnector}

如要将FTP连接器与Learning Manager集成，请学习相应操作过程。

#### 创建连接 {#Createaconnection-1}

1. 在Learning Manager主页，将鼠标悬停在FTP卡/缩略图上方。 此时会显示一个菜单。 点击 **[!UICONTROL Connect]** 菜单中的项。

   ![](assets/mouseover-ftpconnector.png)

   *连接选项*

1. 此时会显示一个对话框，提示您输入电子邮件ID。 提供负责管理公司Learning Manager FTP帐户的人员的电子邮件ID。 点击 **[!UICONTROL Connect]** 提供电子邮件ID后。
1. Learning Manager会向您发送一封电子邮件，提示用户在第一次访问FTP之前重置密码。 用户必须重置密码，并使用此密码来访问Learning Manager FTP帐户。

   >[!NOTE]
   >
   >一个Learning Manager帐户仅可创建一个Learning Manager FTP帐户。

   在“概述”页面中，您可以指定集成的连接名称。 从以下选项中选择要执行的操作：

   * 导入内部用户
   * 导入xAPI
   * 导出用户技能 — 配置计划
   * 导出用户技能 — 按需
   * 导出学习者成绩单 — 配置计划
   * 导出学习者成绩单 — 按需

   ![](assets/ftp-connector-dashboard.png)
   *导出选项*

### 导入

+++内部用户

通过“导入内部用户”选项，您可以按需或计划将用户从CSV中导入Learning Manager。

+++

+++映射属性

成功建立连接后，您便可以映射CSV文件的各列。 它被放置在FTP文件夹中，以对应Learning Manager的相应属性。 此步骤为必须操作。

1. 在“映射属性”页面中，您可以在左侧看见Learning Manager的预期各列，在右侧看见CSV各列名称。 首先，您会在右侧看到一个空的选择框。 通过单击 **选择文件**.
1. 上述步骤会在右侧的选择下拉列表中填充所有CSV列名称。 选择映射到Learning Manager列名称的相应列名称。

   >[!NOTE]
   >
   >经理字段必须映射到电子邮件地址类型的字段。 在可以使用连接器之前，必须映射所有列。

1. 点击 **[!UICONTROL 保存]** 完成映射后。

   连接器现在可以使用了。 已配置的帐户在管理员应用程序中显示为数据源，以便管理员安排导入或用于按需同步。



+++

+++使用Learning Manager FTP连接器

1. 必须将来自外部系统的CSV文件放在以下路径中：

   `code $OPERATION$/$OBJECT_TYPE$/$SUB_OBJECT_TYPE$/data.csv`

   >[!NOTE]
   >
   >在2016年7月版中，仅允许导入用户。 因此，如要使用FTP连接器，请确保已将CSV文件放入以下文件夹：

   `code Home/import/user/internal/*.csv`

1. FTP连接器从CSV文件中获取所有行。 重要的是，一个CSV文件中某位用户对应的行不会出现在任何其他CSV中。
1. 所有CSV都必须包含映射中指定的列。
1. 在流程开始之前，文件夹中必须存在所有必需的CSV。

>[!NOTE]
>
>在将用户导入Learning Manager时，管理员还必须了解如何在Learning Manager中管理用户。 请参阅 [用户管理帮助](migration-manual.md#usermanagement) 了解更多信息。

+++

+++导入xAPI

导入xAPI选项允许您根据需要安排将第三方服务的xAPI语句导入Learning Manager。

+++

+++导入xAPI所需的配置

1. 在配置页面中，选择配置列表中可用的现有配置，以从CSV导入xAPI语句。 单击编辑或 **添加新配置** 导航至“配置导入源”页面的链接。

   **配置**

   * 在“配置导入源”页面中，填写两个字段，即“名称”和“源文件名”。 源文件名应与FTP文件夹位置中提供的文件名匹配。
   * 点击 **[!UICONTROL 保存]** 以保存更改。

   ![](assets/configurations.png)
   *配置*

   **筛选**

   * 在左侧窗格中，单击 **[!UICONTROL 筛选]**.
   * 在“配置导入 — 过滤器”页面中，填写“名称”和“条件”字段以滤除记录。 点击 **[!UICONTROL 添加新过滤器]** 以添加其他过滤器。 您可以通过单击来保存或删除过滤器 **保存** 或 **删除** 选项。

   ![](assets/filter.png)
   *筛选*

   **映射**

   * 在左侧窗格中，单击 **[!UICONTROL 映射]**.
   * 在“导入xAPI语句 — 配置 — 映射”页面的左侧，您可以看到需要与CSV列名称映射的xAPI JSON字段路径名。
   * 默认情况下，需要与CSV列名称映射的三个JSON路径字段名分别为 **actor.mbox**， **verb.id**&#x200B;和 **object.id**. 您可以通过单击添加要映射的其他字段 **添加新映射**.

   * 选择要与Json字段路径名映射的列名称类型（字符串、数字、布尔值或日期类型）。
   * 完成映射后单击“保存” 。 xAPI现在可以按计划或按需导入。

   ![](assets/mapping.png)
   *映射*

1. 在左侧窗格中，单击 **[!UICONTROL 配置计划]**. 点击 **[!UICONTROL 启用计划]** 以计划导入xAPI语句。

   您可以输入开始时间和日期，然后以天为单位输入xAPI导入计划的频率。 例如，每3天启用一次xAPI导入。

   ![](assets/configure-schedule2x.png)
   *导入xAPI语句 — 配置计划*

1. 在左侧窗格中，单击 **[!UICONTROL 按需执行]**.

   ![](assets/on-demand.png)
   *导入xAPI语句 — 按需*

1. 在左侧窗格中，单击 **[!UICONTROL 执行状态]** 按时间顺序查看此连接器所有运行的摘要。 您可以查看导入xAPI的开始日期和持续时间、导入类型（按需或按计划）以及导入状态（xAPI导入进行中、已完成或失败）。

   ![](assets/execution-status2x.png)
   *导入xAPI语句 — 执行状态*

+++

### 导出

+++技能

有两个选项可用于导出用户技能报告。

**[!UICONTROL 用户技能 — 按需]**：您可以使用该选项指定开始日期并导出报告。 将提取从输入的日期到现在的报告。

![](assets/export-on-demand2x.png)
*按需导出选项*

**[!UICONTROL 用户技能 — 配置]**：您可以使用此选项来计划安排报告的提取。 选中“启用计划”复选框，然后指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。

![](assets/user-skills-configure.png)
*配置报告导出*

+++

如要打开已导出文件所处的“导出”文件夹，请打开“用户技能”页面中提供的“FTP文件夹”链接，如下所示：

![](assets/ftp-folder.png)
*用于查看文件的FTP文件夹*

自动导出的文件出现在以下位置 **Home/export/&#42;FTP_location&#42;**

自动导出文件的标题为 **skill_achieves_&#42;日期自&#x200B;&#42;_收件人_&#42;终止日期&#42;.csv**

![](assets/exported-csvs.png)
*导出的.csv文件*

+++学习者成绩单

![](assets/on-demand-report.png)

**配置**：您可以使用此选项来计划安排报告的提取。 选中“启用计划”复选框，然后指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。

![](assets/configure-report.png)

+++

如要打开已导出文件位于FTP中的“导出”文件夹，请打开“学习者成绩单”页面中提供的“FTP文件夹”链接，如下所示

自动导出的文件出现在以下位置 **Home/export/&#42;FTP_location&#42;**

自动导出文件的标题为 **learner_transcript_&#42;日期自&#x200B;&#42;_收件人_&#42;终止日期&#42;.csv**

![](assets/exported-file.png)

### 支持手动csv字段 {#supportformanualcsvfields}

通过FTP导入用户数据时，管理员必须将系统中呈现的所有活动字段都映射到csv中的相应字段。

对于所有csv活动字段，这是必须的。 对于手动活动字段，集成管理员可以选择此选项 **DontImportFromSource**.

通过选择此选项，手动活动字段值不会使用csv导入来填充。 学习者提供的值保持不变。

>[!NOTE]
>
>映射时，如果选项 **DontImportFromSource** 为“csv活动字段”选择此字段，则将从系统中删除此字段。

![](assets/ftp-conector-foractivefields.png)
*活动字段的FTP连接器*

## Lynda连接器 {#lyndaconnector}

Lynda.com的企业用户可使用Lynda连接器供其学习者在Learning Manager内找到并学习Lynda课程。 此连接器可以配置为使用您的API密钥定期从Lynda.com上提取课程。 在Learning Manager中创建课程后，用户可以搜索和使用这些课程。 随后即可在Learning Manager中跟踪学习者进度。

### 配置Lynda连接器 {#configurethelyndaconnector}

1. 在集成管理员信息板中，单击Lynda。

   您会看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置Lynda连接器，请单击“连接”。

   <!--Configure the Exavault FTP account before you configure this connector.-->

1. 在连接页面中，指定连接器的名称。 输入Appkey和您连接的密钥。

   >[!NOTE]
   >
   >联系您的供应商，获取Appkey和密钥。

1. 单击“保存”。

   配置即会保存，并为您的帐户添加Lynda连接。 现在，您可以从主页单击“管理连接” ，并随时编辑您的配置。

1. 如果已建立连接，请单击“管理连接”查看所有连接。

   >[!NOTE]
   >
   >在配置此连接器之前，必须为您的帐户启用迁移功能。

1. 单击要编辑的连接。
1. 在左侧窗格中，单击 **[!UICONTROL 配置]**. 执行以下操作之一：

   * 查看或编辑帐户的详细信息，以及此窗口中的同步计划。 如果要启用此帐户，请选中“启用连接”复选框。
   * 单击编辑并编辑您的凭据。 要撤消对此字段的更新，请单击“重置”
   * 单击“启用计划”以计划同步。 您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。 例如，启用每三天同步一次。

   点击 **[!UICONTROL 保存]** 以保存更改。

   ![](assets/lynda.png)

   *为Learning Manager配置Lynda连接器*

1. 在左侧窗格中，单击“按需执行”。 您可使用此选项从Lynda导入用户订阅源和其他相关数据。 输入按需执行的“开始日期”，然后单击“执行”以执行同步。 将导入从开始日期到现在的所有数据。

   * 如果同步过程中应用程序停机，则您可以单击“禁用同步过程中对Learning Manager的访问”。
   * 如果在执行期间单击“启用对Learning Manager的访问”，则同步期间服务不会中断。

   ![](assets/lynda-ondemand.png)

   *为Lynda连接器执行按需执行*

1. 您还可以随时单击左侧窗格中的“执行状态”，按时间顺序查看此连接器所有运行的摘要。 您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   >[!NOTE]
   >
   >删除并重新创建连接时，连接器的先前运行将再次出现。 在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

   ![](assets/lynda-ondemand.png)

   *查看所有运行的摘要，单击执行状态*

## getAbstract连接器 {#getabstractconnector}

getAbstract.com的企业用户可使用getAbstract连接器供其学习者找到并使用getAbstract摘要。 连接器可以配置为定期提取使用情况数据，前提条件是要在Learning Manager中创建学习者完成情况记录。 继续阅读以了解如何在Learning Manager中配置此连接器。

### 配置getAbstract连接器 {#configurethegetabstractconnector}

1. 在集成管理员信息板中，单击getAbstract。

   您会看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置getAbstract连接器，请单击“连接”。

   <!--Configure the Exavault FTP account before you configure this connector.

   Ensure that you share this FTP credentials with your content provider to access the feeds.-->

1. 在连接名称字段中输入连接的名称。

   在“客户端ID”和“客户端密钥”字段中输入相应的密钥。 请与供应商联系以获取此连接器的相应密钥。

   需要密钥才能获取客户端使用的课程的课程元数据。

1. 如果已建立连接，请从主页单击“getAbstract”>“管理连接”以查看和编辑现有配置。

   >[!NOTE]
   >
   >在配置此连接器之前，必须为您的帐户启用迁移功能。

1. 单击要查看或编辑其配置的连接。

   ![](assets/getabstractschedulepage.png)

   *为Learning Manager配置getAbstract连接器*

1. 在左侧窗格中，单击“配置”。 执行以下操作之一：

   * 查看或编辑帐户的详细信息，以及此窗口中的同步计划。 如果要启用此帐户，请选中“启用连接”复选框。
   * 单击编辑并编辑您的凭据。 要撤消对此字段的更新，请单击“重置”
   * 单击“启用计划”以计划同步。 您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。 例如，启用每三天同步一次。

1. 点击 **[!UICONTROL 保存]**.

   配置即会保存，并为您的帐户添加getAbstract连接。

1. 在左侧窗格中，单击“按需执行”。 您可使用此选项从getAbstract导入用户订阅源和其他相关数据。 输入按需执行的“开始日期”，然后单击“执行”以执行同步。 将导入从开始日期到现在的所有数据。

   * 如果同步过程中应用程序停机，则您可以单击“禁用同步过程中对Learning Manager的访问”。
   * 如果在执行期间单击“启用对Learning Manager的访问”，则同步期间服务不会中断。

1. 您还可以随时单击左侧窗格中的“执行状态”，按时间顺序查看此连接器所有运行的摘要。 您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   >[!NOTE]
   >
   >删除并重新创建连接时，连接器的先前运行将再次出现。 在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

   要使任何类型的同步起作用，请确保getAbstract FTP文件夹中存在同步所指定日期的用户订阅源。

   请参阅以下Excel工作表，该工作表是getAbstract的用户订阅源文件的样本。 文件名必须遵循以下格式： **report_export_yyyy_MM_dd_HHmmss.xlsx** 或 **report_export_yyyy_MM_dd.xlsx**.
   [getAbstract用户订阅源样本Excel表](assets/report-export-20170401175342.xlsx)

## Harvard ManageMentor连接器 {#hmmconnector}

Harvard ManageMentor的企业用户可使用Harvard ManageMentor连接器供其学习者找到并学习Harvard ManageMentor课程。 此连接器可帮助在Learning Manager中创建课程，并可配置为定期获取学习者进度数据。 要配置此连接器，请执行以下步骤：

### 配置Harvard ManagerMentor连接器 {#configuretheharvardmanagermentorconnector}

1. 在集成管理员信息板中，单击Harvard ManageMentor。

   您会看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置Harvard ManageMentor连接器，请单击“连接”。

   <!--Configure the Exavault FTP account before you configure this connector.

   Ensure that you share this FTP credentials with your content provider to access the feeds.-->

1. 在连接名称字段中，输入连接的名称。 单击“连接”以保存此连接。
1. 如果已建立连接，请从主页单击“Harvard ManageMentor”>“管理连接”。 单击要编辑现有配置的连接。

   >[!NOTE]
   >
   >在配置此连接器之前，必须为您的帐户启用迁移功能。

   ![](assets/hmm.png)

   *配置适用于Learning Manager的HarvardManage Mentor连接器*

1. 在左侧窗格中，单击“配置”。 执行以下操作之一：

   * 查看或编辑帐户的详细信息，以及此窗口中的同步计划。 如果要启用此帐户，请选中“启用连接”复选框。
   * 单击“启用计划”以计划同步。 您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。 例如，启用每三天同步一次。

1. 在左侧窗格中，单击“按需执行”。 您可使用此选项从Harvard ManageMentor导入用户订阅源和其他相关数据。 输入按需执行的“开始日期”，然后单击“执行”以执行同步。 将为此连接导入从开始日期到现在的所有数据。

   * 如果同步过程中应用程序停机，则您可以单击“禁用同步过程中对Learning Manager的访问”。
   * 如果在执行期间单击“启用对Learning Manager的访问”，则同步期间服务不会中断。

   如果要每隔几天自动执行同步，请在“重复天数”字段中指定天数。 同步可确保您的帐户使用Harvard ManageMentor的最新版摘要和摘要进行更新。

1. 您还可以随时单击左侧窗格中的“执行状态”，按时间顺序查看此连接器所有运行的摘要。 您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   >[!NOTE]
   >
   >删除并重新创建连接时，连接器的先前运行将再次出现。 在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

   要使同步成功，请确保Harvard ManageMentor FTP文件夹中至少存在以下文件中的一个：

   hmm12_metadata.xlsx：此文件提供Harvard ManageMentor连接器的课程元数据。 确保在上载文件时遵循命名约定。

   client_hmm12_20150125.xlsx：这是Harvard ManageMentor连接器的用户订阅源。 文件命名约定如下 **client_hmm12_yyyyMMdd.xlsx。**

   请参阅以下两个用于此连接器的用户订阅源和课程订阅源文件样本：

   * [Harvard ManageMentor连接器的课程元数据文件](assets/hmm12-metadata.xlsx)
   * [Harvard ManageMentor连接器的用户订阅源](assets/client-hmm12-20170304.xlsx)

## Workday连接器 {#workdayconnector}

借助Workday连接器，您可以将Learning Manager与Workday租户集成以自动同步数据。

### 导入

#### 映射属性

集成管理员可以选择Workday列并将其映射到相应的Learning Manager组属性。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

#### 自动导入用户

用户导入操作能让Learning Manager管理员从Workday获取员工详细信息，并自动将其导入Learning Manager。

#### 过滤用户

Learning Manager管理员可在导入用户前先对其过滤。 例如，Learning Manager管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

### 导出

用户技能导出允许用户自动将用户技能导出到Workday。

>[!NOTE]
>
>使用同一Workday帐户无法同时导出多个Learning Manager帐户中的技能。

### 计划 {#Scheduling-1}

管理员可以根据公司的要求设置计划任务，Learning Manager应用程序中的用户可以根据计划获得最新消息。 同样，集成管理员可以及时安排技能导出，以便与外部系统集成。 可在Learning Manager应用程序中每天执行同步。

### 配置Workday连接器 {#configureworkdayconnector}

>[!PREREQUISITES]
>
>请求公司的Workday管理员创建具有ISU_Permissions文档中定义的权限的集成系统用户(ISU)。 从下面的链接下载副本。

[下载集成系统用户(ISU)安全性的副本。](assets/isu-permissions-v1.pdf) 如要将Workday连接器与Learning Manager集成，请学习相应操作过程。

1. 在Learning Manager主页中，将鼠标悬停在Workday磁贴上。 此时会显示一个菜单。 点击 **[!UICONTROL Connect]** 菜单中的项。

   ![](assets/workday-tile.png)

   *Workday图块*

1. 此时会显示一个对话框，提示您输入新连接的凭据。 在建立连接之前，请输入以下字段。

   * 连接名称：根据您的喜好提供一个连接名称。
   * 主机URL：集成管理员可以从相应的Workday管理员获取主机URL详细信息。
   * 租户：租户是贵公司的内部人员。 您的Workday管理员为您提供了租户详细信息。
   * 用户名和密码：Workday管理员创建具有所需安全权限的集成系统用户(ISU)，并将其共享给集成管理员。

>[!NOTE]
>
>   Learning Manager使用Workday API版本28.1。


![](assets/configure-connector.png)
*配置Workday连接器*

1. 在所有相关字段中输入信息后，单击“连接”。

   >[!NOTE]
   >
   >您也可以将多个Workday连接同步到您的Learning Manager帐户。

在“概述”页面中，您可以指定集成的连接名称。 从以下选项中选择要执行的操作：

* 导入内部用户
* 导出用户技能 — 配置计划
* 导出用户技能 — 按需

![](assets/overview.png)
*Workday概述*

### 导入

#### 映射属性 {#MapAttributes-1}

您可以使用Workday连接器集成Learning Manager和Workday，以自动同步数据。 您可以将所有活动用户从Workday导入到Learning Manager。 可以从各种数据源（包括FTP和Salesforce）导入用户。

在导入用户之前，必须对Learning Manager和Workday中的用户属性进行映射。 在“概述”页面中，使用“导入”下的“内部用户”选项来映射属性。

在“Adobe学习管理器”列下输入Adobe学习管理器凭据。 使用下拉列表为Workday下的列选择正确的凭据。

>[!NOTE]
>
>目前，Learning Manager支持从Workday导入44个用户属性。 使用Learning Manager中的“活动字段”添加更多属性。

![](assets/workday.png)
*映射属性*

选择 **排除临时工** 复选框，以防止导入经理提供的临时工作人员。

Workday有四个级别，而Learning Manager有两个级别。 Workday中的四个级别是技能配置文件类别、技能配置文件、技能项目类别和技能项目。 您的技能名称以及Learning Manager的级别将一同映射到Workday的技能项目之下。

>[!NOTE]
>
>您可以添加其他Workday属性。 请与您的CSAM联系以添加属性。

+++支持的Workday属性列表

wd：User_ID\
wd：Worker_ID\
wd：Personal_Data.wd：Name_Data.wd：Preferred_Name_Data.wd：Name_Detail_Data。@wd：Formatted_Name\
wd：Personal_Data.wd：Name_Data.wd：Legal_Name_Data.wd：Name_Detail_Data.@wd：Formatted_Name\
wd：Personal_Data.wd：Name_Data.wd：Legal_Name_Data.wd：Name_Detail_Data.wd：Prefix_Data.wd：Title_Descriptor\
wd：Personal_Data.wd：Name_Data.wd：Preferred_Name_Data.wd：Name_Detail_Data.wd：Prefix_Data.wd：Title_Descriptor\
wd：Personal_Data.wd：Name_Data.wd：Preferred_Name_Data.wd：Name_Detail_Data.wd：First_Name\
wd：Personal_Data.wd：Name_Data.wd：Preferred_Name_Data.wd：Name_Detail_Data.wd：Last_Name\
wd：Personal_Data.wd：Name_Data.wd：Legal_Name_Data.wd：Name_Detail_Data.wd：First_Name\
wd：Personal_Data.wd：Name_Data.wd：Legal_Name_Data.wd：Name_Detail_Data.wd：Last_Name\
wd：Personal_Data.wd：Contact_Data.wd：Address_Data.0。@wd：Formatted_Address\
wd：Personal_Data.wd：Contact_Data.wd：Address_Data.0.wd：Postal_Code\
wd：Personal_Data.wd：Contact_Data.wd：Address_Data.0.wd：Country_Region_Descriptor\
wd：Personal_Data.wd：Contact_Data.wd：Phone_Data.0。@wd：Formatted_Phone\
wd：Personal_Data.wd：Contact_Data.wd：Phone_Data.0.wd：Country_ISO_Code\
wd：Personal_Data.wd：Contact_Data.wd：Phone_Data.0.wd：International_Phone_Code\
wd：Personal_Data.wd：Contact_Data.wd：Phone_Data.0.wd：Phone_Number\
wd：Personal_Data.wd：Primary_Nationality_Reference.wd：ID.1。$\
wd：Personal_Data.wd：Gender_Reference.wd：ID.1。$\
wd：Personal_Data.wd：Identification_Data.wd：National_ID.0.wd：National_ID_Data.wd：ID\
wd：Personal_Data.wd：Identification_Data.wd：Custom_ID.0.wd：Custom_ID_Data.wd：ID\
wd：User_Account_Data.wd：Default_Display_Language_Reference.wd：ID.1。$\
wd：Role_Data.wd：Organization_Role_Data.wd：Organization_Role.0.wd：Organization_Role_Reference.wd：ID.1。$\
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Position_Title\
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Title\
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Site_Summary_Data.wd：Name\
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Business_Site_Summary_Data.wd：Address_Data.@wd：Formatted_Address\
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Job_Classification_Summary_Data.0.wd：Job_Classification_Reference.wd：ID.1。$\
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Job_Classification_Summary_Data.0.wd：Job_Group_Reference.wd：ID.1。$\
wd：Employment_Data.wd：Worker_Job_Data.0.wd：Position_Data.wd：Work_Space__Reference.wd：ID.1。$\
wd：Employment_Data.wd：Worker_Status_Data.wd：Active\
wd：Employment_Data.wd：Worker_Status_Data.wd：Active_Status_Date\
wd：Employment_Data.wd：Worker_Status_Data.wd：Hire_Date\
wd：Employment_Data.wd：Worker_Status_Data.wd：Original_Hire_Date\
wd：Employment_Data.wd：Worker_Status_Data.wd：Retired\
wd：Employment_Data.wd：Worker_Status_Data.wd：Retirement_Date\
wd：Employment_Data.wd：Worker_Status_Data.wd：已终止\
wd：Employment_Data.wd：Worker_Status_Data.wd：Termination_Date\
wd：Employment_Data.wd：Worker_Status_Data.wd：Termination_Last_Day_of_Work\
wd：Organization_Data.wd：Worker_Organization_Data.0.wd：Organization_Data.wd：Organization_Code\
wd：Organization_Data.wd：Worker_Organization_Data.0.wd：Organization_Data.wd：Organization_Name\
wd：Organization_Data.wd：Worker_Organization_Data.0.wd：Organization_Data.wd：Organization_Type_Reference.wd：ID.1。$\
wd：Organization_Data.wd：Worker_Organization_Data.0.wd：Organization_Data.wd：Organization_Subtype_Reference.wd：ID.1。$\
wd：Qualification_Data.wd：Education.0.wd：School_Name\
wd：Qualification_Data.wd：External_Job_History.0.wd：Job_History_Data.wd：Job_Title\
wd：Qualification_Data.wd：External_Job_History.0.wd：Job_History_Data.wd：Company\
wd：Management_Chain_Data.wd：Worker_Supervisory_Management_Chain_Data.wd：Management_Chain_Data.0.wd：Manager.Employee_ID

+++

### 导出

您可以将用户习得的所有技能从Learning Manager导出到Workday。 仅导出所有活动用户技能，Learning Manager不导出弃用的技能。 您还可以连接多个Learning Manager\
连接到同一Workday连接器。 如果两个Learning Manager帐户中的技能名称相同，则它们会被映射到Workday中的相同技能。 在Workday中更新技能之前，如果两个Learning Manager帐户使用的是同一个Workday帐户，则建议对所有Learning Manager帐户中的技能名称进行更新。

+++用户技能 — 配置

此选项允许您计划安排报告的提取。 确保已启用“使用此连接启用用户技能导出”复选框。 选中“启用计划”复选框，然后指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。 选中“启用计划”复选框，然后输入“开始日期”、“时间”和“n”天后重复。 完成后，单击“保存”。

![](assets/configure-schedule.png)
*配置用户技能报告*

+++

+++用户技能 — 按需

您可以使用该选项指定开始日期并导出报告。 将提取从输入的日期到现在的报告。 输入您要开始生成报告的日期，然后单击“执行”。

![](assets/on-demand-report.png)
*按需用户技能报告*

+++

+++用户技能 — 执行状态

在此可查看所有任务的摘要并获取其状态报告。 您可以通过单击错误报告链接下载错误报告。

![](assets/execution-status.png)
*用户技能执行报告*

+++

## miniOrange连接器 {#miniorangeconnector}

借助miniOrange连接器，您可以将Learning Manager与miniOrange租户集成以自动同步数据。

### 导入

#### 映射属性

集成管理员可以选择miniOrange属性并将其映射到相应的Learning Manager组属性。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

#### 自动导入用户

用户导入操作能让Learning Manager管理员从miniOrange获取员工详细信息，并自动将其导入Learning Manager。

#### 过滤用户

Learning Manager管理员可在导入用户前先对其过滤。 例如，Learning Manager管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

要设置miniOrange连接器，请联系Learning Manager CSM团队。

### 配置miniOrange连接器 {#configureminiorangeconnector}

1. 在Learning Manager主页，将鼠标悬停在miniOrange卡/缩略图上方。 此时会显示一个菜单。 点击  **[!UICONTROL Connect]** 选项。

   ![](assets/miniorange-tile.png)

   *miniOrange连接器图块*

1. 点击 **[!UICONTROL Connect]** 以建立新连接。 出现miniOrange连接器页面。 输入您要映射的帐户的详细信息。

   ![](assets/establish-connection.png)

   *创建连接*

1. 如果要直接将miniOrnage用户导入成为Learning Manager内部用户，请使用 **[!UICONTROL 导入内部用户]** 选项。

   ![](assets/import-users.png)

   *导入内部用户*

1. 在映射页面中，您可以在左侧看见Learning Manager的列，在右侧看见miniOrnage的列。 选择映射到Learning Manager列名称的相应列名称。

   ![](assets/map-attributes.png)

   *映射属性*

1. 如要查看和编辑数据源，作为管理员，单击 **[!UICONTROL 设置>数据源]**.

   已建立的miniOrange源将被列出。 如果需要编辑过滤器，请单击 **[!UICONTROL 编辑]**.

   ![](assets/data-source.png)

   *查看和编辑数据源*

1. 完成导入后，您将收到通知。 要查看或编辑导入日志，请单击 **[!UICONTROL 用户>导入日志。]**

#### 删除连接 {#deleteaconnection}

要删除已建立的miniOrange连接，请执行以下步骤。

## 视频会议连接器（Bluejeans会议和Zoom） {#bluejeansconnector}

您现在可以将Learning Manager与BlueJeans和Zoom连接器集成，并使用它们来主持课程。  通过该连接器，您可以与学习者一起设置视频会议会议/课程。

要设置和使用连接器，请执行以下步骤。

1. 在Learning Manager主页中，将鼠标悬停在BlueJeans/Zoom缩略图上。 此时会显示一个菜单。 点击  **[!UICONTROL Connect]** 选项。

   ![](assets/connectors.png)

   *Zoom连接器图块*

1. BlueJeans/ Zoom连接器页面即会打开。 在相应字段中输入帐户的详细信息，以集成和同步用户订阅源。 您可以从您连接器帐户的管理员处获取详细信息。

   ![](assets/bluejeans-connecotrpage.png)
   *连接到BlueJeans/Zoom*

   >[!NOTE]
   >
   >作为学习者，当启用连接器时，应使用您的Learning Manager帐户所用的电子邮件ID来启用将用户订阅源发送回Learning Manager。

1. 建立连接后，作为作者，即可使用BlueJeans/Zoom创建VC课程作为会议系统。

   ![](assets/vc.jpg)

   *创建虚拟教室课程*

1. 管理员、经理和学习者均可为已创建的课程注册学习者。 注册后，学习者会收到一封电子邮件。 学习者可以登录其Learning Manager帐户来查看计划详细信息并参加课程。
1. 课程完成后，完成报告会发送至Learning Manager。 管理员可查阅完成报告，检查学习者的出勤情况和得分。

   ![](assets/attendence-and-scoringreport.png)
   *出勤和得分报告*

### 创建缩放服务器到服务器OAuth应用程序

创建用于AdobeLearning Manager的缩放服务器到服务器OAuth应用程序时，必须在创建连接时添加AdobeLearning Manager所需的范围。

AdobeLearning Manager需要以下范围，并且必须在OAuth应用程序中选择这些范围。

* 查看所有用户会议/会议:read:admin
* 查看和管理所有用户会议/会议:write:admin
* 查看报告数据/报告:read:admin
* 查看所有用户信息/用户:read:admin
* 查看用户信息并管理用户/用户:write:admin

## Box连接器 {#boxconnector}

借助Box连接器，您可以将Learning Manager与任意外部系统集成以自动同步数据。 需要外部系统能够以CSV格式导出数据，并将其放置在Learning Manager Box帐户内相应文件夹下。 Box连接器功能如下：

您还可以使用FTP连接器进行数据迁移、用户导入和数据导出。 欲知更多信息， [Learning Manager FTP连接器。](connectors.md#main-pars_header_1427405935)

### 数据导入 {#DataImport-1}

用户导入操作能让Learning Manager管理员从Learning Manager Box服务获取员工详细信息，并自动将其导入Learning Manager。 使用此功能，您可以将这些系统生成的CSV放在Box帐户下的相应文件夹中来集成多个系统。 Learning Manager会拾取CSV文件，将其合并，并根据计划导入数据。 有关更多信息，请参阅计划功能。

**映射属性**

集成管理员可以选择CSV列并将其映射到Learning Manager的组属性。 映射只需进行一次。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以重新配置该映射。

## 数据导出 {#dataexport}

数据导出允许用户将用户技能和学习者成绩单导出到Box位置，从而与任何第三方系统集成。

## 计划报告 {#schedulereports}

管理员可以根据公司的要求设置计划任务，Learning Manager应用程序中的用户可以根据计划获得最新消息。 同样，集成管理员可以及时安排技能导出，以便与外部系统集成。 可在Learning Manager应用程序中每天执行同步。

## 配置Box连接器 {#configureboxconnector}

如要将Box连接器与Learning Manager集成，请学习相应操作过程。

1. 在Learning Manager主页，将鼠标悬停在Box卡/缩略图上方。 此时会显示一个菜单。 单击菜单中的“连接”条目。

   ![](assets/screen-shot-2017-10-25at54426pm.png)

   *连接到Box*

1. 此时会显示一个对话框，提示您输入电子邮件ID。 提供负责管理公司Learning Manager Box帐户的人员的电子邮件ID。 提供电子邮件ID后，单击“连接” 。
1. Learning Manager会向您发送一封电子邮件，提示用户在第一次访问Box之前重置密码。 用户必须重置密码，并使用此密码来访问Learning Manager Box帐户。

   >[!NOTE]
   >
   >一个Learning Manager帐户仅可创建一个Learning Manager Box帐户。

   在“概述”页面中，您可以指定集成的连接名称。 从以下选项中选择要执行的操作：

   * 导入内部用户
   * 导入xAPI活动报告
   * 导出用户技能 — 配置计划
   * 导出用户技能 — 按需
   * 导出学习者成绩单 — 配置计划
   * 导出学习者成绩单 — 按需

## 导入

+++内部用户

使用“导入内部用户”选项，您可以计划自动生成用户导入报告。 生成的报告将作为.CSV文件发送给您。

+++

+++映射属性

成功建立连接后，您便可将Box文件夹中存放的CSV文件列映射到Learning Manager的相应属性。 此步骤为必须操作。

1. 在“映射属性”页面中，您可以在左侧看见Learning Manager的预期各列，在右侧看见CSV各列名称。 首先，您会在右侧看到一个空的选择框。 点击“选择文件”，导入任一模板CSV。
1. 上述步骤会在右侧的选择下拉列表中填充所有CSV列名称。 选择映射到Learning Manager列名称的相应列名称。

   *经理字段必须映射到电子邮件地址类型的字段。 在可以使用连接器之前，必须映射所有列。*

1. 完成映射后单击“保存” 。

   连接器现在可以使用了。 已配置的帐户在管理员应用程序中显示为数据源，以便管理员安排导入或用于按需同步。

+++

+++xAPI活动报告

xAPI活动报告选项允许您生成对第三方服务xAPI语句的导入。 这些文件保存为.CSV文件，然后在导入Learning Manager时转换为xAPI语句。

+++

+++导入xAPI所需的配置

1. 在配置页面中，选择配置列表中可用的现有配置，以从CSV导入xAPI语句。 单击编辑或&#x200B;**添加新配置** 链接以导航至“导入xAPI语句 — 配置 — 源文件”页面。

   ![](assets/artboard-11-2x.png)

   *编辑或添加新配置*

   **配置**

   * 在“配置导入源”页面中，填写两个字段，即“名称”和“源文件名”。 源文件名应与FTP文件夹位置中提供的文件名匹配。
   * 点击 **[!UICONTROL 保存]** 以保存更改。

   ![](assets/configurations-main2x.png)

   *配置*

   **筛选**

   * 在左侧窗格中，单击过滤器。
   * 在“配置导入 — 过滤器”页面中，填写“名称”和“条件”字段以滤除记录。 单击“添加新过滤器”以添加其他过滤器。 您可以单击“操作”列下的“保存”或“删除”选项来保存或删除过滤器。

   ![](assets/box-filter-2x.png)

   *筛选*

   **映射**

   * 在左侧窗格中，单击“映射”。
   * 在“配置导入 — 映射”页面的左侧，您可以看到需要与CSV列名称映射的xAPI Json字段路径名。
   * 默认情况下，需要与CSV列名称映射的三个Json路径字段名分别为 **actor.mbox**， **verb.id**&#x200B;和 **object.id**. 您可以通过单击“添加新映射”来添加要映射的其他字段。
   * 选择要与Json字段路径名映射的列名称类型（字符串、数字、布尔值或日期类型）。
   * 完成映射后单击“保存” 。 xAPI现在可以按计划或按需导入。

   ![](assets/box-mapping-2x.png)
   *映射*

1. 在左侧窗格中，单击 **[!UICONTROL 配置计划]**. 单击启用计划以计划导入xAPI语句。 您可以输入开始时间和日期，然后以天为单位输入xAPI导入计划的频率。 例如，每3天启用一次xAPI导入。

   ![](assets/configure-schedulebox2x.png)
   *导入xAPI语句 — 配置计划*

1. 在左侧窗格中，单击 **[!UICONTROL 按需执行]**.

   ![](assets/box-on-demand-2x.png)
   *导入xAPI语句 — 按需*

1. 在左侧窗格中，单击 **[!UICONTROL 执行状态]** 按时间顺序查看此连接器所有运行的摘要。 您可以查看导入xAPI的开始日期和持续时间、导入类型（按需或按计划）以及导入状态（xAPI导入进行中、已完成或失败）。

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

1. Box连接器从CSV文件中获取所有行。 重要的是，一个CSV文件中某位用户对应的行不会出现在任何其他CSV中。
1. 所有CSV都必须包含映射中指定的列。
1. 在流程开始之前，文件夹中必须存在所有必需的CSV。

在将用户导入Learning Manager时，管理员还必须了解如何在Learning Manager中管理用户。 请参阅 [用户管理帮助](migration-manual.md#usermanagement) 了解更多信息。

+++

## 导出

+++技能

有两个选项可用于导出用户技能报告。

用户技能 — 按需：您可以使用该选项指定开始日期并导出报告。 将提取从输入的日期到现在的报告

**[!UICONTROL 用户技能 — 配置]**：您可以使用此选项来计划安排报告的提取。 选中“启用计划”复选框，然后指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。

+++

如要打开已导出文件位于Box中的“导出”文件夹，请打开“用户技能”页面中提供的“Box文件夹”链接，如下所示：

自动导出的文件出现在以下位置 **Home/export/&#42;Box_location&#42;**

自动导出文件的标题为 **skill_achieves_&#42;日期自&#x200B;&#42;_收件人_&#42;终止日期&#42;.csv**

>[!NOTE]
>
>客户负责管理访问权限和Learning Manager团队在Box文件夹中共享的内容。  文件夹中的内容也将物理存储在法兰克福地区。

### 支持手动csv字段 {#Supportformanualcsvfields-1}

通过Box导入用户数据时，管理员必须将系统中呈现的所有活动字段都映射到csv中的相应字段。

对于所有csv活动字段，这是必须的。 对于手动活动字段，集成管理员可以选择此选项 **DontImportFromSource**.

通过选择此选项，手动活动字段值不会使用csv导入来填充。 学习者提供的值保持不变。

>[!NOTE]
>
>映射时，如果选项 **DontImportFromSource** 为“csv活动字段”选择此字段，则将从系统中删除此字段。

![](assets/box-connector-foractivefields.png)
*活动字段的Box连接器*

>[!NOTE]
>
>对于任何使用FTP/Box作为数据源的连接器或迁移，所有处理过的csv文件都将删除。
>
>用于内容连接器(例如LinkedIn)的csv将在七天后删除，而用于导入用户的csv将立即删除。

## linkedIn学习连接器 {#linkedinlearningconnector}

LinkedIn.com的企业用户可使用LinkedIn Learning连接器供其学习者在Learning Manager内找到并学习相关课程。 此连接器可以配置为使用您的API密钥定期提取课程。 在Learning Manager中创建课程后，用户可以搜索和使用这些课程。 随后即可在Learning Manager中跟踪学习者进度。

>[!NOTE]
>
>在LinkedIn学习课程中花费的学习时间通过LinkedIn内容/LinkedIn平台传达给Learning Manager学习平台。 如果LinkedIn学习不发送学习时间，则无法通过我们的学习平台进行记录。 在这种情况下，Learning Manager显示的学习时间为零。

### 配置Linkedln学习门户中的设置 {#configuresettingsinlinkedlnlearningportal}

1. 以管理员身份登录Linkedln学习LMS。
1. 点击 **[!UICONTROL admin]** 从顶部导航面板中选择。
1. 点击 **[!UICONTROL 设置]** 在下一个窗口中按Tab键。
1. 选择 **[!UICONTROL 播放集成]** 在左侧导航面板中，然后单击 **集成** 选项卡。
1. 点击 **[!UICONTROL LMS内容启动设置]** 以展开其设置。
1. 添加以下三个主机名： **learningmanager.adobe.com**， **learningmanagerlrs.adobe.com**， **cpcontents.adobe.com**
1. 选择 **[!UICONTROL 启用AICC集成]**.

   ![](assets/linkedin-learning.png)

   *linkedIn学习配置*

### 配置LinkedIn Learning连接器 {#configurelinkedinlearningconnector}

1. 在集成管理员信息板中，单击 [!UICONTROL linkedIn学习]. 显示了“入门”、“连接”和“管理连接”选项。
1. 如果您是第一次配置LinkedIn学习连接器，请单击 [!UICONTROL Connect].

   <!--Configure the Exavault FTP account before you configure this connector.

   ![](assets/configure.jpg)
   *Configure connection*-->

1. 在连接页面中，指定连接器的名称。 输入Appkey和您连接的密钥。

   >[!NOTE]
   >
   >企业管理员可以从LinkedIn学习管理门户生成一个新的应用程序，以获取Appkey和密钥。

1. 点击 **[!UICONTROL 保存]**.

   配置即会保存，并为您的帐户添加LinkedIn Learning连接。 您现在可以单击 **[!UICONTROL 管理连接]** ，并可随时编辑您的配置。

1. 如果已建立连接，请单击 **[!UICONTROL 管理连接]** 查看您的所有连接。

   >[!NOTE]
   >
   >在配置此连接器之前，必须为您的帐户启用迁移功能。

1. 单击要编辑的连接。
1. 在左侧窗格中，单击“配置”。 执行以下操作之一：

   * 查看或编辑帐户的详细信息，以及此窗口中的同步计划。 选择 **[!UICONTROL 启用连接]** 复选框。
   * 点击 **[!UICONTROL 编辑]** 并编辑您的凭据。 要撤消对此字段的更新，请单击“重置”。
   * 点击 **[!UICONTROL 启用计划]** 以安排您的同步。 您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。 例如，启用每三天同步一次。

   点击 **[!UICONTROL 保存]** 以保存更改。

1. 在左侧窗格中，单击 **[!UICONTROL 按需执行]**. 您可使用此选项从LinkedIn导入用户订阅源和其他相关数据。 输入按需执行的“开始日期”，然后单击“执行”以执行同步。 将导入从开始日期到现在的所有数据。

   * 您可以单击 **[!UICONTROL 禁用访问]** 同步过程中应用程序停机的情况下，重新切换到Learning Manager。
   * 如果您单击 **[!UICONTROL 启用访问]** 在执行期间恢复到Learning Manager，同步期间服务不会中断。

   ![](assets/ondemandexecution.jpg)

   *报告的按需执行*

1. 您还可以随时单击左侧窗格中的“执行状态”，按时间顺序查看此连接器所有运行的摘要。 您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   ![](assets/executionstatus.jpg)

   *报告执行状态*

   >[!NOTE]
   >
   >删除并重新创建连接时，连接器的先前运行将再次出现。 在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

### 筛选LinkedIn学习内容 {#filter-linkedin}

linkedIn连接器中有过滤器，用于根据LinkedIn学习库划分内容。 此外，您还可以根据语言和库来筛选内容，并仅导入使用所需语言的课程。 导入后，根据导入配置将内容划分为多个目录。

筛选条件如下：

**使用以下方式筛选培训：** 从LinkedIn中筛选出对应的课程子集，并导入至Learning Manager。

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

有一个标签类型 —  **自定义标签**，可用来将自定义标签添加到LinkedIn学习课程。 您可以任意添加多个标签，并使用逗号分隔。

![](assets/add-custom-tags.png)

*添加自定义标签*

仅在迁移后才会保存内容。 相关内容将保存在相应的目录中。

## Power BI连接器 {#powerbiconnector}

>[!NOTE]
>
>Learning Manager仅支持与MicrosoftPower BI的商业许可集成。 它无法与Government Cloud上的MicrosoftPower BI集成。

您可使用此连接器的集成功能来利用现有Power BI帐户在Power BI中分析及直观显示Learning Manager中的学习数据。 在配置期间，集成管理员可以将其Power BI工作区设置为使用两个实时数据集（学习者成绩单和用户技能报告）进行增量填充。 然后，您可以使用PowerBI的所有功能和能力按照企业需求开发、部署和分配自定义信息板。

### 配置连接器 {#configuringtheconnector}

要配置连接器，请在 **[!UICONTROL 连接器]** 页面，将鼠标悬停在 **[!UICONTROL Power BI]** 拼贴并单击 **[!UICONTROL Connect]**. 此时将打开“Power BI”页面。 要建立连接，您需要提供应用程序客户端ID、应用程序客户端密钥、租户名称和工作区ID（可选）。 要获取这些凭据，请执行以下步骤。

![](assets/power-bi-configurepage.png)

*配置Power BI连接器*

1. Launch <https://app.powerbi.com/embedsetup>.
1. 点击 **[!UICONTROL 为您的组织嵌入]** 然后登录到您的Microsoft帐户。
1. 输入应用程序的名称。
1. 在“应用程序类型”部分，选择“服务器端Web应用程序”选项。
1. 在 **[!UICONTROL 重定向URL]** 部分，选择该选项 **使用自定义URL** （如果您知道目标应用程序的URL，请选择此选项）。 输入以下URL：

   `https://learningmanager.adobe.com/ctr/app/azure/_callback` （根据环境更新域）

1. 在“主页URL”字段中，输入以下URL `https://learningmanager.adobe.com/`
1. 在“权限”部分，选择 **读取所有数据集** 和 **读取和写入所有数据集**.

   获取租户：联系您的Power BI管理员以获取租户名称。

   获取工作场所ID：仅Power BI专业版用户可创建工作场所。 您可以在Power BI中创建工作场所，并从URL获取ID。

1. 点击 **[!UICONTROL 注册应用程序]** 并存储客户端ID和客户端密钥。

>[!NOTE]
>
>如果要再次授权连接，您必须创建另一个Power App，并指定更名的重定向URL。

您可以使用相同的方法导出学习者成绩单、用户技能和xAPI活动报告。 从左侧面板中选择学习者成绩单/用户技能。 将打开“导出”页面。

启用 **[!UICONTROL 使用此连接复选框启用用户技能/学习者成绩单导出]**. 保存更改。

**导出配置**：如果您要计划安排报告的提取。 选择 **[!UICONTROL 启用计划]** 复选框，并指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。

![](assets/power-bi-configureuserskillpage.png)

*导出配置以计划报告*

**按需导出：** 您可以使用该选项指定开始日期并导出报告。 将提取从输入的日期到现在的报告。

![](assets/power-bi-userskillondemandpage.png)

*按需导出*

可以登录Power BI帐户来查看导出的数据。 导出的数据在数据集选项下列出。

### 在Learning Manager中导出xAPI活动报告 {#exportxapiactivityreportsincaptivateprime}

在PowerBI-xAPI功能页面中，单击 **[!UICONTROL 导出xAPI活动报告]**.

![](assets/powerbi-dashboard.png)
*PowerBI — 导出xAPI活动报告*

在左侧窗格中，选择 **配置** ，然后执行以下步骤：

* 填写与列名和字符串类型匹配的JSON路径字段。
* 要添加更多JSON路径，请单击 **[!UICONTROL 添加]**.
* 您可以通过单击以下位置来编辑JSON路径字段中的条目： **[!UICONTROL 编辑]**.
* 点击 **[!UICONTROL 保存]** 以保存更改。

**配置计划**

在左侧窗格中，单击 **[!UICONTROL 配置计划]** 并执行以下操作：

* 单击“启用使用此连接导出xAPI语句”。
* 单击 **[!UICONTROL 启用计划]** 复选框，并指定开始日期和时间。 您还可以指定重复导出和发送的间隔天数。
* 单击 **[!UICONTROL 保存]** 按钮以保存配置计划设置。

![](assets/configure-schedule.png)
*xAPI导出配置计划*

**按需**

在左侧窗格中，单击 **[!UICONTROL 按需]** 并在“导出xAPi语句 — 按需”页面指定“开始日期”。

![](assets/on-demand-2.png)
*xAPI按需导出*

所有导出的数据都将进入由Power BI帐户中的Adobe创建的数据集。

如果LRS中的少数xAPI语句没有配置用于导出的jsonPower BI，则xAPI导出到LRS会失败。 对于无json路径可用的xAPI语句，应添加N/A常量值并在Power BI中显示。

**执行状态**

选择 **执行状态** 按时间顺序查看所有任务的摘要。 在运行期间，警告标志表示失败。 您可下载错误报告作为 **CSV** 通过单击错误报告链接。

![](assets/execution-status.png)
*xAPI导出执行状态*

### 统一报告 {#unified-reports}

Learning Manager可汇总用户数据、学习者成绩单、游戏、反馈报告等多份报告来创建导出内容，并将之作为一个数据集用于Power BI。

这使Power BI用户能够合并多份报告中的数据，从而在Power BI中展示更强大的分析能力和可视化能力。

![](assets/unified-power-bireports.png)
*统一Power BI报告*

**按需导出**

使用该选项指定开始日期和结束日期并导出报告。 将提取指定日期范围内的报告。

![](assets/on-demand-export.png)
*按需导出*

**计划导出**

如果您要计划安排报告的提取。 选择 **启用计划** 复选框，并指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。

![](assets/configure-schedule.png)
*配置计划*

您还可以将培训报告导出到Power BI。

借助“统一报告”功能，您可将培训报告导出到Power BI。

培训报告包含两个附加字段：

* 已分享课程反馈的用户数量
* 课程的平均星级评分

### 筛选学习者成绩单的状态 {#lt-status}

在Power BI连接的“统一报告”部分中，您可以通过相应选项并根据“学习对象”的状态导出“学习者成绩单”。

* **全选：** 导出指定日期范围内的所有记录或模块级别活动。
* **已完成：** 导出在日期范围内完成的所有记录。
* **进行中：** 导出所有状态为“进行中”的记录。
* **未开始：** 排除已于既定日期范围内注册但在报告生成时尚未开始的记录。

* **取消注册：** 包括在日期范围内取消注册的所有记录。

![](assets/lt-filters.png)
*筛选学习成绩单的状态*

您可以导出所需列表，然后在稍后使用Power BI来分析报告。

### 下载Power BI模板 {#template}

Learning Manager还提供了现成的Power BI模板。 这些模板为AdobeLearning Manager帐户管理员提供了更出色的分析能力。

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

### 导出培训报告

借助“统一报告”功能，您可将培训报告导出到Power BI。

培训报告包含以下附加字段：

* 已分享课程反馈的用户数量
* 课程的平均星级评分

![](assets/export-training-report.png)
*导出培训报告*

### 学习路径相关更改

#### 管理员：学习成绩单和统一报告

**现有连接**

如果在管理员帐户中禁用了“学习路径”选项，则不会在报告中添加行和列。

如果在管理员帐户中启用了“学习路径”选项，则报告将包含类型“学习路径（较高级别）”列，适用于注册学习路径的所有学习者。

**新连接**

如果在管理员帐户中禁用了“学习路径”选项，则培训报告将包含以下列：

* 嵌入式路径：显示学习计划的名称
* 嵌入式路径ID ：显示学习计划的ID。
* 嵌入式课程ID ：显示学习路径内的课程ID。

此外，该报告将包含类型“学习路径（较高级别）”列，适用于注册学习路径的所有学习者。

在“类型”列中，“学习计划”将更名为“学习路径”。 现有连接不会发生更改。 但是，对于新连接，更改将在30天后反映出来。

#### 培训报告：统一报告

**现有连接**

如果在管理员帐户中禁用了“学习路径”选项，则不会在报告中添加行和列。

如果在管理员帐户中启用了“学习路径”选项，则报告将包含“类型”列。 该列包含新值“学习路径（较高级别）（如适用）”。

**新连接**

如果在管理员帐户中禁用了“学习路径”选项，则培训报告将包含以下列：

* **嵌入式路径：** 显示学习计划的名称
* **嵌入式路径ID：** 显示学习计划的ID。
* **嵌入式课程ID：** 显示学习路径内的课程ID。

此外，该报告将包含类型“学习路径（较高级别）”列，适用于注册学习路径的所有学习者。

在“类型”列中，“学习计划”将更名为“学习路径”。 现有连接不会发生更改。 但是，对于新连接，更改将在30天后反映出来。

## 自定义FTP {#custom-ftp}

**先决条件**

>[!NOTE]
>
>要设置自定义FTP，请与您的CSM联系。 CSM将提供设置FTP所需的详细信息。
>
>设置FTP涉及前置时间，并且需要IT支持来允许IP和端口列表，以及在FTP服务器上创建具有特定权限的特定文件夹。

Learning Manager可让您连接到自定义FTP位置。

您的FTP将支持以下功能：

### 数据导入

用户导入操作能让Learning Manager管理员从Learning Manager FTP服务获取员工详细信息，并自动将其导入Learning Manager。 使用此功能，您可以将这些系统生成的CSV放在FTP帐户下的相应文件夹中来集成多个系统。 Learning Manager会拾取CSV文件，将其合并，并根据计划导入数据。 有关更多信息，请参阅计划功能。

**映射属性**

集成管理员可以选择CSV列并将其映射到Learning Manager的组属性。 映射只需进行一次。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以重新配置该映射。

### 数据导出

数据导出允许用户将用户技能和学习者成绩单导出到FTP位置，从而与任何第三方系统集成。

### 计划报告

管理员可以根据公司的要求设置计划任务，Learning Manager应用程序中的用户可以根据计划获得最新消息。 同样，集成管理员可以及时安排技能导出，以便与外部系统集成。 可在Learning Manager应用程序中每天执行同步。

要配置您自己的FTP，请以集成管理员身份登录，然后单击 **[!UICONTROL 自定义FTP]** > **[!UICONTROL Connect]**.

身份验证有两种类型：

![](assets/custom-ftp-authenticationoptions.png)
*自定义FTP身份验证选项*

* **基本：** 在基本身份验证中，您只需提供FTP域URL、用户名和密码。 提供详细信息后，单击“连接”。
* **认证：** 如果客户FTP支持证书身份验证，其便可选择此选项。 单击“生成SSH密钥”后，SSH密钥将下载到您的本地计算机。 打开文件时，密钥显示如下，

![](assets/ssh-public-key.png)
*SSH公钥*

在添加以下详细信息之前，必须将此公钥放入FTP服务器。 在将给定密钥设置为FTP的公钥后，请提供FTP域URL和用户名，然后单击 **Connect** 按钮以设置连接。

完成连接设置后，系统将在ftp位置自动创建用于导入和导出的文件夹。 此后，自定义FTP将提供导入/导出功能。

>[!NOTE]
>
>只能使用SFTP服务器配置自定义FTP连接器。

## ADFS连接器 {#adfsconnector}

建立ADFS连接的先决条件：

* 使用以下URL登录到您的Azure门户：  [https://portal.azure.com/](https://portal.azure.com/) 才能注册应用程序。
* 打开Azure Active Directory。

## 注册应用程序的步骤 {#stepstoregisteryourapplication}

1. 单击Azure Active Directory。 点击 **[!UICONTROL 添加]** > **[!UICONTROL 应用程序注册]**.

   ![](assets/add-app-registration.png)
   *添加应用程序注册*

1. 输入应用程序的名称。

   ![](assets/register-app.png)
   *输入应用程序的名称*

   点击 **[!UICONTROL 注册]**.

1. 在右侧窗格中，选择 **[!UICONTROL 证书和密钥]**.

   ![](assets/add-client-secret.png)

   *选择“证书和密钥”*

1. 添加客户端密钥。

   ![](assets/add-description.png)

   *添加客户端密钥*

1. 为密钥添加描述，并将其到期时间设置为24个月。

   ![](assets/copy-values.png)

   *添加描述*

1. 例如，将值和密钥复制到记事本。

   ![](assets/copy-secret.png)

   *复制值和密钥*

1. 选择 **API权限**.

   ![](assets/click-api-permission.png)

   *包含API权限的左侧窗格*

1. 选择 **添加权限**. 此外，启用该选项 **授予管理员许可**.

   ![](assets/add-permission.png)

   *添加权限*

1. 选择 **Microsoft Graph**.

   ![](assets/ms-graph.png)

   *选择Microsoft Graph*

1. 选择 **应用程序权限**.

   ![](assets/request-api-permission.png)

   *选择应用程序权限*

1. 搜索 *目录* 并选择 **读取目录数据**.

   ![](assets/read-directory-data.png)

   *选择读取目录数据*

1. 输入 *用户* 作为搜索词。

   ![](assets/search-user.png)

   *输入搜索词*

1. 选择 **读取所有用户的完整个人资料**.

   ![](assets/select-read-all.png)

   *选择“读取所有用户的完整个人资料”*

1. 选择 **添加权限**.

   ![](assets/select-add-permission.png)

   *选择“添加权限”*

1. 在AdobeLearning Manager的“ADFS配置”页面中，输入先前获得的客户端ID和客户端密钥。

   点击 **[!UICONTROL Connect]**.

1. 登录到 **portal.azure.com**. 这些值将填充到“租户ID”和“主域”字段中。

### 导入

#### 映射属性

集成管理员可以选择ADFS属性并将其映射到相应的Learning Manager组属性。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

#### 自动导入用户

用户导入操作能让Learning Manager管理员从ADFS获取员工详细信息，并自动将其导入Learning Manager。

#### 过滤用户

Learning Manager管理员可在导入用户前先对其过滤。 例如，Learning Manager管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

要设置ADFS连接器，请联系Learning Manager CSM团队。

## 配置ADFS连接器 {#configureadfsconnector}

1. 在Learning Manager主页，将鼠标悬停在ADFS卡片/缩略图上方。 此时会显示一个菜单。 点击菜单中的连接条目。

   ![](assets/adfs1.jpg)

   *ADFS缩略图*

1. 单击连接以建立新连接。 此时会显示ADFS连接器页面。 输入您要映射的帐户的详细信息。

   ![](assets/adfs2.jpg)

   *建立连接*

1. 如要直接将ADFS用户导入成为Learning Manager内部用户，请使用导入内部用户选项。

   ![](assets/adfs3.jpg)

   *将用户导入Learning Manager*

1. 在映射页面中，您可以在左侧看见Learning Manager的列，在右侧看见ADFS列。 选择映射到Learning Manager列名称的相应列名称。

   ![](assets/adfs4.jpg)

   *映射属性*

1. 如要查看和编辑数据源，作为管理员，单击 **[!UICONTROL 设置]** > **[!UICONTROL 数据源]**.

   已建立的ADFS源将被列出。 如果需要编辑过滤器，请单击 **[!UICONTROL 编辑]**.

   ![](assets/datasource.jpg)
   *数据源设置*

1. 完成导入后，您将收到通知。 要查看或编辑导入日志，请单击 **[!UICONTROL 用户]** > **[!UICONTROL 导入日志]**.

### 删除连接 {#Deleteaconnection-1}

要删除已建立的miniOrange连接，请执行以下步骤。

## Adobe Connect {#connect}

1. 在Adobe Connect上，单击卡上的三个点，然后选择 **Connect**.
1. 单击 **立即配置** “Adobe Connect配置”部分中的链接。
1. 提供公司的Adobe Connect域名和登录凭据。

   Adobe Connect URL示例： ***mycompany.adobeconnect.com***

   您必须提供Adobe连接帐户管理员的电子邮件ID。

   >[!NOTE]
   >
   >Learning Manager仅支持Adobe托管的连接帐户。 示例：.adobeconnect.com。

1. 点击 **[!UICONTROL 集成]**.

   验证电子邮件ID后，Learning Manager会显示消息“Connect成功集成”。 您可以使用Adobe Connect自动查看虚拟教室课程。

   **在Connect帐户管理员对其电子邮件ID进行身份验证后，系统会将请求交予Adobe Connect后端团队进行审批。 通常需要一两天时间才能批准和设置集成。**

   >[!NOTE]
   >
   >Adobe Connect帐户管理员应接受Adobe Connect的使用条款和条件。 如果不接受，则登录身份验证可能会失败。 创建Adobe Connect帐户后，请登录一次帐户。 在首次登录时，会显示条款和条件页面。

### 添加虚拟教室会话信息 {#addvirtualclassroomsessioninformation}

如果虚拟教室课程的作者未提供会话信息，则管理员可提供会话详细信息。

以管理员身份登录，单击虚拟教室课程名称。 单击左侧窗格中的“实例”和“会话详细信息”。  单击“会话详细信息”页面右上角的“编辑”图标以添加会话信息。

通过AdobeLearning Manager和Adobe Connect集成来创建虚拟教室模块或会话，您的Connect帐户应支持多个会议室，提供足够数量的会议室和在线用户同时使用。 这些会议室用于托管Learning Manager虚拟教室模块。 Learning Manager会为其中每个虚拟教室模块或会话动态创建新的Connect会议室。

>[!NOTE]
>
>您必须在AdobeLearning Manager之外单独购买Adobe Connect。

### Adobe Connect长期会议室 {#persistent}

在Adobe Connect中，客户使用他们已在Connect中创建的现有会议室。 Connect中的所有会议室都是长期的，且会议室模板会经过精心设置，以为每个长期会议室提供统一的体验。

您可以使用Adobe Connect中已创建的一个教室创建虚拟教室会话。

Learning Manager还允许学习者通过身份验证进入Connect会议室加入虚拟会话。

![](assets/adobe-connect-authentication.png)
*Adobe Connect身份验证*

使用Adobe Connect创建虚拟教室模块时，可以选择长期教室。 如果 **否** 会像以前一样创建动态会议室。

![](assets/persistent-room-selection.png)
*长期教室选择*

学习者通过Adobe Connect参加并完成课程后，会话的录制以及密码将显示在“学习者”应用程序中。

![](assets/connect-recording.png)
*连接录音*

### 从Adobe Connect导入测验分数 {#quiz-adobe-connect}

将Connect测验数据导入Learning Manager并将其与现有报告工作流程集成，以便Learning Manager用户从报告内的Adobe Connect会话中获取测验数据、用户回答和分数情况，其方法类似于从具有测验功能的自学模块获取数据。

在Connect部分中，如果任何学习者参与了测验课程或开展了支持测验报告的任何交互，则除“完成”以外，系统还会跟踪学习者的所有交互情况。 本课程必须为Connect VC培训。

以下为这一过程的工作流程概要。

**Adobe Connect — 主持人**

* Connect中的主持人负责创建课程并上传包含测验的交互式内容。
* 主机创建 **虚拟教室** 培训并保存VC培训。 主持人可以将上述所建课程链接至VC，也可使用 **共享课程** 在会话期间从Connect应用程序内选择分享课程。

**Learning Manager — 作者**

* 作者在Learning Manager中创建课程，模块类型为 **虚拟教室。**
* 从 **会议系统** 在下拉列表中，选择“连接”作为VC提供方。
* 选择“长期会议”课程，然后选择主持人在Connect中创建的VC教室。 选择讲师。 保存并发布课程。

**Learning Manager — 学习者**

* 课程发布后，学习者便可注册课程。
* 学习者将被重定向到Connect VC会话，Connect主持人允许其访问VC会话。

**Adobe Connect — 主持人**

* 在VC会话中，Connect主持人会共享之前共享的测验。

**Adobe Connect — 学习者**

* 学习者将参加测试，并在完成测试后关闭会话。

**Learning Manager — 学习者**

* 学习者将关闭会话并自动同步会话。

**Learning Manager — 管理员**

* 会话过期后，系统将在计划时段结束后触发导入测验的工作流程。
* 等待系统触发计划并完成处理。 如需从集成管理员端查看处理状态，您可以查看 **执行状态** 在Adobe Connect连接器内查看进度。 执行成功后，状态将更改为 **已完成**.

* 管理员随后选择之前创建的Learning Manager课程。 管理员可查看以下内容：

   * **出席情况与得分**  — 显示最终测验分数和出勤状态。
   * **L2测验分数**

      * **按用户**  — 显示最终测验分数，显示为 **点** 和 **百分比**.
      * **按问题**  — 以报告图表的形式显示测验信息。

## Marketo Engage连接器 {#marketo}

Learning Manager可与营销自动化软件Marketo Engage集成，帮助开展营销活动。

在将新Marketo Engage添加到Learning Manager帐户后，便可通过Marketo Engage连接器为Learning Manager数据库添加（或更新）潜在客户。 其还会将Learning Manager中用户的学习行为（课程注册、课程完成、技能分配和技能成就）与Marketo Engage中相应的潜在客户相关联，并将之作为自定义对象。 营销人员可使用此类信息，根据在Learning Manager中捕获的用户学习行为以及Marketo Engage功能（如“智能列表”）来定位受众。

作为集成管理员，您可以将Learning Manager与Marketo Engage实例集成以自动同步数据。 您可以导出内部用户、培训注册人数以及技能完成事件。 可以按计划执行操作，并可按需配置这些操作。

如需将Learning Manager与您的Marketo帐户集成，您的Marketo帐户需要能够通过API创建架构。

您可以从Marketo应用程序下载以下三份报告：

* 用户报告
* 学习成绩单
* 用户技能报告

创建Marketo Engage连接时，必须提供以下详细信息：

* 连接名称
* 客户端ID
* 客户端密码
* Marketo Engage域

![](assets/marketo-creds.png)

*输入Marketo的凭据*

>[!NOTE]
>
>您可以从Marketo Engage应用程序中获取客户端ID和密钥。 在Marketo应用程序上，您可以从以下位置获取客户端ID和密钥 **启动点** 部分，以及中的Marketo域 **Web服务** 部分。

在 **统一报告** Learning Manager应用程序中的Marketo Engage连接部分，您可以根据以下内容创建营销活动：

* 新用户已添加到Learning Manager
* 新用户已注册课程
* 新用户已完成一门课程
* 学习者已开始学习一种技能
* 学习者已掌握一种技能

与任何其他连接器一样，您可以在本连接器中按需整理并导出数据。

### Marketo Engage中的列映射 {#columnmappinginmarketoengage}

在Marketo中，有两种类型的数据库：

* 潜在客户数据库
* 自定义对象数据库

列映射用于创建潜在客户数据库。 潜在客户即您从“用户报告”中导出的用户。

“用户报告”中的字段皆列于“AdobeLearning Manager”列下方。 Marketo提供的是Marketo列下的字段。 您可以使用这两列将Learning Manager中的任何字段映射到Marketo中的字段。 您可以从Marketo的Learning Manager列加入相关列。 加入列后，即可创建潜在客户数据库。

然后，您可以在Marketo中查看导出的所有用户。

在 **Marketo自定义对象** “Marketo”应用程序中，所有三份报告（“学习者成绩单”、“用户技能”以及“用户报告”）皆列于此。 这些报告包含以下字符串 **&quot;cp_&quot;** 在每个前面。 系统会将每位导出至Marketo的新用户视为潜在客户。

### 事件

将Learning Manager事件中的数据导出至Marketo Engage实例。 选择要按需或按计划导出到Marketo Engage数据库的事件。

* 新用户添加
* 更新用户元数据
* 更新用户活动
* 培训注册
* 自助注册
* 技能完成

## BlueJeans Events {#bj-events}

BlueJeans Events连接器可连接Learning Manager和BlueJeans系统，从而自动同步数据。 使用此连接器，您可以：

* **使用BlueJeans Events设置虚拟会话：** 在BlueJeans中配置新事件，并通过选择相应的BlueJeans事件来在Learning Manager中设置虚拟教室会话。 系统将自动从BlueJeans事件中选择日期和时间详细信息。
* **用户完成情况自动同步：** 通过用户完成情况自动同步流程，Learning Manager管理员可自动获取BlueJeans事件的完成记录。

此新连接器需要一组单独的凭据来进行配置。 现有BlueJeans会议连接器的凭据将不适用于BlueJeans Events连接器。

![](assets/bj-event-connector.png)
*BlueJeans事件连接器的凭据*

### 工作流 {#workflow}

1. BlueJeans Event版主从BlueJeans中创建事件。
1. 作者使用BlueJeans事件URL创建BlueJeans事件课程，该URL将在以后的日期创建。
1. 由于BlueJeans事件具有多个类似的事件标题，因此作者必须将事件与会者URL附加到会议室名称，以便他/她能够选择相应的事件。

   输入事件URL的格式： ***事件名称 — 事件与会者网址***

   对于动态会议室，其行为类似于Adobe Connect的行为。

   ![](assets/bj-eventname.png)
   *BlueJeans Events配置*

1. 作者输入BlueJeans事件网址后，系统将会自动填充日期和时间。
1. 为事件添加讲师。 在BlueJeans事件中，讲师现具有作为演示者的提升权限。

管理员、经理和学习者均可为已创建的课程注册学习者。 注册后，学习者会收到一封电子邮件。 学习者可以登录其Learning Manager帐户来查看计划详细信息并参加课程。

完成课程后，系统会在预定的持续时间后触发完成报告。 管理员可查阅完成报告，检查学习者的出勤情况和得分。

如果BlueJeans Event版主在会话期间启用录制，则会话结束后，可在学习者应用程序中使用该录制内容。

![](assets/bluejeans-event-configure.png)
*BlueJeans Events配置*

启用该复选框时 **获取其他用户创建的事件**，您随后便可以在以下位置添加BlueJeans活动创建者列表： **其他活动创建者** 字段。 在“作者”应用程序中，只有这些用户创建的事件才可通过“预先输入”字段搜索。

如果 **其他活动创建者** 字段留空，所有在BlueJeans中创建的事件都可在作者应用程序中进行搜索。

然后，作者应用程序中的作者从可用事件列表中选择一个事件。 此外，作者还可以向事件添加讲师。 Learning Manager中的这些讲师将成为BlueJeans事件中的主持人。

>[!NOTE]
>
>在BlueJeans Events应用程序中，所有用户必须属于同一企业。

>[!NOTE]
>
>我们添加了一个缓存机制，可改善整体用户体验。 这适用于您选择其他活动创建者的情况。 在此模式下，作者首次搜索事件时即会获取事件。 缓存会持续30分钟，以便作者了解他们必须等待多长时间才能获取新活动。

## Microsoft Teams连接器

Microsoft® Teams®是基于持续聊天的协作平台，可支持文档共享、在线会议和其他业务沟通功能。

AdobeLearning Manager使用虚拟教室连接器与Microsoft Teams会议集成。

Microsoft Teams连接器可连接Learning Manager和Microsoft Teams系统，实现数据自动同步。 以下列表介绍了Microsoft Teams连接器的功能：

**使用Microsoft Teams设置虚拟会话**

此连接器可帮助将您的AdobeLearning Manager帐户与Microsoft Teams帐户集成。 集成后，借助此连接器，Learning Manager中的作者在创建虚拟教室Microsoft Teams时，可使用“模块”作为技术服务提供商。

**允许Microsoft Teams在学习者进入虚拟教室时对其进行身份验证**

会议组织者可允许会议大厅限制用户进入会议，并可控制Microsoft Teams提供的其他会议选项。

**使用用户完成情况自动同步**

通过用户完成情况自动同步流程，Learning Manager管理员可自动获取Teams会议的完成记录和录制URL。

有关详细信息，请参阅  [**在AdobeLearning Manager中安装Microsoft Teams连接器**](install-microsoft-teams-connector.md).

## 培训数据访问

>[!NOTE]
>
>**仅当AdobeLearning Manager作为Adobe Experience Manager的附加项出售时，此特定功能才可用。**

通过Training Data Access连接器，基于AEM Sites的自定义用户界面可检索培训信息并将其呈现给学习者，同时还有助于轻松快速地搜索。

连接器将训练元数据导出到数据存储和检索解决方案。 然后，您可以将基于AEM Sites的界面配置为使用这两个服务来检索培训数据、呈现网页并为学习者提供优化的培训搜索功能。

例如，基于AEM Sites的非登录界面可以使用导出的元数据来帮助学习者搜索、浏览和访问显示培训信息的培训页面

启用此连接器后，您可以构建和渲染基于AEM Sites的网页，并通过AEM为学习者提供自定义体验，学习者可通过公共API（无头LMS）获取课程信息。

### 配置连接器

使用培训数据访问连接器将您的AdobeLearning Manager帐户与数据存储和检索服务以及搜索支持系统集成，以便基于AEM Sites的界面可以检索培训数据、呈现网页并为学习者提供优化的培训搜索功能。

将培训元数据从AdobeLearning Manager导出到数据检索和搜索支持服务。 您还可以创建计划来自动执行这些导出操作。

1. 输入连接的名称和有效的域名。

   ![](assets/create-connection-training-data.png)

   *输入连接和域名*

1. 点击 **[!UICONTROL Connect]**. 将生成基本URL和检索URL。

   ![](assets/base-url.png)

   *生成URL*

1. 启用连接。

   ![](assets/enable-connection.png)

   *启用连接*

1. 在您启用连接后，所有课程、学习路径和证书的图像都将迁移至CDN。
1. 将课程、学习路径和证书的元数据导出到搜索和检索服务中。

### 在AEM中创建网站

**先决条件：** 从安装AEM包  [**GitHub存储库**](https://github.com/adobe/adobe-learning-manager-reference-site/releases/tag/1.0.0).

1. 使用基础和检索URL、客户端ID、客户端密钥和管理员刷新令牌，并在AEM中创建配置。
1. 使用AEM组件创建网站。
1. 发布网站。

有关更多信息，请参阅此文档  [**文档**](../../adobe-learning-manager-integration-aem.md).

### 学习者

发布的网站会显示从面向未登录学习者的搜索服务中检索到的所有迁移课程、证书和学习路径的列表。

学习者单击“课程”、“证书”或“学习路径”后，“概述”页面即会启动。 在该页面上，学习者注册后，必须先登录才能参加课程。

## Adobe Commerce连接器

>[!NOTE]
>
>仅当AdobeLearning Manager作为Adobe Experience Manager的插件出售时，此特定功能才可用。

>[!NOTE]
>
>还可为试用帐户启用此连接器。

AdobeLearning Manager现提供与Adobe Commerce的集成，B2B和B2C客户可以通过该平台打造电子商务体验。

Adobe Commerce是一个可扩展且可伸缩的商务支持解决方案，可让您在单个平台上为B2B和B2C客户打造多渠道商务体验。 使用Adobe Commerce连接器将您的AdobeLearning Manager帐户与Adobe Commerce连接，并在学习平台上实现电子商务功能。

启用此连接器并利用Adobe Commerce功能将学习方案作为付费培训提供。 请注意，您需要先单独购买Adobe Commerce，然后才能使用此连接器将其与AdobeLearning Manager集成。

连接器将培训数据发送到Commerce平台，以便与Adobe Commerce集成，然后学习者就可以在该平台上付款并购买培训。

除了发起购买之外，连接器还从Adobe Commerce收集购买详细信息，AdobeLearning Manager会使用此信息来验证购买并解锁培训访问权限。

**先决条件**

1. 启用  [RabbitMq](https://devdocs.magento.com/cloud/project/services-rabbit.html) 或任何其他报文传送代理。
1. 启用  [CRON](https://devdocs.magento.com/cloud/env/variables-deploy.html#cron_consumers_runner).
1. 对于步骤1和步骤2，请编辑以下文件：

   1. .magento.app.yaml
   1. .magento/services.yaml
   1. .magento.env.yaml

1. 通过自定义模块覆盖选项限制。 此为可选步骤，但强烈建议在处理大型数据集时使用此步骤。
1. 启用页面上的所有异步API。 由于可能有大量数据，因此导出操作是异步进行的。 来自Adobe Commerce的API被调用，同时请求负载也已发送。 请求会将消息推送到队列，且此队列中有一个使用者，该使用者会处理这些消息并在Commerce端创建产品。 默认情况下，Adobe Commerce不提供这种异步处理。 因此必须启用此选项。
1. 在付款成功页面上添加用于返回到ALM的链接。 必须在Adobe Commerce中配置此返回URL。 用于链接的URL。-  `https://learningmanager.adobe.com/app/learner#/postPayment`
1. 将索引从“正在保存”更改为“已计划”。  有关更多信息，请参阅此文档  [KB](https://support.magento.com/hc/en-us/articles/360040227191).
1. 应用以下修补程序。 有关详细信息，请参阅  [应用修补程序](https://devdocs.magento.com/cloud/project/project-patch.html).
1. 快速配置。  云基础架构上的Adobe Commerce需要快速配置，并在预发布环境和生产环境中使用。 有关详细信息，请参阅 [快速设置](https://devdocs.magento.com/cloud/cdn/configure-fastly.html).

### 配置连接器

以集成管理员的身份，在Adobe Commerce连接器中单击 **[!UICONTROL Connect]**.

在配置页面上，输入以下详细信息。 可在Adobe Commerce中获取这些详细信息（授权密钥）。 在Adobe Commerce中创建集成后，可在此处获得凭据。

![](assets/adobe-commerce-configuration.png)
*配置Adobe Commerce连接器*

启用Adobe Commerce连接器连接后，作者可以设置课程、学习路径或证书的价格。

发布课程、学习路径或证书后，学习者可以在学习者应用程序中购买课程。

* **原生Learning Manager：** 学习者可以在Learning Manager中购买课程、学习计划或证书。 仅适用于作者已添加价格的情况。
* **使用AEM站点进行自定义：** 学习者可以从AEM站点购买课程。

### 工作流

Adobe Commerce管理员将Learning Manager配置为集成。

作者将课程、学习路径或证书标记为高级并指定价格。 只有在为帐户启用了电子商务时，才会出现此选项。 有关详细信息，请参阅 [创建课程](../../authors/feature-summary/courses.md).

在Adobe Commerce中同步数据后，才能购买课程或学习路径。

### 将课程导出到Adobe Commerce

作者为各种课程、学习路径或认证设置价格后，您作为集成管理员，会将课程、学习路径或认证导出到Adobe Commerce中。

1. 点击 **[!UICONTROL 导出培训元数据]** > **[!UICONTROL 按需]**.

1. 选择日期。

1. 点击 **[!UICONTROL 执行]**. 成功执行后，所有定价的课程或学习路径都将移至Adobe Commerce。 然后，学习者可以从Learning Manager购买课程。

### 原生学习管理器和Adobe Commerce

#### 学习者

作为学习者，您必须登录才能购买课程、证书或学习路径。

要购买课程，请单击“立即购买”。 您将被重定向到Adobe Commerce以完成购买。 支付成功后，您会看到一条消息，提示您返回Learning Manager并开始课程。 您还必须单独登录Adobe Commerce以完成购买。

从ALM本机版或AEM购买课程、证书或学习路径时，您会收到ALM以及Adobe Commerce发送的电子邮件。

此外，您还可以启用/禁用Adobe Commerce中的电子邮件。

### 带有Adobe Commerce的AEM站点

启用“使用AEM站点自定义”选项后，学习者可以从自定义AEM站点购买课程。

AEM站点将包含Learning Manager的所有元数据，用于启用通过Adobe Commerce进行搜索。 在未登录的情况下，可在Adobe Commerce中获取课程。

可以同时提供登录体验和非登录体验。 未登录的用户可以搜索和浏览课程目录、学习计划和证书。 但是，如果要购买课程，则必须登录到AEM站点。

与本机Learning Manager一样，登录后您可以在购物车中添加课程，然后预览或购买课程。

### 设置Adobe Commerce连接器

#### 先决条件

管理员启用复选框， **为培训启用定价**，在 **“设置”>“常规”** 在管理员应用程序中。 如果启用此选项，作者可以指定培训的价格。 添加Adobe Commerce连接时，将自动选中并强制执行此复选框。

AdobeLearning Manager支持电子商务买卖培训。 在这里，用户可以销售培训以推广其产品的向上销售和交叉销售。

通过集成Adobe Commerce，AdobeLearning Manager可支持购买和销售培训，以便在客户合作伙伴教育情景中提供更完整的客户体验。

此集成的主要目标如下：

* 用户可以通过在AdobeLearning Manager或无头学习界面上销售课程来创造收入。
* 启用与平台的Adobe Commerce集成，以使用Learning Manager的本机应用程序和AEM销售课程。
* 允许Learning Manager的客户以付费课程的形式提供正式学习。
* 学习者可以在决定购买培训之前预览课程。

#### AdobeLearning Manager本机版

**集成管理员**

1. 在“集成管理员”页面上，添加Adobe Commerce连接器。 从在Adobe Commerce中创建的应用程序获取身份验证。
1. 启用Adobe Commerce后，即在AdobeLearning Manager中启用电子商务。 数据根据计划从Learning Manager同步到Adobe Commerce。 数据包括所有培训（付费）以及元数据（用户、技能、作者姓名、价格等）。

>[!NOTE]
>
>AdobeLearning Manager和Adobe Commerce的登录方式不同。

### AEM

在此模式下，学习者将课程从基于AEM的站点中移除，该站点是使用基于AEM的模板和组件构建的。

在AEM站点上，学习者可以使用购物车、添加到购物车按钮、从购物车中删除课程等。

如果用户未登录，他们仍然可以搜索课程目录和查看课程详细信息，但不能购买课程。 作为学习者，您必须登录才能购买课程。

学习者购买课程后，将被重定向到注册状态的课程概述页面，在该页面中，他们可以参加已购买的培训。

#### 无头 — 未登录

学习者可以：

* 在搜索栏中搜索任何培训。
* 按价格范围筛选所有培训。

学习者不能：

* 从概述页面购买课程。
* 预览付费内容。

#### 无头 — 登录

学习者可以：

* 浏览、查看、搜索和筛选付费或免费培训课程。

* 将课程添加到购物车，然后结帐购买。
* 在购物车中添加、更新或删除培训课程。
* 同时购买多个培训课程。
* 在播放器中预览付费课程。
* 查看付款出错的消息。

* 购买课程后，可在电子邮件中查看以附件形式发送的发票。

#### 按需同步

Learning Manager和Adobe Commerce之间的同步每天进行两次。 管理员为电子商务启用帐户后， **使用此连接启用培训元数据导出** 启用此选项后，课程、学习路径和证书的图片会存储在公共CDN中。

如果数据保持不同步，则系统不会为学习者显示定价信息。

对于本机Learning Manager，如果启用了电子商务并完成了Learning Manager与Adobe Commerce之间的同步，则学习者可以查看或搜索免费或付费培训。

对于AEM，没有“立即购买”选项，而只有一个 **添加到购物车** 按钮。 如果未执行同步，此按钮也会保持禁用状态。

#### 常见问题解答

+++哪些课程无法购买？

学习者无法购买重复认证、内容市场培训、已获取的培训、连接器培训、工作辅助和经理批准/指定的课程等课程。
+++

+++“学习者成绩单”和“培训报告”是否有任何更改？

这些报告会显示帐户中所有已购买培训的价格和购买日期。
+++

+++学习者是否可以注册免费培训？

是的，学习者可以注册免费培训。 免费培训在“培训概述”页面上显示“预览并注册”按钮。
+++
