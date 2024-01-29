---
jcr-language: en_us
title: Learning Manager中的xAPI
description: Experience API (xAPI)是一种电子学习软件规范，允许学习内容和学习系统互动，以记录和跟踪所有类型的学习体验。 学习体验会记录于学习记录存储(LRS)中。 LRS既可以存在于传统的学习管理系统(LMS)中，也可以独立存在。
contentowner: dvenkate
preview: true
source-git-commit: 53c1a5283295b56424d697bc26c5db31c2edca0f
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 0%

---



# Learning Manager中的xAPI

## 什么是xAPI？ {#whatisxapi}

Experience API (xAPI)是一种电子学习软件规范，允许学习内容和学习系统互动，以记录和跟踪所有类型的学习体验。 学习体验会记录于学习记录存储(LRS)中。 LRS既可以存在于传统的学习管理系统(LMS)中，也可以独立存在。

有关xAPI的详细信息，请参阅 [xAPIc规范](https://github.com/adlnet/xAPI-Spec).

## Learning Manager如何支持xAPI？ {#howdoeslearningmanagersupportxapi}

Learning Manager内置Learning Record Store。 该LRS能够完全接受来自Learning Manager中托管内容的xAPI语句， 甚至接受第三方生成的xAPI语句。 这些xAPI语句存储在Learning Manager中，并可导出到Learning Manager外部，以可视化方式存储到任何第三方数据仓库系统中。

## 何时使用xAPI？ {#whendoyouusexapi}

越来越需要捕获跨多个系统的最终用户的学习体验。  还需要通过培训内容跟踪学习者的确切参与情况。 它不包括“开始”、“进行中”和“完成”（这些属性是SCORM捕获的唯一属性）。

## 在Learning Manager中使用xAPI {#usingxapiinprime}

### 设置应用程序 {#setupyourapplication}

1. 以集成管理员身份登录。 选择 **[!UICONTROL 应用程序>注册]**.

   ![](assets/appregistration.png)

   *用于注册应用程序的启动页面*

1. 注册新应用程序。

   ![](assets/appregistration.png)

   *注册新应用程序*

1. 定义应用程序的范围。

   * 如果 **[!UICONTROL 管理员角色xAPI读写权限]** 启用后，管理员可以发布和获取xAPI语句和文档。
   * 如果 **[!UICONTROL 学习者角色xAPI读写权限]** 启用后，管理员可以发布和获取xAPI语句和文档。

1. 保存更改。 您会获得开发人员ID和密钥。

**端点**：

单击下面的链接以查看xAPI Swagger文档：

[xAPI Swagger文档](https://learningmanagereu.adobe.com/docs/primeapi/xapi/)

>[!NOTE]
>
>Learning Manager支持的xAPI版本为1.0.3。


## API身份验证 {#apiauthentication}

Learning Manager xAPI使用OAuth 2.0框架对客户端应用程序进行身份验证和授权。 注册应用程序后，您可以获取clientId和clientSecret。 获取URL在浏览器中使用，用于通过SSO、Adobe ID等预配置帐户对Learning Manager用户进行身份验证。

```
GET https://learningmanager.adobe.com/oauth/o/authorize?client_id=<Enter your clientId>&redirect_uri=<Enter a url to redirect to>&state=<Any String data>&scope=<admin:xapi or learner:xapi>&response_type=CODE.
```

## 将xAPI语句作为Learning Manager学习对象进行跟踪 {#trackingxapistatementsasprimelo}

作者现在可以在创建课程时选择xAPI模块，以监控Learning Manager以外的用户体验。 例如，您可以使用此功能评估用于课程消费的第三方平台上的用户活动。

1. 创建 **[!UICONTROL 活动模块]**，在**中[!UICONTROL 类型]**option，使用弹出菜单进行选择  **[!UICONTROL 基于xAPI的模块。]**

   ![](assets/xapimodulecreation.png)

   *选择“基于xAPI的模块”选项*

1. 您需要提供IRI。 如果未提供，Learning Manager会自动生成一个。

   活动对应的IRI在帐户中是唯一的。 这意味着Learning Manager中的两个模块不能具有相同的IRI。 在以下情况下会生成新的IRI：

   * 在不同帐户之间共享具有xAPI模块的课程时。
   * 再次出现具有xAPI模块的认证



   任何具有上述IRI的xAPI语句均会在上述模块中进行跟踪，并反映在Learning Manager报告中。

1. 要复制自动生成的IRI，请重新访问“活动模块”页面。
1. 发布模块。

**注意事项：**

* Learning Manager目前仅支持mbox作为标识符。 不支持其他标识符，包括mboz_sha1、 openid 、帐户。

* 与Learning Manager一起使用时，stateId和profileId为UUID。
* PUT请求不会覆盖xAPI代理/配置文件、活动/配置文件以及活动/状态的文档
* 操作者不支持无法识别的组。
* GET语句不支持参数“related_activities”。
* GET语句不支持参数“format=ids”和“format=canonical”。
* 撤消xAPI语句不会撤销发布该语句时在Learning Manager中执行的任何操作。

## 生成报告 {#generatereports}

xAPI报告可以生成为Excel报告。 以管理员身份打开 **[!UICONTROL 报告> Excel报告> xAPI活动报告]**.

下载的报告会获取学习者和管理员针对任何语句发布的所有信息。

对于任何第三方集成，都可以使用FTP和Box连接器生成/计划相同的报告。 请按以下步骤进行操作：

登录身份 **集成管理员>打开FTP/Box连接器>选择xAPI活动报告** 左侧面板中的“文件”。 选择计划/生成报告。

![](assets/xapischedule.png)

*计划或生成报告*

* 当在xAPI语句中仅发送原始分数而无最高分数时，测验分数不显示在学习者成绩单中。

* 要在Learning Manager中获取百分比分数，通过xAPI发送比例分数。

## 示例报告 {#samplereport}

[xAPI示例报告。](assets/xapireport8842560559890766717csv.zip)
