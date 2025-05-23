---
jcr-language: en_us
title: Adobe Learning Manager 中的 xAPI
description: Experience API (xAPI)是一种电子学习软件规范，允许学习内容和学习系统互动，以记录和跟踪所有类型的学习体验。
exl-id: 8e36b538-a451-448e-a65d-08d286adcfdb
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 49%

---

# Adobe Learning Manager 中的 xAPI

## 什么是 xAPI？ {#whatisxapi}

Experience API (xAPI) 是一种在线学习软件规范，允许学习内容和学习系统互动，以记录和跟踪所有类型的学习体验。 学习体验会记录于学习记录存储 (LRS) 中。 LRS 既可以存在于传统的学习管理系统 (LMS) 中，也可以独立存在。

有关xAPI的详细信息，请参阅： [https://github.com/adlnet/xAPI-Spec](https://github.com/adlnet/xAPI-Spec)。

## Adobe Learning Manager 如何支持 xAPI？ {#howdoescaptivateprimesupportxapi}

Adobe Learning Manager 内置 LRS。该 LRS 能够完全接受来自 Adobe Learning Manager 中托管内容的 xAPI 语句。甚至接受第三方生成的 xAPI 语句。 这些xAPI语句存储在Learning Manager中，并可导出到Learning Manager外部，以可视化方式存储到任何第三方数据仓库系统中。

## 何时使用 xAPI？ {#whendoyouusexapi}

越来越需要捕获跨多个系统的最终用户的学习体验。  还需要通过培训内容跟踪学习者的确切参与情况。 xAPI 不仅仅包含“开始”、“进行中”和“完成”等属性（仅仅是 SCORM 捕获的属性）。

## 在Learning Manager中使用xAPI {#usingxapiinprime}

## 设置应用程序 {#setupyourapplication}

1. 以集成管理员身份登录。选择&#x200B;**[!UICONTROL 应用程序]** > **[!UICONTROL 注册]**。

   ![](assets/appregistration.png)

1. 注册新应用程序。

   ![](assets/appregistration.png)

1. 定义应用程序的范围。

   * 如果启用&#x200B;**[!UICONTROL 管理员角色 xAPI 读写权限]**，则管理员可以发布和获取 xAPI 语句和文档。
   * 如果启用&#x200B;**[!UICONTROL 学习者角色 xAPI 读写权限]**，则学习者可以发布和获取 xAPI 语句和文档。

1. 保存更改。您会获得开发人员 ID 和密钥。

**端点**：

单击下方链接查看 xAPI Swagger 文档：

[https://learningmanagereu.adobe.com/docs/primeapi/xapi/](https://learningmanagereu.adobe.com/docs/primeapi/xapi/)

注意：Learning Manager支持的xAPI版本为1.0.3。

## API 身份验证 {#apiauthentication}

Learning Manager xAPI使用OAuth 2.0框架对客户端应用程序进行身份验证和授权。 注册应用程序后，您可以获取clientId和clientSecret。 获取URL在浏览器中使用，用于通过SSO、Adobe ID等预配置帐户对Learning Manager用户进行身份验证。

```
GET https://learningmanager.adobe.com/oauth/o/authorize?client_id=<Enter your clientId>&redirect_uri=<Enter a url to redirect to>&state=<Any String data>&scope=<admin:xapi or learner:xapi>&response_type=CODE.
```

## 将xAPI语句作为Learning Manager学习对象进行跟踪 {#trackingxapistatementsasprimelo}

作者现在可以在创建课程时选择 xAPI 模块，以监控 Adobe Learning Manager 以外的用户体验。例如，您可以使用此功能评估用于第三方课程消费平台上的用户活动。

1. 创建&#x200B;**[!UICONTROL 活动模块]**&#x200B;时，在&#x200B;**[!UICONTROL 类型]**&#x200B;选项中，使用弹出菜单选择&#x200B;**[!UICONTROL 基于xAPI的模块。]**

   ![](assets/xapimodulecreation.png)

1. 您需要提供 IRI。 如果未提供，Learning Manager会自动生成一个。

   活动对应的 IRI 在帐户中具有唯一性， 这意味着Learning Manager中的两个模块不能具有相同的IRI。 下列情况会生成新的 IRI：

   * 在不同帐户之间共享具有xAPI模块的课程时。
   * 再次出现具有 xAPI 模块的认证



   任何具有上述IRI的xAPI语句均会在上述模块中进行跟踪，并反映在Learning Manager报告中。

1. 若要复制自动生成的 IRI，请重新访问“活动模块”页面。
1. 发布模块。

**注意事项：**

* Learning Manager目前仅支持mbox作为标识符。 不支持其他标识符，包括mboz_sha1、openid、帐户。

* 与Learning Manager一起使用时，stateId和profileId为UUID。
* PUT请求不会覆盖xAPI代理/配置文件、活动/配置文件以及活动/状态的文档
* 操作者不支持无法识别的组。
* GET语句不支持参数“related_activities”。
* GET 语句不支持“format=ids”和“format=canonical”参数。
* 撤消xAPI语句不会撤销发布该语句时在Learning Manager中执行的任何操作。

## 生成报告 {#generatereports}

xAPI报告可以生成为Excel报告。 以管理员身份打开&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL Excel报告]** > **[!UICONTROL xAPI活动报告]**。

下载的报告会获取学习者和管理员针对任何语句发布的所有信息。

对于任何第三方集成，都可以使用FTP和Box连接器生成/计划相同的报告。 请执行以下步骤：

以集成管理员身份登录>打开 FTP/Box 连接器>从左侧窗格中选择“xAPI 活动报告”>选择计划/生成报告。

![](assets/xapischedule.png)

* xAPI 语句中仅发送原始分数，而不发送最高分数时，测试分数不会在 LT 中显示。

* 要在 Adobe Learning Manager 中获取百分比分数，可通过 xAPI 发送换算分数。

## 示例报告 {#samplereport}

[xAPI 示例报告。](assets/xapireport8842560559890766717csv.zip)
