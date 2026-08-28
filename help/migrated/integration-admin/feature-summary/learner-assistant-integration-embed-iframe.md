---
description: 了解如何使用iframe在应用程序中嵌入学习者助手，包括设置、配置和事件处理
jcr-language: en_us
title: 通过嵌入iFrame集成“学习者助手”
source-git-commit: 1549a4592b7a930631dcff6b2e75ec3a3d4f5592
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---


# 使用iframe嵌入学习者助理

## 概述

Adobe Learning Manager (ALM)用户可以将&#x200B;**学习者助理**&#x200B;直接嵌入到其自己的面向学习者的应用程序（例如自定义门户、LMS前端、学习中心等）中 使用标准HTML`<iframe>`。

通过iFrame嵌入后，“学习者助理”可以访问所有“学习者助理”功能，包括：

* Orchestrator
* 应答代理
* Knowledge Agent
* 学习路径代理

>[!IMPORTANT]
>
>iFrame嵌入功能可让您的应用程序完全访问“学习者助理”的基础代理。 但是，您的应用程序（“父应用程序”）负责处理助理发出的任何事件。 例如，当学习者单击助理响应中的引文或课程链接时，助理会发出事件，而您的父应用程序必须处理该事件并执行实际导航。 “学习者助理”不代表您的应用程序导航。

## 先决条件

在开始之前，请确保您已完成：

* 已启用学习者助理的ALM租户。 从管理员设置页面配置所需目录。
* 用于对学习者（或管理员）会话进行身份验证的有效accessToken。 要生成访问令牌，请按照[使用OAuth 2.0](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual#authentication-using-oauth-20)进行身份验证页面上的说明进行操作。 该页面包含进行身份验证并生成继续操作所需的访问令牌所需的步骤。
* 将`<iframe>`嵌入到应用程序中并通过浏览器的postMessage API与其通信的功能。
* 父应用程序的前端代码所有权，因为您的应用程序必须侦听和响应来自嵌入式iFrame的消息。

## 学习助手配置参数

| 参数名称 | 值 | 描述 |
|---|---|---|
| 主机名称 | learningmanager.adobe.com | 指定应用程序的主机域。 |
| accessToken | token123（实际访问令牌） | 用于对用户会话进行身份验证和授权的令牌。 |

## 初始化iFrame

使用嵌入的iFrame配置握手，通过postMessage API将配置传递给学习者助理。

1. 父应用程序将学习助手嵌入为`<iframe>`。
2. 如果未发现基于URL的配置，则Learning Assistant会向父应用程序发送ALM_CHAT_REQUEST_CONFIG事件。
3. 父应用程序使用包含配置负载的ALM_CHAT_CONFIG事件进行响应。 例如：

   ```json
   {
     "hostName": "learningmanager.adobe.com",
     "accessToken": "token123",
     "openByDefault": false,
     "isAdmin": false
   }
   ```

4. 成功初始化后，学习者助理会进行渲染并准备好使用。

## iFrame事件摘要

学习者助理和父级应用程序通过postMessage事件双向通信。

### 传出事件（学习者助理iFrame到父应用程序）

| 事件名称 | 描述 | 传递的参数 |
|---|---|---|
| ALM_CHAT_OPENED | 打开聊天时触发。 | -- |
| ALM_CHAT_CLOSED | 聊天结束后触发。 | -- |
| ALM_CHAT_LO_REDIRECT | 导航至个性化学习路径概述页面。 | loId、loType、instanceId |
| ALM_CHAT_URL_REDIRECT | 在聊天消息中单击外部链接时激发。 | url |
| ALM_CHAT_REQUEST_CONFIG | 从父应用程序请求配置。 | -- |
| ALM_CHAT_WAITING_FOR_REPLY | 指示助理正在处理请求或等待响应。 | isWaitingForReply |
| ALM_CHAT_PERSONALIZED_PATH_CREATED | 保存学习路径时触发。 | -- |

### 传入事件（学习者助理的父级应用程序）

| 事件名称 | 描述 | 有效负载 |
|---|---|---|
| ALM_CHAT_CONFIG | 发送初始化助理所需的配置负载。 | 配置对象 |
| ALM_CHAT_OPEN | 打开“学习者助手”。 | 无 |
| ALM_CHAT_CLOSE | 关闭“学习者助手”。 | 无 |
| ASK_AI_ASSISTANT_QUERY | 打开聊天窗口并向助理提交查询。 | { query： &quot;Question text&quot; } |

## 父应用程序中的事件处理要求

通过iFrame嵌入学习者助理并不会使其成为一个完全自含的构件。 您的父应用程序必须主动侦听传出事件并采取相应操作。 您的应用程序至少应：

* 侦听ALM_CHAT_REQUEST_CONFIG并使用ALM_CHAT_CONFIG进行响应，以便助理可以初始化。
* 处理ALM_CHAT_LO_REDIRECT：当学习者单击助理回复中的引文或源时，您的应用程序会收到loId、loType和instanceId，并负责将学习者导航到正确的课程或学习对象。
* 处理ALM_CHAT_URL_REDIRECT：当学习者单击聊天消息中的外部链接时，您的应用程序会收到该URL并负责打开或导航到该链接（例如，在新选项卡中）。
* （可选）跟踪ALM_CHAT_OPENED / ALM_CHAT_CLOSED / ALM_CHAT_WAITING_FOR_REPLY以反映助理在您自己的UI中的状态（例如，在isWaitingForReply为true时显示加载指示器）。
* （可选）使用ALM_CHAT_OPEN / ALM_CHAT_CLOSE / ASK_AI_ASSISTANT_QUERY以编程方式控制助理。 例如，打开助手，然后从应用程序中的其他位置使用&#x200B;**帮助**&#x200B;按钮预填充查询。

## 需要帮助？

请联系您的Adobe客户成功经理，以进行技术演练。
