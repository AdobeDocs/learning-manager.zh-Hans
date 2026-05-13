---
description: 了解如何将Adobe Connect连接器与Adobe Learning Manager集成
jcr-language: en_us
title: Adobe Connect连接器
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 2%

---


# Adobe Learning Manager中的Adobe Connect连接器

## 简介

Adobe Learning Manager与Adobe Connect集成以帮助您提供和管理虚拟教室培训。 通过此集成，您可以安排会话、使用永久或动态会议室、捕捉出席情况、导入测验结果并为学习者提供会话记录。

## 配置 Adobe Connect

要配置Adobe Connect，请执行以下操作：

1. 以集成管理员身份登录Adobe Learning Manager.
2. 将鼠标悬停在&#x200B;**Adobe Connect**&#x200B;磁贴上，然后选择&#x200B;**连接**。

   ![](assets/adobe-connect-connector1.png)
   _选择“连接”以配置Adobe Connect连接器_

3. 键入以下详细信息：

   - **连接名称**
   - **Adobe Connect URL**
   - **连接管理员电子邮件**
4. 键入&#x200B;**Connect管理员登录ID**（如果未使用Adobe Connect的电子邮件登录，则为必填）。

   ![](assets/adobe-connect-connector2.png)
   _键入Adobe Connect配置所需的详细信息_

5. 选择&#x200B;**启用Connect身份验证**。

   >[!NOTE]
   >
   >仅支持Adobe托管的Connect帐户。 （域必须以.adobeconnect.com结尾）

6. 选择&#x200B;**连接**。

对管理员电子邮件ID进行身份验证后：

- Adobe Learning Manager会显示一条成功消息，确认Connect已集成。
- 该请求将交予Adobe Connect后端团队以获得批准。 这通常需要一到两天的时间。

>[!IMPORTANT]
>
>Adobe Connect帐户管理员在首次登录时必须接受条款和条件。 如果未完成此操作，登录身份验证可能会失败。

## 添加虚拟教室会话信息

如果作者未提供虚拟教室课程的会话详细信息，管理员可以添加这些信息：

1. 以管理员身份登录。
2. 选择VC课程。
3. 选择&#x200B;**实例**，然后选择&#x200B;**会话详细信息**。
4. 选择&#x200B;**编辑**&#x200B;图标以添加或更新会话信息。

>[!NOTE]
>
>您的Connect帐户必须具有足够的会议室和容量，以便并发用户能够运行虚拟课堂。 除非您使用的是长期会议室，否则每个Adobe Learning Manager虚拟教室会话都会自动创建新的Connect会议室。

## 长期会议室

Adobe Connect支持永久会议室，这些会议室可以随时重复使用。

- 您可以使用Connect中的现有长期教室创建虚拟教室会话。
- 您还可以选择让Adobe Learning Manager改为为每个会话创建一个动态会议室。

学习者使用Adobe Connect参加会话时，会使用安全身份验证通过Learning Manager进入会议室。

完成会话后，学习者可以在其Learning Manager应用程序中访问会话录制内容和密码。

## 从 Adobe Connect 导入测验分数

Adobe Learning Manager可以从Adobe Connect会话中导入测验数据，并将其与其他报告工作流程相结合。 这包括测验分数、学习者回答和完成数据，例如自学模块的工作方式。

### 导入测验的工作流程

#### Adobe Connect（主持人）

- Connect主持人负责创建课程并上传包含交互式测验的内容。
- 主持人设置虚拟教室(VC)培训，并将课程链接到VC，或者在会话期间使用&#x200B;**共享课程**&#x200B;选项共享该课程。

#### Adobe Learning Manager（作者）

- 作者在Adobe Learning Manager中创建了模块类型设置为&#x200B;**虚拟教室**&#x200B;的课程。
- 从&#x200B;**会议系统**&#x200B;下拉列表中，选择&#x200B;**Connect**&#x200B;作为VC提供方。
- 选择主持人在Connect中创建的&#x200B;**长期会议室**。
- 指定讲师、保存和发布课程。

#### Adobe Learning Manager（学习者）

- 学习者注册课程并加入Connect VC会话。
- Connect主机允许学习者访问会话。

### Adobe Connect（主持人和学习者）

- 主持人分享答疑中的测验。
- 学习者完成测试并退出会话。

### Adobe Learning Manager（同步与管理员）

- 会话结束后，Adobe Learning Manager会自动同步测验数据。
- 测验导入工作流程在计划持续时间结束后开始。
- 要跟踪进度，集成管理员可以在Adobe Connect连接器中检查&#x200B;**执行状态**。
- 导入完成后，状态将更新为&#x200B;**已完成**。

然后，管理员可以查看导入的结果：

- **考勤和评分：**&#x200B;查看最终测验分数和考勤。
- **L2测验分数：**
   - **按用户：**&#x200B;以分数和百分比显示各个分数。
   - **按问题：**&#x200B;在报告图表中显示测验结果。
