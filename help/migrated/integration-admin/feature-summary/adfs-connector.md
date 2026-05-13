---
description: 了解如何将ADFS连接器与Adobe Learning Manager集成
jcr-language: en_us
title: ADFS连接器
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 3%

---


# Adobe Learning Manager中的ADFS连接器

## 简介

通过Adobe Learning Manager中的ADFS连接器，可使用Active Directory联合身份验证服务(ADFS)与Microsoft Azure Active Directory集成。 此集成支持将用户数据从Azure AD自动同步到Learning Manager。 此连接器具有属性映射、用户筛选和计划导入等功能，可帮助简化用户管理并确保学习者数据保持准确且最新。 这对于依靠ADFS进行集中身份和访问管理的组织特别有用。

## 先决条件

在Adobe Learning Manager中配置ADFS连接器之前，请在Azure门户中完成以下步骤：

- 注册应用程序
- 生成客户端密钥
- 设置API权限

### 在Azure中注册应用程序

要在Azure中注册应用程序，请执行以下操作：

1. 登录到[Azure门户](https://portal.azure.com/)。
2. 导航到&#x200B;**Azure Active Directory**。
3. 选择&#x200B;**添加**，然后选择&#x200B;**应用程序注册**。
4. 键入应用程序的名称，然后选择&#x200B;**注册**。

### 生成客户端密钥

要创建客户端密钥，请执行以下操作：

1. 在新注册的应用中，转到&#x200B;**证书和密钥**。
2. 选择&#x200B;**新建客户端密钥**。
3. 添加描述并将到期时间设置为&#x200B;**24个月**。
4. 将&#x200B;**客户端密钥值**&#x200B;保存在安全位置。

### 设置API权限

添加API权限：

1. 选择&#x200B;**API权限**，然后选择&#x200B;**添加权限**。
2. 选择&#x200B;**Microsoft Graph**，然后选择&#x200B;**申请权限**。
3. 搜索并选择以下权限：

   - **Directory.Read.All** — 读取目录数据
   - **User.Read.All** — 读取所有用户的完整个人资料
4. 选择&#x200B;**添加权限**。
5. 为权限授予&#x200B;**管理员同意**。

## 在Learning Manager中配置ADFS连接器

您可以在Adobe Learning Manager中配置ADFS连接器，以从ADFS导入用户数据、将用户技能导出回ADFS以及安排自动同步以使两个系统保持最新。

要配置ADFS连接器，请执行以下操作：

1. 以集成管理员身份登录Adobe Learning Manager.
2. 将鼠标悬停在&#x200B;**ADFS**&#x200B;连接器图块上。
3. 选择&#x200B;**连接**。

   ![](assets/adfs-connector1.png)
   _选择“连接”以配置ADFS连接器_

### 输入连接详细信息

在ADFS配置页面上：

1. 键入以下详细信息：

   - 连接名称
   - 客户端 ID
   - 客户端密钥

   ![](assets/adfs-connector2.png)
   _键入配置详细信息以连接ADFS_

2. 选择&#x200B;**连接**。
3. Adobe Learning Manager将从Azure门户获取并自动填充&#x200B;**租户ID**&#x200B;和&#x200B;**主域**。

## 从ADFS导入用户

### 映射属性

- 集成管理员可以将ADFS属性映射到Adobe Learning Manager中相应的可分组属性。
- 此映射是一次性配置，可重复用于所有后续用户导入。
- 如果需要，您可以随时修改属性映射。

### 自动导入用户

- Adobe Learning Manager会按计划的时间间隔自动从ADFS中提取用户数据。
- 这有助于使用户记录跨系统保持同步。

### 过滤用户

- 管理员可以应用筛选器来限制导入的用户。
- 例如，仅导入特定经理或部门下的用户。
