---
description: 了解如何将LinkedIn学习连接器与Adobe Learning Manager集成
jcr-language: en_us
title: LinkedIn 学习连接器
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 1%

---


# Adobe Learning Manager中的LinkedIn学习连接器

## 介绍

linkedIn Learning连接器可让您将LinkedIn Learning内容与Adobe Learning Manager无缝集成。 借助此连接器，组织可以自动将LinkedIn学习课程引入Adobe Learning Manager，以便学习者可以直接在平台内查找、注册和完成LinkedIn课程。

设置后，学习者可在Adobe Learning Manager中跟踪其LinkedIn学习内容的进度，从而让管理员可监控完成情况和所花费的时间。 您可以计划自动内容同步、运行按需导入以及按语言、库或自定义标签过滤引入系统的课程。

>[!NOTE]
>
>从LinkedIn学习导入课程时，Adobe Learning Manager会为每个课程生成唯一的学习对象（学习对象）ID。 linkedIn平台会向Adobe Learning Manager报告用于LinkedIn学习内容的学习时间。 如果LinkedIn平台不发送此数据，则Adobe Learning Manager无法记录它，花费的时间将显示为零。

## 配置LinkedIn学习门户设置

配置LinkedIn学习门户设置：

1. 以管理员身份登录&#x200B;**LinkedIn学习LMS**。
2. 从顶部导航面板中选择&#x200B;**管理员**。
3. 单击&#x200B;**设置**&#x200B;选项卡。
4. 从左侧导航中，选择&#x200B;**播放集成**，然后选择&#x200B;**集成**&#x200B;选项卡。
5. 展开&#x200B;**LMS内容启动设置**。
6. 添加以下主机名：

   - learningmanager.adobe.com
   - learningmanagerlrs.adobe.com
   - cpcontents.adobe.com
7. 选择&#x200B;**启用AICC集成**。

   ![](assets/linkedin-connector1.png)
   _选择“启用AICC集成”以配置LinkedIn学习连接器_

## 在Adobe Learning Manager中连接LinkedIn学习

要配置LinkedIn学习连接器，请执行以下操作：

1. 以集成管理员身份登录Adobe Learning Manager.
2. 将鼠标悬停在&#x200B;**LinkedIn Learning**&#x200B;磁贴上，然后选择&#x200B;**连接**。

   ![](assets/linkedin-connector2.png)
   _选择“连接”以配置LinkedIn学习连接器_

3. 在连接设置页面上，执行以下操作：
   - 键入&#x200B;**连接名称**。
   - 键入&#x200B;**应用程序密钥**&#x200B;和&#x200B;**密钥**。

   ![](assets/linkedin-connector3.png)
   _键入连接名称、应用程序密钥和密钥以配置LinkedIn学习连接器_

   >[!NOTE]
   >
   >企业管理员可通过在LinkedIn学习管理门户中创建应用程序来生成这些密钥。

4. 选择&#x200B;**保存**&#x200B;以添加连接。

要编辑现有连接，请在&#x200B;**LinkedIn Learning**&#x200B;磁贴上选择&#x200B;**管理连接**。

>[!IMPORTANT]
>
>必须先为您的帐户启用&#x200B;**迁移**&#x200B;功能，然后才能配置此连接器。


## 管理连接和同步

管理LinkedIn Learning连接器：

1. 选择&#x200B;**管理连接**&#x200B;并选择连接。
2. 在左侧窗格中，选择&#x200B;**配置**。
3. 选择&#x200B;**启用连接**。

   ![](assets/linkedin-connector4.png)
   _在“配置LinkedIn学习”连接器页面中选择“启用连接”_

4. 选择&#x200B;**编辑**&#x200B;以更新凭据。 使用&#x200B;**重置**&#x200B;以撤消编辑。
5. 若要自动同步，请选择&#x200B;**启用计划**。
6. 设置开始日期、时间和频率（例如，每3天）。
7. 选择&#x200B;**“保存”**。

### 按需同步

要运行按需同步，请执行以下操作：

1. 在左侧窗格中选择&#x200B;**按需执行**。
2. 键入&#x200B;**开始日期**。
3. 选择以下任一选项： **启用**&#x200B;或&#x200B;**禁用执行期间对Adobe Learning Manager的访问**：
   - **在执行期间启用对Adobe Learning Manager的访问**：用户无需停机。
   - **在执行期间禁用对Adobe Learning Manager的访问**：在同步期间应用程序不可用。

   ![](assets/linkedin-connector5.png)
   _选择“按需执行”以运行导入_

4. 选择“**执行**”，以便从该日期开始从LinkedIn Learning导入用户订阅源和数据。

要监视所有同步运行，请执行以下操作：

在左侧窗格中选择&#x200B;**执行状态**&#x200B;以查看所有同步的历史记录、持续时间、类型（已计划或按需）和当前状态（正在进行、已完成）。

>[!NOTE]
>
>如果删除并重新创建连接，则会保留以前的运行，并在&#x200B;**执行状态**&#x200B;中显示。 您只能重新运行最近的同步。

## 筛选 LinkedIn 学习内容

设置连接器时，您可以筛选要导入的LinkedIn学习课程。

要设置过滤器，请执行以下操作：

1. 在左侧窗格中选择&#x200B;**筛选器**。
2. 在“**使用**&#x200B;筛选培训”下选择所需选项。
   - **无筛选器** — 导入所有课程。
   - **语言** — 按特定语言筛选课程。
   - **库** — 按LinkedIn学习库筛选课程。
3. 如果按&#x200B;**语言**&#x200B;筛选，请选择所需的语言。 例如，**英语**&#x200B;和&#x200B;**西班牙语**。
4. 在&#x200B;**将培训导入**&#x200B;中，选择课程导入位置。
5. 选择如何组织导入的课程。
6. 为&#x200B;**基于**&#x200B;选项隔离培训选择以下任一选项：

   - **语言** — 按语言分组。
   - **库** — 按库分组。
7. 在&#x200B;**导入标签**&#x200B;下，选择要应用于导入的课程的标签类型。

   - **语言**
   - **库**
   - **主题**
   - **主题**
   - **自定义标记**
8. 在&#x200B;**自定义标记**&#x200B;字段中，键入要分配的自定义标记。 用逗号分隔多个标签。

   ![](assets/linkedin-connector6.png)
   _选择筛选器选项以从LinkedIn学习连接器导入数据_

9. 如果希望学习者能够取消注册这些课程，请选择&#x200B;**用户可以取消注册**。
10. 选择&#x200B;**保存**&#x200B;以应用您的筛选器和导入设置。
