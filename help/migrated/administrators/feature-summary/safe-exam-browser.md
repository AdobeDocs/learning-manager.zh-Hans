---
title: 安全考试浏览器
description: 在Adobe Learning Manager中的帐户级别启用安全考试浏览器集成，以便作者需要安全的浏览器环境才能进行本机测验。
source-git-commit: 8f23f95cd81e5b64932281c990d27be0c390850b
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 1%
---

# 安全考试浏览器

安全考试浏览器通过在评估期间限制对其他浏览器和应用程序的访问，为学习者参加本机Adobe Learning Manager测验提供安全的环境。

管理员可以在帐户级别启用安全考试浏览器集成，并上传配置文件(.seb)以定义测验限制。 启用集成后，作者可以配置各个测验，以要求使用安全考试浏览器。

本文介绍如何为您的帐户启用安全考试浏览器集成。

## 启用安全考试浏览器集成

配置“安全考试浏览器”集成，使作者可在配置测验时使用该选项。 在开始之前，请确保您拥有帐户的安全考试浏览器文件。

要启用安全考试浏览器集成，请执行以下操作：

1. 以&#x200B;**管理员**&#x200B;的身份登录ALM。
1. 选择&#x200B;**设置** > **常规**。
1. 导航到&#x200B;**安全考试浏览器集成**。
1. 选择&#x200B;**“编辑”**。

   这将扩展&#x200B;**安全考试浏览器集成**。

1. 选择&#x200B;**启用**。
1. 选择&#x200B;**浏览**&#x200B;并从系统上传安全考试浏览器文件。 有关详细信息，请查看[配置安全检查浏览器文件](#configure-the-seb-file-for-macos)配置。

   ![“常规”设置中的“安全考试浏览器”集成设置](assets/safe-exam-browser-integration-settings.png "“常规”设置中的“安全考试浏览器”集成设置")

1. 选择&#x200B;**“保存”**。

   现在，作者可以在配置受支持的测验时启用安全考试浏览器。

查看[使用SEB创建课程](../../authors/feature-summary/create-a-course-with-safe-exam-browser.md)，了解有关将“安全考试浏览器”配置为&#x200B;**作者**&#x200B;的更多信息。

### 为macOS配置.seb文件 {#configure-the-seb-file-for-macos}

使用SEB配置工具创建.seb文件，以定义测验限制、安全设置和允许的应用程序。 在使用Safe Exam Browser (SEB)之前，请确保.seb文件满足以下要求：

1. 将browserWindowWebView参数设置为3(整数)以启用SEB。
1. 将startURL设置为与目标环境相对应的URL。
1. 确保.seb文件包含所需的quitURL信息。
