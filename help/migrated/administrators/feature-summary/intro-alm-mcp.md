---
description: 将Adobe Learning Manager扩展到Claude、ChatGPT Enterprise和自定义客服专员，以便学习者可以查找课程、跟踪进度并获取答案。
jcr-language: en_us
title: Adobe Learning Manager模型上下文协议服务器
exl-id: 8d0a25a6-1301-4f68-8db7-e3b1d3ff6537
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 0%
---

# Adobe Learning Manager模型上下文协议服务器

模型上下文协议(MCP)是一种开放标准，允许AI客户端发现和调用外部工具。 Adobe Learning Manager MCP服务器可将Adobe Learning Manager学习者工具公开到任何MCP兼容的客户端，例如自定义企业代理、Claude或ChatGPT Enterprise。 学习者可从已使用的客户端获取培训和进度，而学习内容和记录仍保留在Adobe Learning Manager中。

## 工作原理

学习者向AI客户端发送自然语言请求。 客户端选择最相关的学习者工具，并使用学习者的OAuth访问令牌调用MCP服务器。 Adobe Learning Manager在该学习者身份下运行该工具并返回结果，客户端即编写最终响应。

每个呼叫均包含学习者身份。 因此，学习者只能检索他们已被允许访问的内容和记录。

AI客户端调用MCP服务器，该服务器会将每个请求路由到匹配的学习者工具。

## 学习者功能

学习者在已经使用的AI客户端中使用自然语言工作。 客户端会解释每个请求，调用相应的Adobe Learning Manager学习者工具，然后根据学习者可访问的内容返回响应。 学习者可以：

* 发现他们可用的课程、认证和学习路径。
* 跟踪其注册、进度和截止日期，包括即将过期的学习。
* 从学习内容中获取答案。
* 根据目标生成个性化学习路径并保存。

有关完整列表，请查看&#x200B;**学习者工具参考**。

## 客户和合作伙伴培训

>[!IMPORTANT]
>
>构建自己的企业代理的客户也可以连接到服务器。 例如，合作伙伴组织可以通过自己的代理为自己的客户提供学习权限。

客户和合作伙伴教育是MCP服务器的主要用途。 组织如果自行构建企业AI代理，则可以将这些代理连接到Adobe Learning Manager学习者工具。 然后，他们的客户和合作伙伴会在他们已使用的助理中学习，而不用转到单独的学习助理。

例如，Acme Inc.会构建自己的企业AI助手。 Acme Inc.合作伙伴访问助理，了解Acme Inc.产品。 助手通过MCP服务器连接到Acme Inc. Adobe Learning Manager帐户，并返回与学习相关的响应。 合作伙伴永远不会离开Acme Inc.的体验。

此方法使组织能够：

* 利用合作伙伴现有的AI体验进行学习。
* 使用Adobe Learning Manager学习者工具扩展自定义企业代理。
* 将学习嵌入到他们自己的工作流程中。
* 将学习与其企业AI生态系统集成。

## 员工教育

已经使用AI客户端的员工（如Claude）可以在那里获取学习信息。 例如，员工无需切换到Adobe Learning Manager，即可检查已分配的学习、查看注册内容、查找主题课程或请求学习路径。 对于示例请求，进一步了解[学习者示例提示](/help/migrated/learners/feature-summary/sample-prompts-for-learners.md)。

此方法使员工能够：

* 留在他们已使用的工具中。
* 无论身在何处，都可以到达学习目的地。
* 使用任何MCP兼容的AI客户端作为Adobe Learning Manager的入口点。
* 在不更改上下文的情况下检索学习信息。

## 一个服务器同时适用于两个受众

客户和合作伙伴教育以及员工教育使用相同的学习者工具和相同的服务器。 只有观众会改变。 选择适合您的学习者身份的方法。

| **受众** | **示例** | **学习者工作场所** |
|----|----|----|
| 外部 | 客户和合作伙伴 | 您组织自己的企业AI代理 |
| 内部 | 员工 | 企业AI客户端，例如Claude或ChatGPT Enterprise |

## 设置角色

设置分为三个角色。

* **管理员：**&#x200B;在Adobe Learning Manager中创建MCP客户端应用程序并对其进行管理。 详细了解[配置MCP服务器](/help/migrated/administrators/feature-summary/configure-mcp-admin.md)。
* **AI客户端管理员：**&#x200B;将服务器添加到组织的企业AI客户端，如Claude或ChatGPT Enterprise。
* **学习者：**&#x200B;在AI客户端中选择&#x200B;**Connect**，对连接进行身份验证并提供其Adobe Learning Manager帐户详细信息。

## 学习者请求的安全性

每个学习者都对连接进行身份验证并提供其Adobe Learning Manager帐户详细信息。 每个请求均以该学习者身份运行，因此AI客户端仅返回学习者可在Adobe Learning Manager中访问的信息。 服务器不向学习者授予额外访问权限。

## 限制

* MCP服务器仅适用于Adobe Learning Manager Ultimate层帐户。
* 工具的可用性取决于AI客户端支持的功能。
* 服务器将每个请求都视为新请求。 仅当AI客户端保留对话上下文时，多轮对话才有效。
