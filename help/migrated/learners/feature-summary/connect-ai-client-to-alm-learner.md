---
description: 授权AI客户端访问一次Adobe Learning Manager，以便以自然语言询问课程、注册和学习路径相关信息。
jcr-language: en_us
title: 将您的AI客户端连接到Adobe Learning Manager
exl-id: dfb3d08d-405d-468c-9126-71a345815d5c
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%
---

# 将您的AI客户端连接到Adobe Learning Manager

## 概述

集成管理员必须先配置连接器。 如果您没有看到连接器，请与您的管理员联系。 **该连接器仅适用于Adobe Learning Manager Ultimate层帐户**。 管理员可以查看[将Adobe Learning Manager添加到您的企业AI客户端](/help/migrated/administrators/feature-summary/add-alm-to-ai-client.md)。

1. 打开组织的AI客户端，例如Claude或ChatGPT Enterprise。
2. 在连接器列表中查找Adobe Learning Manager连接器。
3. 选择&#x200B;**连接**。
4. 对连接进行身份验证并在出现提示时提供您的Adobe Learning Manager帐户详细信息。
5. 询问有关学习的问题。 如需获取创意，请详细了解[学习者示例提示](/help/migrated/learners/feature-summary/sample-prompts-for-learners.md)。

>[!NOTE]
>
>您只需进行一次身份验证。 您的请求以您自己的权限运行，因此您只能看到在Adobe Learning Manager中可以访问的内容。

## 故障排除

**找不到连接器**
请让您的管理员为您启用该连接器。

**AI客户端不记得您之前的问题**
服务器将每个请求都视为新请求。 对话是否继续取决于您的AI客户端。 请在下一个问题中重述相关详细信息。

**AI客户端未调用连接器**
根据您的需要命名问题，例如注册或课程主题。
