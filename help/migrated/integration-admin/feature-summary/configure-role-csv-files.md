---
jcr-language: en_us
title: 通过CSV文件管理自定义角色
description: 集成管理员可以通过CSV在其帐户中批量添加大量自定义角色，并可将相同角色分配给各种用户。 此方法使自定义角色的创建过程自动化。
contentowner: saghosh
source-git-commit: ab6737e8b43222a6538921b0628a504a5f15859d
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 0%

---



# 通过CSV文件管理自定义角色

集成管理员可以通过CSV在其帐户中批量添加大量自定义角色，并可将相同角色分配给各种用户。 此方法使自定义角色的创建过程自动化。

您可以通过Learning Manager FTP和Box连接器配置角色。

登录到Box或ExaVault存储帐户后，集成管理员可以在帐户中添加以下csv：

* role.csv
* user_role.csv

要开始使用，请下载csv并根据您的要求更改值。

**role.csv**
[示例文件 — role.csv](assets/role.csv) [示例文件 — user_role.csv](assets/user-role.csv)

<table>
 <tbody>
  <tr>
   <td>
    <p><b>列名称</b></p></td>
   <td>
    <p><b>描述</b></p></td>
   <td>
    <p><b>示例值</b></p></td>
  </tr>
  <tr>
   <td>
    <p>名称</p></td>
   <td>
    <p>在CSV中标识要分配给用户的角色。</p></td>
   <td>
    <p>销售作者</p></td>
  </tr>
  <tr>
   <td>
    <p>&lt;Entity&gt;</p></td>
   <td>
    <p>确定每个实体类型（如COURSE、CATALOG等）的访问类型（完整、写入、注册、报告、无）。</p></td>
   <td>
    <p>完整</p>
    <p>无</p>
    <p>写入 | 举报</p>
    <p>列名称将与目录、课程、学习计划等实体类型名称相对应。</p>
    <p>CSV中将出现每种实体类型的一列。 不应授予其权限的实体应包括在NONE值内</p></td>
  </tr>
  <tr>
   <td>
    <p>目录范围说明符</p></td>
   <td>
    <p>单个目录名称或以PIPE (|)分隔的目录名称列表，确定此角色的范围。</p></td>
   <td>
    <p>销售目录 | 常规目录</p></td>
  </tr>
  <tr>
   <td>
    <p>用户组范围说明符</p></td>
   <td>
    <p>用户组属性名称和值，用于确定此角色的用户范围。</p>
    <p>有关范围，请参阅下面的部分。</p></td>
   <td>
    <p>location=伦敦</p></td>
  </tr>
  <tr>
   <td>
    <p>描述</p></td>
   <td>
    <p>可选的用户友好描述，帮助了解角色的用途和后续参考。</p></td>
   <td>
    <p>对销售目录中的学习对象的完全作者访问权限</p></td>
  </tr>
 </tbody>
</table>

除“说明”之外的所有列都是必需的。

## 定义用户组的范围 {#definescopeofusergroups}

您可以通过以下方式为各种类型的组指定用户组的范围：

* 用户组名称原样（例如，所有作者、我的自定义组）
* 叶属性和值（例如，Department=HR）
* 自行注册个人资料组(self_registration=profilename)
* 外部注册个人资料组(ext_registration=profilename)
* 经理的直接下属团队(manager_direct=`<emailid>`)
* 经理的完整组织(manager_org=`<emailid>`)

**user_role.csv**

<table>
 <tbody>
  <tr>
   <td>
    <p><b>列名称</b></p></td>
   <td>
    <p><b>描述</b></p></td>
   <td>
    <p><b>注释</b></p></td>
  </tr>
  <tr>
   <td>
    <p>Id</p></td>
   <td>
    <p>要为其分配可配置角色的用户的电子邮件ID。</p></td>
   <td>
    <p>如果为用户分配了可配置角色，则该角色将被替换为CSV中指定的新角色。 未报告错误。</p></td>
  </tr>
  <tr>
   <td>
    <p>CustomRole</p></td>
   <td>
    <p>要分配给用户的可配置角色的名称</p></td>
   <td>
    <p>角色名称必须是CSV中指定的现有角色。 管理员通过UI创建的角色可以在此处使用。</p></td>
  </tr>
 </tbody>
</table>

**全范围功能**

每当为以下任何功能（帐户级别功能）分配完全权限时，系统都会自动将用户组范围和目录范围视为“完全”，因为用户对这些功能的访问不能受到限制。

如果在CSV中提供了任何目录名称或用户组名称，则会用“完整”权限覆盖它们。

* 公告
* 技能
* 游戏
* 用户
* 学习方案
* 电子邮件模板

## 在帐户中添加角色 — CSV {#addtherolecsvsintheaccount}

在您的Box帐户中选择 **导入>用户>内部**，然后上传文件 — role.csv和user_role.csv。

* 自定义角色CSV必须复制到文件夹“import->user->internal->user_role”中
* 必须将用户CSV复制到“import->user->internal”文件夹中

两个CSV都必须仅通过Box或FTP上传，并且无法通过UI上传。

>[!NOTE]
>
>用户CSV文件是必填项，但自定义角色CSV是可选的。 处理存在的所有文件，跳过其他文件。

管理员无法在UI中看到使用csv文件创建的自定义角色。 UI创建（或稍后创建）的角色不会与这些角色相关或影响。

通过csv创建的自定义角色可以完全通过csv本身进行管理。 这包括添加、修改和删除角色。

通过从user_role csv中删除分配条目，可以撤销分配的角色。 但通过管理员UI完成的分配不受此影响。

要分配和撤销自定义角色，请更新csv文件。

## 自定义角色的同步 {#synchronizationofcustomroles}

集成管理员将基于角色的CSV上传到连接器存储后，管理员可以启用与CSV的同步。 每次在CSV中更新、添加或删除自定义角色时，管理员都可以同步文件中的信息，并使角色列表成为最新列表。

在“管理员”面板上的“开始使用”页面上，单击 **[!UICONTROL 设置]** > **[!UICONTROL 数据源]**.

在“同步设置”部分，启用该选项 **[!UICONTROL 启用自动同步]**.

![](assets/sync-settings.png)

*选择启用自动同步选项*

选择此选项后，您可以将同步时间安排在您在“同步时间”字段中指定的确切时间处。 如果将同步时间指定为12:00 AM，则自定义角色将在每天的指定时间完全更新。

如果要按需同步数据，请单击 **[!UICONTROL 立即同步]**.

## 配置角色时的约束 {#constraintswhileconfiguringroles}

在任何帐户中，角色的名称都必须唯一。 因此，通过UI或CSV创建的角色的名称不得与通过UI或CSV创建的另一个角色相同。

在相似的行中，无法从管理员UI为用户分配通过CSV创建的可配置角色，因为这些角色将不可用。

但是，用户分配CSV可用于分配通过UI创建的角色。
