---
description: 让学习者在Claude、ChatGPT Enterprise和自定义客服专员中发现课程、跟踪进度并从Adobe Learning Manager内容获得答案。
jcr-language: en_us
title: Adobe Learning Manager模型上下文协议服务器
exl-id: 8d0a25a6-1301-4f68-8db7-e3b1d3ff6537
source-git-commit: f6dc1e97076edf812862b80a6ed5931989c660da
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%
---

# Adobe Learning Manager模型上下文协议服务器

## 概述

模型上下文协议(MCP)是AI客户端连接到工具的标准方式。 Adobe Learning Manager MCP服务器可将学习带到学习者已经在工作的地方。 它将Adobe Learning Manager学习者工具公开到支持MCP的任何AI客户端，例如自定义企业代理、Claude或ChatGPT。 然后，学习者可以从同一客户端访问其培训及进度，同时内容留在Adobe Learning Manager中。

## 学习者功能

学习者在已经使用的AI客户端中使用自然语言工作。 客户端会解释每个请求，调用相应的Adobe Learning Manager学习者工具，然后根据学习者可访问的内容返回响应。 学习者可以：

* 发现他们可用的课程、认证和学习路径。
* 跟踪其注册、进度和截止日期，包括即将过期的学习。
* 从学习内容中获取答案。
* 根据目标生成个性化学习路径并保存。
有关完整列表，请查看**学习者工具参考**。

AI客户端调用MCP服务器，该服务器会将每个请求路由到匹配的学习者工具。

有关完整列表，请查看&#x200B;**学习者工具参考**。

## 客户和合作伙伴培训

客户和合作伙伴教育是MCP服务器的主要用途。 组织如果自行构建企业AI代理，则可以将这些代理连接到Adobe Learning Manager学习者工具。 然后，他们的客户和合作伙伴会在他们已使用的助理中学习，而不用转到单独的学习助理。

例如，Acme Inc.会构建自己的企业AI助手。 Acme Inc.的一位合作伙伴访问Tech Corp的环境，以了解有关Tech Corp产品的信息。 Acme的助理通过MCP服务器连接到其Adobe Learning Manager帐户，并返回与学习相关的响应，因此合作伙伴永远不会离开Acme体验。

此方法使组织能够：

* 在合作伙伴现有的AI体验中学习。
* 让自定义企业客服专员使用Adobe Learning Manager学习者工具。
* 将学习整合到他们自己的工作流程中。
* 将学习与其企业AI生态系统集成。

## 员工教育

已经使用AI客户端的员工（如Claude）可以在那里获取学习信息。 例如，员工无需切换到Adobe Learning Manager，即可检查已分配的学习、查看注册内容、查找主题课程或请求学习路径。 有关示例请求，请参阅[学习者示例提示](https://word-edit.officeapps.live.com/docs/sample-prompts-adobe-learning-manager-learners)。

此方法使员工能够：

* 停留在他们已有的工具中。
* 无论身在何处，都可以到达学习目的地。
* 使用任何支持MCP的AI客户端作为Adobe Learning Manager的入口点。
* 在不更改上下文的情况下获取学习信息。

## 一个服务器同时适用于两个受众

客户和合作伙伴教育以及员工教育使用相同的学习者工具和相同的服务器。 只有观众会改变。 选择适合您的学习者身份的方法。

| **受众** | **示例** | **学习者工作场所** |
|----|----|----|
| 外部 | 客户和合作伙伴 | 您组织自己的企业AI代理 |
| 内部 | 员工 | 企业AI客户端，例如Claude或ChatGPT Enterprise |

## 设置角色

设置分为三个角色。

* **管理员：**&#x200B;在Adobe Learning Manager中创建MCP客户端应用程序并对其进行管理。 请参阅[配置MCP服务器](https://word-edit.officeapps.live.com/docs/configure-model-context-protocol-server-adobe-learning-manager)。
* **AI客户端管理员：**&#x200B;将服务器添加到组织的企业AI客户端，如Claude或ChatGPT Enterprise。
* **学习者：**&#x200B;在AI客户端中选择&#x200B;**Connect**，对连接进行身份验证并提供其Adobe Learning Manager帐户详细信息。

## 学习者请求的安全性

每个学习者都对连接进行身份验证并提供其Adobe Learning Manager帐户详细信息。 该请求以该学习者身份运行，因此AI客户端仅返回学习者可在Adobe Learning Manager中访问的信息。 服务器不向学习者授予额外访问权限。

## 本次更新中的MCP限制

* 工具的可用性取决于AI客户端支持的功能。
* 每个请求都被视为新请求。 仅当AI客户端保留对话上下文时，多轮对话才有效。
