---
jcr-language: en_us
title: AdobeLearning Manager中的API弃用
description: 随着AdobeLearning Manager中API的发展，API会定期进行重组或升级。 当API不断发展变化时，旧版API会遭到弃用并最终被删除。 本页包含从已弃用的API版本迁移到更新且更稳定的API版本时需要了解的信息。
contentowner: saghosh
source-git-commit: 83fdd06aed823a50458d50c8ac240d56af873a6d
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 0%

---


# AdobeLearning Manager中的API弃用

## API在AdobeLearning Manager 2024年3月版中的弃用功能

### 费率限制的更改

下一版AdobeLearning Manager将调整新客户的API速率限制。 对于现有帐户，仅管理员API将受费率限制。 90天（约3个月）后，我们将调整所有API的速率限制，但现有帐户将根据当前使用情况列入白名单。 现有帐户需要重新访问其学习者API使用情况。

对于新帐户，如果他们想要提高费率限制，则必须联系ALM的客户成功团队。

#### 哪些API将受限制

对于新帐户，所有管理员、学习者和搜索API都将实施速率限制和突发流量。

API突发速率或突发限制是指在有限的时间范围内允许以短突发对API发出的最大请求数。

下表列出了API的速率和突发限制。

<table>
    <tr>
        <th>API</th>
        <th>请求数 — RPM</th>
        <th>请求数 — 突发</th>
    </tr>
    <tr>
        <td>管理员</td>
        <td>5</td>
        <td>5</td>
    </tr>
    <tr>
        <td>学习者</td>
        <td>20</td>
        <td>5</td>
    </tr>
    <tr>
        <td>Search</td>
        <td>50</td>
        <td>5</td>
    </tr>
</table>

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

在下一版AdobeLearning Manager中，学习对象实例摘要端点会缓存completionCount、enrollmentCount、seatLimit和waitlistCount。 在注册或取消注册发生更改之前，缓存信息会一直保留。 对于超过1000个注册的帐户，我们将假定这些估计帐户，并使所有现有帐户和新帐户的结果无效。

>[!NOTE]
>
>对于超过1000的计数，建议将其解释为估计值而不是精确的数字，因为这些将从缓存中检索。

### 按名称排序

在AdobeLearning Manager的下一版本中，以下API的排序字段中的 — name已弃用：

* GET/userGroups/{userGroupId}/users
* GET/users

>[!NOTE]
>
>对于所有现有帐户和新帐户，不再支持按名称和 — name排序。


## API在AdobeLearning Manager 2023年11月版中的弃用功能

### 覆盖标志

在2023年11月版AdobeLearning Manager中，我们已停用API的覆盖标志。 覆盖标志不是公共API规范的一部分，用于后端测试。 该标志现停止用于学习者API。 但是，该标记对管理员API仍然有效。

我们之所以弃用“学习者API”旗标，是因为覆盖旗标正通过“学习者API”获取大量数据。

以后，以下学习者API将停止工作，因为它有覆盖标志。

<code>https://captivateprime.adobe.com/primeapi/v2/users?page[偏移]=0&amp;page[限制]=10&amp;sort=id&amp;override=TRUE</code>

### 针对基于技能的新建议的API更改

AdobeLearning Manager可改善针对启用客户和合作伙伴帐户的推荐。 这一改进在推荐算法上随着课程排名算法的变化，学习路径和认证方式的变化为内容发现提供了更好的用户体验。

算法将不再允许基于对等项的建议。 这一更改不会影响现有用户，但“业界公认”选项将继续存在。 对于“自定义”选项，AdobeLearning Manager将不再允许基于同事的自定义选择。

配对组现在已成为帐户，学习者将看到一个显示组中趋势主题的字符串。 所有建议都可作解释。 例如，如果您正在查看某个主题上的内容，信息条上的信息卡将显示该课程的原因。

### 通知公告变更报告

在早期版本的AdobeLearning Manager中，“通知公告”报告没有任何过滤器。 AdobeLearning Manager已下载帐户中的所有通知。

在2023年11月版中，我们添加了一个日期过滤器，您可以使用该过滤器在指定时间段内下载通知。  但是，您只能下载最近六个月的报告。