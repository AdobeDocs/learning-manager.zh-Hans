---
jcr-language: en_us
title: Learning Manager中的API速率限制
contentowner: saghosh
preview: true
source-git-commit: 544c695a77c21dd9162b9b943b6119d27aa373dc
workflow-type: tm+mt
source-wordcount: '1757'
ht-degree: 51%

---



# Learning Manager中的API速率限制

## 速率限制简介 {#introductiontoratelimiting}

AdobeLearning Manager提供了丰富的REST API套件，可帮助客户构建与Learning Manager集成的应用程序，甚至还可以构建自定义用户体验和工作流扩展以帮助客户开展业务。

调用API时，Learning Manager服务器会使用共享的计算资源，因此我们必须谨慎确保应用程序性能良好，且不会危及平台的性能和可用性特征。 这可以通过引入对API客户端调用方式（频率和速度）的限制来实现。

例如，应用程序可能尝试获取该帐户中的所有用户，并可能以较快的速度进行多个分页API调用。 不经意间，开发人员可能会将此称为一个紧密循环，导致服务器负载过大，应用程序运行迟缓，甚至会因占用超出预期或需要的资源而危及平台。

为了解决这个问题，我们引入了速率限制，限制单个用户在特定帐户的特定客户端应用程序中可以进行多少次API调用。 我们根据每分钟请求数（简称RPM）衡量这一情况。 例如，当我们说GETAPI调用的限制为600 RPM时，这仅意味着单个用户在一分钟内不能超过最多600个调用，如果用户超过该限制，则用户将获得速率限制。 以毫秒粒度跟踪请求，因此此限制对应于每100毫秒(ms)1个请求。 还有一个称为“突发”的参数，它与速率限制一起定义，它定义了用户可以在超过指定速率（在本例中为600RPM）的情况下发出多少请求。 例如，如果Burst参数为10，则意味着一个队列中最多会分配10个插槽，当请求“太快”（在本例中是早于100毫秒）到达时，如果队列中有可用于该请求的插槽，则会立即处理该请求。 该插槽随后被标记为“已占用”，并且在经过适当的时间之前（在本例中为100毫秒之后）不会被释放以供另一请求使用。 现实世界的流量通常具有突发性，这就是Burst参数所起作用的地方。 对于Learning Manager平台，我们为特定API版本（例如V2）、角色（学习者/管理员）和谓词(GET/PUT/POST/DELETE/PATCH)定义了限制。 在上面的示例中，我们假设速率限制为(600， 10)。

尽管我们一直对Learning Manager中的公共API设置速率限制，但到目前为止，我们在允许使用非常高的RPM方面表现得相当自由。 然而，随着您首选的学习平台的增长，我们API的使用出现了快速增长，为了所有客户的利益以及更好地管理平台，我们决定明确记录这些速率限制。 在这种情况下，我们已升级API，以开始返回新的API响应（HTTP状态代码429）；您尚未看到该响应。 当超出速率限制时，会向API客户端提供此响应。 客户端应用程序现在需要处理这个符合其应用程序逻辑的响应代码；本文档的主要目的是帮助开发人员提供必要的信息，以便在他们看到这样的响应时在其代码中加入正确的逻辑。

## 如何确认强制的速率限制？ {#howtoconfirmtheenforcedratelimits}

对于每个请求，响应标头都包含以下信息：

```
x-rate-limit: 600r/m 
x-burst: 10
```

* x-rate-limit以每分钟请求数为单位指定基本请求速率阈值。
* x-burst指定接受多少个超过基本请求速率的请求才能立即处理。

## 如何捕获由速率限制导致的错误？ {#howtocatcherrorscausedbyratelimits}

对于每个请求，您可以检查是否触及了速率限制。 如果您收到响应代码429“{&quot;message&quot;：&quot;429 Too many requests&quot;}”，则您已达到速率限制。

最好在捕获429响应的脚本中包含代码。 如果脚本忽略“请求过多”错误并继续尝试发出请求，则可能会开始收到空错误。 此时，错误信息对诊断问题将没有帮助。

例如，遇到速率限制的curl请求可能会返回以下响应：

```
< HTTP/2 429 
< date: Wed, 04 Nov 2020 06:53:04 GMT 
< content-type: application/json; charset=utf-8 
< server: openresty 
< x-rate-limit: 60r/m 
< x-burst: 10 
< retry-after: 10.752 
< access-control-allow-credentials: true 
< access-control-allow-methods: GET, POST, OPTIONS, PUT, HEAD, DELETE, PATCH 
< access-control-allow-headers: X-acap-all-roles, X-acap-account,X-acap-user,X-acap-caller-role,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type, x-experience-api-version, Authorization, X-CSRF-TOKEN, X-HTTP-Method-Override 
< strict-transport-security: max-age=31536000; includeSubDomains 
< x-frame-options: SAMEORIGIN 
< x-xss-protection: 1 
< x-content-type-options: nosniff 
< x-request-id: gwBBFC9741-58A5-43B1-B1FE-7D14275961E7 
< strict-transport-security: max-age=31536000; includeSubDomains
```

响应包含有关以下键的信息：

```
status: 429 
retry-after: 10.752
```

状态代码429表示“请求过多”，当前请求不会被处理。 retry-after标头指定您可以在10.752秒后重试API调用。 在经过足够的时间重试之前，您的代码应停止发出其他API请求。

以下伪代码显示了捕获速率限制错误的简单方法：

```
response = request.get(url) 
if response.status equals 429: 
    alert('Rate limited. Waiting to retry…') 
    wait(response.retry-after) 
    retry(url)
```

事实上，我们甚至创建了一个Learning Manager虚拟API，供您尽情使用并轻松处理429状态代码。

```
curl -X GET --header 'Accept: application/json' --header 'Authorization: oauth < 
<token>
  >' 'https://learningmanager.adobe.com/learningmanagerapi/v2/dummy 
</token>
```

此虚拟API的限制为：

```
x-rate-limit: 5r/m 
x-burst: 2
```

虚拟API的限制有意地较低，因此您很快就会触及速率限制，从而可集中更多精力开发代码以捕获和处理速率限制错误。

## 测试虚拟API {#testingthedummyapi}

我们提供了一个端点，供您查看速率限制的工作方式。 为此，我们创建了一个名为GET/dummy的特殊端点，它具有学习者读取范围。 此API已特意配置为使用非常严格的速率限制，即每分钟5个请求，突发限制= 2。

您可以利用低于5 RPM和高于5 RPM的速率在此端点轻松测试这一点。 根据响应标头中的信息，编写代码以处理HTTPS状态代码429。

为了便于您查看，您可以查看说明此情况的示例JavaCript代码。 单击此 [小提琴](https://jsfiddle.net/ACAPJS/9yv8zcmL/) 并查看实际操作代码。

此应用程序要求您为帐户提供学习者角色应用程序令牌。 请参阅 [Application Developer手册](https://captivateLearning Manager.adobe.com/docs/Learning Managerapi/v2/)，了解有关API令牌的信息，您可以使用Learning Manager集成管理员应用程序的“开发人员资源”部分中的令牌帮助程序生成令牌。

此应用程序正在一次性循环对虚拟API进行10次调用。 由于虚拟API的速率限制为(5， 2)，因此Learning Manager收到的前5+2个调用成功后，即会超出速率限制，您会看到相应的成功响应。

但是，请注意此应用程序在响应中如何查找429状态代码以及如何处理它们。 当此应用程序收到此类响应时，将在API响应中打印详细信息、等待建议的时间量并重试失败的尝试。

## 处理速率限制的最佳做法 {#bestpracticestohandleratelimiting}

很多时候，帐户中的数据不会经常更改。 例如，帐户中的课程可能不会经常更改。 与其每次都尝试获取所有数据，不如在需要时查看能否获取特定数据，并考虑使用缓存机制。 这样，当您的应用程序确实需要发出多次调用时，您就可以在费率限制范围内拥有足够的配额来发出这些重要调用。

某些数据可能更改更频繁，因此您可能需要更频繁地获取这些数据。 即使这样，请问您自己的应用程序是否能够承受稍有过时的数据量（缓存中可能包含一些数据，您几分钟前已获取），因为它可能与用户的工作流程无关。 即使您必须从服务器获取新的数据，也可以明智地只获取您需要的特定数据，而不是获取所有数据。

有时，由于API可能不够灵活，无法仅通过一次调用就为您提供所需的数据，因此您无法选择获取大量数据。 查看API是否为您提供了筛选器和排序标准，以便您可以最大限度地减少调用次数；您仍应考虑缓存，因为您帐户中的许多用户可能需要相同的数据。

如果您在使用GUI的交互式应用程序环境中获取的数据过多，则可能是应用程序尝试执行的操作过多，并且可能会使用户不堪重负，同时还会出现大量影响应用程序用户体验的信息/功能。

在构建非交互式应用程序（可能类似于日常作业）时，您可能需要批量获取大量数据。 在此类情况下，请考虑使用主要旨在以CSV格式返回批量数据的作业API。 请注意，作业API将有一个配额约束，您可以每天调用N次。

由于Learning Manager已实施JSONAPI规范，因此您也可以在API中旁加载一些数据。 这将帮助您节省进行其他API调用的时间，但您必须避免过于急切地获取数据。 由于旁加载的数据有时可能非常大，因此在API分页调用中，最大页面大小限制为10；但对于不包含在内的API调用，您可以指定较大的页面大小（最多100）

最终，如果您在短时间内发出大量API请求，则将超出请求的API速率限制。 达到此限制后，Learning Manager将停止处理任何其他请求，直到超过特定时间量为止。

本文的最后一节概述了速率限制。 建议您熟悉限制。

## V2 API端点的速率限制 {#ratelimitsforv2apiendpoints}

下表提供了各个V2端点的限制。 目前，费率限制并未针对客户实施，但这些限制将从DD/MM/YYYY强制实施。 因此，客户必须查看其现有应用程序的代码，了解如何调整代码以了解这些速率限制，以及如何使用HTTP状态代码429处理API响应。

<table> 
 <tbody>
  <tr> 
   <td><p><b>操作</b></p></td> 
   <td><p><b>管理员API</b></p></td> 
   <td><p><b>学习者 API</b></p></td> 
  </tr> 
  <tr> 
   <td><p>DELETE</p></td> 
   <td><p>(25， 10) <br></p></td> 
   <td><p>(20， 10)<br></p></td> 
  </tr> 
  <tr> 
   <td><p>PATCH</p></td> 
   <td><p>(60, 20)</p></td> 
   <td><p>(15， 5) <br></p></td> 
  </tr> 
  <tr> 
   <td><p>POST</p></td> 
   <td><p>(30， 10)<br></p></td> 
   <td><p>(30， 10)<br></p></td> 
  </tr> 
  <tr> 
   <td><p>PUT</p></td> 
   <td><p>(20， 10)<br></p></td> 
   <td><p>(20， 10)<br></p></td> 
  </tr> 
  <tr> 
   <td><p>GET</p></td> 
   <td><p>(100， 100)<br></p></td> 
   <td><p>(100， 30)<br></p></td> 
  </tr> 
 </tbody>
</table>

