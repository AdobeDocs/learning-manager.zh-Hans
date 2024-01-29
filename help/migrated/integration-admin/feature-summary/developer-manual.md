---
jcr-language: en_us
title: 应用程序开发人员手册
description: Learning Manager V1 API现已弃用。 V1 API将从2021年2月28日起停止工作。 我们建议您使用V2 API与Learning Manager交互。
contentowner: jayakarr
source-git-commit: ab6737e8b43222a6538921b0628a504a5f15859d
workflow-type: tm+mt
source-wordcount: '3279'
ht-degree: 0%

---



# 应用程序开发人员手册

Learning Manager V1 API现已弃用。 V1 API将从2021年2月28日起停止工作。 我们建议您使用V2 API与Learning Manager交互。

## 概述 {#overview}

[AdobeLearning Manager](http://www.adobe.com/in/products/learningmanager.html) 是一个由云托管、以学习者为中心的自助式学习管理解决方案。 客户可以使用Learning Manager API以编程方式访问Learning Manager资源，并将其与其他企业应用程序集成。 Adobe合作伙伴还可使用该API通过扩展Learning Manager的功能或将其与其他应用程序或服务集成来提升其价值主张。

### 使用场景 {#usagescenario}

使用Learning Manager API，开发人员可以构建可扩展Learning Manager功能或将Learning Manager与其他企业应用程序工作流程集成的自包含应用程序。 您可以使用您选择的任何技术来开发Web应用程序、桌面客户端或移动应用程序。 作为开发人员，您可以从Learning Manager中访问应用程序数据。 您开发的应用程序部署在Learning Manager平台之外，您可以完全控制应用程序的开发生命周期。 通常，应用程序由客户组织开发，用于其Learning Manager帐户，并且这些应用程序专属于该特定客户组织。 此外，Adobe合作伙伴可以使用Learning Manager API构建一般应用程序，大量Learning Manager客户都可以使用此API。

## Learning Manager API {#apidescription}

Learning Manager API以REST原则为基础，可通过HTTP向应用程序开发人员公开Learning Manager对象模型的关键元素。 在了解API端点和HTTP方法的详细信息之前，开发人员可以熟悉各种Learning Manager对象、其属性和相互关系。 深入了解模型之后，大致了解API请求和响应的结构，以及API之间通用的一些常用编程术语也同样很有帮助。

有关各种API端点和方法的详细信息，请参阅  [Learning Manager API文档](https://learningmanager.adobe.com/docs/primeapi/v2/).

## API身份验证 {#apiauthentication}

在编写可对Learning Manager进行API调用的应用程序时，您必须使用集成管理员应用程序注册应用程序。

Learning Manager API使用OAuth 2.0框架对客户端应用程序进行身份验证和授权。

**过程**

**1. 设置应用程序**

您可以使用客户端ID和客户端密钥设置应用程序以使用适当的端点。 注册应用程序后，您可以获取clientId和clientSecret。 获取URL应在浏览器中使用，因为它会使用SSO、Adobe ID等预配置帐户对Learning Manager用户进行身份验证。

```
GET https://learningmanager.adobe.com/oauth/o/authorize?client_id=<Enter your clientId>&redirect_uri=<Enter a url to redirect to>&state=<Any String data>&scope=<one or more comma separated scopes>&response_type=CODE.
```

身份验证成功后，浏览器将重定向到上述URL中提到的redirect_uri。 参数 **代码** 将与重定向uri一起附加。

**2. 从代码获取刷新令牌**

`POST https://learningmanager.adobe.com/oauth/token Content-Type: application/x-www-form-urlencoded`

发布请求的正文：

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

POST [https://learningmanager.adobe.com/oauth/token/refresh](https://learningmanager.adobe.com/oauth/token/refresh) Content-Type： application/x-www-form-urlencoded

发布请求的正文：

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

**用于验证访问令牌详细信息的URL**

`GET https://learningmanager.adobe.com/oauth/token/check?access_token=<access_token>`

**使用限制**

访问令牌的有效期为七天。 一天之后，必须使用刷新令牌生成新的访问令牌。 如果在现有访问令牌仍然有效时从刷新令牌生成新的访问令牌，则返回现有令牌。

Learning Manager API中的一些常用术语阐述如下，仅供参考。

**包括**

开发人员可以访问单个API对象模型，还可以访问与该模型关联的多个模型。 要访问后续相关模型，需要了解每个模型与其他模型的关系。 **包括** 参数允许开发者访问依赖模型。 可以使用逗号分隔符访问多个模型。 有关使用的示例和更多详细信息，请参阅 **包括**，请参阅本页中的示例API模型部分。

**API请求**

可以通过发出HTTP请求来发出API请求。 根据端点和方法，开发者可以选择各种HTTP动词，例如GET、PUT、POST、DELETE、PATCH等。 对于某些请求，可以传递查询参数。 当请求特定数据模型时，用户还可以请求相关模型，如JSON API规范中所述。 中介绍了典型API请求的结构 [示例模型使用情况](#main-pars_header_1415780624).

**API响应**

当客户端发出API请求时，根据JSON API规范获取SON文档。 响应还包含HTTP状态代码，开发人员可以验证该代码，以便在其应用程序逻辑中执行相应的后续步骤。 中介绍了典型API响应的结构  [示例模型使用情况](#main-pars_header_1415780624).

**错误**

当API请求失败时，将获得错误响应。 响应中返回的HTTP状态代码指示错误的性质。 错误代码用API参考中每个模型的编号表示。 200、204、400和404是API中表示的一些常见错误，表示HTTP访问问题。

**字段**

API对象的属性及其关系统称为“字段”。 请参阅 [JSON API，了解更多信息。](http://jsonapi.org/format/#document-resource-object-fields) 在进行API调用以从模型中获取一个或多个特定属性时，可以使用“字段”作为参数。 在没有Fields参数的情况下，API调用会从模型中获取所有可用属性。 例如，在以下API调用中，字段[技能]=name仅获取技能模型的名称属性。

https://learningmanager.adobe.com/primeapi/v2/users/{userId}/userSkills/{id}?include=skillLevel.skill&amp;fields[skill]=name

**分页**

有时，API请求会在响应中返回一长串对象。 在这种情况下，分页属性使开发人员能够按顺序获取多个页面的结果，其中每个页面包含一系列记录。 例如，Learning Manager中的分页属性可让您设置页面可显示的最大记录数。 此外，您还可以定义要在页面上显示的记录的范围值。

**排序**

API模型中允许排序。 根据模型，选择要对结果应用的排序类型。 可以按升序或降序应用排序。 例如，如果指定 `code sort=name`，则按名称升序排序。 如果您指定 `code sort=-name`，它按名称降序排序。 请参阅 [有关更多信息，请参阅JSON API规范](http://jsonapi.org/format/#fetching-sorting).

## API用法图示 {#samplemodel}

如果开发人员希望获取技能名称、技能级别分配的最高点数以及学习者在该技能中获得的点数，我们来考虑一个情景。

Learning Manager API中的userSkill模型包含id、类型、dateAchired、dateCreated、pointsEarned作为默认属性。 因此，当开发人员使用GET方法获取userSkill模型的详细信息时，与默认属性相关的当前数据将显示在响应输出中。

但是，在这种情况下，开发人员希望获得用户的技能名称和技能级别点数。 Learning Manager API能让您使用关系字段和include参数访问相关信息。 在关系标签中获取用户Skill的相关模型。 您可以将这些模型与userSkill一起调用，以获取每个关联模型的详细信息。 要获取此信息，请使用 **`code include`** 每个关联模型都有点（句点）分隔值的参数。 您可以使用逗号作为分隔符来请求其他模型，例如user include=skillLevel.skill，course

**API调用**

`https://learningmanagerqe1.adobe.com/primeapi/v1/users/%7buserId%7d/userSkills/%7bid%7d?include=skillLevel.skill&fields%5bskill%5d=name&fields%5bskillLevel%5d=maxCredits&fields%5buserSkill%5d=pointsEarned`

例如，用户ID可以为746783，而用户ID为：746783_4426_1。

**API调用的响应**

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

## Learning Manager模型 {#models}

Learning Manager API允许开发人员将Learning Manager对象作为RESTful资源进行访问。 每个API端点代表一个资源，通常是一个对象实例（如Badge）或此类对象的集合。 然后，开发人员使用PUT、GET、POST和DELETE等HTTP谓词对这些对象（集合）执行CRUD操作。

+++V1 API

下图表示V1 API中Learning Manager对象模型的各种元素。

![](assets/er-diag-primemodels.png)

下表介绍了Learning Manager V1对象模型的各种元素：

<table border="1" cellspacing="0" cellpadding="0">
 <tbody>
  <tr>
   <td>
    <p><strong>序列号</strong></p></td>
   <td>
    <p><strong>Learning Manager对象</strong></p></td>
   <td>
    <p><strong>描述</strong></p></td>
  </tr>
  <tr>
   <td>
    <p>1.      </p></td>
   <td>
    <p>用户</p></td>
   <td>
    <p>用户是Learning Manager中的关键模型。 用户通常是使用学习对象的公司内部或外部学习者。 但是，除学习者之外，他们可能还扮演一些其他角色，如作者和经理。 用户ID、类型、电子邮件是一些内嵌属性。 </p></td>
  </tr>
  <tr>
   <td>
    <p>2.      </p></td>
   <td>
    <p>课程</p></td>
   <td>
    <p>课程是Learning Manager支持的学习对象之一，由一个或多个模块组成。 </p></td>
  </tr>
  <tr>
   <td>
    <p>3.      </p></td>
   <td>
    <p>模块</p></td>
   <td>
    <p>模块是在Learning Manager中创建学习对象时所用的构造块。 模块可以分为四种不同类型，例如教室、虚拟教室、活动和自学模块。 使用此模块模型可获取帐户中所有模块的详细信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>4.      </p></td>
   <td>
    <p>认证</p></td>
   <td>
    <p>向成功完成课程的学习者授予认证。 使用认证前，您必须在应用程序中完成课程。 </p></td>
  </tr>
  <tr>
   <td>
    <p>5.      </p></td>
   <td>
    <p>学习计划</p></td>
   <td>
    <p>学习计划是专门设计的课程，旨在满足用户的特定学习要求。 通常，学习计划用于推动完成横跨各个课程的学习目标。 </p></td>
  </tr>
  <tr>
   <td>
    <p>6.      </p></td>
   <td>
    <p>徽章</p></td>
   <td>
    <p>徽章是学习者在课程学习过程中达到特定的阶段性目标时获得的一种成就标志。 </p></td>
  </tr>
  <tr>
   <td>
    <p>7.      </p></td>
   <td>
    <p>技能</p></td>
   <td>
    <p>技能模型由级别和积分组成。 学习者可以在完成相关课程后获得技能。 </p></td>
  </tr>
  <tr>
   <td>
    <p>8.      </p></td>
   <td>
    <p>认证注册</p></td>
   <td>
    <p>此模型提供用户注册单个认证的详细信息。</p></td>
  </tr>
  <tr>
   <td>
    <p>9.  </p></td>
   <td>
    <p>课程注册</p></td>
   <td>
    <p>此模型提供用户注册单个课程的详细信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>10.  </p></td>
   <td>
    <p>课程实例</p></td>
   <td>
    <p>一个课程可以关联一或多个实例。 您可以获取课程实例 </p></td>
  </tr>
  <tr>
   <td>
    <p>11.  </p></td>
   <td>
    <p>课程技能</p></td>
   <td>
    <p>课程技能模型会列明通过完成课程获得单一技能的进度。</p></td>
  </tr>
  <tr>
   <td>
    <p>12.  </p></td>
   <td>
    <p>课程模块</p></td>
   <td>课程模块模型会指明课程中会如何加入某个模块。 例如，模块是用于预先测试还是用于内容。</td>
  </tr>
  <tr>
   <td>
    <p>13.  </p></td>
   <td>learningProgramInstance</td>
   <td>
    <p>学习计划可以包含多个具有学习计划相似属性的实例，或自定义实例。 </p></td>
  </tr>
  <tr>
   <td>
    <p>14.  </p></td>
   <td>
    <p>工作辅助</p></td>
   <td>
    <p>工作辅助是可供学习者访问的学习内容，不设任何注册或完成标准。 您可以提取更新日期、状态、ID信息及其相关模型，如工作辅助版本、作者和技能级别。 </p></td>
  </tr>
  <tr>
   <td>
    <p>15.  </p></td>
   <td>
    <p>jobAidVersion</p></td>
   <td>
    <p>根据内容修订次数和上传次数，工作辅助可关联一或多个版本。 此模型提供单个工作辅助版本的详细信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>16.  </p></td>
   <td>
    <p>learningProgramInstanceEnrollment</p></td>
   <td>
    <p>学习计划由一或多个实例组成。 学习者可以自行注册或由管理员分配学习计划实例。 此模型提供用户注册单个学习计划实例的详细信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>17.  </p></td>
   <td>
    <p>模块版本</p></td>
   <td>
    <p>模块可具有一或多个版本，具体取决于修订后的内容上传。 使用此模型可获取有关任何单个模块版本的特定信息。 </p></td>
  </tr>
  <tr>
   <td>
    <p>18.  </p></td>
   <td>
    <p>技能级别</p></td>
   <td>
    <p>技能级别由一门或多门课程组成，学完这些课程后即可获得相应级别和相关学分。 </p></td>
  </tr>
  <tr>
   <td>
    <p>19.  </p></td>
   <td>
    <p>userBadge</p></td>
   <td>
    <p>UserBadge将单个徽章与单个用户相关联。 它包含一些详细信息，如徽章获取时间、assertionUrl等。 </p></td>
  </tr>
  <tr>
   <td>
    <p>20.  </p></td>
   <td>
    <p>用户技能</p></td>
   <td>
    <p>用户技能表明单个用户达到的单个技能级别。</p></td>
  </tr>
 </tbody>
</table>

+++

+++V2 API

以下是V2 API中Learning Manager类图的各个元素。

![](assets/v2api-class-diagram.jpg)

<table>
 <tbody>
  <tr>
   <th><b>Learning Manager对象</b></th>
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
   <td>用户是Learning Manager中的关键模型。 用户通常是使用学习对象的公司内部或外部学习者。 但是，除学习者之外，他们可能还扮演一些其他角色，如作者和经理。 用户ID、类型、电子邮件是一些内嵌属性。 </td>
  </tr>
  <tr>
   <td>资源</td>
   <td>这用于为模块要封装的每个内容资源建模。 所有资源都封装在 <code>
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
   <td>技能模型由级别和积分组成。 学习者可以在完成相关课程后获得技能。 <br></td>
  </tr>
  <tr>
   <td>技能级别</td>
   <td>技能级别由一门或多门课程组成，学完这些课程后即可获得相应级别和相关学分。 <br></td>
  </tr>
  <tr>
   <td>learningobject</td>
   <td>学习对象是对用户可以注册和学习的各种对象的抽象。 目前Learning Manager有四种学习对象 — 课程、认证、学习计划 <code>
     and
    </code> 工作辅助。<br></td>
  </tr>
  <tr>
   <td>learningobjectinstance<br></td>
   <td>学习对象的特定实例。<br></td>
  </tr>
  <tr>
   <td>learningObjectResource</td>
   <td>这等同于 <code>
     module
    </code>. 课程由一门课程组成 <code>
     of
    </code> 更多模块。 在Learning Manager中，模块可以采用多种等效的方式提供。 因此， <code>
     loResource
    </code> 这些同等资源基本上都包含在内。<br></td>
  </tr>
  <tr>
   <td>loResourceGrade<br></td>
   <td>这封装了用户在其注册的学习对象上下文中使用特定资源的结果。 它包含如下信息：所花费的时间 <code>
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
   <td>L1 Feedback封装了学习者针对与学习对象相关的反馈问题提供的答案。 通常，如果配置为收集学习者的此类反馈，则系统会在用户完成学习对象后收集此信息。<br></td>
  </tr>
  <tr>
   <td>注册<br></td>
   <td>此抽象概念封装了与特定事务相关的详细信息，该事务表示将特定用户分配给特定学习对象实例。<br></td>
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
名称\
子域\
主题数据\
时区代码

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
名称\
state

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
名称\
state

+++

+++data

**属性**
id\
名称

+++

+++游戏

**属性**
颜色\
名称\
点

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
state\
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
state\
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
state

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
内容类型\
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
名称\
onlyQuiz\
reportingInfo\
reportingType\
seatLimit

+++

+++技能

**属性**
描述\
id\
名称\
state

**关系**
级别(skillLevel)

+++

+++skillLevel

**属性**
id\
级别\
maxCredits\
名称\
**关系**
徽章\
技能

+++

+++用户

**属性**
avatarurl\
个人资料\
contentLocale\
email\
字段\
id\
名称\
pointsEarned\
个人资料\
角色\
state\
时区代码\
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
四分之一

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

作为开发人员，您必须在Learning Manager上创建试用帐户，以便您可以完全访问该帐户中的所有角色。 为了能够编写应用程序，开发人员必须创建一些用户和课程，并使帐户处于合理的状态，这样正在开发的应用程序才能访问一些示例数据。

## 创建客户端ID和密钥 {#createclientidandsecret}

1. 向内 **集成管理员** 登录，单击 **[!UICONTROL 应用程序]** 在左侧窗格中。

   ![](assets/application-development-menu.png)

   *选择集成管理员应用程序*

1. 点击 **[!UICONTROL 注册]** ，以注册您的应用程序详细信息。 此时会显示注册页面。

   ![](assets/register-application.png)

   *注册应用程序*

   必须填写此页中的所有字段。

   **应用程序名称**：输入您的应用程序名称。 不必使用相同的应用程序名称，它可以是任何有效的名称。

   **URL**：如果您知道托管应用程序的确切URL，则可以提及它。 如果您不知道，则可以提及您的公司URL。 此字段中的有效URL名称是必填项。

   **重定向域**：输入在OAuth身份验证后Learning Manager应用程序要重定向到的应用程序的域名。 您可以在此处提及多个URL，但必须使用有效URL，例如 `http://google.com`， `http://yahoo.com` 等等。

   **描述：** 输入应用程序的简要说明。

   **范围：** 从四个可用选项中选择一个来定义应用程序范围。 根据您在此处提到的选择，您的应用程序可访问Learning Manager API端点。 例如，如果选择 **学习者角色读取权限**，则您的应用程序以只读方式访问所有Learning Manager学习者API端点。

   **仅针对此帐户？**\
   **是**  — 如果选择“是”，则其他帐户管理员无法看到该应用程序。\
   **否**  — 如果选择“否”，则其他帐户管理员也可以访问此应用程序，但他们需要使用应用程序id来访问此应用程序。 应用程序ID在Learning Manager应用程序编辑模式下生成和显示。

   如果您选择 **管理员角色读写权限** 在注册应用程序时作为范围，然后选择 **管理员角色读取权限** 在创作API时，您仍可以拥有应用程序的写入权限，因为应用程序注册范围取代授权工作流程。

1. 点击 **[!UICONTROL 注册]** ，然后在注册页面中填写详细信息。

## 应用程序开发和测试 {#applicationdevelopmentandtesting}

开发人员可以使用Learning Manager API构建任何应用程序。 开发人员必须确保他们的帐户包含一些有效的用户和课程。 他们可创建一些虚拟用户和课程，并在试用帐户中模拟活动，以便测试应用程序的功能。

## 应用程序部署 {#applicationdeployment}

我们建议生产帐户的Learning Manager管理员或集成管理员负责将其应用程序提供给公司内的用户。 应用程序经过测试且被认为可用于生产后，请通知生产帐户的管理员。 理想情况下，管理员需要为生产帐户中的应用程序生成新的客户端ID和客户端密钥，并执行必要步骤以安全方式将这些密钥并入应用程序中。 部署应用程序的实际过程因企业而异，公司的Learning Manager管理员需要获得公司IT/IS部门的支持才能完成部署。

## 外部应用程序审批 {#externalapplicationapproval}

您可以通过单击 **批准** (位于右上角的 **应用程序** 页面。 提供外部应用程序ID并单击 **保存。**

![](assets/add-external-application.png)

*添加和批准外部应用程序*

## 常见问题解答

+++Learning Manager是否集成了电子商务？

AdobeLearning Manager未集成电子商务。 但是，我们提供API，以便您可以创建自己的无头LMS和实施电子商务功能。
+++
