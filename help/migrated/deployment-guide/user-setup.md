---
jcr-language: en_us
title: 在 Adobe Learning Manager 中设置用户
contentowner: shhivkum
preview: true
source-git-commit: 0fabd369e70e15ba22fead0177a24aafd851d88d
workflow-type: tm+mt
source-wordcount: '1816'
ht-degree: 63%

---



# 在 Adobe Learning Manager 中设置用户

## 内部和外部用户 {#internalandexternalusers}

在包括 Adobe Learning Manager 在内的任何 LMS 中，管理用户都是一个重要方面。 Adobe Learning Manager 允许用户将用户分为内部用户和外部用户。 内部用户是属于特定组织或组的用户。 通常，企业内的用户是内部用户。 这些用户拥有特定的学习对象，而这些对象具有特定的截止日期，由经理或管理员予以分配。

相反，外部用户通常是特定 Adobe Learning Manager 帐户的临时用户。 这些用户可通过单击通过电子邮件收到的临时外部链接来访问特定的学习对象。 外部用户个人资料通常具有到期日期。 例如，进行 Java 认证的组织可能会有任何用户临时登录以完成相关课程，然后尝试认证。 通常，面向外部用户的教室培训和课程的可容纳人数也有限。

继续阅读以了解如何在 Adobe Learning Manager 中添加内部用户和外部用户。

## 设置外部用户 {#setupexternalusers}

作为管理员，您可能需要将外部用户（例如合作伙伴公司的员工）添加到您的 Adobe Learning Manager 帐户中。 要添加外部用户，请执行以下操作：

1. 在**[!UICONTROL **管理员**]**登录页面上，单击左侧导航窗格中的**[!UICONTROL **用户**]**。
1. 在**[!UICONTROL **用户**]**页面中，单击左侧导览窗格中的**[!UICONTROL **外部**]**。 系统会显示外部用户页面，其中包含外部用户列表（如有）。
1. 单击页面右上角的**[!UICONTROL **添加**]**。

   ![](assets/set-up-external-users-step3.png)

1. 在**[!UICONTROL **添加用户**]**弹出对话框中，以下字段为必填字段：

   * **[!UICONTROL **配置文件名称**：]**为正在创建的外部配置文件指定名称。
   * **[!UICONTROL **&#x200B;经理电子邮件&#x200B;**：]**&#x200B;指定外部用户的经理电子邮件地址。
   * **[!UICONTROL **&#x200B;分配的名额&#x200B;**：]**&#x200B;指定可以注册课程的学习者数量。
   * **[!UICONTROL **&#x200B;到期&#x200B;**：]**&#x200B;指定到期日期，超过该日期外部用户将无法注册或使用课程。

1. 单击&#x200B;**[!UICONTROL **“高级设置”**。]**
1. （可选）在创建外部个人资料时设置以下选项：

   * **[!UICONTROL **&#x200B;添加图像&#x200B;**：]**&#x200B;拖放所需的图像。 此图像会显示在用户的“学习者”页面中。
   * **[!UICONTROL **&#x200B;登录要求&#x200B;**：]**&#x200B;指定用户需要登录的天数。 如果外部用户超过此登录期限，学习者将无法访问或使用学习对象。
   * **[!UICONTROL **&#x200B;允许的域&#x200B;**：]**&#x200B;指定用逗号分隔的域。 只有具有指定域的用户才能注册该帐户。
   * **[!UICONTROL **&#x200B;需要电子邮件验证&#x200B;**：]**&#x200B;如果要将验证电子邮件发送给用户，请选中此复选框



1. 单击&#x200B;**[!UICONTROL “保存”]**。



   ![](assets/set-up-external-users-step7.png)

   系统会显示一个包含 URL 的弹出对话框。 您可以复制此 URL 并将其发送给外部用户。 默认情况下，系统会向用户发送一封包含此 URL 的电子邮件。

1. 添加外部配置文件时，这些配置文件显示在&#x200B;**[!UICONTROL **&#x200B;外部用户页面&#x200B;**中（**&#x200B;管理员&#x200B;**>**&#x200B;用户&#x200B;**>**&#x200B;外部&#x200B;**）。]**&#x200B;还将为这些用户显示名额限制、到期日期和登录要求。
1. 要随时编辑外部用户的设置，请单击用户名。 系统会显示&#x200B;**[!UICONTROL 编辑外部注册]**&#x200B;对话框。 修改设置，然后单击&#x200B;**[!UICONTROL **&#x200B;保存&#x200B;**。]**
1. 您还可以随时通过单击外部个人资料旁边的电子邮件/复制 URL 图标来重新发送欢迎电子邮件或复制 URL。

   ![](assets/set-up-external-users-step10.png)

## 暂停使用外部用户个人资料 {#pausetheexternaluserprofile}

将外部用户组添加到 Adobe Learning Manager 后，您也可以暂停外部用户的注册流程。在暂停后，外部用户的注册流程将被阻止。但是，此过程仅在用户尚未通过接受邀请来进行注册时才有效。

要暂停外部用户组，请单击页面右上角的**[!UICONTROL **操作**]**，然后选择&#x200B;**[!UICONTROL 暂停]**。

## 恢复外部用户个人资料 {#resumeexternaluserprofile}

可随时通过选择“继续”选项撤销暂停。单击页面右上角的**[!UICONTROL **操作**]**，然后选择&#x200B;**[!UICONTROL 继续]**。

**[!UICONTROL 外部用户状态]**

在Learning Manager中，以下状态适用于外部用户：

* **非活动状态** — 在此状态下，外部用户注册已过期。 在通过添加用户工作流程添加外部用户时，管理员为外部用户设置到期日。
* **活动状态** — 在此状态下，外部用户可以注册到Learning Manager应用程序，也可以登录到该应用程序。
* **暂停** - 在此状态下，外部用户的注册流程将被阻止。但是，现有用户可以继续登录。

## 设置内部用户 {#setupinternalusers}

作为管理员，您可能要为企业或组织设置用户。 这些用户也称为内部用户。 内部用户可以使用单点登录或使用 Adobe ID 登录应用程序。 然后，这些用户可以按照自己的要求访问和使用学习对象。 要为组织设置内部用户，可以使用三种方法：

* 使用 CSV 批量添加用户
* 通过自行注册添加用户
* 添加单个内部用户



## 使用 CSV 文件添加用户 {#addingusersusingacsvfile}

如果用户数量较多，则可以选择此方法来添加内部用户。 首次使用 CSV 添加用户时，必须将 CSV 数据内容映射到应用程序标签。 随后，当您添加新用户或更新用户数据时，系统将保留相同的映射。 如要批量添加内部用户，请执行以下操作：

1. 在&#x200B;**[!UICONTROL 管理员主页]**&#x200B;页面上，单击左侧导航窗格中的**[!UICONTROL **用户**]**。
1. 单击&#x200B;**[!UICONTROL **&#x200B;添加&#x200B;**>**&#x200B;上传CSV **。]**
1. 在弹出对话框中，单击&#x200B;**[!UICONTROL **&#x200B;导入&#x200B;**。]**
1. 浏览至 CSV 文件的保存位置。 单击&#x200B;**[!UICONTROL “打开”]**。
1. 导入 CSV 文件，并将 CSV 文件的内容映射到应用程序标签。 此步骤仅在您首次上传 CSV 文件时适用。
1. 单击**[!UICONTROL **保存**]**以保存映射。
1. 单击**[!UICONTROL **添加**]**以上传已映射到应用程序数据的CSV文件。

### 创建要上传的 CSV 文件时的注意事项： {#considerationswhencreatingthecsvfileforupload}

在创建CSV文件以上传内部用户时，必须输入数据的一些必填字段如下所示：员工姓名、员工电子邮件、员工的个人资料或职称以及经理层次结构。

每个员工的姓名和邮箱均可以直接映射到应用程序数据。 请注意，您必须将 CSV 文件中指定的邮箱指定为经理邮箱。 您可以在创建 CSV 文件时定义 Manager ID，也可以在上传 CSV 文件时指定与经理 ID 对应的邮箱 ID。

***在将ID添加为员工的经理ID之前，请确保将经理添加为CSV文件中的员工。***

***确保条目之间没有多余的空格，以便成功上传CSV文件。***

要查看 CSV 文件的快照示例，请单击此处：

![](assets/considerations-whencreatingthecsvfileforupload.png)

若要下载示例CSV文件，请下载`<give link to zip file>`。

<!--Zip file reference, no source file-->

### 设置根用户 {#settinguprootuser}

自动批量导入用户。

## 通过自行注册添加用户 {#addingusersthroughselfregistration}

除了批量添加内部用户外，您还可以通过自行注册来添加用户。 您可以使用自行注册，让员工自行注册成为 Adobe Learning Manager 帐户的习者。 创建自行注册个人资料时，系统将创建一个唯一的 URL。 与员工共享此 URL，以便他们能够在 Adobe Learning Manager 中注册。

1. 在&#x200B;**[!UICONTROL 管理员主页]**&#x200B;页面，单击左侧导览窗格中的&#x200B;**[!UICONTROL “用户”]**。
1. 单击&#x200B;**[!UICONTROL **&#x200B;添加&#x200B;**>**&#x200B;自行注册&#x200B;**。]**

   ![](assets/adding-users-throughself-registration-step2.png)

1. 在&#x200B;**[!UICONTROL 添加用户]**&#x200B;弹出对话框中，在&#x200B;**[!UICONTROL 个人资料名称]**&#x200B;字段中指定员工的姓名。
1. 在&#x200B;**[!UICONTROL 经理姓名]**&#x200B;字段中，输入员工经理的姓名。
1. （可选）您可以使用&#x200B;**[!UICONTROL 添加图像]**&#x200B;字段添加员工的个人资料图片。
1. 单击&#x200B;**[!UICONTROL “保存”]**。

   ![](assets/adding-users-throughself-registration-step6.png)

   系统会显示另一个弹出对话框，其中包含已成功创建个人资料的消息。 此对话框中还会生成一个唯一的 URL。

1. 与员工共享此 URL，以便他们能够自行注册成为学习者。

   ![](assets/adding-users-throughself-registration-step7.png)

## 在 Adobe Learning Manager 中添加单个用户 {#addsingleusersincaptivateprime}

添加单个用户是将内部用户添加到帐户的第三种方法。 当您想要添加少许用户时，此步骤为理想之选。 如要添加单个用户，请执行以下操作：

1. 在&#x200B;**[!UICONTROL 管理员主页]**&#x200B;页面，单击左侧导览窗格中的&#x200B;**[!UICONTROL “用户”]**。
1. 单击&#x200B;**[!UICONTROL **&#x200B;添加&#x200B;**>**&#x200B;单个用户&#x200B;**。]**



1. 在“添加用户”弹出对话框中，指定用户的以下详细信息：

   * **[!UICONTROL 姓名]** **[!UICONTROL ：]**&#x200B;指定员工或内部用户的姓名。 此字段为必填项。

   * **[!UICONTROL 电子邮件]** **[!UICONTROL ：]**&#x200B;指定员工的电子邮件ID。 此字段为必填项。

   * **[!UICONTROL 配置文件]** **[!UICONTROL ：]**&#x200B;指定员工的职务或职务。

   * **[!UICONTROL **&#x200B;经理的姓名&#x200B;**：]**&#x200B;指定经理的姓名。 应该已将经理添加到此处指定的数据库中。
   * **[!UICONTROL ** DOJ **：]**&#x200B;指定加入员工的日期。
   * **[!UICONTROL **位置**：]**指定员工的位置。 例如，如果您的组织分布在多个地理位置，请指定员工所在的位置。



   ![](assets/add-single-usersincaptivateprime-step3.png)

1. 单击“**[!UICONTROL 添加]**”。
1. 系统会显示一条消息，说明用户已成功添加。 用户会通过指定的邮箱 ID 收到验证链接。 用户可以单击此链接以激活其帐户并开始访问 Adobe Learning Manager。

   ![](assets/add-single-usersincaptivateprime-step5.png)

## 在 Adobe Learning Manager 中管理用户组 {#managingusergroupsincaptivateprime}

用户组只不过是一组与所定义的类别相关的用户。 作为管理员，您可以使用用户组根据学习者的属性快速选择学习者。 此外，您还可以快速将徽标或目录分配给用户组，并生成有关其进度的自定义报告。

Learning Manager中有两种类型的用户组：自定义和自动生成。 将学习者添加到帐户时，会根据帐户中用户的角色和属性自动创建某些默认组。 这些组是自动生成的。 例如，包含所有学习者或所有作者的组。

***无法编辑自动生成组的名称和说明。***

要在 Adobe Learning Manager 中查看自动生成的用户组，请在左侧窗格中单击&#x200B;**[!UICONTROL “自动生成”]**。 应用程序会显示可用于您的帐户的所有自动生成的用户组的列表。

您还可以在 Adobe Learning Manager 中使用选定的用户列表创建自定义组。 自定义组允许您指定用户组的名称、描述和属性。 在Learning Manager中创建的自定义组本质上是动态的。 即，如果添加了具有类似属性的新用户，则会自动将其添加到这些用户组。

## 创建自定义用户组 {#createcustomusergroups}

1. 在 Adobe Learning Manager 管理员主页中，单击&#x200B;**[!UICONTROL “用户”]**。
1. 在“自定义用户组”页面中，单击页面右上角的**[!UICONTROL **添加**]**。

   系统会显示&#x200B;**[!UICONTROL 添加用户组]**&#x200B;对话框。

   ![](assets/creating-custom-usergroups.png)

1. 为您的用户组指定名称和描述。 例如，Dev-Users 包括来自产品开发团队的用户。
1. 通过在&#x200B;**[!UICONTROL **&#x200B;添加用户&#x200B;**字段中输入用户名或用户配置文件，将用户添加到自定义用户组。]**
1. 若要向自定义组添加更多用户，请单击&#x200B;**[!UICONTROL **&#x200B;添加更多用户&#x200B;**。]**
1. 添加完所有用户后，单击**[!UICONTROL 保存]**以保存自定义用户组。

