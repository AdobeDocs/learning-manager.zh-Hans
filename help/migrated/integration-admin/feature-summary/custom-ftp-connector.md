---
description: Adobe Learning Manager中的自定义FTP连接器
jcr-language: en_us
title: 自定义FTP连接器
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# Adobe Learning Manager中的自定义FTP连接器

## 简介

利用Adobe Learning Manager中的自定义FTP连接器，您可以在Adobe Learning Manager和您组织的FTP (SFTP)服务器之间实现安全、自动的数据交换。 通过此集成，管理员可以从外部系统导入用户数据，并按计划导出学习者成绩单或技能数据。 此设置可简化数据同步、减少手动工作，并支持与第三方HR或报告系统的无缝集成。 配置需要与您的IT团队进行协调，并需要Adobe的客户成功经理(CSM)的帮助。

>[!NOTE]
>
>要配置自定义FTP连接，请联系您的客户成功经理(CSM)。 设置过程可能需要IT团队的帮助，以将IP地址列入白名单、打开所需的端口以及创建具有必要访问权限的文件夹。

## 支持的功能

自定义FTP连接器支持以下操作：

### 数据导入

用户导入过程会自动从FTP服务器获取员工数据，并将其导入Adobe Learning Manager。 在集成多个生成包含用户数据的CSV文件的系统时，此功能非常有用。

- 将CSV文件放在FTP服务器上指定的&#x200B;**导入**&#x200B;文件夹中。
- Adobe Learning Manager会检测文件，根据需要将其合并，并根据定义的计划导入用户数据。

请参阅[计划](/help/migrated/integration-admin/feature-summary/custom-ftp-connector.md#scheduling-reports)部分以了解如何自动执行此过程。

### 属性映射

作为集成管理员，您可以将CSV文件中的列映射到Adobe Learning Manager中的可分组属性。

- 映射是一次性设置。
- 相同的映射用于后续导入。
- 如果数据结构发生更改，则可以重新配置映射。

### 数据导出

Adobe Learning Manager允许您导出：

- 用户技能
- 学习者成绩单

这些报告文件位于FTP上的export文件夹中，可供第三方系统用于报告、分析或其他下游流程。

### 计划报告

集成管理员可以计划以下两项：

- 用户导入
- 学习者成绩单导出

计划可确保Adobe Learning Manager环境与源系统保持同步。 您可以根据需要配置每日同步或自定义时间间隔。

## 设置自定义FTP连接器

配置自定义FTP连接器：

1. 以集成管理员身份登录Adobe Learning Manager.
2. 将鼠标悬停在&#x200B;**自定义FTP**&#x200B;磁贴上，然后选择&#x200B;**连接**。

   ![](assets/custom-ftp-connector1.png)
   _选择“连接”以配置自定义FTP连接器_

### 选择身份验证方法

您可以使用以下两种身份验证类型之一配置自定义FTP连接：

#### 基本身份验证帐户

1. 键入以下详细信息：

   - **您的FTP域**
   - **FTP用户名**
   - **FTP密码**

   ![](assets/custom-ftp-connector2.png)
   _键入配置的FTP域、用户名和密码。_

2. 选择&#x200B;**连接**。

#### 证书身份验证

如果您的FTP服务器支持SSH密钥身份验证：

1. 选择&#x200B;**生成SSH密钥**。

   ![](assets/custom-ftp-connector3.png)
   _选择“生成SSH密钥”以下载密钥_

2. 公钥将下载到您的计算机。
3. 将此密钥添加到FTP服务器的授权密钥列表中。
4. 键入以下详细信息：

   - **您的FTP域**
   - **FTP用户名**
5. 选择&#x200B;**连接**。

>[!NOTE]
>
>自定义FTP配置仅支持&#x200B;**SFTP**&#x200B;服务器。

## 连接后设置

建立连接后：

- Adobe Learning Manager会自动在您的FTP服务器上为&#x200B;**导入**&#x200B;和&#x200B;**导出**&#x200B;创建文件夹。
- 您可以根据计划和映射设置开始导入和导出数据。
