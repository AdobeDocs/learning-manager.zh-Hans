---
jcr-language: en_us
title: 管理 CSV 文件中的自定义角色
description: 集成管理员可以通过 CSV 在其账户中批量添加多个自定义角色，并可将相应的角色分配给不同的用户。此方法可以自动创建相关自定义角色。
contentowner: saghosh
exl-id: fce2f457-2834-491a-8331-64086f5a51b5
source-git-commit: 5f2b5fb60856b77b53edaea014639087eb1a8fcf
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 83%

---

# 管理 CSV 文件中的自定义角色

集成管理员可以通过 CSV 在其账户中批量添加多个自定义角色，并可将相应的角色分配给不同的用户。此方法可以自动创建相关自定义角色。

您可以通过 Adobe Learning Manager FTP 和 Box 连接器来配置角色。

登录Box存储帐户后，集成管理员可以在帐户中添加以下csv：

* role.csv
* user_role.csv

要开始使用，请下载 csv 并根据您的要求更改相应的值。

**role.csv**
* 示例文件： [role.csv](assets/role.csv)
* 示例文件： [user_role.csv](assets/user_role.csv)

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
    <p>确定在 CSV 中将要分配给用户的角色。</p></td>
   <td>
    <p>销售作者</p></td>
  </tr>
  <tr>
   <td>
    <p>&lt;Entity&gt;</p></td>
   <td>
    <p>确定每个实体类型（如COURSE、CATALOG等）的访问类型（完整、写入、注册、报告、无）。</p></td>
   <td>
    <p>完全</p>
    <p>无</p>
    <p>写入 | 报告</p>
    <p>列名称将与实体类型名称对应，例如目录、课程、学习计划等。</p>
    <p>在 CSV 中，每种实体类型均对应一列。未授予许可的实体应包含在内，其值为“无”(NONE)</p></td>
  </tr>
  <tr>
   <td>
    <p>目录范围说明符</p></td>
   <td>
    <p>单个目录名称或者采用竖线 (|) 分隔的“目录名称”列表，用于确定角色的范围。</p></td>
   <td>
    <p>销售目录 | 总目录</p></td>
  </tr>
  <tr>
   <td>
    <p>用户组范围说明符</p></td>
   <td>
    <p>“用户组属性”名称和值用于确定此角色用户的范围。</p>
    <p>请参阅下面的部分了解范围。</p></td>
   <td>
    <p>位置=伦敦</p></td>
  </tr>
  <tr>
   <td>
    <p>描述</p></td>
   <td>
    <p>（可选）用户友好型描述有助于了解角色的用途，方便日后参考。</p></td>
   <td>
    <p>对销售目录中的学习对象拥有完全作者访问权限</p></td>
  </tr>
 </tbody>
</table>

除“描述”之外的所有列都必填。

## 定义用户组的范围 {#definescopeofusergroups}

您可以通过以下方式为各类用户组指定相应的范围：

* 用户组名称保持不变（例如，All Authors、My Custom Group）
* 叶属性和值（例如，Department=HR）
* 自注册资料组 (self_registration=profilename)
* 外部注册资料组 (self_registration=profilename)
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
    <p><b>评论</b></p></td>
  </tr>
  <tr>
   <td>
    <p>ID</p></td>
   <td>
    <p>将对其分配可配置角色的用户的电子邮件 ID。</p></td>
   <td>
    <p>如果该用户已分配了可配置角色，则该角色将被替换为 CSV 中指定的新角色。 没有报告错误。</p></td>
  </tr>
  <tr>
   <td>
    <p>CustomRole</p></td>
   <td>
    <p>将要分配给用户的可配置角色的名称</p></td>
   <td>
    <p>该角色名称必须是 CSV 中指定的现有角色。 由管理员通过用户界面创建的角色也可在此处使用。</p></td>
  </tr>
 </tbody>
</table>

**完全范围功能**

为以下任何功能（帐户级功能）分配完全权限时，“用户组范围”和“目录范围”将自动设为“完全”，因为用户对这些功能的访问权限不能受限。

如果 CSV 中提供了任何“目录”名称或“用户组”名称，这些名称会被“完全”权限替代。

* 公告
* 技能
* 游戏
* 用户
* 学习计划
* 电子邮件模板

## 在帐户中添加角色CSV {#addtherolecsvsintheaccount}

在 Box 帐户中，选择&#x200B;**“导入 > 用户 > 内部”**，然后上传文件 role.csv 和 user_role.csv。

* 自定义角色CSV必须复制到文件夹“import->user->internal->user_role”中
* 必须将用户CSV复制到“import->user->internal”文件夹中

两个 CSV 文件均必须通过 Box 或 FTP 上传，不得通过用户界面上传。

>[!NOTE]
>
>用户CSV文件是必填项，但自定义角色CSV是可选的。 所有存在的文件均会处理，其他文件则予以跳过。

通过 csv 文件创建的自定义角色对用户界面中的管理员不可见。这些角色与通过用户界面创建的（或稍后创建的）角色没有关系，也不受其影响。

通过csv创建的自定义角色可以完全通过csv本身进行管理。 这包括添加、修改和删除角色。

从 user_role csv 删除分配条目即可撤销已分配的角色。但通过管理员用户界面完成的分配不受此影响。

要分配和撤销某个自定义角色，请更新 csv 文件。

## 同步自定义角色 {#synchronizationofcustomroles}

在集成管理员将基于角色的 CSV 上传到连接器的存储空间后，管理员可以启用与 CSV 同步。每次在 CSV 中更新、添加或删除任何自定义角色时，管理员都可以同步文件中的信息并使角色列表保持为最新版本。

在“管理员”面板上的“开始使用”页面上，单击 **[!UICONTROL 设置]** > **[!UICONTROL 数据源]**.

在“同步设置”部分中，启用选项&#x200B;**[!UICONTROL “启用自动同步“]** 。

![](assets/sync-settings.png)

*选择启用自动同步选项*

选中此项后，您即可在“同步时间”字段中指定确切时间，安排同步时间。 如果指定的同步时间为上午 12:00，自定义角色即会在每天指定的时间准时进行更新。

如果要按需同步数据，单击&#x200B;**[!UICONTROL “立即同步”]**。

## 配置角色时的限制 {#constraintswhileconfiguringroles}

在任何帐户中，角色名称必须唯一。 因此，通过用户界面或 CSV 创建的角色名称不得与由用户界面或 CSV 创建的其他角色同名。

同样，在管理员用户界面上，无法为用户分配由 CSV 创建的可配置角色，因为这些角色不可用。

然而，用户分配 CSV 可以分配由用户界面创建的角色。
