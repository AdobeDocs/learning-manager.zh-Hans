---
description: 将Adobe Learning Manager MCP Server注册为企业AI客户端中的连接器，以便公司中的学习者可以连接和查询其学习内容。
jcr-language: en_us
title: 将Adobe Learning Manager添加到您的企业AI客户端
exl-id: d893efb7-dc0d-4a3a-88d6-b315340e5daa
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%
---

# 将Adobe Learning Manager添加到您的企业AI客户端

## 概述

您需要AI客户端中的管理员权限。 在开始之前，请从Adobe Learning Manager管理员处获取MCP端点URL、客户端ID和密钥。 详细了解[配置模型上下文协议服务器](/help/migrated/administrators/feature-summary/configure-mcp-admin.md)。

## 添加连接器

1. 以管理员身份登录您的企业AI客户端。
2. 打开连接器的“管理员”设置。
3. 添加使用模型上下文协议的自定义连接器。
4. 输入Adobe Learning Manager MCP终结点URL。
5. 输入客户端ID以及您的Adobe Learning Manager管理员提供的密钥。
6. 保存连接器。
7. 为学习者提供连接器。

>[!NOTE]
>
>AI客户端界面经常更改。 如果这些步骤与您的客户端不匹配，请参阅AI客户端供应商的文档来添加远程连接器。

## 故障排除

**学习者看不到该连接器。**
确认已为学习者的工作区或组启用连接器。

**当学习者选择“连接”时，授权失败。**
验证客户端ID和密钥是否与Adobe Learning Manager中服务器的**客户端凭据**&#x200B;页面上的值匹配。
