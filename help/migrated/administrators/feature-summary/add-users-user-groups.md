---
description: 了解如何在 Adobe Learning Manager 应用程序中添加用户或用户组。
jcr-language: en_us
title: 添加用户和创建用户组
contentowner: manochan
exl-id: 7df98f2b-c422-4733-8ce4-5489506d4fdf
source-git-commit: f964dd3f1adeadb76f4843c9af229ce5f09afde1
workflow-type: tm+mt
source-wordcount: '4231'
ht-degree: 58%

---

# 添加用户和创建用户组

了解如何在 Adobe Learning Manager 应用程序中添加用户或用户组。


<!--![](assets/user-mgmt-new.png)-->

## 管理用户组

>[!INFO]
>
>在本培训中，您将了解如何按姓名、电子邮件ID以及合并多个自动生成的用户组来创建用户组。<br><br>[![按钮](assets/launch-training-button.png)](https://learningmanager.adobe.com/app/learner?accountId=98632&amp;sdid=QLD1P6BS&amp;mv=display&amp;mv2=display#/course/7555694)</br></br>

<!--[Launch training](https://learningmanager.adobe.com/app/learner?accountId=98632&sdid=QLD1P6BS&mv=display&mv2=display#/course/7555694)-->

<!--In this training, you will learn how to create a user group by names, email IDs, and combining multiple auto-generated user groups.-->

<!--[![button](assets/launch-training-button.png)](https://learningmanager.adobe.com/app/learner?accountId=98632&sdid=QLD1P6BS&mv=display&mv2=display#/course/7555694)-->

如果您无法启动培训，请写入<almacademy@adobe.com>。

## 概述 {#overview}

在 Adobe Learning Manager 中，您可以承担以下角色：

* **管理员：**&#x200B;管理员定义公司的培训策略。管理员可以添加学习者，为学习者搜索所需技能、管理和分配课程，创建学习计划、认证和学习计划，以及管理整个公司的报告。
* **作者：**&#x200B;作者是教学设计师和内容创作者。作者可以向 Adobe Learning Manager 添加模块和课程。
* **经理：**&#x200B;经理负责管理团队的学习活动。经理可以指定团队成员参加课程，批准团队成员的请求，并提供有关团队成员完成培训后的绩效反馈。管理人员还可以查看其团队的报告以跟踪其绩效。
* **学习者：**&#x200B;学习者可以访问分配给他们的课程、学习计划和认证。学习者还可以使用目录浏览所有可用课程，并自行注册课程、学习计划或认证。

作为管理员，您可以通过以下三种方式添加用户：

* 内部
* 外部
* 用户组

## 添加单个用户 {#addasingleuser}

使用单个用户选项将内部学习者添加到Adobe Learning Manager。

>[!INFO]
>
>在本培训中，您将了解如何将内部学习者添加到Adobe Learning Manager。<br><br>[![按钮](assets/launch-training-button.png)](https://learningmanager.adobe.com/app/learner?accountId=98632&amp;sdid=QGMZPB2T&amp;mv=display&amp;mv2=display#/course/7555534)</br></br>


如果您无法启动培训，请写入<almacademy@adobe.com>。

要添加用户，

1. 以管理员身份登录 Adobe Learning Manager。
1. 在主页上，单击&#x200B;**[!UICONTROL “添加用户”]**。在此页面上，您可以使用 CSV 一次添加单个用户或多个用户。您还可以为内部员工创建自行注册链接或创建外部学习者个人资料。
1. 要添加单个用户，请单击&#x200B;**[!UICONTROL 右上角的添加]**，然后选择“**[!UICONTROL 单个用户]**”选项。

1. 要添加单个用户，请单击&#x200B;**[!UICONTROL 右上角的添加]**，然后选择“**单个用户**”选项。


   ![](assets/single-user.png)
   *添加单个内部用户*

1. 在&#x200B;**[!UICONTROL “添加用户”]**&#x200B;对话框中，输入学习者的详细信息。对于&#x200B;**[!UICONTROL “管理员的名称”]**&#x200B;字段，选择系统中现有用户的名称。

   ![](assets/manager.png)
   *“添加用户”对话框*

1. 要在 Adobe Learning Manager 中添加新用户，请单击&#x200B;**[!UICONTROL “添加”]**。添加用户后，用户会收到验证邮件。然后，学习者激活帐户并开始使用 Adobe Learning Manager。如果您需要向Learning Manager帐户添加有限数量的学习者，此工作流程非常有用。 但是，如果您计划注册一个大型公司的所有员工，您可以一次性完成添加。有关更多信息，请参阅下一节。

## 批量添加用户 {#addusersinbulk}

### 管理用户

在本培训中，您将了解如何分配和删除角色、发送欢迎电子邮件以及删除和清除用户。

[![按钮](assets/launch-training-button.png)](https://learningmanager.adobe.com/app/learner?accountId=98632&amp;sdid=4X3B8VJ2&amp;mv=display&amp;mv2=display#/course/7555586)

如果您无法启动培训，请写入<almacademy@adobe.com>。

通常，大多数公司使用人力资源管理系统 (HRMS) 来维护所有员工记录，例如，职务、位置、加入日期或员工层级。您可以将此数据导出为 CSV 格式。要导入 CSV，请按以下步骤操作：


1. 单击右上角的&#x200B;**[!UICONTROL “添加”]**，然后选择&#x200B;**[!UICONTROL “上传 CSV”]**&#x200B;选项。

   ![](assets/upload-a-csv.png)
   *上传CSV以批量添加用户*

1. 您上传的 CSV 包含字段，如下所示：

   ![](assets/csv.png)
   *CSV的结构*

   您必须维护主CSV，并在主CSV上执行所有添加和删除操作。 主 CSV 包含以下字段：

   * 名称&#42;
   * 电子邮件&#42;
   * 配置文件
   * 经理

   (&#42;)必填字段。

1. 单击&#x200B;**[!UICONTROL “上传 CSV”]**&#x200B;选项后，将显示以下对话框。

   ![](assets/upload-a-csv-dialog.png)
   *上传CSV对话框*

1. 选择 CSV 或拖放文件。选择文件后，使用CSV文件中的数据字段映射数据字段。 单击所需的下拉列表，然后选择正确的字段。

   ![](assets/map-data-fields.png)
   *映射CSV中的字段*

1. 要开始导入用户，请单击&#x200B;**[!UICONTROL “保存”]**。您可以看到确认消息。

   ![](assets/save-csv.png)
   *成功上传CSV的确认消息*

1. 新用户随即会添加到您的 Adobe Learning Manager 帐户中。要选择新用户，请选中名字旁边的复选框，以便选择每个用户。

   ![](assets/select-new-users.png)
   *已添加新用户*

>[!NOTE]
>
>有关详细信息，请参阅常见问题解答，[批量添加用户](../add-users-in-bulk.md)。

选择用户后，您可以执行以下操作：

## 注册用户 {#registerauser}

选择用户后，单击右上角的&#x200B;**[!UICONTROL “操作”]**，然后单击&#x200B;**[!UICONTROL “注册”]**。

所选用户会收到一封“欢迎”电子邮件。如果学习者已拥有一个现成的 Adobe ID，则可以单击此链接。如果他们没有现成的Adobe ID，他们可以继续并单击“欢迎”链接以创建Adobe ID，并将其链接到其Learning Manager帐户。

## 分配角色 {#assignarole}

将学习者添加到 Adobe Learning Manager 帐户后，如果要更改其角色，请单击页面右上角的“操作”。选择&#x200B;**[!UICONTROL 分配角色]**&#x200B;选项。您可以在此处决定是否要为学习者提供“作者”访问权限或“管理员”权限。在您分配角色后，该学习者具有该帐户的“作者”访问权限，可以添加模块和创建课程。

![](assets/assign-a-role.png)
*为用户分配角色*

## 删除角色 {#removearole}

您还可以删除用户的“作者”或“管理员”访问权限。选择一个或多个学习者，单击&#x200B;**[!UICONTROL “操作”]**，然后选择&#x200B;**[!UICONTROL “删除角色”]**。选择一个选项，例如&#x200B;**[!UICONTROL 删除作者]**，即可撤消作者对该学习者的访问权限。

>[!NOTE]
>
>您无法手动将“经理”角色分配给系统中的某个人。当在“经理”仪表板下添加一个或多个员工时，这些员工会自动获得经理仪表板的访问权限。

## 删除用户 {#deleteauser}

要删除用户，请单击&#x200B;**[!UICONTROL “操作”]**，然后选择&#x200B;**[!UICONTROL “删除用户”]**。在确认对话框中，单击&#x200B;**[!UICONTROL “是”]**，学习者将被删除。

![](assets/delete-a-role.png)
*删除用户的确认消息*

## 编辑用户 {#editauser}

在用户列表中，选择一个用户，然后单击该用户。在用户详细信息上，单击&#x200B;**[!UICONTROL 编辑]** ( ![](assets/edit-pen.png))按钮。 在&#x200B;**[!UICONTROL “编辑用户”]**&#x200B;对话框中，进行必要的编辑并保存更改，单击&#x200B;**[!UICONTROL 保存]**。

![](assets/edit-user.png)
*“编辑用户”对话框*

## 活动字段

### 管理用户属性

>[!INFO]
>
>在本培训中，您将学习如何添加、自定义和配置活动字段。<br><br>[![按钮](assets/launch-training-button.png)](https://learningmanager.adobe.com/app/learner?accountId=98632&amp;sdid=55KD8M1Z&amp;mv=display&amp;mv2=display#/course/7555741)</br></br>

如果您无法启动培训，请写入<almacademy@adobe.com>。

Adobe Learning Manager保留用户属性及其值的大小写区分性。 **例如**，区分大小写时，用户属性为“location”，其值“PARIS”将保留并以相同方式显示。 如果出现任何问题，管理员现在可以编辑属性名称和值，以更正任何有关大小写的错误。

管理员可以通过访问&#x200B;**[!UICONTROL 管理员应用]** > **[!UICONTROL 用户]** > **[!UICONTROL 用户组]**&#x200B;并单击组名称来执行此操作。

管理员可以通过用户界面为学习者添加和更新允许的属性值。

活动字段的类型：

* 可分组：根据“值”对学习者进行分组
* 可报告：根据活动字段创建报告用户组
* 可导出：导出为用户组报告时可以看到这些字段。

## 创建自注册链接 {#createaselfregistrationlink}

您还可以让公司中的员工自行注册为 Adobe Learning Manager 帐户的学习者，而无需获得您以管理员身份提供的帮助。管理员可以创建自行注册链接并与员工共享，员工可以使用其Adobe凭据进一步注册Learning Manager。

在页面右上角，单击“**[!UICONTROL 添加]**”，然后选择“**[!UICONTROL 自行注册]**”。


![](assets/self-registration.png)
*创建自行注册为学习者的链接*

出现&#x200B;**[!UICONTROL “添加自行注册个人资料”]**&#x200B;对话框。为此个人资料命名。然后添加经理的姓名。务必确认经理已经是Learning Manager的注册学习者。

![](assets/add-self-registrationprofile.png)
*为自行注册添加个人资料*

单击&#x200B;**[!UICONTROL “保存”]**&#x200B;后，将生成一个 URL，您可以与学习者共享该 URL，以便其单击 URL 并自行注册。

## 注册外部学习者 {#enrollexternallearners}

在 Adobe Learning Manager 中，您还可以为具有有限访问权限的外部合作伙伴或机构创建注册链接，并为他们提供学习材料。

内部和外部注册之间存在一些差异。

<table>
 <tbody>
  <tr>
   <td>
    <p><b>内部用户</b></p></td>
   <td>
    <p><b>外部用户</b></p></td>
  </tr>
  <tr>
   <td>
    <p>使用 Adobe ID 或 SSO 凭据登录。</p></td>
   <td>
    <p>使用任何电子邮件 ID 登录。</p></td>
  </tr>
  <tr>
   <td>
    <p>游戏功能可用。</p></td>
   <td>
    <p>游戏功能可用。 管理员必须在“游戏”设置中为外部学习者启用游戏。</p></td>
  </tr>
  <tr>
   <td>
    <p>学习者等级可用。</p></td>
   <td>
    <p>学习者等级不可用。</p></td>
  </tr>
 </tbody>
</table>

要注册外部用户，请执行以下步骤：

1. 在左侧导航窗格中，单击&#x200B;**[!UICONTROL “外部”]**。

   ![](assets/click-external.png)

   *注册外部用户*

1. 在页面右上角，单击&#x200B;**[!UICONTROL “添加”]**。

1. 在&#x200B;**“添加外部注册个人资料”**&#x200B;对话框中，添加以下详细信息：


   * 合作伙伴组织的配置文件名称。
   * 合作伙伴公司经理的电子邮件地址。
   * 此合作伙伴的外部注册的名额限制。
   * 设定截止日期的到期日，以不再允许此组的新注册。 到期日后，只有现有注册用户才能访问此培训。

   ![](assets/map-data-fields-2.png)

   *“添加外部注册个人资料”对话框*

   * 在“**[!UICONTROL 高级设置]**”部分中，输入以下内容：

      * **[!UICONTROL 登录要求]：**&#x200B;指定天数。 如果学习者在上述期间没有登录，则会被删除。
      * **[!UICONTROL 允许的域]：**&#x200B;用逗号分隔的白名单电子邮件域名列表。
      * **[!UICONTROL 需要电子邮件验证]：**&#x200B;选择此选项可以为学习者强制进行电子邮件验证。

   ![](assets/email-verificationrequired.png)

   *在“高级设置”部分输入详细信息*

1. 单击&#x200B;**[!UICONTROL “保存”]**&#x200B;后，可以看到以下确认消息。您必须与外部合作伙伴共享该 URL。

   ![](assets/save-and-share-urlwithexternalusers.png)

## 启用外部个人资料 {#enableanexternalprofile}

创建外部个人资料后，必须启用其状态。从外部个人资料列表中，选择所需个人资料，然后切换状态按钮。

![](assets/choose-required-profiles.png)
*启用外部个人资料*

这样将启用“外部注册”链接。欢迎电子邮件会自动发送给合作伙伴。您还可以通过单击“复制 URL”图标 () 复制链接并与合作伙伴共享，也可以通过单击“邮件”图标 () 将欢迎电子邮件重新发送给合作伙伴公司。

合作伙伴经理可以与必须接受PrLearning Manager课程培训的员工共享此链接。 在单击链接后，他们可以在填写一些细节后自行注册，以便在 Adobe Learning Manager 上创建他们的个人资料。这些用户不会与内部员工一起出现在“学习者”选项卡上。您可以在&#x200B;**[!UICONTROL “外部学习者”]**&#x200B;选项卡下看到他们的名字。

## 暂停外部个人资料 {#pause}

将外部用户组添加到Learning Manager后，您也可以暂停外部用户的注册流程。 暂停后，外部用户的注册过程将被阻止。 但是，此过程仅在用户尚未通过接受邀请来进行注册时才有效。

要暂停外部用户组，请选择一个或多个组，单击页面右上角的&#x200B;**[!UICONTROL “操作”]**，然后单击&#x200B;**[!UICONTROL “暂停”]**。

## 恢复外部个人资料 {#resumeanexternalprofile}

您可以随时撤消外部合作伙伴的暂停状态并恢复正常服务。单击页面右上角的“**[!UICONTROL 操作]**”，然后选择“**[!UICONTROL 继续]**”。

以下状态适用于外部用户：

* **非活动状态** — 在此状态下，外部用户的注册已过期。 在通过添加用户工作流程添加外部用户时，管理员为外部用户设置到期日。
* **活动状态** - 在此状态下，外部用户可以注册到 Adobe Learning Manager 应用程序，然后登录到应用程序。
* **暂停** - 在此状态下，外部用户的注册流程将被阻止。但是，现有用户可以继续登录。

## 检查使用的坐席 {#checkusedseats}

在外部个人资料列表中，单击&#x200B;**[!UICONTROL “使用的坐席”]**。您可以查看合作伙伴公司中已添加的学习者数量。

![](assets/seats-used.png)
*检查使用的坐席*

## 删除用户 {#Deleteauser-1}

选择一个用户，然后从右上角单击&#x200B;**[!UICONTROL 操作]** > **[!UICONTROL 删除用户]**。

## 更改个人资料 {#changeprofile}

要将用户移动到其他外部个人资料，请从右上角选择一个用户，单击&#x200B;**[!UICONTROL 操作]** > **[!UICONTROL 更改个人资料]**。 从个人资料列表中，选择个人资料，然后单击&#x200B;**[!UICONTROL “更改”]**。

## 分配角色 {#Assignarole-1}

选择用户，然后从右上角单击“**[!UICONTROL 操作]**”>“**[!UICONTROL 分配角色]**”>“**设为`<role>`**”。 用户将获得新角色。

## 删除角色 {#Removearole-1}

选择用户，然后从右上角单击“**[!UICONTROL 操作]**”>“**[!UICONTROL 删除角色]**”>“**删除`<role>`**”。 所选角色将从分配给用户的角色列表中删除。

## 创建用户组 {#createusergroups}

用户组是一组与类别相关的用户。用户组可帮助管理员根据其属性选择公司中的学习者，然后为其分配学习内容。此外，这些用户组允许管理员将自定义徽标和目录分配给学习者，并显示有关其进度的自定义报告。

要访问用户组，请在左侧导航窗格中单击&#x200B;**[!UICONTROL “用户组”]**。

![](assets/user-groups.png)
*创建用户组*

Adobe Learning Manager 中有两种类型的组：自定义和自动生成。将学习者添加到您的帐户时，会根据其常用属性自动创建某些组。

要查看自动创建的组，请单击选项卡&#x200B;**[!UICONTROL “自动生成”]**。

![](assets/auto-generated.png)
*查看自动生成的组*

您可以看到各种组，例如所有内部用户、所有经理以及按照各成本中心、部门和经理团队组成的组。

除自动生成的组外，您还可以创建自定义组。要添加新的自定义组，请在右上角单击“**[!UICONTROL 添加]**”。

1. 输入组的名称和说明。
1. 在“按类型搜索”字段中输入用户名或个人资料，然后从下拉列表中选择，以添加用户。

1. 要添加更多学习者，请单击&#x200B;**[!UICONTROL 添加更多用户]**。

1. 要创建用户组，请单击&#x200B;**[!UICONTROL “保存”]**。

现在，已创建此自定义组并将其添加到个人资料中。您创建的用户组本质上是动态的。如果添加了具有类似属性的新用户，则会自动将其添加到用户组。

要查看用户所属的组列表，请导航到&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 用户组]**，搜索该用户的名称，然后选择它。 这将显示用户所属的所有组。

![](assets/list-of-group.png)

### 下载用户组中的用户列表

要下载特定用户组中的用户列表，请导航到&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 用户组]**，选择组旁边的&#x200B;**[!UICONTROL 下载图标]**。 这将生成一个CSV文件，其中包含该组中的用户列表。

![](assets/download-list-of-user.png)

## 排除用户组

有时，您可能希望从大型用户组中排除一小组用户。 如果您通过学习计划在培训中注册此特定用户组，或要为目录设置正确的可见性，则必须执行此操作。 在此版本的Learning Manager中，您可以在创建自定义用户组时排除学习者或用户组。 在“添加用户组”对话框中，可利用“排除学习者”部分实现此目的。

![](assets/exclude-user-groups.png)
*排除用户组*

例如，如果您想设置一个学习计划，让所有满足 location = California except Store-5（位于 California）条件的用户都可以注册课程。

## 高级设置 {#advancedsettings}

### 数据源 {#datasources}

当您想要将用户或学习数据从公司数据库导入/同步到Learning Manager应用程序时，可以使用此功能。 还可设置此同步的频率。


在左侧窗格的&#x200B;**[!UICONTROL 高级]**&#x200B;部分下单击&#x200B;**[!UICONTROL 数据源]**。


![](assets/data-sources-add-users.png)

*要导入或同步用户的数据源*

从&#x200B;**[!UICONTROL 源]**&#x200B;下拉列表中选择数据源类型，选择更新频率，如果需要立即同步，请单击&#x200B;**[!UICONTROL 立即同步]**，或单击&#x200B;**[!UICONTROL 保存]。**&#x200B;内部用户的数据源类型有SFDC、FTP等。

您可以添加多个数据源。

### 活动字段 {#activefields}

除了用户注册期间提供的功能外，此功能还允许管理员添加更多活动字段。

单击用户页面中的&#x200B;**[!UICONTROL 可用活动字段]**。 学习者只能从自定义值提供的值中进行选择。

![](assets/active-fields.png)
*活动字段*

### 配置字段 {#configurefields}

**内部用户**

您可以为内部用户添加用户字段的自定义值。

要添加自定义值，请执行以下步骤：

1. 单击内部用户的&#x200B;**[!UICONTROL 修改值]**。

   ![](assets/modify-values.png)
   *修改内部用户的值*

1. 出现“**自定义字段中的值**”对话框。

   ![](assets/values-in-customfields.png)
   *“自定义字段中的值”对话框*

1. 从&#x200B;**[!UICONTROL “选择字段”]**&#x200B;下拉菜单中选择要添加的值。
1. 在&#x200B;**[!UICONTROL “新值”]**&#x200B;字段中输入新值。
1. 单击&#x200B;**[!UICONTROL “完成”]**。
1. 单击右上角的“保存”以&#x200B;**[!UICONTROL 保存]**&#x200B;更改。

**外部用户**

添加与内部用户的值类似的自定义值。

![](assets/modify-values-forexternalusers.png)
*修改外部用户的值*

### 设置 {#settings}

**用户显示**

如果启用选项&#x200B;**“在学习者登录时仅显示未填写的字段”**，则用户在登录时只会看到空白字段。

![](assets/settings-tab.png)
*显示未填写的字段*

使用此选项，管理员可以决定他/她在这些字段填充后是要显示还是隐藏字段。

## 限制报告中的活动字段 {#restrictactivefields}

Learning Manager 27.7针对活动字段引入了两个新选项： **[!UICONTROL 可报告]**&#x200B;和&#x200B;**[!UICONTROL 可导出]**。

![](assets/options-in-activefields.png)
*活动字段中的选项*

对于 CSV 字段和手动添加的字段，如果“活动字段”已被标记为&#x200B;**[!UICONTROL “可报告”]**，则该活动字段即可在仪表板报告内的过滤器中搜索。

![](assets/filters-in-a-dashboardreport.png)
*仪表板报告中的筛选器*

如果活动字段已被标记为&#x200B;**[!UICONTROL “可导出”]**，则在下载任何 Excel 报表时，活动字段即会显示在 Excel 文件中。

这些选项适用于所有内部和外部活动字段。

您只能删除自定义活动字段。

## 用户显示

您可以对学习者隐藏整个“完成配置文件”页面。 学习者登录后，该页面将不会弹出。

请注意，现有的默认行为不会更改。 这是管理员现在可使用的可选功能。

启用以下选项：

![](assets/user-display.png)
*“用户显示”部分*

## 通过FTP和Box连接器支持手动CSV字段 {#import-connector}

用户通常希望在学习者登录Learning Manager时手动提供活动字段。 目前可在用户手动导入CSV时，在Learning Manager中完成此操作。

CSV可能不包含所有活动字段。 对于已上传的CSV中未更新的所有活动字段，用户需要输入此类活动字段的数据。

目前，所有活动字段都必须从源CSV映射到某个字段。

有时，用户不希望将活动字段映射到CSV中指定的字段。 在这种情况下，用户可以将“活动”字段映射到值&#x200B;**[!UICONTROL DontImportFromSource]**。 从FTP和Box连接器导入用户时，从下拉列表中选择此值。

## 自定义角色 {#customroles}

将您选择的任何字段添加为用户信息的一部分，然后单击“**[!UICONTROL 保存]**”。 添加字段后，您还可以在&#x200B;**[!UICONTROL 编辑用户]**&#x200B;对话框中交叉检查字段的可用性。


添加字段后，您会注意到有刻度线标记的字段源自数据源或 CSV，如下面快照中所述。管理员可以通过启用或禁用字段来编辑这些源字段。

**Learning Manager中活动字段的值**

可通过以下方式获取活动字段的值：

1. Adobe Learning Manager 应用程序从与您帐户关联的数据源导入元数据。
1. 从手动导入的 CSV 文件捕获的元数据。
1. 学习者在登录时填充元数据
1. 管理员输入用户的数据。

>[!NOTE]
>
>Adobe Learning Manager 应用程序会自动通过这些元数据创建用户组。

**添加自定值**

您可以在“内部”和“外部”用户字段中为用户字段添加自定义值。

要添加自定义值，请执行以下步骤：

可以添加和删除自定义字段，这些字段适用于所有用户。可以启用或禁用 CSV 字段，这些字段仅在您于活动字段中完成修改，并上传 CSV 后生效。所有内部活动字段适用于所有类型的内部用户。外部字段仅适用于外部用户。如果 CSV 中存在自定义字段，则在下一次上传时，系统会自动将其转换为 CSV 字段，并启用该字段。

## CSV 字段的值 {#valuesforcsvfields}

如果启用了&#x200B;**[!UICONTROL “限制选择”]**&#x200B;复选框，用户只能从 CSV 字段的预定义字段中进行选择。

![](assets/value-field-for-csv.png)
*限制选择复选框*

## 导入日志 {#importlogs}

在此空间中，您可以查看管理员使用批量导入功能添加的，用户 CSV 导入历史记录。您还可以单击页面右上角的“**[!UICONTROL 添加]**”，以使用CSV上传功能添加用户。

## 多值活动字段

使用此功能，活动字段可以具有多个字段。 在一个帐户中，最多可以有三个多值活动字段。 多值活动字段可供外部和内部用户使用。

将活动字段标记为多值字段后，无法再将其转换回单值字段。 此过程不可逆。

现有的单值字段不能标记为多值字段。

要创建多值活动字段，请执行以下步骤：

1. 添加活动字段。

   ![添加活动字段](assets/add-active-field.png)
   *添加活动字段*

1. 单击“添加”。
1. 在“设置”选项卡中，将新字段标记为多值字段。

   ![标记为多值](assets/mark-multi-valued.png)
   *标记为多值*

   将出现一个复选框，**[!UICONTROL “学习者可配置”]**，禁用该复选框后，学习者将无法在“个人资料”页面上看到该字段。

1. 使用CSV或者单击“修改值”来添加值。

   ![添加值](assets/add-values.png)
   *添加值*

1. 单击&#x200B;[!UICONTROL **“完成”**]。

>[!NOTE]
>
>创建用户组并填充字段后，无法将多个值转换为单个值，反之亦然。

### 通过 CSV 添加多值活动字段

请按以下步骤操作：

1. 创建一个以列形式包含新活动字段的 CSV（逗号分隔或单值）。
1. 导入 CSV。
1. 在“自定义字段中的值”对话框中将字段标记为多值字段。
1. 再次导入 CSV。

CSV 必须包含与标记为多值的活动字段具有相同名称的列。

CSV 包含以下字段：

* **[!UICONTROL 用户]**：以角色形式创建的用户组。
* **[!UICONTROL 角色]**：具有值的多值活动字段。

如果使用新值或删除的值重新上传 CSV，活动字段和组也会相应更新。

### 报告

所有报告都包含多值活动字段及其值。

管理员可以添加自动生成的活动字段，并配置用户活动和培训报告。

“学习者成绩单”报告包含所有活动字段和逗号分隔的值。 管理员随后可相应地过滤数据。

## 用户组报告

Adobe Learning Manager的新用户组报告提供了在管理员离开时不受管理的组的可见性，可帮助管理用户组。 管理员可以访问&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 用户组]**&#x200B;部分下的报告。 它提供有关每个组的详细信息，包括：

* 用户组类型
* 组名称
* 描述
* 创建者（名称）
* 创建者（电子邮件）
* 创建时间： （UTC时区）
* 用户数

要下载报告，请执行以下步骤：

1. 以&#x200B;**[!UICONTROL 管理员]**&#x200B;身份登录。
2. 选择&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 用户组]**。
3. 选择&#x200B;**[!UICONTROL 操作]** > **[!UICONTROL 下载用户组报告]**。

![](assets/download-user-group-report.png)
_下载用户组报告_

## 常见问题解答 {#faq}

+++如何在Learning Manager中注册用户？

添加用户并为该用户分配角色后，您可以按以下步骤注册用户：

1. 选择用户后，单击右上角的&#x200B;**[!UICONTROL “操作”]**，然后单击&#x200B;**[!UICONTROL “注册”]**。

1. 在弹出窗口中，单击&#x200B;**[!UICONTROL “是”]**。

所选用户会收到一封“欢迎”电子邮件。 如果学习者已拥有一个现成的 Adobe ID，则可以单击此链接。如果他们没有现成的Adobe ID，他们可以继续并单击“欢迎”链接以创建Adobe ID，并将其链接到其Learning Manager帐户。

学习者必须单击电子邮件中的链接，因为它有助于Learning Manager验证学习者的帐户。

+++

+++如何编辑用户数据？

要编辑用户，请按以下步骤操作：

1. 在用户列表中，单击数据需要编辑的用户。
1. 单击铅笔图标，如下所示。

![](assets/edit-user-data.png)

在&#x200B;**“编辑用户”**&#x200B;对话框中，更新相应字段。 要保存更改，请单击&#x200B;**[!UICONTROL “保存”]**。

+++

+++如何在Learning Manager中暂停和恢复外部用户？

在“外部用户”列表中，选择要删除的用户。 在右上角，单击“**[!UICONTROL 操作]**”>“**[!UICONTROL 暂停]**”。

有关更多信息，请参 [阅暂停外部配置文件](add-users-user-groups.md#pause)。

暂停配置文件后，外部配置文件将状态显示为“暂 ***停”***。

+++

+++如何向新创建的外部个人资料发送欢迎电子邮件？

添加外部用户时，在&#x200B;**[!UICONTROL 添加外部注册个人资料]**&#x200B;对话框中，输入外部经理的电子邮件。 当您单击“保存”时，系统也会向您指定的电子邮件地址发送欢迎电子邮件。 如要再次发送欢迎邮件，请单击信封图标，如下所示：

![](assets/send-welcome-mail.png)

+++

+++如何创建自定义用户组？

单击&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 用户组]**，然后在“用户组”页面上单击&#x200B;**[!UICONTROL 添加]**。 在“添加用户组”对话框中，单独添加用户和以团队形式添加用户。

![](assets/custom-user-group.png)

+++

+++如何禁用已填充的活动字段？

如果您希望学习者仅看到他人填写的活动字段，请按以下步骤操作：

1. 单击&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 活动字段]**。

1. 单击&#x200B;**[!UICONTROL 设置]**&#x200B;并启用选项&#x200B;**[!UICONTROL 在学习者登录时仅显示未填写的字段]**。

1. 单击&#x200B;**[!UICONTROL “保存”]**。

+++

+++如何防止学习者在活动字段中输入随机值？

您可以限制学习者的选择，这样他们就只能选择预定义的值，而不能输入任何随机值。 请按以下步骤操作：

1. 单击&#x200B;**[!UICONTROL 用户]** > **[!UICONTROL 活动字段]**。
1. 启用&#x200B;**[!UICONTROL “限制选择”]**&#x200B;选项。
1. 单击&#x200B;**[!UICONTROL “完成”]**。

+++

+++如何区分CSV活动字段和自定义活动字段？

您只能启用或禁用 CSV 活动字段，无法将其删除。 另一方面，您无法启用或禁用自定义活动字段。

+++
