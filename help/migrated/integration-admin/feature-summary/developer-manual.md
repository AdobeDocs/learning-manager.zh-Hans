---
jcr-language: en_us
title: 应用程序开发人员手册
description: Adobe Learning Manager V1 API 现已弃用。 V1 API 将自 2021 年 2 月 28 日起停用。我们建议您使用V2 API与Learning Manager交互。
contentowner: jayakarr
exl-id: fa9313ac-67de-4467-9253-7eeabcf14204
source-git-commit: 447a4e041d74cf086afada3794ac08a04e70c2ca
workflow-type: tm+mt
source-wordcount: '3385'
ht-degree: 62%

---

# 应用程序开发人员手册

>[!NOTE]
>
>Adobe Learning Manager V1 API 现已弃用。 我们建议您使用V2 API与Learning Manager交互。


## 概述 {#overview}

[Adobe Learning Manager](http://www.adobe.com/in/products/learningmanager.html) 是一款基于云端、以学习者为中心的自助式学习管理解决方案。客户可以使用 Adobe Learning Manager API 以编程方式访问 Adobe Learning Manager 资源，以将之与其他企业应用程序集成。Adobe 合作伙伴也可以使用 API，扩展 Adobe Learning Manager 的功能或将之与其他应用程序或服务进行集成，从而提高其价值。

### 使用场景 {#usagescenario}

开发人员使用 Adobe Learning Manager API 可以构建独立的应用程序，从而扩展 Adobe Learning Manager 的功能，或者可将 Adobe Learning Manager 与其他企业应用程序工作流程进行集成。您可以使用您选择的任何技术来开发 Web 应用程序、桌面客户端或移动应用程序。 作为开发人员，您可以从Learning Manager中访问应用程序数据。 您开发的应用程序部署在Learning Manager平台之外，您可以完全控制应用程序的开发生命周期。 通常应用程序由客户公司进行开发，以便与其 Adobe Learning Manager 帐户结合使用，因此对于特定客户公司来说是隐私应用程序。此外，Adobe 合作伙伴可以使用 Adobe Learning Manager API 构建通用应用程序，这些应用程序可供大量 Adobe Learning Manager 客户使用。

## Adobe Learning Manager API {#apidescription}

Adobe Learning Manager API 基于 REST 原则，并通过 HTTP 将 Adobe Learning Manager 对象模型的关键要素显示给应用程序开发人员。开发人员在了解 API 端点的详细信息和 HTTP 方法前，可以先熟悉各种 Adobe Learning Manager 对象、其属性和内部关系。深入了解模型之后，大致了解 API 请求和响应的结构，以及 API 之间通用的一些常用编程术语也同样很有帮助。

有关各种API端点和方法的详细信息，请参阅  [Learning Manager API文档](https://learningmanager.adobe.com/docs/primeapi/v2/).

## 学习者API

AdobeLearning Manager — 学习者API允许您为用户创建自定义学习体验。 使用这些API需要有效的用户令牌，并且仅用于拥有完全许可/注册学习者的工作流程。

>[!IMPORTANT]
>
>不得按原样将这些参数用于任何类型的数据检索，以支持任何未登录用户/共享用户或任何其他此类情况。

未登录的用例需要特殊处理。

**如果您对适当使用这些API有任何疑问，请与解决方案体系结构团队联系，并确保解决方案设计师在您部署解决方案之前已经审查过该解决方案**.

## API 身份验证 {#apiauthentication}

在编写向 Adobe Learning Manager 调用 API 的应用程序时，您必须使用集成管理应用程序进行注册。

Adobe Learning Manager API 使用 OAuth 2.0 框架对客户端应用程序进行身份验证和授权。

**步骤**

**1. 设置应用程序**

您可以使用客户端ID和客户端密钥设置应用程序以使用适当的端点。 注册应用程序后，您可以获取clientId和clientSecret。 应在浏览器中使用 Get URL，因为它会使用预配置的帐户（如 SSO、Adobe ID 等）对 Adobe Learning Manager 用户进行身份验证。

```
GET https://learningmanager.adobe.com/oauth/o/authorize?client_id=<Enter your clientId>&redirect_uri=<Enter a url to redirect to>&state=<Any String data>&scope=<one or more comma separated scopes>&response_type=CODE.
```

身份验证成功后，浏览器将重定向到上述 URL 中提到的 redirect_uri。 参数&#x200B;**代码**&#x200B;随重定向 URI 一起追加。

**2. 通过代码获取刷新令牌**

`POST https://learningmanager.adobe.com/oauth/token Content-Type: application/x-www-form-urlencoded`

发布请求正文：

```
client_id: 
<enter your clientid>
 & 
 client_secret: 
 <enter your clientsecret>
  & 
  code: 
  <code from step 1></code>
 </enter>
</enter>
```

**3.** **从刷新令牌获取访问令牌**

用于获取访问令牌的URL：

POST [https://learningmanager.adobe.com/oauth/token/refresh](https://learningmanager.adobe.com/oauth/token/refresh) Content-Type: application/x-www-form-urlencoded

发布请求正文：

```
client_id: 
<enter your clientid>
 & 
 client_secret: 
 <enter your clientsecret>
  & 
  refresh_token: 
  <refresh token>
   
  </refresh>
 </enter>
</enter>
```

**用于验证访问令牌详细信息的 URL**

`GET https://learningmanager.adobe.com/oauth/token/check?access_token=<access_token>`

**使用限制**

访问令牌的有效期为七天。 一天后，您必须使用刷新令牌生成新的访问令牌。 如果在现有访问令牌仍然有效的情况下用刷新令牌生成了新的访问令牌，则现有令牌将失效。

下面将介绍 Adobe Learning Manager API 中的一些常用术语，供您参考。

**“Includes”**

开发人员可以访问单个 API 对象模型，也可以访问与该模型关联的多个模型。 如需访问后续相关模型，您需要了解每个模型与其他模型之间的关系。 **包括** 参数允许开发者访问依赖模型。 可以使用逗号分隔符访问多个模型。 有关使用的示例和更多详细信息，请参阅 **包括**，请参阅本页中的示例API模型部分。

**API 请求**

可以通过发出 HTTP 请求来实现 API 请求。 开发人员可以根据端点和方法的不同，选择不同的 HTTP 动词，如 GET、PUT、POST、DELETE、PATCH 等。 对于某些请求，可以传递查询参数。 在请求特定数据模型时，用户还可以按 JSON API 规范中所述请求相关模型。 [示例模型用法](#main-pars_header_1415780624)中介绍了典型 API 请求的结构。

**API 响应**

当客户端发出 API 请求时，将根据 JSON API 规范获取 SON 文档。 响应还包含HTTP状态代码，开发人员可以验证该代码，以便在其应用程序逻辑中执行相应的后续步骤。 中介绍了典型API响应的结构  [示例模型使用情况](#main-pars_header_1415780624).

**错误**

当 API 请求失败时，会得到错误响应。 响应中返回的 HTTP 状态码表示错误的性质。 错误代码以 API 引用中每个模型的数字显示。 200、204、400和404是API中表示的一些常见错误，表示HTTP访问问题。

**字段**

API 对象的属性及其关系统称为“字段”。 有关更多信息，请参阅 [JSON API。](http://jsonapi.org/format/#document-resource-object-fields) 在进行API调用以从模型中获取一个或多个特定属性时，可以使用“字段”作为参数。 如果没有“字段”参数，API 调用将从模型中获取所有可用属性。 例如，在以下API调用中，字段[技能]=name仅获取技能模型的名称属性。

https://learningmanager.adobe.com/primeapi/v2/users/{userId}/userSkills/{id}?include=skillLevel.skill&amp;fields[skill]=name

**分页**

有时，API 请求会导致在响应中返回一长串对象。 在这种情况下，分页属性使开发人员能够按多个页面依次获取结果，其中每个页面包含一系列记录。 例如，Adobe Learning Manager 中的分页属性可以让您设置页面中显示的最大记录数。此外，您还可以定义要在页面上显示的记录的范围值。

**排序**

API 模型中允许排序。 根据模型，选择要对结果应用的排序类型。 可以按升序或降序应用排序。 例如，如果指定 `code sort=name`，则按名称升序排序。 如果您指定 `code sort=-name`，它按名称降序排序。 请参阅 [有关更多信息，请参阅JSON API规范](http://jsonapi.org/format/#fetching-sorting).

## API 使用说明 {#samplemodel}

如果开发人员希望获取技能名称、技能级别分配的最高点数以及学习者在该技能中获得的点数，我们来考虑一个情景。

Adobe Learning Manager API 中 userSkill 模型由 id、type、dateAchieved、dateCreated、pointsEarned 等默认属性组成。因此，当开发人员使用 GET 方法获取 userSkill 模型的详细信息时，当前与默认属性相关的数据会显示在响应输出中。

但是，在这种情况下，开发人员希望获得用户的技能名称和技能级别的分数。 Adobe Learning Manager API 可以让您使用关系字段和“include”参数来访问这些相关信息。userSkill 的关联模型可在“关系”标签中获取。 您可以通过调用这些模型以及 userSkill 来获取每个关联模型的详细信息。 要获取此信息，请使用 **`code include`** 每个关联模型都有点（句点）分隔值的参数。 您可以使用逗号作为分隔符来请求其他模型，例如user include=skillLevel.skill，course

**API 调用**

`https://learningmanagerqe1.adobe.com/primeapi/v1/users/%7buserId%7d/userSkills/%7bid%7d?include=skillLevel.skill&fields%5bskill%5d=name&fields%5bskillLevel%5d=maxCredits&fields%5buserSkill%5d=pointsEarned`

例如，userId 可以是 746783，userSkills id 为 746783_4426_1。

**API 调用的响应**

```
\{ 
 "links": {"self": "https://learningmanager.adobe.com/primeapi/v2/users/746783/userSkills/746783_4426_1?include=skillLevel.skill&fields[userSkill]=pointsEarned&fields[skillLevel]=maxCredits&fields[skill]=name"}, 
 "data": { 
 "id": "746783_4426_1", 
 "type": "userSkill", 
 "attributes": {"pointsEarned": 5}, 
 "links": {"self": "https://learningmanager.adobe.com/primeapi/v2/users/746783/userSkills/746783_4426_1"} 
 }, 
 "included": [ 
 { 
 "id": "4426", 
 "type": "skill", 
 "attributes": {"name": "Java"}, 
 "links": {"self": "https://learningmanager.adobe.com/primeapi/v2/skills/4426"} 
 }, 
 { 
 "id": "4426_1", 
 "type": "skillLevel", 
 "attributes": {"maxCredits": 10} 
 } 
 ] 
} 
```

## Adobe Learning Manager 模型 {#models}

Adobe Learning Manager API 允许开发人员以 RESTful 资源的形式访问 Adobe Learning Manager 对象。 每个 API 端点都表示一个资源，通常为一个徽章之类的对象实例，或此类对象的集合。随后，开发人员可以使用 HTTP 动词，例如 PUT、GET、POST 和 DELETE 在这些对象（集合）上执行 CRUD 操作。

+++V1 API

下图表示 V1 API 中 Adobe Learning Manager 对象模型的各个元素。

![](assets/er-diag-primemodels.png)

下表介绍了Learning Manager V1对象模型的各种元素：

<table border="1" cellspacing="0" cellpadding="0">
 <tbody>
  <tr>
   <td>
    <p><strong>序列号</strong></p></td>
   <td>
    <p><strong>Adobe Learning Manager 对象</strong></p></td>
   <td>
    <p><strong>描述</strong></p></td>
  </tr>
  <tr>
   <td>
    <p>1.      </p></td>
   <td>
    <p>用户</p></td>
   <td>
    <p>用户是 Adobe Learning Manager 中的关键模型。用户通常是使用学习对象的企业内部或外部学习者。 但是，除学习者之外，他们可能还扮演一些其他角色，如作者和经理。用户 ID、类型、电子邮件是一些内联属性。 </p></td>
  </tr>
  <tr>
   <td>
    <p>2.      </p></td>
   <td>
    <p>课程</p></td>
   <td>
    <p>课程是 Adobe Learning Manager 支持的学习对象之一，由一个或多个模块组成。 </p></td>
  </tr>
  <tr>
   <td>
    <p>3.      </p></td>
   <td>
    <p>模块</p></td>
   <td>
    <p>模块是在 Adobe Learning Manager 中创建学习对象时所用的构造块。模块可以分为四种不同类型，如教室、虚拟教室、活动和自学模块。 使用此模块模型可获取帐户中所有模块的详细信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>4.       </p></td>
   <td>
    <p>认证</p></td>
   <td>
    <p>向成功完成课程的学习者授予认证。 使用认证前，您须在应用程序中完成相应课程。 </p></td>
  </tr>
  <tr>
   <td>
    <p>5.       </p></td>
   <td>
    <p>学习计划</p></td>
   <td>
    <p>学习计划是专门设计的课程，旨在满足用户的特定学习需求。 一般而言，学习计划用于推动完成横跨各个课程的学习目标。 </p></td>
  </tr>
  <tr>
   <td>
    <p>6.       </p></td>
   <td>
    <p>徽章</p></td>
   <td>
    <p>徽章是学习者在课程学习过程中达到特定的阶段性目标时获得的一种成就标志。 </p></td>
  </tr>
  <tr>
   <td>
    <p>7.       </p></td>
   <td>
    <p>技能</p></td>
   <td>
    <p>技能模型由级别和学分组成。 学习者可以在完成相关课程后获得技能。 </p></td>
  </tr>
  <tr>
   <td>
    <p>8.       </p></td>
   <td>
    <p>认证注册</p></td>
   <td>
    <p>此模型提供用户注册单个认证的详细信息。</p></td>
  </tr>
  <tr>
   <td>
    <p>9.   </p></td>
   <td>
    <p>课程注册</p></td>
   <td>
    <p>此模型提供用户注册单个课程的详细信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>10.   </p></td>
   <td>
    <p>课程实例</p></td>
   <td>
    <p>一个课程可以关联一或多个实例。 您可以获取课程实例 </p></td>
  </tr>
  <tr>
   <td>
    <p>11.   </p></td>
   <td>
    <p>课程技能</p></td>
   <td>
    <p>课程技能模型会列明通过完成课程获得单一技能的进度。</p></td>
  </tr>
  <tr>
   <td>
    <p>12.   </p></td>
   <td>
    <p>课程模块</p></td>
   <td>课程模块模型会指明课程中会如何加入某个模块。 例如，模块是用于预先测试还是用于内容。</td>
  </tr>
  <tr>
   <td>
    <p>13.   </p></td>
   <td>学习计划实例</td>
   <td>
    <p>学习计划可以包含多个具有学习计划相似属性的实例，或自定义实例。 </p></td>
  </tr>
  <tr>
   <td>
    <p>14.   </p></td>
   <td>
    <p>工作辅助</p></td>
   <td>
    <p>工作辅助是可供学习者访问的学习内容，不设任何注册或完成标准。 您可以提取更新日期、状态、ID 信息及其相关模型，如工作辅助版本、作者和技能级别。 </p></td>
  </tr>
  <tr>
   <td>
    <p>15.   </p></td>
   <td>
    <p>工作辅助版本</p></td>
   <td>
    <p>根据内容修订次数和上传数量，工作辅助可关联一或多个版本。 此模型提供单个工作辅助版本的详细信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>16.   </p></td>
   <td>
    <p>学习计划实例注册</p></td>
   <td>
    <p>学习计划由一或多个实例组成。 学习者可以自行注册或由管理员分配学习计划实例。 此模型提供用户注册单个学习计划实例的详细信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>17.   </p></td>
   <td>
    <p>模块版本</p></td>
   <td>
    <p>模块可具有一或多个版本，具体视修订内容的上传次数而定。 使用此模型可获取任一模块版本的特定信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>18.   </p></td>
   <td>
    <p>技能级别</p></td>
   <td>
    <p>技能级别由一或多门课程组成，学完这些课程后即可获得对应级别和相关学分。 </p></td>
  </tr>
  <tr>
   <td>
    <p>19.   </p></td>
   <td>
    <p>userBadge</p></td>
   <td>
    <p>UserBadge将单个徽章与单个用户相关联。 它包含一些详细信息，如徽章获取时间、assertionUrl 等。 </p></td>
  </tr>
  <tr>
   <td>
    <p>20.   </p></td>
   <td>
    <p>用户技能</p></td>
   <td>
    <p>用户技能表明单个用户达到的单个技能级别。</p></td>
  </tr>
 </tbody>
</table>

+++

+++V2 API

以下是 V2 API 中 Adobe Learning Manager 类图的各个元素。

![](assets/v2api-class-diagram.jpg)

<table>
 <tbody>
  <tr>
   <th><b>Adobe Learning Manager 对象</b></th>
   <th><b>描述</b></th>
  </tr>
  <tr>
   <td>帐户</td>
   <td>封装Learning Manager客户的详细信息。</td>
  </tr>
  <tr>
   <td><code>
     badge
    </code></td>
   <td>徽章是学习者在课程学习过程中达到特定的阶段性目标时获得的一种成就标志。 <br></td>
  </tr>
  <tr>
   <td><code>
     catalog
    </code></td>
   <td>目录是学习对象的集合。</td>
  </tr>
  <tr>
   <td><code>
     user
    </code></td>
   <td>用户是 Adobe Learning Manager 中的关键模型。用户通常是使用学习对象的企业内部或外部学习者。 但是，除学习者之外，他们可能还扮演一些其他角色，如作者和经理。 用户 ID、类型、电子邮件是一些内联属性。 </td>
  </tr>
  <tr>
   <td>资源</td>
   <td>此模型用于对模块试图封装的每个内容资源进行建模。 所有资源都封装在 <code>
     an
    </code> <code>
     loResource
    </code> 在学习目标方面等同，但在交付类型或内容区域设置方面不同。<br></td>
  </tr>
  <tr>
   <td>userNotification</td>
   <td>此模型包含与学习者相关的通知信息。<br></td>
  </tr>
  <tr>
   <td>用户技能</td>
   <td>用户技能表明单个用户达到的单个技能级别。<br></td>
  </tr>
  <tr>
   <td>userBadge</td>
   <td>UserBadge将单个徽章 <code>
     with
    </code> 单个用户。 它包含一些细节，比如它是何时完成的， <code>
     assertionUrl
    </code> 等等。 <br></td>
  </tr>
  <tr>
   <td>技能</td>
   <td>技能模型由级别和学分组成。 学习者可以在完成相关课程后获得技能。 <br></td>
  </tr>
  <tr>
   <td>技能级别</td>
   <td>技能级别由一或多门课程组成，学完这些课程后即可获得对应级别和相关学分。 <br></td>
  </tr>
  <tr>
   <td>learningObject</td>
   <td>学习对象是一个抽象概念，指的是用户可以注册和学习的各种对象。 目前Learning Manager有四种学习对象 — 课程、认证、学习计划 <code>
     and
    </code> 工作辅助。<br></td>
  </tr>
  <tr>
   <td>学习对象实例<br></td>
   <td>学习对象的特定实例。<br></td>
  </tr>
  <tr>
   <td>learningObjectResource</td>
   <td>这等同于 <code>
     module
    </code>. 课程由一门课程组成 <code>
     of
    </code> 更多模块。 在 Adobe Learning Manager 中，系统会以多种等效方式提供模块。因此， <code>
     loResource
    </code> 这些同等资源基本上都包含在内。<br></td>
  </tr>
  <tr>
   <td>loResourceGrade<br></td>
   <td>这封装了用户在其注册的学习对象背景中使用特定资源的结果。 它包含如下信息：所花费的时间 <code>
     user
    </code> 在资源中，用户进行的进度百分比、通过/失败状态以及用户在任何相关测验中获得的分数。<br></td>
  </tr>
  <tr>
   <td>日历<br></td>
   <td>日历对象是以下对象的列表 <code>
     upcoming classroom
    </code> 或用户可以注册的虚拟教室课程。<br></td>
  </tr>
  <tr>
   <td>l1FeedbackInfo<br></td>
   <td>L1 Feedback 封装了学习者针对与学习对象相关的反馈问题提供的答案。 通常，如果配置为收集学习者的此类反馈，则系统会在用户完成学习对象后收集此信息。<br></td>
  </tr>
  <tr>
   <td>注册<br></td>
   <td>此抽象概念封装了与某事务相关的详细信息，该事务表示将特定用户分配给特定的学习对象实例。<br></td>
  </tr>
 </tbody>
</table>

+++

对象属性和关系的列表。

+++account

**属性**
dateCreated\
gamificationenabled\
id\
区域设置\
loginUrl\
logoUrl\
name\
子域\
主题数据\
timeZoneCode

**关系**
contentLocales(localizationMetadata)\
gamificationLevels(gamificationLevel)\
时区（时区）\
uiLocales(localizationMetadata)

+++

+++badge

**属性**
id\
imageUrl\
name\
或

+++

+++catalog

**属性**
dateCreated\
datupdated\
描述\
id\
isDefault\
isInternallySearchable\
isListable\
name\
或

+++

+++data

**属性**
id\
名称

+++

+++游戏

**属性**
颜色\
name\
点数

+++

+++learningObject

**属性**
authorNames\
dateCreated\
datePublished\
datupdated\
有效性指标\
enrollmenttype\
id\
imageUrl\
isExternal\
isSubLoOrderEnforced\
loType\
或\
标记

**关系**
作者（用户）\
enrollment(learningObjectInstanceEnrollment)\
实例(learningObjectInstance)\
prerequisiteLO(learningObject)\
skills(learningObjectSkill)\
subLO(learningObject)\
supplementaryLOs(learningObject)\
supplementaryResources（资源）

+++

+++learningObjectInstance

**属性**
完成截止日期\
dateCreated\
enrollmentCount\
id\
isDefault\
seatLimit\
或\
有效性

**关系**
徽章\
l1FeedbackInfo(feedbackInfo)\
learningObject(learningObject)\
loResources(learningObjectResource)\
localizedMetadata(localizationMetadata)\
subLoInstances(learningObjectInstance)

+++

+++learningObjectInstanceEnrollment

**属性**
dateCompleted\
dateEnrolled\
dateStarted\
hasPassed\
id\
progresspercent\
分数\
或

**关系**
学习者（用户）\
learnerBadge(userBadge)\
learningObject(learningObject)\
loInstance(learningObjectInstance)\
loResourceGrades(learningObjectResourceGrade)

+++

+++learningObjectResource

**属性**
externalReporting\
id\
loResourceType\
resourceType\
版本

**关系**
learningObject(learningObject)\
loInstance(learningObjectInstance)\
localizedMetadata(localizationMetadata)\
resources（资源）

+++

+++learningObjectResourceGrade

**属性**
dateCompleted\
dateStarted\
dateSuccess\
duration\
hasPassed\
id\
progresspercent\
分数

**关系**
loResource(learningObjectResource)

+++

+++learningObjectSkill

**属性**
积分\
id\
**关系**
learningObject(learningObject)\
技能级别（技能级别）

+++

+++recommendation

**属性**
id\
原因

**关系**
learningObject(learningObject)

+++

+++resource

**属性**
authorDesiredDuration\
完成截止日期\
contentStructureInfoUrl\
contentType\
contentZipSize\
contentZipUrl\
dateCreated\
dateStart\
desiredDuration\
downloadUrl\
extraData\
hasQuiz\
hasToc\
id\
instructorName\
isDefault\
区域设置\
位置\
name\
onlyQuiz\
reportingInfo\
reportingType\
seatLimit

+++

+++技能

**属性**
描述\
id\
name\
或

**关系**
级别(skillLevel)

+++

+++skillLevel

**属性**
id\
级别\
maxCredits\
name\
**关系**
徽章\
技能

+++

+++用户

**属性**
avatarurl\
个人资料\
contentLocale\
电子邮件\
字段\
id\
name\
pointsEarned\
配置文件\
角色\
或\
timeZoneCode\
uiLocale

**关系**
帐户（帐户）\
manager（用户）

+++

+++userBadge

**属性**
assertionUrl\
dateAchieded\
id\
modelType

**关系**
徽章\
学习者（用户）\
model(learningObject)

+++

+++userCalenda

**属性**
课程\
课程类型\
dateStart\
已注册\
id\
月\
季度

**关系**
containerLO(learningObject)\
course(learningObject)

+++

+++userNotification

**属性**
actionTaken\
渠道\
dateCreated\
id\
消息\
modelIds\
modelName\
modelType\
读取\
角色

+++

+++userSkill

**属性**
dateAchieded\
dateCreated\
id\
pointsEarned

**关系**
learnerBadge(userBadge)\
learningObject(learningObject)\
技能级别（技能级别）\
user（用户）

+++

## 应用程序开发过程 {#registration}

## 先决条件 {#prerequisites}

作为开发人员，您必须在 Adobe Learning Manager 上创建试用帐户，以便拥有该帐户中所有角色的访问权限。若要编写应用程序，开发人员还需要创建一些用户帐户和课程，并为帐户设置合理的状态，以确保正在开发的应用程序能够访问部分示例数据。

## 创建客户端 ID 和密钥 {#createclientidandsecret}

1. 向内 **集成管理员** 登录，单击 **[!UICONTROL 应用程序]** 在左侧窗格中。

   ![](assets/application-development-menu.png)

   *选择集成管理员应用程序*

1. 点击 **[!UICONTROL 注册]** ，以注册您的应用程序详细信息。 此时会显示注册页面。

   ![](assets/register-application.png)

   *注册应用程序*

   必须填写此页面中的所有字段。

   **应用程序名称**：输入应用程序名称。 不必使用相同的应用程序名称，它可以是任何有效的名称。

   **URL**：如果您知道托管应用程序的确切 URL，可以提及它。 如果不知道，则可以提及公司 URL。 此字段中的有效URL名称是必填项。

   **重定向域**：在完成 OAuth 身份验证后，您希望 Adobe Learning Manager 应用程序重定向至哪款应用程序？请在此输入其域名。您可以在此处提及多个URL，但必须使用有效URL，例如 `http://google.com`， `http://yahoo.com` 等等。

   **描述：** 输入应用程序的简要说明。

   **范围：** 从四个可用选项中选择一个来定义应用程序范围。 根据您在此处提到的选择，Adobe Learning Manager API 端点可供您的应用程序访问。例如，如果选择 **学习者角色读取权限**，则您的应用程序以只读方式访问所有Learning Manager学习者API端点。

   **仅针对此帐户？**\
   **是**  — 如果选择“是”，则其他帐户管理员无法看到该应用程序。\
   **否**  — 如果选择“否”，则其他帐户管理员也可以访问此应用程序，但他们需要使用应用程序id来访问此应用程序。 应用程序ID在Learning Manager应用程序编辑模式下生成和显示。

   如果您选择 **管理员角色读写权限** 在注册应用程序时作为范围，然后选择 **管理员角色读取权限** 在创作API时，您仍可以拥有应用程序的写入权限，因为应用程序注册范围取代授权工作流程。

1. 在注册页中填写详细信息后，单击右上角的&#x200B;**[!UICONTROL “注册”]**。

## 应用程序开发和测试 {#applicationdevelopmentandtesting}

开发人员可以使用 Adobe Learning Manager API 构建任何应用程序。开发人员必须确保其帐户由一些有效用户和课程组成。 他们可以创建一些虚拟用户和课程，并在试用帐户中模拟相关活动，以便测试应用程序的功能。

## 应用程序部署 {#applicationdeployment}

我们建议生产帐户的 Adobe Learning Manager 管理员或集成管理员负责将应用程序提供给其企业内用户。在应用程序经过测试并被认为可以用于生产后，请将该生产帐户告知管理员。 理想情况下，管理员希望在生产帐户中为应用程序生成新的客户端 ID 和客户端密钥，并执行必要的步骤，以安全方式将它们纳入应用程序中。 部署应用程序的实际过程因企业而异，您所在企业的 Adobe Learning Manager 管理员必须获得企业内 IT/IS 部门的支持才能完成部署。

## 外部应用程序审批 {#externalapplicationapproval}

您可以通过单击 **批准** (位于右上角的 **应用程序** 页面。 提供外部应用程序 ID，然后单击&#x200B;**“保存”。**

![](assets/add-external-application.png)

*添加和批准外部应用程序*

## 常见问题解答

+++Learning Manager是否集成了电子商务？

Adobe Learning Manager 未集成电子商务。但我们提供 API，便于您创建自己的无头 LMS 及实现电子商务功能。
+++
