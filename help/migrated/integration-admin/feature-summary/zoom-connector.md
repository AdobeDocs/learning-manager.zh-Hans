---
description: 了解如何将Zoom连接器与Adobe Learning Manager集成
jcr-language: en_us
title: 缩放连接器
contentowner: mmanuel
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: 3628dd3701949da127b138e0e1ffc2db8e84eab1
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 2%
---

# Adobe Learning Manager中的缩放连接器

## 简介

借助Adobe Learning Manager中的Zoom连接器，公司能够提供实时虚拟教室会话、管理学习者注册情况以及跟踪出勤和完成情况。 它还支持在单个帐户内建立多个Zoom连接，集成管理员可根据角色或用户组管理访问权限，作者可为课程会话选择可用连接。 会话结束后，出勤和性能数据会同步回Adobe Learning Manager以进行报告和跟踪。

## 设置缩放连接器

要配置缩放连接器，请执行以下操作：

1. 以集成管理员身份登录Adobe Learning Manager.
2. 将鼠标悬停在&#x200B;**缩放**&#x200B;图块上。

   ![](assets/zoom-connector1.png)
   _在Adobe Learning Manager中配置缩放连接器_

3. 选择&#x200B;**连接**。 “缩放连接器设置”页面随即打开。
4. 在相应字段中键入以下帐户详细信息。 您可以从Zoom帐户管理员处获取这些凭据：

   * 连接名称
   * 缩放帐户ID
   * 客户端 ID
   * 客户端密钥
   * 超级管理员电子邮件地址
   * 可以使用此连接器的角色或组（可选）

   ![](assets/zoom-connector2.png)
   _键入配置详细信息以设置缩放连接器_

5. 选择&#x200B;**连接**&#x200B;以建立集成。

>[!NOTE]
>
>启用连接器时，**学习者必须为其Zoom和Adobe Learning Manager帐户使用相同的电子邮件地址**，以确保正确同步用户数据。

## 添加多个缩放连接

您可以将多个Zoom连接添加到Adobe Learning Manager，每个连接都链接到不同的Zoom帐户。 例如，您可以为不同的合作伙伴或团队创建单独的连接，并指定每个连接可使用哪些角色或用户组。

您可以添加的连接数量取决于您的Adobe Learning Manager帐户级别：

| **帐户层** | **最大缩放连接数** |
|---|---|
| 的权限， | 6 |
| Ultimate | 50 |

## 创建Zoom课程

建立连接后：

1. 以&#x200B;**作者**&#x200B;身份登录并创建新的虚拟教室课程。
2. 选择&#x200B;**Zoom**&#x200B;作为会议系统，然后从列表中选择要使用的Zoom连接。
   >[!NOTE]
   >
   >该列表仅显示您的角色或用户组可用的连接，会话一次使用一个连接。
3. 通过管理员、经理或自助注册为学习者分配课程。
4. 注册后，学习者会收到一封包含课程详细信息的电子邮件。
5. 学习者可以登录其Adobe Learning Manager帐户来访问课程并加入Zoom会话。

## 缩放适用于作者的连接

创建或编辑课程会话时，您可以从“缩放连接”中选择适用于您的角色或用户组的连接。 集成管理员定义可以访问每个Zoom连接的角色或用户组。

例如，假设集成管理员配置两个Zoom连接： **合作伙伴A Zoom**&#x200B;和&#x200B;**合作伙伴B Zoom**，并将每个连接分配给不同的用户组：

* 如果您同时属于合作伙伴A和合作伙伴B组，则可以选择任一连接。
* 如果您仅属于合作伙伴A组，则可以选择&#x200B;**合作伙伴A缩放**。
* 如果您不属于任一组，则无法选择这些连接。

>[!NOTE]
>
>一个会话只能使用一个Zoom连接。 如果有多个连接可用，请选择要用于会话的连接。

## 管理缩放连接

**管理连接**&#x200B;页面显示为您的帐户配置的Zoom连接。 **可见**&#x200B;列指示可使用每个连接的角色或用户组。 在此页面中，您可以编辑、启用或禁用以及删除现有的缩放连接。

![使用“启用连接”、“凭据”和“角色”或“组”设置缩放连接“配置”页面](assets/zoom-connection-configure-page.png "使用“启用连接”、“凭据”和“角色”或“组”设置缩放连接“配置”页面")

### 编辑缩放连接

要编辑现有缩放连接，请执行以下操作：

1. 在&#x200B;**管理连接**&#x200B;页面上选择要编辑的连接。
1. 在“配置”选项卡上，更新以下任意选项：

   1. 要更新Zoom帐户凭据，请选择&#x200B;**凭据**&#x200B;旁边的&#x200B;**编辑**，并更新所需的详细信息。
   1. 要更改谁可以使用连接，请更新可以使用此连接器的&#x200B;**角色或组**。

1. 选择&#x200B;**“保存”**。

### 启用或禁用缩放连接

默认情况下，将启用新的缩放连接。 您可以禁用连接，以防止作者在不删除连接的情况下使用连接。

要禁用连接：

1. 在&#x200B;**管理连接**&#x200B;页面上，选择要禁用的连接。
1. 打开&#x200B;**启用连接**。
1. 选择&#x200B;**“保存”**。

   已禁用的连接不再适用于关联角色或组中的用户。

要重新启用连接，请选择&#x200B;**启用连接**，然后选择&#x200B;**保存**。

### 删除缩放连接

要删除Zoom连接：

1. 在&#x200B;**管理连接**&#x200B;页面上，导航到要删除的连接。
1. 选择连接旁边的&#x200B;**删除**&#x200B;图标。
1. 选择&#x200B;**删除**。

## 跟踪出勤和完成情况

虚拟会话结束后：

* Adobe Learning Manager会自动从Zoom接收完成状态。
* 管理员可以在Adobe Learning Manager中查看出勤和得分报告，以跟踪学习者的参与程度和表现。

## 创建缩放服务器到服务器OAuth应用程序

要将“缩放”连接器与Adobe Learning Manager一起使用，必须创建“缩放服务器到服务器”OAuth应用程序并配置所需范围。

### 所需的OAuth范围

在Zoom中创建应用程序时，请确保选择以下范围：

| 您想要什么 | 搜索此关键字 | 然后选取 |
|---|---|---|
| 查看所有用户会议 | 会议 | `meeting:read:meeting:admin, meeting:read:list_meetings:admin` |
| 查看/管理所有用户会议 | 会议 | `meeting:update:meeting:admin, meeting:delete:meeting:admin, meeting:write:meeting:admin` |
| 查看报告数据 | 报告 | `report:read:meeting:admin, report:read:user:admin` （选择与您的终结点匹配的终结点。） |
| 查看所有用户信息 | 用户 | `user:read:user:admin, user:read:list_users:admin` |
| 管理用户 | 用户 | `user:update:user:admin, user:write:user:admin` |
| 添加会议注册者 | 注册者 | `meeting:write:registrant:admin` |
| 列出所有会议注册者 | 注册者 | `meeting:read:list_registrants:admin` |
| 子帐户会议 | 会议+查找:master | `meeting:write:meeting:master` |
| 会议参与者报告 | 参与者 | `report:read:list_meeting_participants:admin` |

