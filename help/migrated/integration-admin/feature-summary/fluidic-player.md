---
description: 阅读本文，了解如何在自定义应用程序中嵌入流体播放器。
jcr-language: en_us
title: 嵌入式流体播放器
contentowner: dvenkate
preview: true
source-git-commit: fba5e5ddc1964b485be473bf356806f234688cf4
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 24%

---



# 嵌入式流体播放器

阅读本文，了解如何在自定义应用程序中嵌入流体播放器。

企业现在可以在 Adobe Learning Manager 之外为学习者提供自定义体验。您可以使用公共API，获取与学习对象、学习者注册和学习进度相关的所有信息，并将这些信息显示在您的网站上。 更重要的是，您可以在自己的网站中嵌入 Adobe Learning Manager 的流体播放器，以便学习者可以直接从您的网站使用内容。您能够使用流体播放器播放 Adobe Learning Manager 支持的任何内容。在您的网站中嵌入的与您在Learning Manager中使用的功能完全相同。

**播放任何电子学习内容[](../../learners/feature-summary/fluidic-player.md#main-pars_text_779047019)**

流体播放器能够以一致且直观的方式播放几乎任何类型的电子学习内容，无需任何插件，亦无需下载任何内容。 无论内容属于哪种文件类型，学习者启动内容之后，即开始播放。

**备注和书签**

无论内容属于哪种文件类型，您都可以为其备注并添加书签。 如果想从长文件或视频中进行选择，您可以将找到符合自己需求信息的位置标记为书签。 可以搜索备注和书签或通过电子邮件发送。 单击备注和书签即可进入流体播放器，恰好位于视频或文档页面的位置。

有关流体播放器的更多信息，请参阅 [流体播放器](../../learners/feature-summary/fluidic-player.md).

以下是您可以使用嵌入式流体播放器的一些示例。

* 您可以在自己的**网站中使用嵌入式流体播放器**列出员工已注册的课程，并在同一页面提供启动培训的链接。 这意味着学习者可以在您的Intranet网站上参加培训。

* 如果您从事培训业务，您可能拥有一个网站，供客户购买课程。 您可以将嵌入式播放器与该网站集成，以便客户可以使用在您的网站上购买的内容。

## 在网站中嵌入流体播放器的操作步骤 {#stepstoembedfluidicplayerinyourwebsite}

如需构建自定义应用以在您的网站嵌入流体播放器，需执行以下三个基本步骤：

1. 在 Adobe Learning Manager 的集成管理员应用中创建应用程序。
1. 检索访问令牌。
1. 使用访问令牌通过公共API从Learning Manager检索资源。

### 1. 在“集成管理员”中创建应用程序 {#1createanapplicationinintegrationadmin}

需执行此步骤，才能创建用于检索刷新令牌和访问令牌的应用程序/客户端 ID 和应用程序/客户端密钥。 有关创建应用程序的更多信息，请参见  [应用程序开发过程。](developer-manual.md#main-pars_header_994876235)

1. 转到&#x200B;**[!UICONTROL 集成管理员]**&#x200B;应用并打开&#x200B;**[!UICONTROL “应用程序”]**。

1. 选择页面右上角的&#x200B;**[!UICONTROL “注册”]**。
1. 此时会打开&#x200B;**[!UICONTROL “注册新应用程序”]**&#x200B;窗口。 填写必填字段。
1. 如果需要在多个帐户之间共享自定义应用程序，请选择 **[!UICONTROL 否]** 在选项字段中  **[!UICONTROL 仅针对此帐户？]**
1. 要保存应用程序并生成应用程序 ID 和密钥，请单击&#x200B;**[!UICONTROL “保存”]**。

### 2. 检索访问令牌 {#2retrievingaccesstoken}

由于Learning Manager使用OAUTH2.0，因此需要访问令牌才能使用公共API检索资源。 您可以使用刷新令牌、客户端 ID 或客户端密钥获取访问令牌。

**2.1刷新令牌**

* 检索 OAuth 代码

需要 OAuth 代码才能检索刷新令牌。 Learning Manager在使用以下URL登录时将用户重定向至带有OAuth代码的重定向URL（示例应用程序的“oauthredirect.html”文件举例说明了如何提取OAuth代码）：

```
code https://learningmanager.adobe.com/oauth/o/authorize  
client_id= <application_id>  
&redirect_uri=<redirect_uri>  
&state=<dummy_data>  
&scope=learner:read,learner:write  
&response_type=CODE  
&account=<account_id>  
&email=<email_id>
```

这里， **[!UICONTROL 客户端ID]** 是在步骤1中获得的应用程序ID。
**[!UICONTROL redirect_url]** 是在步骤1中设置的redirect_url。
**[!UICONTROL state]** 是我们需要以此为依据筛选重定向URL以获取OAuth代码的任何虚拟数据。 范围是第1步中设置的学习者范围。
**[!UICONTROL response_typ]**e始终是“代码”。\
**[!UICONTROL 帐户]**是可选字段\
**[!UICONTROL email]** 是可选字段\
&#42; 如果同时提供帐户ID和电子邮件，则上述URL允许用户登录同一帐户。 示例应用程序的“index.html”文件中描述了此端点示例。

* 检索刷新令牌

收到OAuth代码后，可以使用从以下端点接收的OAuth代码、客户端ID和客户端密钥检索刷新令牌：

**https://learningmanager.adobe.com/oauth/token**

作为对帖子请求的响应，您会收到以下信息：

i. refresh_token\
二。 access_token\
三。 user_id\
四。 expires_in\
v. user_role\
六。 account_id

**2.2从刷新令牌中检索访问令牌**

要检索访问令牌，请将包含refresh_token、client_id和client_secret的另一请求作为帖子正文发送到以下URL：

**https://learningmanager.adobe.com/oauth/token/refresh**

作为对帖子请求的响应，您会收到以下信息：\
i. refresh_token\
二。 access_token\
三。 user_id\
四。 expires_in\
v. user_role\
六。 account_id

### 3. 使用公共 API 检索资源 {#3retrieveresourcesusingpublicapi}

第3步，您需要使用访问令牌通过公共API从Learning Manager检索资源。  进行任何公共api调用都需要访问令牌，并且需要将其添加到标头中，如示例应用程序所示。

## 嵌入式播放器 {#embeddableplayer}

第三方应用程序可以利用嵌入式播放器，播放学习对象的内容。

**在嵌入式播放器中打开课程**

1. 创建可嵌入的 URL

   要使用嵌入式播放器打开课程，您需要创建可嵌入的URL，如下所示：

   `https://learningmanager.adobe.com/app/player?lo_id=<v2-api course id>&access_token=<access_token>`

   在此 URL 中，lo_id 需要符合 V2 API 课程 ID 格式。

   示例： `https://learningmanager.adobe.com/app/player?lo_id=course:123456&access_token=45b269b75ac65d6696d53617f512450f`

   认证、学习计划和工作辅助也可以在嵌入式播放器中播放。

   示例： `https://learningmanager.adobe.com/app/player?lo_id=certification:12345&access_token=c1a4847dfbf4007826a027d481b93c1e`

   `https://learningmanager.adobe.com/app/player?lo_id=learningProgram:12345&access_token=c1a4847dfbf4007826a027d481b93c1e`

   `https://learningmanager.adobe.com/app/player?lo_id=jobAid:1234&access_token=c1a4847dfbf4007826a027d481b93c1e`

1. 在iframe的“src”属性中设置此URL。

**关闭嵌入式播放器**

```
code window.addEventListener("message", function closePlayer(){  
   if(event.data === "status:close"){  
     //handle closing event  
   }  
});
```

## 示例应用程序教程 {#sampleapplicationtutorial}

附加的PDF文档包含示例应用程序教程。
[嵌入流体播放器的示例教程和教程源。](assets/sample-applicationtutorial.zip) 替代内容

如果您是管理员，您可以在流体播放器中设置课程材料，为学习者提供替代内容。 例如，如果不同地区的学习者可能希望使用多种语言，则您可以用多种语言创建相同的内容。 流体播放器将为学习者提供其可能设置的语言，但学习者还可以选择直接从播放器内切换到替代语言。

特定于视频的控件

Learning Manager流体播放器所使用的流技术可为学习者提供视频播放体验，在启动视频时不会有任何延迟，并且任何设备均无需磁盘空间。 流体播放器还提供了播放速度（1倍、1.5倍）和skip +-10秒等智能控制功能，旨在为学习者提供与其学习速度相匹配的准确控制级别。

这项工作需要由您的IT团队中的某个人员或外部顾问来完成，他们可构建一个应用程序，然后托管在您的站点上。

1. 使用指向需要学习的准确学习对象的参数修改Learning Manager嵌入式播放器URL。

   URL：  [https://learningmanager.adobe.com/app/player](https://cpcontents.adobe.com/public/embedplayer/index22fa615ec2baa034a22090c8cd4289fa.html)

1. 使用以下任一参数启动课程：

   * course_id ：这是要启动的课程的ID
   * learning_program_id ：这是要启动的学习计划的ID
   * certification_id ：这是要启动的认证的ID
   * lo_id ：要播放的学习对象（课程/学习计划/认证/工作辅助）的ID


1. 将访问令牌用作必需的参数。

   * access_token ：这是安全参数，请使用公共API oauth访问令牌

   您可以通过在集成管理员中设置嵌入式流体播放器来获取令牌。 您可以获取可用作访问令牌的身份验证令牌。

   创建的URL示例；https://learningmanager.adobe.com/app/player?lo_id=&quot;+lo_id+&quot;&amp;access_token=&quot;+accToken

   在此URL中， lo_id将是课程、学习计划、认证和工作辅助的ID。

   lo_id — 课程示例：21324，learningProgram：2143，certification：23432，jobAid：237

1. 调用Learning Manager API以检索上述参数。

   这些API调用将由IT团队/顾问编写并托管在您的站点上的应用程序进行。

   有关使用API的更多详细信息，请参阅此处：

   Learning Manager V1 API - [https://learningmanager.adobe.com/docs/primeapi/v1/](https://learningmanager.adobe.com/docs/primeapi/v1/)



   Learning Manager V2 API - [https://learningmanager.adobe.com/docs/primeapi/v2/](https://learningmanager.adobe.com/docs/primeapi/v2/)

   对象的ID不同于V1和V2 API。 嵌入式播放器需要v2格式的ID。 使用V2中的ID映射API将V1 ID转换为V2 ID。

   构建URL后，应用程序将其用于向学习者显示的一种方法是将其放在iFrame中。 单击此链接可启动流体播放器，并附带特定课程。

   ![](assets/salesforce-player.png)

   如要查看进度和完成报告，请登录Learning Manager。

   学习者关闭播放器后，流体播放器将使用html5 postMessage向父元素发送“关闭”消息。 加载控制器应处理此消息并继续。

使用指向需要学习的准确学习对象的参数修改Learning Manager嵌入式播放器URL。

URL：  [https://learningmanager.adobe.com/app/player](https://learningmanager.adobe.com/app/player)

以下任一参数均可用于启动课程：

* course_id ：这是要启动的课程的ID
* learning_program_id ：这是要启动的学习计划的ID
* certification_id ：这是要启动的认证的ID
* lo_id ：要播放的学习对象（课程/学习计划/认证/工作辅助）的ID

必需的参数：

* access_token ：这是安全参数，请使用公共API oauth访问令牌

调用Learning Manager API以检索上述参数。 这些API调用将由IT团队/顾问编写并托管在您的站点上的应用程序进行。

有关使用API的更多详细信息，请参阅此处：

Learning Manager V1 API - [https://learningmanager.adobe.com/docs/primeapi/v1/](https://learningmanager.adobe.com/docs/primeapi/v1/)



Learning Manager V2 API -  [https://learningmanager.adobe.com/docs/primeapi/v2/](https://learningmanager.adobe.com/docs/primeapi/v2/)


