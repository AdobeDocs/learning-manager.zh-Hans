---
description: 了解如何使用连接器将Salesforce与Learning Manager集成，以及如何将FTP与Learning Manager集成并使用FTP连接器自动上传CSV。
jcr-language: en_us
title: Learning Manager连接器
preview: true
source-git-commit: 2317aa899a82abe24d38c4e40a06df3646fde310
workflow-type: tm+mt
source-wordcount: '6293'
ht-degree: 0%

---



# Learning Manager连接器

了解如何使用连接器将Salesforce与Learning Manager集成，以及如何将FTP与Learning Manager集成并使用FTP连接器自动上传CSV。

企业有其他应用程序和系统，可能需要与Learning Manager集成。 连接器是一种实用程序，可帮助执行基于数据的集成，例如从外部系统将数据导入Learning Manager，或从Learning Manager中将数据导出至外部系统。 在2016年7月版中，连接器仅支持从外部系统批量导入Learning Manager用户。

Learning Manager提供Salesforce和FTP连接器。 借助Salesforce连接器，公司的集成管理员可以将其Salesforce应用程序与Learning Manager集成。 作为集成商，您还可以使用FTP连接器将一组用户自动导入到企业应用程序中。

Learning Manager还提供Lynda、getAbstract和Harvard Management System连接器，使学习者能够访问和使用Lynda.com、getAbstract和Harvard ManageMentor中的课程。

继续阅读以了解如何在Learning Manager中配置和使用各连接器。

![](assets/connectorslist.jpg)

## Salesforce连接器 {#sfconnector}

Salesforce连接器可连接Learning Manager和Salesforce帐户，从而自动同步数据。 Salesforce连接器的功能包括：

### 映射属性

集成管理员可以选择Salesforce列并将其映射到相应的Learning Manager组属性。 这是一次性操作。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

### 自动导入用户

用户导入操作能让Learning Manager管理员从Salesforce获取员工详细信息，并自动将其导入Learning Manager。 这一自动化操作在创建并将CSV上传到Learning Manager的过程中能避免手动工作。

### 自动计划

结合使用自动计划功能以及自动用户导入功能可提高工作效率。 Learning Manager管理员可根据公司的需求设置计划。 Learning Manager应用程序中的用户可以根据计划获得最新消息。 可在Learning Manager应用程序中每天执行同步。

### 过滤用户

Learning Manager管理员可在导入用户前先对其过滤。 例如，Learning Manager管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

## 配置Salesforce连接器 {#configuresalesforceconnector}

了解将Learning Manager与Salesforce集成的过程。

### 先决条件 {#prerequisites}

确保您拥有Salesforce公司的URL。 例如，如果您的公司名称是 **myorg**，Salesforce URL可以是 [https://myorg.salesforce.com](https://myorg.salesforce.com/). 这是将Salesforce帐户与Learning Manager连接所需的唯一输入。

此外，请确保您拥有相应的凭据以登录到帐户。

## 创建连接 {#createaconnection}

1. 在Learning Manager主页，将鼠标悬停在Salesforce信息卡/缩略图上方。 此时会显示一个菜单。 点击 **[!UICONTROL Connect]** 菜单中的项。

   ![](assets/mouserover-salesforce.png)

1. 此时会显示一个对话框，提示您输入组织URL。 点击 **[!UICONTROL Connect]** 在提供URL后。
1. 连接成功后，会显示覆盖页面。

## 映射属性 {#mapattributes}

成功建立连接后，您可以将Salesforce列映射到Learning Manager的相应属性。 此步骤为必须操作。

1. 在映射页面中，您可以在左侧看见Learning Manager的列，在右侧看见Salesforce的列。 选择映射到Learning Manager列名称的相应列名称。

   ![](assets/sfdc-map-columns.png)

   左侧显示的Learning Manager列数据是从活动字段中获取的。 该 **管理者** 字段必须映射到电子邮件地址类型的字段。 在可以使用连接器之前，必须映射所有列。

1. 点击 **[!UICONTROL 保存]** 完成映射后。
1. 连接器现在可以使用了。 现已配置的帐户在管理员应用程序中显示为数据源，以便管理员安排导入或用于按需同步。

## 使用Salesforce连接器 {#usingsalesforceconnector}

Salesforce连接器会连接到Salesforce.com来获取已配置用户，并将其添加到Learning Manager。

## Learning Manager FTP连接器 {#ftpconnector}

借助FTP连接器，您可将Learning Manager与任意外部系统集成以自动同步数据。 需要外部系统能够以CSV格式导出数据，并将其放置在Learning Manager FTP帐户内相应文件夹下。 FTP连接器的功能包括：

您还可以使用Box连接器进行数据迁移、用户导入和数据导出。 有关详细信息，请参阅 [Box连接器。](third-party-connectors.md#main-pars_header_302653946)

## 数据导入 {#dataimport}

用户导入操作能让Learning Manager管理员从Learning Manager FTP服务获取员工详细信息，并自动将其导入Learning Manager。 使用此功能，您可以将这些系统生成的CSV放在FTP帐户下的相应文件夹中来集成多个系统。 Learning Manager会拾取CSV文件，将其合并，并根据计划导入数据。 有关更多信息，请参阅计划功能。

**映射属性**

集成管理员可以选择CSV列并将其映射到Learning Manager的组属性。 映射只需进行一次。 映射完成后，相同映射就能用在随后的用户导入中。如果管理员想要为导入用户使用不同的映射，则可以重新配置映射。

## 导出数据 {#exportdata}

数据导出允许用户将用户技能导出到FTP位置，以便与任何第三方系统集成。

## 计划 {#scheduling}

管理员可以根据公司的要求设置计划任务，Learning Manager应用程序中的用户可以根据计划获得最新消息。 同样，集成管理员可以及时安排技能导出，以便与外部系统集成。 可在Learning Manager应用程序中每天执行同步。

## 配置Learning Manager FTP连接器 {#configurecaptivateprimeftpconnector}

了解将Learning Manager与FTP连接器集成的过程。

### 创建连接 {#Createaconnection-1}

1. 在Learning Manager主页，将鼠标悬停在FTP卡/缩略图上方。 此时会显示一个菜单。 点击 **[!UICONTROL Connect]** 菜单中的项。

   ![](assets/mouseover-ftpconnector.png)

1. 此时会显示一个对话框，提示您输入电子邮件ID。 提供负责管理公司Learning Manager FTP帐户的人员的电子邮件ID。 点击 **[!UICONTROL Connect]** 提供电子邮件ID后。
1. Learning Manager会向您发送一封电子邮件，提示用户在第一次访问FTP之前重置密码。 用户必须重置密码，并使用此密码来访问Learning Manager FTP帐户。

   一个Learning Manager帐户仅可创建一个Learning Manager FTP帐户。

   在“概述”页面中，您可以指定集成的连接名称。 从以下选项中选择要执行的操作：

   * 导入内部用户
   * 导出用户技能 — 配置计划
   * 导出用户技能 — 按需

   ![](assets/connectors-overview.png)

## 导入

+++内部用户

使用“导入内部用户”选项，您可以计划自动生成用户导入报告。 生成的报告将作为.CSV文件发送给您。

+++

+++映射属性

成功建立连接后，您便可将FTP文件夹中要放置的CSV文件列映射到Learning Manager的相应属性。 此步骤为必须操作。

1. 在“映射属性”页面中，您可以在左侧看见Learning Manager的预期各列，在右侧看见CSV各列名称。 首先，您会在右侧看到一个空的选择框。 通过单击 **选择文件**.
1. 上述步骤会在右侧的选择下拉列表中填充所有CSV列名称。 选择映射到Learning Manager列名称的相应列名称。

   *经理字段必须映射到电子邮件地址类型的字段。 在可以使用连接器之前，必须映射所有列。*

1. 点击 **[!UICONTROL 保存]** 完成映射后。

   连接器现在可以使用了。 刚配置的帐户现在将显示为管理员应用程序中的一个数据源，以便管理员安排导入或用于按需同步。



+++

+++使用Learning Manager FTP连接器

1. 来自外部系统的CSV文件应放置在以下路径中：

   `code $OPERATION$/$OBJECT_TYPE$/$SUB_OBJECT_TYPE$/data.csv`

   **注：** 在2016年7月版中，仅允许导入用户。 因此，要使用FTP连接器，您必须确保将CSV文件放入以下文件夹：

   `code Home/import/user/internal/*.csv`

1. FTP连接器从CSV文件中获取所有行，因此重要的是，一个CSV文件中与用户对应的行不会出现在任何其他CSV中。
1. 所有CSV均应包含映射中指定的列。
1. 在流程开始之前，文件夹中应存在所有必需的CSV。

在将用户导入Learning Manager时，管理员还需要了解如何在Learning Manager中管理用户。 请参阅 [用户管理帮助](../integration-admin/feature-summary/migration-manual.md#usermanagement) 了解更多信息。

+++

## 导出

+++技能

有两个选项可用于导出用户技能报告。

**[!UICONTROL 用户技能 — 按需]**：可以指定开始日期并使用选项导出报告。报告将从输入的日期提取到现在。

![](assets/user-skills-on-demand.png)

**[!UICONTROL 用户技能 — 配置]**：您可以使用此选项来计划安排报告的提取。 选中“启用计划”复选框，然后指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。

![](assets/user-skills-configure.png)

+++

如要打开已导出文件位于FTP中的“导出”文件夹，请打开“用户技能”页面中提供的“FTP文件夹”链接，如下所示：

![](assets/ftp-folder.png)

自动导出的文件将出现在以下位置 **Home/export/&#42;FTP_location&#42;**

自动导出文件的标题将为 **skill_achieves_&#42;日期自&#x200B;&#42;_收件人_&#42;终止日期&#42;.csv**

![](assets/exported-csvs.png)

## Lynda连接器 {#lyndaconnector}

Lynda.com的企业用户可利用Lynda连接器供其学习者在Learning Manager内找到并学习Lynda课程。 此连接器可以配置为使用您的API密钥定期从Lynda.com上提取课程。 在Learning Manager中创建课程后，用户可以搜索和使用这些课程。 随后即可在Learning Manager中跟踪学习者进度。

### 配置Lynda连接器 {#configurethelyndaconnector}

1. 在集成管理员信息板中，单击Lynda。

   您将看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置Lynda连接器，请单击“连接”。

   在配置此连接器之前，必须配置Exavault FTP帐户。

1. 在连接页面中，指定连接器的名称。 输入Appkey和您连接的密钥。

   您必须联系您的供应商才能获取Appkey和密钥。

1. 单击“保存”。

   配置即会保存，并为您的帐户添加Lynda连接。 现在，您可以从主页单击“管理连接” ，并随时编辑您的配置。

1. 如果已建立连接，请单击“管理连接”查看所有连接。

   在配置此连接器之前，必须为您的帐户启用迁移功能。

1. 单击要编辑的连接。
1. 在左侧窗格中，单击“配置”。 执行以下操作之一：

   * 查看或编辑帐户的详细信息，以及此窗口中的同步计划。 如果要启用此帐户，必须选中“启用连接”复选框。
   * 单击编辑并编辑您的凭据。 单击“重置”可撤消对此字段的更新。
   * 单击“启用计划”以计划同步。 您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。 例如，启用每3天同步一次。

   单击“保存”以保存更改。

   ![](assets/lynda.png)

1. 在左侧窗格中，单击“按需执行”。 您可使用此选项从Lynda导入用户订阅源和其他相关数据。 输入按需执行的“开始日期”，然后单击“执行”以执行同步。 将导入从开始日期到现在的所有数据。

   * 执行期间，如果应用程序在同步过程中停机，您可以单击“禁用对Learning Manager的访问” 。
   * 如果在执行期间单击“启用对Learning Manager的访问”，则同步期间服务不会中断。

   ![](assets/lynda-ondemand.png)

1. 您还可以随时单击左侧窗格中的“执行状态”，按时间顺序查看此连接器所有运行的摘要。 您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   删除并重新创建连接时，连接器的先前运行将再次出现。 在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

   ![](assets/lynda-executionstatus.png)

## getAbstract连接器 {#getabstractconnector}

getAbstract.com的企业用户可使用getAbstract连接器供其学习者找到并使用getAbstract摘要。 连接器可以配置为定期提取使用情况数据，前提条件是要在Learning Manager中创建学习者完成情况记录。 继续阅读以了解如何在Learning Manager中配置此连接器。

### 配置getAbstract连接器 {#configurethegetabstractconnector}

1. 在集成管理员信息板中，单击getAbstract。

   您会看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置getAbstract连接器，请单击“连接”。

   在配置此连接器之前，必须配置Exavault FTP帐户。

   确保与内容提供商共享此FTP凭据以访问订阅源。

1. 在连接名称字段中输入连接的名称。

   在“客户端ID”和“客户端密钥”字段中输入相应的密钥。 您可能需要联系您的供应商以获取此连接器的相应密钥。

   需要密钥才能获取客户端使用的课程的课程元数据。

1. 如果已建立连接，请从主页单击“getAbstract”>“管理连接”以查看和编辑现有配置。

   在配置此连接器之前，必须为您的帐户启用迁移功能。

1. 单击要查看或编辑其配置的连接。

   ![](assets/getabstractschedulepage.png)

1. 在左侧窗格中，单击“配置”。 执行以下操作之一：

   * 查看或编辑帐户的详细信息，以及此窗口中的同步计划。 如果要启用此帐户，必须选中“启用连接”复选框。
   * 单击编辑并编辑您的凭据。 单击“重置”可撤消对此字段的更新。
   * 单击“启用计划”以计划同步。 您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。 例如，启用每3天同步一次。

1. 单击“保存”。

   配置即会保存，并为您的帐户添加getAbstract连接。

1. 在左侧窗格中，单击“按需执行”。 您可使用此选项从getAbstract导入用户订阅源和其他相关数据。 输入按需执行的“开始日期”，然后单击“执行”以执行同步。 将导入从开始日期到现在的所有数据。

   * 执行期间，如果应用程序在同步过程中停机，您可以单击“禁用对Learning Manager的访问” 。
   * 如果在执行期间单击“启用对Learning Manager的访问”，则同步期间服务不会中断。

1. 您还可以随时单击左侧窗格中的“执行状态”，按时间顺序查看此连接器所有运行的摘要。 您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   删除并重新创建连接时，连接器的先前运行将再次出现。 在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

   要使任何类型的同步起作用，必须确保getAbstract FTP文件夹中存在用户订阅源以匹配同步中指定的日期。

   请参阅以下Excel工作表，该工作表是getAbstract的用户订阅源文件的样本。 文件名应采用以下格式：** report_export_yyyy_MM_dd_HHmmss.xlsx**或 **report_export_yyyy_MM_dd.xlsx**.
   [getAbstract用户订阅源样本Excel表](assets/report-export-20170401175342.xlsx)

## Harvard ManageMentor连接器 {#hmmconnector}

Harvard ManageMentor的企业用户可以使用Harvard ManageMentor连接器供其学习者找到并学习Harvard ManageMentor课程。 此连接器可帮助在Learning Manager中创建课程，并可配置为定期获取学习者进度数据。 要配置此连接器，请执行以下步骤：

### 配置Harvard ManagerMentor连接器 {#configuretheharvardmanagermentorconnector}

1. 在集成管理员信息板中，单击Harvard ManageMentor。

   您会看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置Harvard ManageMentor连接器，请单击“连接”。

   在配置此连接器之前，还必须配置Exavault FTP帐户。

   确保与内容提供商共享此FTP凭据以访问订阅源。

1. 在连接名称字段中，输入连接的名称。 单击“连接”以保存此连接。
1. 如果已建立连接，请从主页单击“Harvard ManageMentor”>“管理连接”。 单击要编辑的连接以编辑现有配置。

   在配置此连接器之前，必须为您的帐户启用迁移功能。

   ![](assets/hmm.png)

1. 在左侧窗格中，单击“配置”。 执行以下操作之一：

   * 查看或编辑帐户的详细信息，以及此窗口中的同步计划。 如果要启用此帐户，必须选中“启用连接”复选框。
   * 单击“启用计划”以计划同步。 您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。 例如，启用每3天同步一次。

1. 在左侧窗格中，单击“按需执行”。 您可使用此选项从Harvard ManageMentor导入用户订阅源和其他相关数据。 输入按需执行的“开始日期”，然后单击“执行”以执行同步。 将为此连接导入从开始日期到现在的所有数据。

   * 执行期间，如果应用程序在同步过程中停机，您可以单击“禁用对Learning Manager的访问” 。
   * 如果在执行期间单击“启用对Learning Manager的访问”，则同步期间服务不会中断。

   如果要每隔几天自动执行同步，请在“重复天数”字段中指定天数。 同步可确保您的帐户使用Harvard ManageMentor的最新版摘要和摘要进行更新。

1. 您还可以随时单击左侧窗格中的“执行状态”，按时间顺序查看此连接器所有运行的摘要。 您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   删除并重新创建连接时，连接器的先前运行将再次出现。 在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

   要使同步成功，您必须确保Harvard ManageMentor FTP文件夹中至少存在以下文件中的一个：

   hmm12_metadata.xlsx：此文件提供Harvard ManageMentor连接器的课程元数据。 确保在上载文件时遵循命名约定。

   client_hmm12_20150125.xlsx：这是Harvard ManageMentor连接器的用户订阅源。 必须遵循的文件命名约定是 **client_hmm12_yyyyMMdd.xlsx。**

   请参阅以下两个用于此连接器的用户订阅源和课程订阅源文件样本：
   [Harvard ManageMentor连接器的课程元数据文件](assets/hmm12-metadata.xlsx) [Harvard ManageMentor连接器的用户订阅源](assets/client-hmm12-20170304.xlsx)

## Workday连接器 {#workdayconnector}

借助Workday连接器，您可以将Learning Manager与Workday租户集成以自动同步数据。

### 导入

#### 映射属性

集成管理员可以选择Workday列并将其映射到相应的Learning Manager组属性。 这是一次性的操作。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

#### 自动导入用户

用户导入操作能让Learning Manager管理员从Workday获取员工详细信息，并自动将其导入Learning Manager。

#### 过滤用户

Learning Manager管理员可在导入用户前先对其过滤。 例如，Learning Manager管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

## 导出

用户技能导出允许用户自动将用户技能导出到Workday。

使用同一Workday帐户无法同时导出多个Learning Manager帐户中的技能。

## 计划 {#Scheduling-1}

管理员可以根据公司的要求设置计划任务，Learning Manager应用程序中的用户可以根据计划获得最新消息。 同样，集成管理员可以及时安排技能导出，以便与外部系统集成。 可在Learning Manager应用程序中每天执行同步。

## 配置Workday连接器 {#configureworkdayconnector}

**前提条件**：请求公司的Workday管理员创建具有ISU_Permissions文档中定义的权限的集成系统用户(ISU)。 从下面的链接下载副本。
[下载集成系统用户(ISU)安全性的副本。](assets/isu-permissions-v1.pdf) 了解将Learning Manager与Workday连接器集成的过程。

1. 在Learning Manager主页中，将鼠标悬停在Workday磁贴上。 此时会显示一个菜单。 点击 **[!UICONTROL Connect]** 菜单中的项。

   ![](assets/workday-tile.png)

1. 此时会显示一个对话框，提示您输入新连接的凭据。 以下是在建立连接之前需要输入的字段。

   * 连接名称：根据您的喜好提供一个连接名称。
   * 主机URL：集成管理员可以从相应的Workday管理员获取主机URL详细信息。
   * 租户：租户是贵公司的内部人员。 您的Workday管理员将为您提供租户详细信息。
   * 用户名和密码：Workday管理员创建具有所需安全权限的集成系统用户(ISU)，并将其共享给集成管理员。

   注意：Learning Manager使用Workday API版本28.1。

   ![](assets/configure-connector.png)

1. 在所有相关字段中输入信息后，单击“连接”。

   您也可以将多个Workday连接同步到您的Learning Manager帐户。

在“概述”页面中，您可以指定集成的连接名称。 从以下选项中选择要执行的操作：

* 导入内部用户
* 导出用户技能 — 配置计划
* 导出用户技能 — 按需

![](assets/overview.png)

## 导入

### 映射属性 {#MapAttributes-1}

您可以使用Workday连接器集成Learning Manager和Workday，以自动同步数据。 您可以将所有活动用户从Workday导入到Learning Manager。 可以从各种数据源（包括FTP和Salesforce）导入用户。

Learning Manager和Workday中的用户属性需要在导入用户之前进行映射。 在“概述”页面中，使用“导入”下的“内部用户”选项来映射属性。

在“Adobe学习管理器”列下输入Adobe学习管理器凭据。 使用下拉列表为Workday下的列选择正确的凭据。

目前，Learning Manager支持从Workday导入44个用户属性。 使用Learning Manager中的“活动字段”添加其他属性。

![](assets/map-attributes.png)

Workday有四个级别，而Learning Manager有两个级别。 Workday中的四个级别是技能配置文件类别、技能配置文件、技能项目类别和技能项目。 您的技能名称以及Learning Manager的级别将一同映射到Workday的技能项目之下。

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

## 导出

您可以将用户习得的所有技能从Learning Manager导出到Workday。 请注意，系统仅会导出所有活动用户技能，Learning Manager不导出已弃用的技能。 您还可以将多个Learning Manager帐户连接到同一个Workday连接器。 如果两个Learning Manager帐户中的技能名称相同，则它们会被映射到Workday中的相同技能。 如果两个Learning Manager帐户使用的是同一个Workday帐户，则建议先更新所有Learning Manager帐户中的技能名称，然后再更新Workday中的技能。

+++用户技能 — 配置

此选项允许您计划安排报告的提取。 确保已启用“使用此连接启用用户技能导出”复选框。 选中“启用计划”复选框，然后指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。 选中“启用计划”复选框，然后输入开始日期、时间和几天后重复。 完成后，单击“保存”。

![](assets/configure-schedule.png)

+++

+++用户技能 — 按需

您可以使用该选项指定开始日期并导出报告。 将提取从输入的日期到现在的报告。 输入您要开始生成报告的日期，然后单击“执行”。

![](assets/on-demand-report.png)

+++

+++用户技能 — 执行状态

在此可查看所有任务的摘要并获取其状态报告。 您可以通过单击错误报告链接下载错误报告。

![](assets/execution-status.png)

+++

## miniOrange连接器 {#miniorangeconnector}

借助miniOrange连接器，您可以将Learning Manager与miniOrange租户集成以自动同步数据。

### 导入

#### 映射属性

集成管理员可以选择miniOrange属性并将其映射到相应的Learning Manager组属性。 这是一次性的操作。 映射完成后，相同映射就能用在随后的用户导入中。 如果管理员想要针对导入用户使用不同的映射，则可以对其进行重新配置。

#### 自动导入用户

用户导入操作能让Learning Manager管理员从miniOrange获取员工详细信息，并自动将其导入Learning Manager。

#### 过滤用户

Learning Manager管理员可在导入用户前先对其过滤。 例如，Learning Manager管理员可以选择导入一位或多位经理属下层次结构中的所有用户。

要设置miniOrange连接器，请联系Learning Manager CSM团队。

## 配置miniOrange连接器 {#configureminiorangeconnector}

1. 在Learning Manager主页，将鼠标悬停在miniOrange卡/缩略图上方。 此时会显示一个菜单。 点击  **[!UICONTROL Connect]** 选项。

   ![](assets/miniorange-tile.png)

1. 单击连接以建立新连接。 出现miniOrange连接器页面。 输入您要映射的帐户的详细信息。

   ![](assets/establish-connection.png)

1. 如果要直接将miniOrnage用户导入成为Learning Manager内部用户，请使用 **[!UICONTROL 导入内部用户]** 选项。

   ![](assets/import-users.png)

1. 在映射页面中，您可以在左侧看见Learning Manager的列，在右侧看见miniOrnage的列。 选择映射到Learning Manager列名称的相应列名称。

   ![](assets/map-attributes.png)

1. 如要查看和编辑数据源，作为管理员，单击 **[!UICONTROL 设置>数据源]**.

   已建立的miniOrange源将被列出。 如果需要编辑过滤器，请单击 **[!UICONTROL 编辑]**.

   ![](assets/data-source.png)

1. 完成导入后，您将收到通知。 要查看或编辑导入日志，请单击 **[!UICONTROL 用户>导入日志。]**

### 删除连接 {#deleteaconnection}

按照以下步骤删除已建立的miniOrange连接。

## BlueJeans连接器 {#bluejeansconnector}

您现在可以将Learning Manager与BlueJeans连接器集成，并使用BlueJeans托管课程。 BlueJeans可让您启动音频和视频会议呼叫、视频聊天和网络研讨会。

请按照以下步骤设置并使用连接器。

1. 在Learning Manager主页，将鼠标悬停在BlueJeans卡/缩略图上方。 此时会显示一个菜单。 点击  **[!UICONTROL Connect]** 选项。

   ![](assets/miniorange.png)

1. BlueJeans连接器页面即会打开。 在相应字段中输入帐户的详细信息，以集成Learning Manager和BlueJeans来同步用户订阅源。 您可以从BlueJeans帐户的管理员处获取详细信息。

   ![](assets/bluejeans-connecotrpage.png)

   作为学习者，当启用连接器时，应使用您的Learning Manager帐户所用的电子邮件ID来启用将用户订阅源发送回Learning Manager。

1. 建立连接后，作为作者，即可使用BlueJeans作为会议系统创建VC课程。

   ![](assets/conferencing-systems.png)

1. 管理员、经理和学习者均可为已创建的课程注册学习者。 注册后，学习者会收到一封电子邮件。 学习者可以登录其Learning Manager帐户来查看计划详细信息并参加课程。
1. 课程完成后，完成报告会发送至Learning Manager。 管理员可查阅完成报告，检查学习者的出勤情况和得分。

   ![](assets/-attendence-and-scoringreport.png)

## Box连接器 {#boxconnector}

借助BOX连接器，您可以将Learning Manager与任意外部系统集成以自动同步数据。 需要外部系统能够以CSV格式导出数据，并将其放置在Learning Manager Box帐户内相应文件夹下。 Box连接器功能如下：

您还可以使用FTP连接器进行数据迁移、用户导入和数据导出。 欲知更多信息， [Learning Manager FTP连接器。](third-party-connectors.md#main-pars_header_1427405935)

## 数据导入 {#DataImport-1}

用户导入操作能让Learning Manager管理员从Learning Manager Box服务获取员工详细信息，并自动将其导入Learning Manager。 使用此功能，您可以将这些系统生成的CSV放在Box帐户下的相应文件夹中来集成多个系统。 Learning Manager会拾取CSV文件，将其合并，并根据计划导入数据。 有关更多信息，请参阅计划功能。

**映射属性**

集成管理员可以选择CSV列并将其映射到Learning Manager的组属性。 映射只需进行一次。 映射完成后，相同映射就能用在随后的用户导入中。如果管理员想要为导入用户使用不同的映射，则可以重新配置映射。

## 数据导出 {#dataexport}

数据导出允许用户将用户技能导出到Box位置，以便与任何第三方系统集成。

## 计划报告 {#schedulereports}

管理员可以根据公司的要求设置计划任务，Learning Manager应用程序中的用户可以根据计划获得最新消息。 同样，集成管理员可以及时安排技能导出，以便与外部系统集成。 可在Learning Manager应用程序中每天执行同步。

## 配置Box连接器 {#configureboxconnector}

了解将Learning Manager与Box连接器集成的过程。

1. 在Learning Manager主页，将鼠标悬停在Box卡/缩略图上方。 此时会显示一个菜单。 单击菜单中的“连接”条目。

   ![](assets/screen-shot-2017-10-25at54426pm.png)

1. 此时会显示一个对话框，提示您输入电子邮件ID。 提供负责管理公司Learning Manager Box帐户的人员的电子邮件ID。 提供电子邮件ID后，单击“连接” 。

1. Learning Manager会向您发送一封电子邮件，提示用户在第一次访问Box之前重置密码。 用户必须重置密码，并使用此密码来访问Learning Manager Box帐户。

   一个Learning Manager帐户仅可创建一个Learning Manager Box帐户。

   在“概述”页面中，您可以指定集成的连接名称。 从以下选项中选择要执行的操作：

   * 导入内部用户
   * 导出用户技能 — 配置计划
   * 导出用户技能 — 按需

## 导入

+++内部用户

使用“导入内部用户”选项，您可以计划自动生成用户导入报告。 生成的报告将作为.CSV文件发送给您。

+++

+++映射属性

成功建立连接后，您便可将Box文件夹中要放置的CSV文件列映射到Learning Manager的相应属性。 此步骤为必须操作。

1. 在“映射属性”页面中，您可以在左侧看见Learning Manager的预期各列，在右侧看见CSV各列名称。 首先，您会在右侧看到一个空的选择框。 点击“选择文件”，导入任一模板CSV。

1. 上述步骤会在右侧的选择下拉列表中填充所有CSV列名称。 选择映射到Learning Manager列名称的相应列名称。

   *经理字段必须映射到电子邮件地址类型的字段。 在可以使用连接器之前，必须映射所有列。*

1. 完成映射后单击“保存” 。

   连接器现在可以使用了。 刚配置的帐户现在将显示为管理员应用程序中的一个数据源，以便管理员安排导入或用于按需同步。

+++

+++使用Learning Manager Box连接器

1. 来自外部系统的CSV文件应放置在以下路径中：

   `code $OPERATION$/$OBJECT_TYPE$/$SUB_OBJECT_TYPE$/data.csv`

   **注：** 在2016年7月版中，仅允许导入用户。 因此，如要使用Box连接器，您必须确保已将CSV文件放入以下文件夹：\
   `code Home/import/user/internal/*.csv`

1. Box连接器从CSV文件中获取所有行，因此，务必确保一个CSV文件中与用户对应的行不出现在任何其他CSV中。
1. 所有CSV均应包含映射中指定的列。
1. 在流程开始之前，文件夹中应存在所有必需的CSV。

在将用户导入Learning Manager时，管理员还需要了解如何在Learning Manager中管理用户。 请参阅 [用户管理帮助](../integration-admin/feature-summary/migration-manual.md#usermanagement) 了解更多信息。

+++

## 导出

+++技能

有两个选项可用于导出用户技能报告。

用户技能 — 按需：您可以指定开始日期并使用选项导出报告。报告将从输入的日期提取到现在

**[!UICONTROL 用户技能 — 配置]**：您可以使用此选项来计划安排报告的提取。 选中“启用计划”复选框，然后指定开始日期和时间。 您还可以指定生成和发送报告的时间间隔。

+++

如要打开已导出文件位于Box中的“导出”文件夹，请打开“用户技能”页面中提供的“Box文件夹”链接，如下所示：

自动导出的文件将出现在以下位置 **Home/export/&#42;Box_location&#42;**

自动导出文件的标题将为 **skill_achieves_&#42;日期自&#x200B;&#42;_收件人_&#42;终止日期&#42;.csv**

由Learning Manager团队共享的访问权限和Box文件夹中的内容应由客户管理。  另请注意，文件夹中的内容将物理存储在法兰克福地区。

## LinkedInLearning连接器 {#linkedinlearningconnector}

LinkedIn.com的企业用户可利用LinkedInLearning连接器供其学习者在Learning Manager内找到并学习课程。 此连接器可以配置为使用您的API密钥定期提取课程。 在Learning Manager中创建课程后，用户可以搜索和使用这些课程。 随后即可在Learning Manager中跟踪学习者进度。

### 配置LinkedIn连接器 {#configurelinkedinconnector}

1. 在集成管理员信息板中，单击LinkedInLearning。

   您将看到三个选项磁贴：“入门”、“连接”和“管理连接”。

1. 如果您是第一次配置LinkedInLearning连接器，请单击“连接”。

   在配置此连接器之前，必须配置Exavault FTP帐户。

1. 在连接页面中，指定连接器的名称。 输入Appkey和您连接的密钥。

   您必须联系您的供应商以获取Appkey和密钥。

1. 单击“保存”。

   配置即会保存，并为您的帐户添加LinkedInLearning连接。 现在，您可以从主页单击“管理连接” ，并随时编辑您的配置。

1. 如果已建立连接，请单击“管理连接”查看所有连接。

   在配置此连接器之前，必须为您的帐户启用迁移功能。

1. 单击要编辑的连接。
1. 在左侧窗格中，单击“配置”。 执行以下操作之一：

   * 查看或编辑帐户的详细信息，以及此窗口中的同步计划。 如果要启用此帐户，必须选中“启用连接”复选框。
   * 单击编辑并编辑您的凭据。 单击“重置”可撤消对此字段的更新。
   * 单击“启用计划”以计划同步。 您可以输入开始时间和日期，然后以天为单位输入同步计划的频率。 例如，启用每3天同步一次。

   单击“保存”以保存更改。

1. 在左侧窗格中，单击“按需执行”。 您可使用此选项从LinkedIn导入用户订阅源和其他相关数据。 输入按需执行的“开始日期”，然后单击“执行”以执行同步。 将导入从开始日期到现在的所有数据。

   * 执行期间，如果应用程序在同步过程中停机，您可以单击“禁用对Learning Manager的访问” 。
   * 如果在执行期间单击“启用对Learning Manager的访问”，则同步期间服务不会中断。

1. 您还可以随时单击左侧窗格中的“执行状态”，按时间顺序查看此连接器所有运行的摘要。 您可以查看同步的开始日期和持续时间、同步类型（是否为按需同步）和同步状态（同步是在进行还是已完成）。

   删除并重新创建连接时，连接器的先前运行将再次出现。 在删除连接之前，您可以查看所有运行。

   您只能为最新同步执行重新运行。

