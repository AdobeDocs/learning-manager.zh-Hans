---
description: 在您自己的Claude帐户中将Adobe Learning Manager MCP服务器注册为自定义连接器，并进行身份验证以查询您的学习。
jcr-language: en_us
title: 将Adobe Learning Manager作为学习者添加到Claude
exl-id: 31c00b29-4919-48b7-9993-ed3ac358ba5e
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%
---

# 将Adobe Learning Manager作为学习者添加到Claude

## 概述

仅当您的组织尚未为您添加连接器时，才使用这些步骤。 如果连接器出现在Claude中，请改为选择&#x200B;**连接**。

## 在Claude中添加连接器

1. 在Claude中，转到&#x200B;**自定义** > **连接器**。
2. 选择&#x200B;**添加** (**+**)，然后选择&#x200B;**添加自定义连接器**。
3. 输入&#x200B;**名称**，例如Adobe Learning Manager。
4. 在&#x200B;**远程MCP服务器URL**&#x200B;中输入MCP终结点URL。
5. 选择&#x200B;**继续**。
6. 在&#x200B;**身份验证**&#x200B;下，保持&#x200B;**立即登录**。
7. 在&#x200B;**OAuth客户端**&#x200B;下，选择&#x200B;**使用您自己的OAuth客户端**。
8. 在&#x200B;**客户端ID**&#x200B;中输入客户端ID。
9. 在&#x200B;**客户端密钥**&#x200B;中输入密钥。
10. 选择&#x200B;**添加**。
11. 在登录页面打开时登录Adobe Learning Manager 。

登录后，该连接器显示已连接。 询问有关学习的问题。 如需获取创意，请详细了解[学习者示例提示](/help/migrated/learners/feature-summary/sample-prompts-for-learners.md)。

>[!IMPORTANT]
>
>Claude将“客户端密钥”字段标记为可选字段，但Adobe Learning Manager需要它。 如果您将其留空或输入了错误值，则登录将失败，并显示&#x200B;**授权失败**&#x200B;消息。

>[!NOTE]
>
>您的请求以您自己的权限运行。 克劳德只能看见Adobe Learning Manager的样子。

## 使用其他Adobe Learning Manager帐户

如果您的浏览器已有活动的Adobe Learning Manager会话，Claude无需询问凭据即可连接到该帐户。 要以其他用户身份进行连接，请先注销Adobe Learning Manager，或使用专用浏览器窗口。

## 其他AI客户端

对于ChatGPT或其他客户端，步骤会有所不同。 有关添加自定义连接器的信息，请参阅AI客户端的文档，并使用来自管理员的相同三个值。

## 故障排除

**登录显示未注册的重定向消息。**
您的管理员必须将Claude域添加到服务器的**重定向域**。 请让您的管理员添加<https://claude.ai>，然后重试。

**Claude表示授权失败。**
检查密钥是否有多余空间或值错误。 从管理员那里再次复制，删除该连接器，然后再次添加它。

**您以错误用户的身份连接。**
断开连接器连接，注销Adobe Learning Manager，然后在专用浏览器窗口中重新连接。

**Claude要求您再次登录。**
您的会话已过期，或者您的访问权限已被撤销。 选择**连接**&#x200B;以再次登录。
