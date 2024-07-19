---
jcr-language: en_us
title: Adobe Learning Manager中的API弃用
description: 随着Adobe Learning Manager中API的发展，API会定期进行重新组织或升级。 当API不断发展变化时，旧版API会遭到弃用并最终被删除。 本页包含从已弃用的API版本迁移到更新且更稳定的API版本时需要了解的信息。
contentowner: saghosh
exl-id: 0fe9a3cb-9114-42d6-81ae-1a4f28c984fa
source-git-commit: 670d0477b246af2a0257e41eca799817e391b348
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 32%

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

由于偏移值检索的记录数量过多并且降低了整体性能，因此我们强制实施了&#x200B;**500**&#x200B;条记录的限制。 在下一个版本中，管理员和学习者的&#x200B;**GET用户** API最多可返回&#x200B;**500**&#x200B;条记录。

如果需要获取更多记录，请使用&#x200B;**GET作业** API。

<!--### Exclude paths 

At present, Learning Manager APIs follow a graph data structure, which allows you to fetch data by traversing the API model through includes. Even though you could traverse an API up to seven levels, fetching the data using a single API call is computationally expensive. 

We recommend that all existing and new customers make small calls multiple times instead of one large call. This approach will prevent unwanted data from being loaded in the call. 

We want to enforce these restrictions on new accounts and maintain a whitelist of existing accounts.-->

#### 已弃用的路径

以下路径已弃用：

* /learningObjects
   * 已弃用的路径：
      * enrollment.loInstance.loResources.resources
      * instances.loResources.resources
   * 新路径：
      * enrollment.loInstance.loResources
      * instances.loResources

* /learningObjects/{id}
   * 已弃用的路径：
      * enrollment.instances.subLoInstances.learningObject
   * 新路径：
      * enrollment.instances.subLoInstances

* /enrollments
   * 已弃用的路径：
      * loInstance.learningObject.enrollment
   * 新路径：
      * loInstance.learningObject

* /learningObjects/{id}
   * 已弃用的路径：
      * instance.subLoInstances.learningObject.enrollment.loResourceGrades
   * 新路径：
      * instance.subLoInstances

<!--### Instance summary count changes 

Currently, in the LO summary endpoint, you fetch the number of all possible instances. For example, for a course, you can view the number of enrollments and waitlists in the response for **GET /learningObjects/{loId}/instances/{loInstanceId}/summary**. You can then view the completionCount and enrollmentCount in the response. If the course is a VC or classroom, you can also view its seat limit and waitlist limit. 

The process of retrieving the completion and enrollment counts is computationally expensive, therefore the calculation is done on a request basis. If the data is not present in the cache, the data is reloaded, which is computationally intensive. If there are many users enrolling in a course, the counts will be large, and effectively impacts CPU performance. 

In the next release of Adobe Learning Manager, in the LO Instance summary endpoint, the completionCount, enrollmentCount, seatLimit, and waitlistCount are cached. The cached information persists till there are changes in enrollments or unenrollments. For counts exceeding 1000 enrollments, we'll assume the estimated counts, and invalidate the results for all existing and new accounts.

>[!NOTE]
>
>For counts, such as, completionCount, enrollmentCount, seatLimit, and waitlistCount exceeding1000, it's advisable to interpret them as estimates rather than precise figures, as these will be retrieved from cache.-->

### 按名称排序

在Adobe Learning Manager的下一个版本中，以下API的排序字段中的name和 — name已弃用：

* /userGroups/{userGroupId}/usersGET
* GET/users

>[!NOTE]
>
>对于所有现有帐户和新帐户，不再支持按名称和 — name排序。


## Adobe Learning Manager 2023年11月版中的API弃用

### 覆盖标志

在2023年11月版Adobe Learning Manager中，我们已停止使用API中的override标志。 覆盖标志不是公共 API 规范的一部分，旨在用于后端测试。 现已停止为学习者 API 应用该标志。 但是，该标记对管理员 API 仍然有效。

我们之所以弃用“学习者API”旗标，是因为覆盖旗标正通过“学习者API”获取大量数据。

今后，以下学习者 API 将停止运行，因为这些 API 具有覆盖标志。

_/primeapi/v2/users？page[offset]=0&amp;page[limit]=10&amp;sort=id&amp;override=TRUE_

### 针对基于技能的新建议的API更改

Adobe Learning Manager 改进了对支持客户和合作伙伴的帐户的建议。 推荐算法的改进以及课程、学习路径和认证排名算法的变化为内容发现提供了更好的用户体验。

该算法将不再支持基于同行的建议。 这一更改不会影响现有用户，但“业界公认”选项将继续存在。 对于“自定义”选项，Adobe Learning Manager 将不再支持基于同行的自定义选择。

配对组现在已成为帐户，学习者将看到一个显示组内趋势主题的字符串。 所有建议都附有说明。 例如，如果您正在查看有关某个主题的内容，信息条上的信息卡将显示建议该课程的原因。

### 通知公告变更报告

在Adobe Learning Manager的早期版本中，“通知公告”报告没有任何过滤器。 Adobe Learning Manager 已下载帐户中的所有通知。

在2023年11月版中，我们添加了一个日期过滤器，您可以使用该过滤器在指定时间段内下载通知。  但是，您只能下载最近六个月的报告。

### GET/users终结点中的高偏移值已弃用

为了提高Adobe性能并更有效地管理资源利用率，**管理员**&#x200B;和&#x200B;**学习者**&#x200B;作用域的GET/users端点中均弃用了高偏移值。 我们建议使用&#x200B;**作业API**&#x200B;检索具有偏移值的记录。

