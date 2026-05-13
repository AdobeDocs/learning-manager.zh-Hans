---
description: 了解如何将Harvard ManageMentor与Adobe Learning Manager集成
jcr-language: en_us
title: Harvard ManageMentor 连接器
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---


# Adobe Learning Manager中的Harvard ManageMentor连接器

## 简介

**Harvard ManageMentor连接器**&#x200B;专为使用Harvard ManageMentor的企业客户而设计。 它允许学习者直接从Adobe Learning Manager发现和访问Harvard ManageMentor课程。 连接后，系统可以定期获取学习者进度数据，并根据导入的元数据在Adobe Learning Manager中创建课程。

本文介绍了如何在Adobe Learning Manager中配置和使用Harvard ManageMentor连接器。

通过此集成，集成管理员可以将公司的Harvard ManageMentor帐户连接到Adobe Learning Manager，从而自动导入课程并跟踪学习者进度，而无需从头开始创建新培训内容。

## 先决条件

在配置连接器之前，请确保已为您的帐户启用&#x200B;**迁移**&#x200B;功能。

## 设置连接器

使用Harvard ManageMentor连接器将课程从Harvard ManageMentor导入到Adobe Learning Manager。 连接帐户后，您可以导入课程详细信息并跟踪学习者进度。

要设置连接器，请执行以下操作：

1. 以集成管理员身份登录。
2. 在主页上选择&#x200B;**Harvard ManageMentor**。
3. 从连接器磁贴上的以下选项中进行选择：
   - **入门**
   - **连接**
   - **管理连接**

   ![](assets/harvard-managementor-connector1.png)
   _Harvard ManageMentor图块显示三个配置选项_

## 创建新连接

要创建新连接，请执行以下操作：

1. 在&#x200B;**Harvard ManageMentor**&#x200B;磁贴上选择&#x200B;**连接**。

   ![](assets/harvard-managementor-connector2.png)
   _选择“连接”以新建Harvard ManageMentor连接_

2. 在&#x200B;**连接名称**&#x200B;字段中键入连接。
3. 选择&#x200B;**连接**&#x200B;以创建连接。

   ![](assets/harvard-managementor-connector3.png)
   _在“连接名称”字段中键入名称_

## 管理连接

设置Harvard ManageMentor连接器后，即可在Adobe Learning Manager中管理连接。 您可以更改同步设置并手动或按计划运行同步。

### 启用连接

要启用连接，请执行以下操作：

1. 在&#x200B;**Harvard ManageMentor**&#x200B;磁贴上选择&#x200B;**管理连接**。

   ![](assets/harvard-managementor-connector4.png)
   _管理连接以配置和计划数据导入_

2. 选择连接。
3. 从左侧导航窗格中选择&#x200B;**配置**。
4. 选择&#x200B;**启用连接**，然后选择&#x200B;**保存**。

   ![](assets/harvard-managementor-connector5.png)
   _启用Harvard ManageMentor连接器以导入数据_

### 计划同步

要计划同步，请执行以下操作：

1. 在&#x200B;**Harvard ManageMentor**&#x200B;磁贴上选择&#x200B;**管理连接**。
2. 选择连接。
3. 从左侧导航窗格中选择&#x200B;**配置**。
4. 在&#x200B;**计划同步**&#x200B;部分下选择&#x200B;**启用计划**。

   ![](assets/harvard-managementor-connector6.png)
   _安排将数据从Harvard ManageMentor导入到Adobe Learning Manager_

5. 选择UTC格式的开始日期和时间。
6. 键入同步应在几天后重复。
7. 选择&#x200B;**“保存”**。

将保存同步设置。 连接器将按计划运行，并从Harvard ManageMentor将数据导入Adobe Learning Manager。

## 运行按需同步

使用&#x200B;**按需同步**&#x200B;选项，您可以手动将Harvard ManageMentor中的数据导入Adobe Learning Manager。 当您想要立即更新学习者活动数据，而无需等待下一个计划的同步时，此功能非常有用。

要运行按需数据导入，请执行以下操作：

1. 在&#x200B;**Harvard ManageMentor**&#x200B;磁贴上选择&#x200B;**管理连接**。
2. 选择连接。
3. 从左侧窗格中选择&#x200B;**按需执行**。
4. 选择&#x200B;**开始日期**。

   ![](assets/harvard-managementor-connector7.png)
   _运行即时数据从Harvard ManageMentor导入到Adobe Learning Manager的按需请求_

5. 选择下列选项之一：

   - **在执行期间禁用对Adobe Learning Manager的访问**：如果同步可能会导致停机，建议使用该选项。
   - **在执行期间启用对Adobe Learning Manager的访问**：建议使用此选项以避免服务中断。
6. 选择“**执行**”以导入从开始日期到现在的所有数据。

### 查看执行历史记录

“执行状态”页按顺序列出所有同步运行。 如果运行出现错误，则会显示警告图标。 如果需要，您可以检查错误日志、修复CSV文件并重新运行最新同步。

要查看执行历史记录，请执行以下操作：

1. 在左侧窗格中选择&#x200B;**执行状态**。
2. 您可以看到以下列：
   - **运行**
   - **开始日期**
   - **持续时间**
   - **类型**（已计划或按需）
   - **状态**（正在进行或完成）

   ![](assets/harvard-managementor-connector8.png)
   _查看按需导入和计划导入的执行状态_

>[!NOTE]
>
>如果删除并重新创建连接，则仍将显示以前运行的执行历史记录。 您只能重新运行最新的同步。

### 同步要求

确保Harvard ManageMentor FTP文件夹中存在以下文件：

- **hmm12_metadata.csv**&#x200B;此文件包含课程元数据。 请遵循正确的文件命名格式。
- **client_hmm12_yyyyMMdd.csv**&#x200B;此文件是用户订阅源。 日期格式应与yyyyMMdd匹配。

**示例文件**

- [&#x200B; Harvard ManageMentor连接器的课程元数据文件](https://experienceleague.adobe.com/docs/learning-manager/assets/hmm12-metadata.csv?lang=en)
- [用于Harvard ManageMentor连接器的用户源文件](https://experienceleague.adobe.com/docs/learning-manager/assets/client-hmm12-20170304.csv?lang=en)
