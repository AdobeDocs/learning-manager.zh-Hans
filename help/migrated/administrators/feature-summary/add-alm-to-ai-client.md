---
description: 将Adobe Learning Manager MCP服务器添加到企业AI客户端（例如Claude或ChatGPT Enterprise），以便学习者可以连接到该服务器
jcr-language: en_us
title: 将Adobe Learning Manager添加到您的企业AI客户端
exl-id: d893efb7-dc0d-4a3a-88d6-b315340e5daa
source-git-commit: 05691364449234a4782e2de5d4752c7b277f5fd4
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%
---

# 将Adobe Learning Manager添加到您的企业AI客户端

您需要AI客户端中的管理员权限。 首先从您的Adobe Learning Manager管理员处获取MCP端点URL、客户端ID和密钥。 有关更多详细信息，请查看&#x200B;**配置模型上下文协议服务器**。

## 添加连接器

1. 以管理员身份登录您的企业AI客户端。
2. 打开连接器的管理员设置。
3. 添加使用模型上下文协议的自定义连接器。
4. 输入Adobe Learning Manager MCP终结点URL。
5. 输入Adobe Learning Manager管理员提供的客户端ID和密钥。
6. 保存连接器。
7. 为学习者提供连接器。

>[!NOTE]
>
>AI客户端界面经常发生变化。 如果这些步骤与您的客户端不匹配，请参阅AI客户端供应商提供的有关添加远程连接器的文档。

## 故障排除

**学习者看不到该连接器。** 确认已为学习者的工作区或组启用连接器。

**当学习者选择“连接”时，授权失败。** 检查客户端ID和密钥是否与Adobe Learning Manager中服务器的&#x200B;**客户端凭据**&#x200B;页面上的值匹配。
