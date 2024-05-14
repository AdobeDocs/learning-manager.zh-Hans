---
jcr-language: en_us
title: Adobe Learning Manager中的API弃用
description: 随着Adobe Learning Manager中API的发展，API会定期进行重新组织或升级。 当API不断发展变化时，旧版API会遭到弃用并最终被删除。 本页包含从已弃用的API版本迁移到更新且更稳定的API版本时需要了解的信息。
contentowner: saghosh
exl-id: 0fe9a3cb-9114-42d6-81ae-1a4f28c984fa
source-git-commit: dd0b8aecbe54d6aecf17e4d9acec5769e7302ecd
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 20%

---

# Adobe Learning Manager中的API弃用和更改

## Adobe Learning Manager 2024年3月版中的API弃用

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

### 偏移限制的更改

由于偏移值检索到大量记录并减慢了整体性能，因此我们强制实施了 **500** 记录。 在下一版本中，管理员和学习者均 **GET用户** API最多可返回 **500** 记录。

如果需要获取更多记录，请使用 **GET职位** API。

对方限额之变动适用于所有新客户。 对于现有客户，适用90天规则。

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

* /enrollments
   * 已弃用的路径：
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

检索完成和注册计数的过程计算上很昂贵，因此计算是在请求的基础上进行的。 如果高速缓存中不存在数据，则会重新加载数据，这会占用大量计算资源。 如果课程中有许多用户注册，则课程数量会很大，并会对CPU性能产生有效影响。

在下一个版本的Adobe Learning Manager中，学习对象实例摘要端点中的completionCount、enrollmentCount、seatLimit和waitlistCount会进行缓存。 在注册或取消注册发生更改之前，缓存信息会一直保留。 对于超过1000个注册的帐户，我们将假定这些估计帐户，并使所有现有帐户和新帐户的结果无效。

>[!NOTE]
>
>对于超过1000的计数，建议将其解释为估计值而不是精确的数字，因为这些将从缓存中检索。

### 按名称排序

在Adobe Learning Manager的下一个版本中，以下API的排序字段中的name和 — name已弃用：

* GET/userGroups/{userGroupId}/users
* GET/users

>[!NOTE]
>
>对于所有现有帐户和新帐户，不再支持按名称和 — name排序。


## Adobe Learning Manager 2023年11月版中的API弃用

### 覆盖标志

在2023年11月版Adobe Learning Manager中，我们已停止使用API中的override标志。 覆盖标志不是公共 API 规范的一部分，旨在用于后端测试。 现已停止为学习者 API 应用该标志。 但是，该标记对管理员 API 仍然有效。

我们之所以弃用“学习者API”旗标，是因为覆盖旗标正通过“学习者API”获取大量数据。

今后，以下学习者 API 将停止运行，因为这些 API 具有覆盖标志。

_/primeapi/v2/users？page[偏移]=0&amp;page[限制]=10&amp;sort=id&amp;override=TRUE_

### 针对基于技能的新建议的API更改

Adobe Learning Manager 改进了对支持客户和合作伙伴的帐户的建议。 推荐算法的改进以及课程、学习路径和认证排名算法的变化为内容发现提供了更好的用户体验。

该算法将不再支持基于同行的建议。 这一更改不会影响现有用户，但“业界公认”选项将继续存在。 对于“自定义”选项，Adobe Learning Manager 将不再支持基于同行的自定义选择。

配对组现在已成为帐户，学习者将看到一个显示组内趋势主题的字符串。 所有建议都附有说明。 例如，如果您正在查看有关某个主题的内容，信息条上的信息卡将显示建议该课程的原因。

### 通知公告变更报告

在Adobe Learning Manager的早期版本中，“通知公告”报告没有任何过滤器。 Adobe Learning Manager 已下载帐户中的所有通知。

在2023年11月版中，我们添加了一个日期过滤器，您可以使用该过滤器在指定时间段内下载通知。  但是，您只能下载最近六个月的报告。

### GET/users终结点中的高偏移值已弃用

为了改进系统性能并更有效地管理资源利用率，Adobe在GET/users端点中为两者都弃用了高偏移值 **管理员** 和 **学习者** 范围。 我们建议使用 **作业API** 以检索具有偏移值的记录。

