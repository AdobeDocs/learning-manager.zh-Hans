---
jcr-language: en_us
title: Adobe Learning Manager 中的 API 弃用
description: 随着 Adobe Learning Manager 中 API 的发展，API 会定期重组或升级。 当 API 发展时，旧的 API 将被弃用并最终被删除。 此页面包含从已弃用的 API 版本迁移到更新、更稳定的 API 版本时需要了解的信息。
contentowner: saghosh
source-git-commit: 01cdcd816fe101af55adf0902f4e3660a1a098ce
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 21%

---


# Adobe Learning Manager 中的 API 弃用和更改

## API在AdobeLearning Manager 2024年3月版中的弃用功能

<!-- ### Changes in Rate Limits

With the next release of Adobe Learning Manager, we're restructuring API rate limits for new accounts. For existing accounts, only the Admin APIs will be rate-limited. After 90 days (about 3 months), we will restructure rate limits for all APIs, but existing accounts will be whitelisted according to current usage. Existing accounts need to revisit their learner API usage. 

For new accounts, if they want to increase the rate limits, they must contact the Customer Success team of ALM. 

#### Which APIs will be rate limited 

For new accounts, all Admin, Learner, and Search APIs will have rate limits and burst enforced.  

The API burst rate or burst limit refers to the maximum number of requests allowed to be made to an API in a short burst within a limited timeframe. 

The following table lists the rate and burst limits for the APIs.

<table>
    <tr>
        <th>API</th>
        <th>Number of requests-RPM</th>
        <th>Number of requests-Burst</th>
    </tr>
    <tr>
        <td>Admin</td>
        <td>5</td>
        <td>5</td>
    </tr>
    <tr>
        <td>Learner</td>
        <td>20</td>
        <td>5</td>
    </tr>
    <tr>
        <td>Search</td>
        <td>50</td>
        <td>5</td>
    </tr>
</table>
-->

### 对偏移限制的更改

由于偏移值检索了大量记录并降低了整体性能，因此我们强制实施了 500 **条记录的限制**。在下一版本中，对于管理员和学习者， **GET 用户** API 最多 **将返回 500** 条记录。

如果需要获取更多记录，请使用 **GET 作业** API。

抵消限制的更改适用于所有新客户。 对于现有客户，适用 90 天规则。

### 排除路径

目前，Learning Manager API遵循图形数据结构，允许您通过遍历include的API模型来获取数据。 即使您最多可以跨越7个级别的API，使用单个API调用获取数据在计算上仍然非常昂贵。

我们建议所有现有客户和新客户多次发起小型呼叫，而不是一次大型呼叫。 此方法将防止在调用中加载不需要的数据。

我们希望对新帐户执行这些限制，并保留现有帐户的白名单。

#### 已弃用的路径

以下路径已弃用：

* /learningObjects
   * 已弃用的路径：
      * enrollment.loInstance.loResources.resources
      * instances.loResources.resources
   * 新路径：
      * enrollment.loInstance.loResources
      * instances.loResources

* /learningObject/{id}
   * 已弃用的路径：
      * enrollment.instances.subLoInstances.learningObject
   * 新路径：
      * enrollment.instances.subLoInstances

* /入学 人数
   * 弃用路径：
      * loInstance.learningObject.enrollment
   * 新路径：
      * loInstance.learningObject

* /learningObject/{id}
   * 已弃用的路径：
      * instance.subLoInstances.learningObject.enrollment.loResourceGrades
   * 新路径：
      * instance.subLoInstances

### 实例汇总计数更改

目前，在学习对象摘要端点中，您将获取所有可能实例的数量。 例如，对于某个课程，您可以在响应中查看注册和轮候表的数目， **GET/learningObjects/{loId}/instances/{loInstanceId}/summary**. 然后，您可以在响应中查看completionCount和enrollmentCount。 如果课程是虚拟教室或教室，您还可以查看其名额限制和轮候表限制。

检索完成和注册计数的过程计算上很昂贵，因此计算是在请求的基础上进行的。 如果缓存中不存在数据，则会重新加载数据，这会占用大量计算。 如果注册了某个课程的用户很多，则计数将会很大，并且会切实影响 CPU 性能。

在下一版本的 Adobe Learning Manager 的 LO 实例摘要端点中，将缓存 completionCount、enrollmentCount、seatLimit 和 waitlistCount。 缓存的信息将一直保留到注册或取消注册发生更改为止。 对于超过1000个注册的帐户，我们将假定这些估计帐户，并使所有现有帐户和新帐户的结果无效。

>[!NOTE]
>
>对于超过1000的计数，建议将其解释为估计值而不是精确的数字，因为这些将从缓存中检索。

### 按名称排序

在下一版本的 Adobe Learning Manager 中，以下 API 的排序字段中弃用了 name 和 –name：

* GET/userGroups/{userGroupId}/users
* GET/users

>[!NOTE]
>
>对于所有现有帐户和新帐户，不再支持按名称和 — name排序。


## API在AdobeLearning Manager 2023年11月版中的弃用功能

### 覆盖标志

在2023年11月版AdobeLearning Manager中，我们已停用API的覆盖标志。 覆盖标志不是公共 API 规范的一部分，旨在用于后端测试。 现已停止为学习者 API 应用该标志。 但是，该标记对管理员 API 仍然有效。

我们之所以弃用“学习者API”旗标，是因为覆盖旗标正通过“学习者API”获取大量数据。

今后，以下学习者 API 将停止运行，因为这些 API 具有覆盖标志。

_/primeapi/v2/users？page[偏移]=0&amp;page[限制]=10&amp;sort=id&amp;override=TRUE_

### 基于技能的新建议的 API 更改

Adobe Learning Manager 改进了对支持客户和合作伙伴的帐户的建议。 推荐算法的改进以及课程、学习路径和认证排名算法的变化为内容发现提供了更好的用户体验。

该算法将不再支持基于同行的建议。 这一更改不会影响现有用户，但“业界公认”选项将继续存在。 对于“自定义”选项，Adobe Learning Manager 将不再支持基于同行的自定义选择。

配对组现在已成为帐户，学习者将看到一个显示组内趋势主题的字符串。 所有建议都附有说明。 例如，如果您正在查看有关某个主题的内容，信息条上的信息卡将显示建议该课程的原因。

### 通知公告报告的变化

在早期版本的 Adobe Learning Manager 中，通知通知报告没有任何过滤器。 Adobe Learning Manager 已下载帐户中的所有通知。

在 2023 年 11 月版本中，我们添加了一个日期筛选器，您可以使用该筛选器在指定时间段内下载通知。  但是，您只能下载过去六个月的报告。