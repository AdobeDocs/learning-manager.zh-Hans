---
description: 为您的组织配置一次模型上下文协议(MCP)服务器，以便AI助理可以安全地访问学习者的培训。
jcr-language: en_us
title: 配置Adobe Learning Manager MCP服务器
exl-id: b5d2c08e-a11e-4f55-9ba5-a652a9575678
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '2095'
ht-degree: 1%
---

# 配置Adobe Learning Manager MCP服务器

## 概述

配置包含两个步骤。 首先，在Adobe Learning Manager中创建一个MCP服务器。 其次，将服务器连接到AI助手。 之后，学习者从AI助理使用Adobe Learning Manager进行身份验证，然后可以使用MCP工具。

## 要求

* 已为您的Learning Manager帐户启用MCP服务器。 请联系您的Adobe客户成功经理或Adobe支持部门以启用它。 在此之前，每个请求都返回403 Forbidden。
* MCP服务器是一个后端标记功能，仅适用于&#x200B;**Ultimate层**&#x200B;帐户。
* AI Assistant的管理员有权在该平台上添加和配置连接器。

## 工作原理

MCP客户端（如Claude或ChatGPT）将请求连同学习者的OAuth访问令牌一起发送到MCP服务器URL。 每个工具均以该令牌表示的学习者权限运行。 因此，学习者只能通过MCP服务器执行已允许在Adobe Learning Manager中执行的操作。

服务器使用OAuth 2.0授权代码流。 AI Assistant将使用Adobe Learning Manager应用程序的客户端ID和客户端密钥作为机密客户端进行身份验证。 服务器不支持OAuth动态客户端注册。

## 在Learning Manager中创建MCP服务器

创建MCP服务器将设置OAuth应用程序，并为您提供MCP服务器URL、客户端ID和客户端密钥。

1. 以集成管理员身份登录Learning Manager。
2. 在导航菜单中，选择&#x200B;**MCP服务器**。
3. 在右上角，选择&#x200B;**创建**。

   ![](/help/migrated/integration-admin/feature-summary/assets/1.5-Integration-Administrator-Configure-ALM-MCP-server-image1.png)

4. 在&#x200B;**应用程序详细信息**&#x200B;页面上，输入以下内容，然后选择&#x200B;**下一步**：

   * **应用程序名称：**&#x200B;最多输入50个字符，例如，对于Claude输入ALM。 学习者在授权连接时会看到此名称，因此请选择他们能够识别的名称。
   * **重定向域：**&#x200B;输入每个AI Assistant的回调域，每行一个域。 在开始每个路径时都不要包含路径。 该字段为必填项。
   * **描述：**&#x200B;输入最多150个字符，例如，允许学习者使用来自Claude的ALM。

5. 在&#x200B;**工具配置**&#x200B;页面上，查看AI助理用于确定何时调用每个工具的工具和说明。 要更改描述，请选择&#x200B;**操作** (**...**) > **编辑**。 若要恢复默认值，请选择&#x200B;**重置**。 然后选择&#x200B;**下一步**。
6. 在&#x200B;**客户端凭据**&#x200B;页面上，复制&#x200B;**MCP服务器URL**、**客户端ID**&#x200B;和&#x200B;**客户端密钥**。 安全保存。 您需要他们来连接AI助手。

MCP服务器始终具有“学习者”范围，因此没有可选择的范围。

为计划连接的每个AI Assistant注册域。

| **AI助手** | **重定向域以注册** | **完整回调URL（引用）** |
|----|----|----|
| 克劳德 | [https://claude.ai](https://claude.ai/)和[https://claude.com](https://claude.com/) | <https://claude.ai/api/mcp/auth_callback> |
| ChatGPT | [https://chatgpt.com](https://chatgpt.com/) | <https://chatgpt.com/connector/oauth/&lt;id>\>（ChatGPT会在设置过程中显示ID） |

>[!IMPORTANT]
>
>注册确切的域，如[https://chatgpt.com](https://chatgpt.com/)。 请勿使用部分通配符，例如[https://*chatgpt.com*](https://chatgpt.com)*，因为它们可以与不相关的域匹配。 要允许子域，请使用全标签通配符，如* [*https://*.example.com](https://encoded-592c9deb-987b-4562-aa3c-9fa3d37d83e9.uri/https%3a%2f%2f.example.com)。

如果列出其所有重定向域，则一台MCP服务器可以提供多个AI助手。 要撤销一个助理的访问权限而不影响其他助理，请为每个助理创建单独的MCP服务器。 所有服务器都使用相同的MCP服务器URL。

您只需要MCP服务器URL。 Claude和ChatGPT可自动发现Learning Manager OAuth端点。 对于手动设置，请查看Learning Manager MCP服务器的[OAuth端点](#oauth-endpoints-reference)。

## 连接您的MCP客户端

AI Assistant的管理员可连接MCP服务器。 客户端界面经常更改。 如果这些步骤不再匹配，请参阅客户机的文档。

>[!NOTE]
>
>AI客户端会重构answer_learning_content_question工具返回的响应并设置其格式，因此答案的详细程度因客户端而异。

在开始之前，请确认已为您的帐户启用MCP服务器，并且您具有上一节中的MCP服务器URL、客户端ID和客户端密钥。

### 连接Claude Pro或Max

**注意：**&#x200B;客户会对answer_learning_content_question工具的回复重新构图并设置格式，因此问题回复的详细程度会发生变化。

1. 在Claude中，转到&#x200B;**自定义** \> **连接器**。
2. 选择&#x200B;**添加** (+)，然后选择&#x200B;**添加自定义连接器**。
3. 输入连接器详细信息，然后选择&#x200B;**继续**：

   1. **名称：**&#x200B;输入学习者可识别的名称，例如Adobe Learning Manager。
   2. **远程MCP服务器URL：**&#x200B;从“客户端凭据”页面输入格式为[https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp)的MCP服务器URL。

4. 在&#x200B;**身份验证**&#x200B;下，保持&#x200B;**立即登录**。 Claude读取Learning Manager OAuth设置并将匹配选项标记为&#x200B;*已检测到*。
5. 在&#x200B;**OAuth客户端**&#x200B;下，选择&#x200B;**使用您自己的OAuth客户端**。 粘贴&#x200B;**客户端ID**&#x200B;和&#x200B;**客户端密钥**。
6. 选择&#x200B;**添加**。 Claude打开Learning Manager登录页面。 登录后，该连接器显示已连接。

>[!NOTE]
>
>Claude将“客户端密钥”字段标记为可选字段，但Learning Manager需要它。 如果您将其留空或输入了错误值，则登录将失败，并显示“授权失败”消息。

### 连接Claude团队版或企业版

只有组织所有者或具有可以管理连接器的角色的成员才能添加连接器。 成员永远不会看到客户端ID或客户端密钥。

>[!NOTE]
>
>客户会对answer_learning_content_question工具的回答重新构图并设置格式，因此问题响应的详细程度会发生变化。

1. 在Claude中，以组织所有者或具有管理连接器权限的成员身份登录。
2. 转到&#x200B;**组织设置** \> **连接器**。
3. 选择“**添加**”，将鼠标悬停在“**自定义**”上，然后选择“**Web**”。
4. 输入名称和MCP服务器URL，然后设置&#x200B;**身份验证**&#x200B;和&#x200B;**OAuth客户端**，如上一个过程的步骤4和5中所述。
5. 选择&#x200B;**添加**。

现在您的组织可以使用该连接器。 每个成员选择&#x200B;**Connect**&#x200B;并使用他们自己的帐户登录Learning Manager。

### 连接ChatGPT团队版或企业版

>[!NOTE]
>
>客户会对answer_learning_content_question工具的回答重新构图并设置格式，因此问题响应的详细程度会发生变化。

1. 以工作区所有者或管理员身份登录ChatGPT。
2. 在左侧边栏中，单击&#x200B;**插件**。
3. 单击右上角的“**添加**”，然后选择“**创建MCP应用程序**”。
4. 在&#x200B;**新建插件**&#x200B;窗口中，配置连接：

   * **姓名：** Adobe Learning Manager，或学习者用来识别学习平台的名称。
   * **连接：**&#x200B;保持选择&#x200B;**服务器URL**，并输入[https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp)
   * **身份验证：** OAuth

   ![](/help/migrated/integration-admin/feature-summary/assets/1.5-Integration-Administrator-Configure-ALM-MCP-server-image2.png)

5. 单击&#x200B;**高级OAuth设置**。 ChatGPT会自动发现ALM OAuth端点。
6. 在&#x200B;**客户端注册**&#x200B;下，保持&#x200B;**注册方法**&#x200B;设置为&#x200B;**用户定义的OAuth客户端**，然后在步骤1中输入&#x200B;**OAuth客户端ID**&#x200B;和&#x200B;**OAuth客户端密钥**。
7. 检查此面板中显示的&#x200B;**回调URL**。 其域(<https://chatgpt.com>)必须位于步骤1中MCP服务器的&#x200B;**重定向域**&#x200B;中。

   ![](/help/migrated/integration-admin/feature-summary/assets/1.5-Integration-Administrator-Configure-ALM-MCP-server-image3.png)

       **将自动发现端点**
   
   通常不需要更改OAuth端点。 如果ChatGPT要求这些服务，请使用：身份验证URL [https://\[alm-host\]/oauth/o/authorize](https://[alm-host]/oauth/o/authorize)，令牌URL [https://\[alm-host\]/oauth/token](https://[alm-host]/oauth/token)，注册URL为空，资源[https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp)，范围学习者:write。

8. 选择“**我理解并希望继续**”，然后单击“**创建**”。
9. 在&#x200B;**连接**&#x200B;窗口中，单击&#x200B;**继续**&#x200B;并登录ALM。 该窗口应显示&#x200B;*已被您的管理员批准*。
10. 将该插件提供给您工作区中的目标用户。

    ![](/help/migrated/integration-admin/feature-summary/assets/1.5-Integration-Administrator-Configure-ALM-MCP-server-image4.png)

## 最终用户身份验证

管理员完成配置后，学习者从其AI Assistant连接器列表中添加Adobe Learning Manager连接器，然后选择“连接”。 此时会打开Adobe Learning Manager登录页面。 学习者登录（通过SSO，如果帐户使用）并批准访问权限后，AI助手将链接到学习者的Adobe Learning Manager帐户。

>[!NOTE]
>
>如果浏览器已有活动的Adobe Learning Manager会话，则助理无需请求凭据即可连接到该用户。 要以其他用户身份进行连接，请先注销Adobe Learning Manager，或使用专用浏览器窗口。

身份验证是一个一次性步骤。 如果学习者的访问权限被撤销或其会话过期，助理会提示他们重新登录。

## 旋转客户端密钥或撤销访问权限

无法重新生成客户端密钥。 要旋转它，请执行以下操作：

1. 创建新的MCP服务器，如本文前面所述。
2. 使用新的客户端ID和客户端密钥更新AI Assistant。
3. 在&#x200B;**集成管理员** > **MCP服务器**&#x200B;中，为旧服务器选择&#x200B;**操作** (**...**) > **删除**。

切换后，学习者必须重新登录。

要断开所有学习者的AI Assistant连接，请从同一页面删除其MCP服务器。

## 可用工具

MCP服务器公开以下工具。 所有这些应用程序均以登录学习者的权限运行。

<table>
<colgroup>
<col style="width: 46%" />
<col style="width: 31%" />
<col style="width: 21%" />
</colgroup>
<thead>
<tr>
<th><strong>工具</strong></th>
<th><strong>功能</strong></th>
<th><strong>提示示例</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>search_learning_itemsread-only</td>
<td>在目录中搜索课程、学习路径、认证、工作辅助、徽章、技能、目录和标签。 过滤器：类型、学习者状态、技能、标签、目录、交付格式、价格和语言。 每页最多返回10个结果。</td>
<td>“初学者蟒蛇课程”<br />
“免费法语课堂培训”</td>
</tr>
<tr>
<td>list_my_learning_enrollmentsread-only</td>
<td>列出学习者的已注册、进行中和已完成的学习，以及状态、进度和截止日期。 默认情况下，最近注册时间为优先。</td>
<td>“我注册了什么？”<br />
“什么即将到期？”<br />
“我已完成的培训”</td>
</tr>
<tr>
<td>get_learning_objectread-only</td>
<td>按ID获取课程、学习路径、认证或工作辅助的完整详细信息，可以选择包括实例、技能和子项目。</td>
<td>“告诉我有关第二门课程的更多信息”</td>
</tr>
<tr>
<td>get_my_learning_profileread-only</td>
<td>获取学习者的ALM配置文件，包括帐户和经理。</td>
<td>“谁是我在ALM的经理？”</td>
</tr>
<tr>
<td>answer_learning_content_questionuses AI积分</td>
<td>根据课程内容和引用内容，使用ALM学习助手回答有关课程主题的问题。 返回助理用于跟进问题的对话ID。</td>
<td>“说明我的网络课程涵盖的TCP与UDP”</td>
</tr>
<tr>
<td>personalized_learning_path</td>
<td>在Adobe Learning Manager中根据学习者的目标、主题和学习需求提供个性化的学习路径。 支持生成课程推荐、将选定的学习路径保存到学习者帐户、列出学习者保存的学习路径（操作列表）以及按id获取一个保存的学习路径的详细信息和课程（操作详细信息）。 帮助学习者确定相关的学习内容，以发展技能并实现学习目标。</td>
<td>将所选学习路径保存到我的帐户。</td>
</tr>
</tbody>
</table>

通过answer_learning_content_question开始的对话会显示在“学习者AI对话”报告中，与“ALM学习助理”中的对话相同。

## 限制

| **限制** | **值** |
|----|----|
| 每页搜索结果（搜索和注册） | 最多10。 对更多页面使用返回的光标。 |
| answer_learning_content_question比率 | 每个学习者每分钟处理10个请求（突发5个），一次最多处理2个请求 |
| 支持的MCP协议版本 | 2025-11-25, 2025-06-18, 2025-03-26 |
| 运输 | 可流式处理的HTTP，无状态（仅POST；无服务器发送的事件流） |

## OAuth端点引用 {#oauth-endpoints-reference}

Claude和ChatGPT可以自动发现这些信息。 这里列出了需要手动输入的客户或代理。 将`alm-host`替换为MCP服务器URL中的主机（您的区域主机或ALM自定义域）。

| **值** | **URL** |
|----|----|
| MCP服务器URL | [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp) |
| 授权URL | [https://\[alm-host\]/oauth/o/authorize](https://[alm-host]/oauth/o/authorize) |
| 令牌 URL | [https://\[alm-host\]/oauth/token](https://[alm-host]/oauth/token) |
| 刷新URL | [https://\[alm-host\]/oauth/token/refresh](https://[alm-host]/oauth/token/refresh) |
| 授权服务器基础 | [https://\[alm-host](https://[alm-host)\] |
| 资源 | [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp) |
| 范围 | 学习者:write |

## 故障排除

| **症状** | **原因和修复** |
|----|----|
| 登录期间未注册的重定向 | AI助理的回调域不在应用程序的&#x200B;**重定向域**&#x200B;中。 添加它（例如，<https://claude.ai>）并重试。 |
| 登录成功，然后助理显示授权失败（客户端无效） | 在助理中输入的客户端密钥与应用程序不匹配。 从ALM中再次复制它，检查额外空格，然后重新连接。 |
| 所有请求返回403禁止 | 您的帐户未启用MCP服务器。 联系Adobe支持。 |
| 已作为错误的ALM用户连接 | 浏览器已有一个ALM会话。 断开连接、注销ALM（或使用专用窗口），然后重新连接。 |
| 从问答工具中“超出速率限制” | 学习者已超出问答费率限制。 请稍等片刻，然后重试。 |
| 助手要求重新登录 | 学习者的令牌已过期或已撤销。 再次单击&#x200B;**连接**。 |

## 常见问题解答

**学习者是否可以在管理员未设置的情况下使用MCP服务器？**
数字 集成管理员必须在Adobe Learning Manager中创建MCP服务器（步骤1），因为MCP服务器不支持动态客户端注册。

**我们是否可以使用自己的域？**
是。 如果您的Adobe Learning Manager帐户具有自定义域，请在所有URL中使用该域代替`alm-host`。

**哪些ALM角色可以使用MCP服务器？**
任何Adobe Learning Manager用户都可以连接。 这些工具在学习者上下文中工作，ALM自己的权限检查会应用于每个请求。
