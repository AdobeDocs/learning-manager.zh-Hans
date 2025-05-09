---
description: 了解 Adobe Learning Manager 应用程序中与管理员角色相关联的报告。
jcr-language: en_us
title: 报告
contentowner: manochan
exl-id: 31b176b7-4b8f-4851-a0c5-4eee58bceb41
source-git-commit: f6bc1fa9384fc728f6abca7bb0fd9f62bb1f9e04
workflow-type: tm+mt
source-wordcount: '7809'
ht-degree: 52%

---

# 报告

了解 Adobe Learning Manager 应用程序中与管理员角色相关联的报告。

Adobe Learning Manager 可让您创建各种报告来跟踪、监控和控制学习者活动。被跟踪的学习者活动会自动收集到数据库中。经理和管理员可从数据库生成报告。

## 概述 {#overview}

管理员和经理的报告生成过程相似。经理可以查看与其下属相对应的报告，而管理员可以查看整个公司范围的报告。

报告会汇总到信息板。报告必须位于信息板中。报告页面中默认存在&#x200B;**[!UICONTROL 默认仪表板]**。 您添加的任何报告都会移动到此默认信息板。要将报告添加到单个仪表板，请使用下拉箭头并选择&#x200B;**[!UICONTROL 添加报告]**。 有关创建信息板的更多信息，请参阅本页上的“信息板”部分。

## 报告类型 {#typesofreports}

Adobe Learning Manager 支持四种主要类型的报告，例如完成、花费的时间、技能和效果。您可以使用以下报告类型生成300多种变化的报告：

* 学习者的课程交付统计信息
* 课程效果报告
* 学习者技能报告
* 学习者的学习计划注册统计信息
* 学习者花费的学习时间
* 学习者计数
* 认证完成

## 用户活动信息板 {#useractivitydashboards}

查看一段时间内平台上所有用户活动的摘要。 配置用户组并应用过滤器。

用户活动信息板显示用户在帐户中的活动。 列出的三个报告为：

* **注册用户：**&#x200B;此报告提供每周在您的帐户中注册的用户数信息。 对于拥有月活跃单位许可的帐户，报告会转为显示 MAU 单位。

* **用户访问报告：**&#x200B;此报告提供有关每天访问平台的用户数量的信息。 您也可获取月度报告。

* **花费的学习时间报告：**&#x200B;此报告提供平台中每天花费的学习时间的信息。 您也可获取月度报告。

### 已注册的用户 {#registeredusers}

Adobe Learning Manager 记录每周在系统中注册的用户数。管理员可以查看此报告以了解一周中某日用户的注册数。 注册数一次存储一周，且不会更改。 因此，历史注册数与系统中的当前学习者群组无关。

此报告提供每周在您的帐户中注册的用户数信息。

对于拥有月活跃单位许可的帐户，报告会转为显示 MAU 单位。

![](assets/registered-usersreport.png)
*已注册用户报告*

***适用于月访问单位帐户：***

**月活跃用户报告**

此报告显示每月在学习平台中处于活跃状态的学员计数。 如果用户执行此处提到的任何学习操作，则该月内此用户会被视为活跃用户。 这与月活跃单位的计数方式相同。

月活跃计数按月计一次并会存储一个月，且不会更改。 因此，显示的历史计数与系统中当前的学习者群组无关。

### 用户访问 {#uservisits}

此报告显示一天或一个月内访问系统的学员总数。 仅浏览学习平台而不进行任何学习，也被视为对学习平台的一次“访问”。 这有助于管理员了解访问系统的用户总数。 在每月第一天，Adobe Learning Manager 会创建前一个月访问平台的用户总数记录。它还会捕获这些用户的用户组信息。

仅记录由管理员配置的用户组。 这还允许管理员对月度历史数据应用用户组过滤器。 请注意，如果修改了用户组配置，并且Learning Manager之前几个月未记录此用户组的数据，则Learning Manager将无法显示之前几个月新配置的用户组的数据。

此报告包含通过各种方式（如网页、移动应用程序、无头自定义解决方案等）访问平台的用户。 设备应用程序使用情况图表仅明确提到了使用 Adobe Learning Manager 的设备应用程序访问平台的用户。这有助于管理员识别其帐户中移动应用程序的使用情况。

![](assets/user-visit-report.png)
*用户访问报告*

### 学习时间花费报告 {#learningtimespentreport}

您可在此处查看双轴折线图，其中显示了所有学员在 12 个月内所花费的总学习时间。 第二个轴表示个人所花学习时间的中位数。

为不同学习对象（如学习计划和认证）花费的时间按以下项目计算：

* 包含静态和交互内容的自学课程。
* 使用URL的活动课程。
* 启用了周末旗标的周末课程。
* 自动标记出勤的 VC Connect 课程。
* 为不同学习对象（如学习计划和认证）花费的时间。
* xAPI语句，用于xAPI活动课程。

您可以进一步将图表导出为 Excel 电子表格。

系统提供了用于选择用户组配置的过滤器，该过滤器将有助于查看有关不同用户组的数据。

选定的日期和用户组过滤器将应用于信息板中的所有相关图表。

>[!NOTE]
>
>对于&#x200B;**[!UICONTROL “用户访问”]**&#x200B;和&#x200B;**[!UICONTROL “学习时间花费”]**&#x200B;报告，所显示的默认数据（未配置任何用户组时）将面向整个帐户。

## 培训内容信息板 {#trainingcontentdashboard}

培训内容信息板提供平台上可获取的培训的具体情况。 您可以查看热门培训或跟踪所有可获取的培训。

### 培训报告 {#trainingsreport}

此报告提供平台上每月可获取的培训（已发布状态）总数的信息。 它显示了平台在一段时间内提供的培训数量。

![](assets/training-report.png)
*培训报告*

### 有效培训报告 {#activetrainingsreport}

此报告提供在选定时间范围内有效的培训信息。 有效培训是指在指定时间内注册、通过播放器观看或已完成的培训。

对于有效培训，当未完成任何用户组配置时，您将可选取所有根用户（具有经理角色）内部组的数据。 除根用户用户组外，您还可视需要再配置 10 个用户组。

![](assets/active-trainingsreport.png)
*有效培训报告*

>[!NOTE]
>
>数据不会在您选择&#x200B;**[!UICONTROL 所有用户]**&#x200B;和&#x200B;**[!UICONTROL 12个月]**&#x200B;筛选器时按预期显示，而会在您选择&#x200B;**[!UICONTROL 所有内部用户组]时显示。**

<table>
 <tbody>
  <tr>
   <td>
    <p><b>参考</b></p></td>
   <td>
    <p><b>指标</b></p></td>
   <td>
    <p><b>描述</b></p></td>
  </tr>
  <tr>
   <td>
    <p>1</p></td>
   <td>
    <p>开始率 (%)</p></td>
   <td>
    <p>开始课程的学员人数与注册人数的比率。</p></td>
  </tr>
  <tr>
   <td>
    <p>2</p></td>
   <td>
    <p>完成率 (%)</p></td>
   <td>
    <p>完成课程的用户总数与开始课程的用户总数的比率。<br></p></td>
  </tr>
  <tr>
   <td>
    <p>3</p></td>
   <td>
    <p>学员反馈</p></td>
   <td>
    <p>在 1 到 10 的范围内，将收到的所有 L1 反馈响应的平均值四舍五入到最接近的整数。<br></p></td>
  </tr>
  <tr>
   <td>
    <p>4</p></td>
   <td>
    <p>经理反馈</p></td>
   <td>
    <p>在 1 到 5 的范围内，将收到的所有 L3 反馈响应的平均值四舍五入到最接近的整数<br></p></td>
  </tr>
 </tbody>
</table>

培训报告还附加了两栏：

1. 课程的平均星级评分。
1. 已对课程进行评级的学习者数。
1. 嵌入式路径
1. 嵌入式路径 ID
1. 嵌入式课程 ID

>[!NOTE]
>
>“开始率”、“完成率”、“学员反馈”和“经理反馈”不受所应用的过滤器的影响。 过滤器仅影响注册数、查看次数和完成数。

>[!NOTE]
>
>您可以为培训内容和用户活动这两份报告最多配置 10 个用户组。 系统最长可能需要 24 小时才能完成处理过程并使新配置的过滤器可供使用。

## 学习摘要信息板 {#dashboards}

### 生成信息板报告

>[!INFO]
>
>在本培训中，您将了解如何从数据库生成信息板报告。<br><br>[![按钮](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/8318854)</br></br>


如果您无法启动培训，请写入<almacademy@adobe.com>。

查看平台中所有学习活动的摘要报告。 在此页面上，您可以看到所选root用户的团队和外部配置文件的以下摘要信息。 还可以选择时间范围：

* 以注册数、查看次数和完成数的形式展示的学习摘要
* 顶级技能
* 合规性摘要

![](assets/summary-charts.png)
*摘要图表*

如果有内部根级别经理，则他们将会依次显示。

所有外部配置文件将列在内部配置文件（内部根级别用户）之后。

如果外部配置文件中有经理，则经理层次结构将显示在&#x200B;**[!UICONTROL 显示]**&#x200B;的数据下拉列表中。 用户将在所有详细信息页面（学习摘要、合规性和技能状态）的经理层次结构中列出

否则，列表中将显示所有单个用户的详细信息。

如要查看各种内部团队的更精细的注册详情，请单击&#x200B;**[!UICONTROL “学习摘要详情”]**。

![](assets/learning-sunnarydetails.png)
*学习摘要详细信息*

单击任何注册时，您都可以看到每个经理的学习者以及他们注册的学习对象。 您还可以查看每个学习者的进度及完成情况的详细信息。

![](assets/learners-for-a-manager.png)
*分配给经理的学习者*

单击任意团队并将其报告导出为 csv 文件。 管理员可以通过选择用户组或单个用户导出任何用户组或单个用户的报告，然后从&#x200B;**[!UICONTROL 操作]**&#x200B;下拉列表中导出详细信息。

此外，您还可以看到正在进行和已习得的技能的条形图视图。 您可以添加/删除要在图表中显示的技能。

![](assets/skill-status-stackedbarchart.png)
*技能状态栈叠条形图*

### 合规性信息板

**Adobe Learning Manager**&#x200B;为所有管理员和经理提供合规性信息板。 管理员可以创建合规性信息板并与经理共享。 经理将能够查看其应用程序上新共享的信息板，并轻松跟踪其团队成员在特定培训中的合规性。 合规性信息板允许管理员将自定义合规性课程分类为特定类别（例如，销售、营销和法律领域）。 自定义合规性类别由&#x200B;**[!UICONTROL 目录标签]**&#x200B;提供支持。

![](assets/compliance-dashboard-admin.png)

_合规性信息板 — 管理员视图_

管理员还可以通过选择&#x200B;**[!UICONTROL 转到合规性信息板]**&#x200B;来检查每个经理团队的合规性状态。 管理员可以单独与经理或与组共享一组培训课程。 这有助于经理轻松跟踪其队友在指定培训中的合规性。

#### 管理员工作流程

##### 创建自定义合规性标签

合规性标签是一种目录标签，将课程/学习路径/认证归类为合规性类型。
要创建自定义合规性标签，请执行以下步骤：

1. 在管理员应用中，转到&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 常规]**。
1. 选择&#x200B;**[!UICONTROL 自定义合规性类型]**&#x200B;选项以启用自定义合规性标签。


   ![](assets/custom-compliance.png)
   _启用自定义合规性_

   >[!NOTE]
   >
   >引入了此新目录标签，将课程、学习路径和认证归类为合规性类型。 要启用&#x200B;**[!UICONTROL 自定义合规性类型]**&#x200B;选项，必须首先在同一页面启用&#x200B;**[!UICONTROL 显示目录标签]**&#x200B;选项。

1. 转到&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 目录标签]**&#x200B;并选择&#x200B;**[!UICONTROL 合规性类型]**。
1. 在&#x200B;**[!UICONTROL 值]**&#x200B;文本框中键入值（例如，Legal、Sales），然后选择&#x200B;**[!UICONTROL 添加值]**。

   ![](assets/custom-compliance-values.png)
   _添加自定义合规性的值_

1. 选择&#x200B;**[!UICONTROL “保存”]**。

>[!NOTE]
>
>作者必须在其应用程序中创建/编辑课程时添加这些合规性标签。 请参阅[将合规性标签添加到课程/学习路径/认证](/help/migrated/authors/feature-summary/courses.md#add-compliance-labels-to-courselearning-pathcertification)。

##### 创建和共享合规性信息板

要创建和共享合规性信息板，请执行以下步骤：

1. 转到&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 学习摘要]**。
1. 在&#x200B;**[!UICONTROL 合规性信息板]**&#x200B;部分，选择&#x200B;**[!UICONTROL 与经理共享]**。
1. 选择&#x200B;**[!UICONTROL 共享仪表板]**，然后从&#x200B;**[!UICONTROL 选择合规性标签]**&#x200B;下拉菜单中选择创建的标签。


   ![](assets/compliance-type.png)
   _选择合规性类型_

1. 在&#x200B;**[!UICONTROL 与]**&#x200B;共享文本框中键入并选择经理的姓名。
1. 选择&#x200B;**[!UICONTROL 共享]**&#x200B;以将仪表板发送给所选经理。

>[!NOTE]
>
>共享新仪表板将覆盖所选经理的应用程序中的现有仪表板。 经理将能够查看管理员新共享的信息板。

#### 与管理员和自定义管理员共享合规性信息板

管理员可以与其他管理员和自定义管理员共享信息板，使其能够即时访问所有合规性信息板。

按照以下步骤与管理员和自定义管理员共享信息板：

1. 以&#x200B;**[!UICONTROL 管理员]**&#x200B;身份登录。
2. 导航至&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 学习摘要]**。
3. 在&#x200B;**[!UICONTROL 合规性信息板]**&#x200B;部分选择&#x200B;**[!UICONTROL 管理员视图]**。
4. 选择&#x200B;**[!UICONTROL 共享仪表板]**&#x200B;按钮。

   ![](assets/share-dashboard.png)
   _共享仪表板 — 管理员_

5. 从&#x200B;**[!UICONTROL 选择自定义合规性]**&#x200B;下拉菜单中选择合规性标签。 此选项将选择具有选定合规性标签的所有课程。
6. 选择要与管理员共享的其他课程、学习路径或认证。

   ![](assets/share-button.png)
   _共享合规性信息板_

7. 选择要共享仪表板的用户或用户组，然后选择&#x200B;**[!UICONTROL 共享]**。

##### 查看合规性信息板 — 自定义管理员和其他管理员

所选用户组中的所有自定义管理员和其他管理员都可以在其应用程序上看到合规性信息板。

请按照以下步骤查看合规性信息板：

1. 导航至&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 学习摘要]** > **[!UICONTROL 合规性信息板]**。
2. 在&#x200B;**[!UICONTROL 合规性信息板]**&#x200B;部分选择&#x200B;**[!UICONTROL 您的视图]**。
3. 选择&#x200B;**[!UICONTROL 转到合规性信息板]**&#x200B;选项，您将看到管理员共享的新合规性信息板。

   ![](assets/compliance-custom-view.png)
   _查看合规性信息板 — 自定义管理员_

#### 与商店经理共享

管理员可以与商店经理共享合规性信息板，以便他们监控学习者的合规性进度。

请按照以下步骤与商店经理共享信息板：

1. 以&#x200B;**[!UICONTROL 管理员]**&#x200B;身份登录。
2. 导航至&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 学习摘要]** > **[!UICONTROL 合规性信息板]**。
3. 在&#x200B;**[!UICONTROL 合规性仪表板]**&#x200B;部分中选择&#x200B;**[!UICONTROL 经理视图]**。
4. 选择&#x200B;**[!UICONTROL 共享仪表板]**&#x200B;按钮。

   ![](assets/share-manager.png)
   _与经理共享合规性信息板_

5. 从&#x200B;**[!UICONTROL 选择自定义合规性]**&#x200B;下拉菜单中选择合规性标签。
此选项将选择具有选定合规性标签的所有课程。
6. 选择要与管理员共享的其他课程、学习路径或认证。
7. 选择要共享仪表板的用户或用户组，然后选择&#x200B;**[!UICONTROL 共享]**。

##### 查看合规性信息板 — 经理

有关详细信息，请参阅此文章[查看合规性仪表板](/help/migrated/managers/feature-summary/manager-dashboard.md#view-the-dashboard)。

#### 编辑仪表板

执行以下步骤可编辑合规性信息板：

1. 以&#x200B;**[!UICONTROL 管理员]**&#x200B;身份登录。
2. 导航至&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 学习摘要]** > **[!UICONTROL 合规性信息板]**。
3. 在&#x200B;**[!UICONTROL 合规性信息板]**&#x200B;部分中选择&#x200B;**[!UICONTROL 管理员视图]**&#x200B;或&#x200B;**[!UICONTROL 经理视图]**。 您可以在此部分中查看合规性信息板。
4. 在要编辑的合规性仪表板上，选择&#x200B;**[!UICONTROL 编辑]**。

   ![](assets/edit.png)
   _编辑合规性信息板_

5. 更改所需的详细信息，然后选择&#x200B;**[!UICONTROL 共享]**。
6. 合规性信息板将与所选经理共享。

#### 退出仪表板 — 管理员

按照以下步骤退出合规性信息板：

1. 以&#x200B;**[!UICONTROL 管理员]**&#x200B;身份登录。
2. 导航至&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 学习摘要]** > **[!UICONTROL 合规性信息板]**。
3. 在&#x200B;**[!UICONTROL 合规性信息板]**&#x200B;部分中选择&#x200B;**[!UICONTROL 管理员视图]**&#x200B;或&#x200B;**[!UICONTROL 经理视图]**。 您可以在此部分中查看合规性信息板。
4. 在要删除的合规性信息板中选择&#x200B;**[!UICONTROL 撤消]**，然后选择&#x200B;**[!UICONTROL 继续]**。
5. 此操作将从经理的应用程序中删除共享合规性信息板。

   ![](assets/manager-edit.png)
   _退出合规性信息板_

#### 为学习者设置默认合规性构件

请按照以下步骤为学习者设置默认合规性小组件：

1. 以&#x200B;**[!UICONTROL 管理员]**&#x200B;身份登录。
2. 导航至&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 学习摘要]** > **[!UICONTROL 合规性信息板]**。
3. 在&#x200B;**[!UICONTROL 合规性信息板]**&#x200B;部分选择&#x200B;**[!UICONTROL 学习者视图]**。
4. 在&#x200B;**[!UICONTROL 学习者视图]**&#x200B;部分中选择&#x200B;**[!UICONTROL 更改]**。

   ![](assets/learner-widget.png)
   _为学习者设置默认合规性小组件_
5. 从&#x200B;**[!UICONTROL 自定义合规性]**&#x200B;下拉菜单中选择合规性标签。 此选项将选择具有选定合规性标签的所有课程。
6. 选择“**[!UICONTROL 继续]**”以设置默认合规性构件。

学习者可以在主页上的合规性小组件上查看所选课程或学习路径。 有关详细信息，请参阅[合规性仪表板小组件](/help/migrated/learners/feature-summary/learner-home-page.md#compliance-dashboard-widget)。

## 自定义报告

管理员可以使用&#x200B;**[!UICONTROL 报告]**&#x200B;部分中提供的自定义模板生成特定报告。

### 示例报告 {#samplereports}

**[!UICONTROL “示例报告”]**&#x200B;选项卡用于显示基于示例数据点的部分参考性报告。浏览这些报告以了解使用帐户数据可以生成哪些不同类型的丰富报告。

### 信息板报告 {#dashboardreports}

信息板为报告合集。您可以根据自己的选择将报告分组到信息板。 要查看您创建的所有讨论区，请单击此讨论区选项卡。 从&#x200B;**[!UICONTROL 查看仪表板]**&#x200B;下拉列表中，可以选择默认主板或您创建的仪表板。

### Excel 报告 {#excelreports}

可通过&#x200B;**[!UICONTROL “Excel 报告”]**&#x200B;选项卡导出 XLS 文件格式的报告。

以下是可供下载的报告类型。

* 课程报告
* 学习者成绩单
* 公告报告
* 工作辅助报告
* 内容审查追踪
* 用户审查追踪
* 登录/访问报告
* 游戏成绩单
* 游戏审查追踪

### 课程报告 {#coursereports}

管理员可下载课程报告。请执行以下步骤：

1. 打开&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]** > **[!UICONTROL Excel报告]** > **[!UICONTROL 课程报告]**。
1. 此时会显示&#x200B;**[!UICONTROL “课程报告”]**&#x200B;对话框。选择要提取报告的课程，然后单击&#x200B;**[!UICONTROL “显示”]**。

   ![](assets/course-reports.png)
   *课程报告*

1. 您会被重定向到课程页面。通过选择特定的注册类型，您可以根据每个注册按用户和问题导出测验分数。
1. 选择&#x200B;**[!UICONTROL “导出测验分数”]**&#x200B;以导出报告。此时会显示&#x200B;**[!UICONTROL “生成报告请求”]**&#x200B;对话框。单击&#x200B;**[!UICONTROL “确定”]**&#x200B;以确认。

   ![](assets/generating-reportrequest.png)
   *正在生成报告请求*

   >[!NOTE]
   >
   >如果配置了模块的多次尝试选项，则导出的测验分数报告将包含每次尝试的分数详细信息。

### 生成课程报告

>[!INFO]
>
>在本培训中，您将了解如何导出课程报告并为这些报告设置电子邮件订阅。<br><br>[![按钮](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/8318904)</br></br>


如果您无法启动培训，请写入<almacademy@adobe.com>。

### 学习者成绩单 {#LearnerTranscripts-1}

公司的管理员可通过 Adobe Learning Manager 生成与学习者相关联的成绩单。学习者成绩单报告载有以下内容：

1. 学习者成绩单：学习活动信息板
1. 技能：技能信息板
1. 合规性信息板

Excel 报告中学习者成绩单的“必修积分”和“已修积分”列显示小数数值。

有关生成学习者成绩单报告等方面的信息，请参阅[学习者成绩单](learner-transcripts.md)。

### 公告报告 {#announcementsreports}

管理员可以为所有由其发送的公告生成报告。该报告的详细信息如下：

* 公告类型
* 公告名称
* 公告日期
* 公告状态
* 学习者姓名

要下载报告，请执行以下任一步骤：

1. 打开&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]** > **[!UICONTROL Excel报告]** > **[!UICONTROL 公告报告]**。 将打开&#x200B;**[!UICONTROL 生成报告请求]**&#x200B;对话框。 单击“确定”。
1. [!UICONTROL **公告**] > [!UICONTROL **操作**] > [!UICONTROL **导出报告**]。

   ![](assets/announcements.png)
   *公告报告*

1. 您可以单击设置图标下方的&#x200B;**[!UICONTROL 导出报告]**，为特定公告提取报告。

   ![](assets/announcements-specific-report.png)
   *报告特定公告*

### 工作辅助报告 {#jobaidsreport}

工作辅助是学习者无需注册任何学习对象（例如课程或学习计划）即可访问的培训内容。管理员可提取并下载工作辅助报告。

提取的报告包含有关以下内容的信息：

* 名称
* 工作辅助类型
* 工作辅助状态（“已发布”或“已撤消”）
* 注册日期
* 完成日期
* 下载日期
* 学习者姓名
* 经理姓名
* 创建人

要下载报告，执行以下任一操作：

* 打开&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]** > **[!UICONTROL Excel报告]** > **[!UICONTROL 工作辅助报告]**。 此时会显示&#x200B;**[!UICONTROL “生成报告请求”]**&#x200B;对话框。单击&#x200B;**[!UICONTROL “确定”]**。
* 打开&#x200B;**[!UICONTROL 工作辅助]** > **[!UICONTROL 操作]** > **[!UICONTROL 导出报告]**。

![](assets/job-aids.png)
*工作辅助报告*

* 还可通过单击设置图标下的&#x200B;**[!UICONTROL “导出报告”]**&#x200B;来提取特定工作辅助的报告。

![](assets/job-aid-specific-download.png)
*报告特定工作辅助*

### 工作辅助报告

在列表中选择&#x200B;**[!UICONTROL 工作辅助报告]**&#x200B;后，您会看到两个选项：

![工作辅助报告](assets/job-aids-new.png)
*下载工作辅助美国客服注册报告*

**所有工作辅助**：如果帐户中的工作辅助数量少于1,000万个，则生成的报告将包含所有工作辅助的注册信息。 这将是默认选择。 如果行数超过1,000万，则会显示错误，您必须手动选择所需的工作辅助。

**所选工作辅助**：如果选择此选项，您可以输入要为其生成报告的工作辅助。 您至多可以选择10个工作辅助。 Adobe Learning Manager会检查工作辅助的数量是否超过1,000万个。

![工作辅助报告注册](assets/job-aids-2-new.png)
*选择工作辅助*

**工作辅助报告**

如果选择此选项，则会下载系统中所有工作辅助的详细信息及其元数据和培训。

下载的报告包含以下字段：

* 工作辅助名称
* 语言
* ID
* 类型
* 持续时间（分钟）
* 状态
* 发布日期（UTC 时区）
* 按姓名创建
* 按电子邮件创建
* 按用户唯一 ID 创建
* 目录
* 学习路径
* 课程
* 标签
* 技能

**工作辅助用户注册报告**

注册报告包含用户注册详细信息以及其他信息。

下载的报告包含以下字段：

* 工作辅助名称
* 类型
* 状态
* 注册日期（UTC 时区）
* 完成日期（UTC时区）
* 下载日期（UTC时区）
* 学习者姓名
* 电子邮件
* 用户唯一 ID
* 经理姓名
* 经理电子邮件
* 经理用户唯一 ID
* 按姓名分配
* 按电子邮件分配
* 按用户唯一 ID 分配
* 按姓名创建
* 按电子邮件创建
* 按用户唯一 ID 创建
* 作业代码
* 新字段
* 配置文件

### 内容审查追踪报告 {#contentaudittrailreports}

使用&#x200B;**[!UICONTROL 内容审核追踪]**&#x200B;报告生成器可生成课程在系统中有效期内所做的所有更改和编辑的报告。 生成的报告提取了以下信息。

* 对象 ID
* 对象名称
* 对象类型
* 修改类型
* 描述
* 引用的对象 ID
* 引用的对象名称
* 修改者用户名
* 修改人用户 ID
* 修改日期（UTC 时区）

在&#x200B;**修改类型**&#x200B;列中，您将获得以下详细信息：

| 修改类型 | 描述 |
| --- | --- |
| 创建 | 已创建课程 |
| 认证添加 | 认证已添加到目录 |
| 认证删除 | 已从目录中删除认证 |
| 内容添加 | 内容已添加到模块 |
| 课程添加 | 课程已添加至学习路径 |
| 课程删除 | 课程已从“学习路径”中删除 |
| 添加自定义标签 | 自定义标签已添加到目录 |
| 自定义标签移除 | 已从目录中删除自定义标签 |
| 删除 | 已删除目录 |
| 添加工作辅助 | 工作辅助已添加到目录 |
| 工作辅助移除 | 已从目录中删除工作辅助 |
| 学习路径添加 | 学习路径已添加到目录 |
| 学习路径移除 | 学习路径已从目录中删除 |
| 模块内容添加 | 模块已添加到课程（“内容”部分） |
| 模块内容移除 | 已从课程（“内容”部分）中删除模块 |
| 已发布 | 课程或学习路径已发布并添加到默认目录 |
| 已重新发布 | 课程已重新发布 |
| 资源添加 | 资源已添加到课程 |
| 资源删除 | 已从课程中删除资源 |
| 已弃用 | 已弃用的课程 |
| 添加共享目录 | 目录已共享到目录 |
| 删除共享目录 | 目录共享已从目录中删除 |
| 共享目录更新 | 目录共享状态：活动 |
| 更新 | 课程或学习路径已更新 |
| 用户组添加 | 用户组已添加到目录 |
| 用户组删除 | 已从目录中删除用户组 |

在生成的报告中不提取有关元数据的信息。

要生成课程追踪审查报告，请执行以下步骤。

1. 选择“**[!UICONTROL 报告]**”>“**[!UICONTROL Excel报告]**”>“**[!UICONTROL 课程审核记录]**”。 此时会显示&#x200B;**[!UICONTROL “内容审查追踪”]**&#x200B;对话框。

   ![](assets/course-audit-trial.png)
   *课程审核记录*

1. 选择要下载报告的课程、学习计划和认证。如未指定，则默认下载所有报告。
1. 选择报告的日期范围，然后单击&#x200B;**[!UICONTROL 生成]**。
1. 生成报告，并通知您内容审查报告已准备就绪。您可下载该报告。

### 用户审查追踪报告 {#useraudittrailreports}

用户审查追踪捕获用户、用户组和自行注册配置文件的生命周期。 它还可捕获用户增加、删除和经理变更等内容。 此外，还记录自注册配置文件的创建和删除。还可以暂停和恢复自注册。

可添加、启用、禁用、暂停或恢复外部配置文件；可添加、删除、暂停或恢复自注册。还会捕捉 CSV 上传。

1. 选择&#x200B;**[!UICONTROL 报告> Excel报告>用户轨迹]**。 此时将显示“用户审查追踪”对话框。
1. 此时会显示用户审查追踪对话框。从弹出菜单中选择日期范围。可以选择生成最近一周或最近一个月的报告，也可以选择自定义日期。

   ![](assets/user-audit-trail.png)
   *用户审核记录*

1. 单击&#x200B;**[!UICONTROL “生成”]**&#x200B;以生成报告。

**[!UICONTROL “用户审查追踪报告”]**&#x200B;对话框中有两个过滤器。

**日期范围过滤器：**&#x200B;选择要为其生成报告的日期范围。 有以下三个选项：

* 最近一周
* 最近一个月
* 自定义日期

选择学习者过滤器：搜索用户或用户组。

导出的报告将包含同时符合两个指定搜索条件的用户的数据。

![](assets/user-audit-trail.png)
*用户审核记录*

>[!NOTE]
>
>分配或删除技能时，可以针对用户审查报告追踪已分配或删除的技能。

### 扩展配置报告

此报告提供所有已添加本机扩展的配置详细信息（包括其激活状态）的信息。 要了解如何下载扩展报告，请参阅[下载扩展报告](native-extensibility.md#download-extension-report)。

### xAPI 活动报告

此报告提供在xAPI活动模块期间记录和生成的所有xAPI语句的数据。

要下载此报告，请执行以下步骤：

1. 选择&#x200B;**[!UICONTROL 报告> Excel报告> xAPI活动报告]**。 此时会显示“xAPI活动报告”对话框。
1. 从弹出菜单中选择日期范围。可以选择生成最近一周或最近一个月的报告，也可以选择自定义日期。
1. 从下拉菜单中选择学习者和活动。
1. 选择“**[!UICONTROL 生成]**”以生成报告。

### 游戏报告 {#gamification}

管理员可下载 CSV 格式的游戏成绩单。您可以下载单个用户或用户组的报告。 用户名、用户电子邮件、用户的UUID、总用户得分、收集的分解、用户参与的组名称、经理姓名和活动字段值均在报告中获取。 管理员可以使用此报告评估和了解用户在企业级的排名或特定组的排名。

1. 选择“报告”>“Excel报告”>“游戏报告”。

   ![](assets/gamification.png)
   *游戏报告*

1. 此时会显示游戏成绩单对话框。按照姓名、配置文件、用户组、电子邮件 ID 或 UUID 选择学习者。

   ![](assets/gamification-transcriptsdialog.png)
   *游戏成绩单对话框*

1. 单击“**[!UICONTROL 生成]**”以生成报告。

   生成学习者报告后，您必须能够导出帐户中所有（内部、外部或已删除）用户的当前和已获得级别信息。 您还可以查看学习者获得各级别的日期：

   * 铜级获得日期
   * 银级获得日期
   * 金级获得日期
   * 白金级获得日期

   这些列包含首次获得该级别的日期。 当前级别&#x200B;**[!UICONTROL 列]**&#x200B;显示学习者的当前级别。

   管理员重置游戏后，学习者的所有点数会相应重置。

### 游戏审核记录报告 {#gamification-audit-trail}

此报告包含学习者因各规则而获得的游戏点数的历史记录和原因。

### 下载报告

1. 选择游戏审查追踪URL。
1. 在&#x200B;**游戏审核记录**&#x200B;弹出窗口中，选择日期范围。
1. 选择&#x200B;**生成**。

报告会下载为CSV文件。 该文件包含以下列：

* 名称
* 电子邮件/UUID、
* 状态
* 操作
* 点，
* 平衡点
* 规则/任务
* 规则/任务子任务，
* 规则/任务详细信息
* 文字，
* 名称，
* 实例名称实现日期（UTC时区）
* 规则/任务开始时间
* 规则/任务结束时间

### 注册和取消注册报告 {#enrollmentandunenrollmentreport}

管理员和经理可以提取报告，了解已注册和已取消注册的学习者。 管理员可查看已注册或已取消注册课程、学习计划或认证的实例的任何学习者、管理员或经理，并导出报告。而作为经理，您只能获取团队成员的报告。 经理无法在经理应用程序中将已删除的学习者或您自己的姓名视为已注册或已取消注册的学习者。

要下载报告，请执行以下步骤：打开&#x200B;**[!UICONTROL 课程/学习计划/认证]** > **[!UICONTROL 学习者]** > **[!UICONTROL 操作]** > **[!UICONTROL 导出报告]**。

![](assets/unenrollment.png)
*取消注册报告*

### 反馈报告 {#feedback-report}

作为管理员，您现在可以获取特定时间段内所选培训的学员反馈 (L1) 和经理反馈 (L3)。

您可以从UI或通过PowerBI连接器导出数据以进行更深入的分析。

L1和L3反馈报告提供了一个可用选项，允许用户下载&#x200B;**一年**&#x200B;内选定培训或任意日期范围内多达10项选定培训的L1和L3响应综合反馈报告。

以管理员身份登录，单击&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]**，然后在报告列表中，单击&#x200B;**[!UICONTROL 反馈报告]**。

![](assets/download-feedbackreport.png)
*下载反馈报告*

选择过滤器后单击下载，您将收到以CSV格式下载报告的通知。

下载的报告将包含各种详细信息，例如培训名称和类型、实例名称、学习者姓名和电子邮件、反馈类型（L1或L3）、为新数据提交的反馈日期等。

对于此功能实施之前的现有数据，将显示学习对象完成日期、学习对象完成日期、L1反馈问题、不同列中的自定进度的实际文本和课堂文本、L1反馈各自的响应、经理姓名和电子邮件、L3反馈值和提交日期、活动字段。

您也可以从用户界面导出数据或将数据导出到Power BI（支持任何日期范围内的所有培训），以便进行更深入的分析

### 培训报告 {#training-report}

Learning Manager支持培训报告功能，管理员可以通过该功能下载培训详细信息及其关联的元数据，如作者、发布日期、技能、目录标签等。

在管理员应用程序上，单击&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]** > **[!UICONTROL Excel报告]** > **[!UICONTROL 培训报告]**。

您可以下载以下报告：

* 选定培训（限选 10 个）- 从任意目录中选择一或多个培训（最多 10 个）
* 所选目录中的培训（限选 5 个）-（最多可选择五个目录）
* 所有培训 -（帐户中的所有培训）

![](assets/download-trainingreport.png)
*下载培训报告*

在“高级选项”部分中，可用选项如下：

* 包括课程映射及学习计划/认证
* 包括模块级别信息

选择过滤器并单击“下载”后，您将收到以CSV格式下载报告的通知。

报告将包含以下字段：

*目录名称、培训类型、培训ID、培训专属ID、培训名称、子培训、模块、培训或模块持续时间、格式、培训状态、技能、作者、上次发布日期、上次完成日期、讲师注册计数、开始计数、完成计数、L1平均分、L2平均分、L3平均分、收到的L1反馈、收到的L2反馈、收到的L3反馈、目录标签。*

![](assets/more-options.png)
*其他选项*

### 会话摘要报告 {#session-summary-report}

“会话摘要报告”包含在指定日期内为学习者计划的所有会话。

管理员可利用此报告导出给定日期范围内的所有虚拟和教室会话详细信息。 管理员还可以导出有关特定培训或讲师的会话报告。

这也有助于管理员了解每月规划的课程，并确定讲师的日程安排和已交付的课程。

作为管理员，请单击&#x200B;**[!UICONTROL 自定义报告]** > **[!UICONTROL 会话摘要报告]**。

在随后出现的对话框中选择日期范围，然后选择培训或讲师以获取摘要。

![](assets/session-summary-report.png)
*会话摘要报告*

下载的 CSV 报告包含以下字段：

* 开始日期和时间
* 结束日期和时间

* 模块名称
* 会话时长（以分钟为单位）
* 名额数
* 位置
* 实例名称
* 课程名称
* 课程 ID
* 讲师姓名
* 讲师电子邮件
* 注册计数
* 会话类型
* 轮候表限制
* 轮候表数量
* 轮候表用户的电子邮件
* 位置信息
* 位置所属地区

### 讲师利用率报告

此报告收集讲师每天在已分配的会话上花费的上课时间（以分钟为单位）。 自选定的开始日期起，可下载三个月内的报告。

若要下载报告，请单击&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]** > **[!UICONTROL 讲师利用率报告]**。

选择一名或多名讲师以及日期范围。

![下载讲师利用率报告](assets/utilization-report.png)
*下载讲师利用率报告*

下载的报告包含以下字段：

* 讲师姓名
* 讲师 ID
* 能力级别
* 日期（以列显示）。 如果在某个日期使用了讲师，则会列出会话数。 如果在某个日期未使用讲师，则该值将显示为零。

该报告包含从所选月份起三个月的记录。

要检索所有讲师的记录，请将“讲师”字段留空。

此外，有权生成报告的自定义管理员可以检索此报告。

### 用户审查追踪报告

此报告获取有关切换实例、“从实例”切换到“到实例”、按时间、日期等的学习者的信息。

选择学习者或用户组。

若要下载报告，请单击&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]** > **[!UICONTROL 用户审核跟踪报告]**。

![下载用户审查追踪报告](assets/user-audit-report.png)

*下载用户审查追踪报告*

### 学习计划报告

此报告包含帐户中所有学习计划的详细信息，例如相关用户组、状态和触发信息。

报告包含以下内容：

* 学习计划的名称
* 类型（发生时间）
* 培训（已完成）
* 技能（已获得）
* 日期（日期）
* 操作
* 状态，创建者
* 创建日期
* 上次修改日期
* 用户组（适用于）
* 用户组（添加到）
* 在此之后注册
* 学习元素类型
* 学习元素
* 学习元素实例
* 学习元素
* 完成日期
* 学习元素提醒
* 范围 - 目录
* 范围 - 用户组

### 自定义角色的审计追踪

管理员可以下载自定义角色审核报告，以跟踪对自定义角色所做的所有更改，包括创建、修改和删除自定义角色及其关联的功能访问权限。

要下载报告，请执行以下步骤：

1. 以管理员身份登录。
2. 选择“报告”>“自定义报告”。
3. 选择自定义角色审核记录并选择日期范围
4. 选择生成以下载报告。

“自定义角色审查追踪”报告包含以下字段：

* 角色 ID
* 角色名称
* 活动类型
* 修改类型
* 描述
* 引用对象类型
* 引用对象 ID
* 引用对象名称
* 引用的对象电子邮件
* 按用户名修改
* 修改者用户UUID
* 按用户电子邮件修改
* 修改日期（UTC时区）
* 源

## 电子邮件订阅 {#emailsubscriptions}

您可以通过订阅感兴趣的报告以一封电邮形式接收。

### 设置电子邮件订阅

>[!INFO]
>
>在本培训中，您将了解如何为信息板报告设置电子邮件订阅。<br><br>[![按钮](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/8318927)</br></br>


如果您无法启动培训，请写入<almacademy@adobe.com>。

在&#x200B;**[!UICONTROL 报告]**&#x200B;页面中，单击&#x200B;**[!UICONTROL 订阅]**&#x200B;选项卡。 此时会显示订阅页面。

要从下拉列表中选择报告名称，请在报告字段中键入报告名称。 从下拉列表中选择电子邮件的频率。您可以添加电子邮件的主题并提供备用电子邮件 ID。

您可以编辑和删除订阅。

## 历史报告

Adobe Learning Manager (ALM)中的历史报告是指捕获学习平台内的历史数据和活动的报告。 这些报告可以让您深入了解过去的学习者活动、培训内容、用户组业绩和其他相关数据。 管理员可利用历史报告跟踪、监控和分析学习计划在一段时间内的进展情况和效果。

### 课程访问报告

课程访问报告提供有关每个课程重新访问的信息。

要下载此报告，请执行以下步骤：

1. 转到&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]** > **[!UICONTROL 历史报告]**。
1. 选择&#x200B;**[!UICONTROL 课程访问报告]**。 将打开“生成报告请求”对话框。
1. 从下拉菜单中选择年份和季度。
1. 选择&#x200B;**[!UICONTROL 生成]**。

### 登录/访问报告

登录/访问报告提供有关用户登录和访问的信息。 您可以一次生成包含三个月数据的报告。

要下载此报告，请执行以下步骤：

1. 转到&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]** > **[!UICONTROL 历史报告]**。
1. 选择&#x200B;**[!UICONTROL 登录/访问报告]**。 将打开“生成报告请求”对话框。
1. 从下拉菜单中选择年份和季度。
1. 选择&#x200B;**[!UICONTROL 生成]**。

## 创建信息板 {#createadashboard}

1. 要开始创建自己的讨论区，请单击页面右侧的“添加信息板”。

   ![](assets/add-dashboards.png)
   *添加仪表板*

1. 提供信息板的名称和描述。
1. 如果要与任何经理共享仪表板，请在&#x200B;**[!UICONTROL 共享对象]**&#x200B;字段中选择他们。 您可以使用任何正常选择标准进行此操作。
1. 单击&#x200B;**[!UICONTROL 保存]。**

您可以在&#x200B;**[!UICONTROL “信息板报告”]**&#x200B;选项卡中查看最近创建的讨论区。

要将报告添加到讨论区，请单击讨论区窗口右上角的下拉列表，然后单击&#x200B;**[!UICONTROL 添加报告]**。 以这种方式创建的报告会与信息板关联。

>[!NOTE]
>
>在“报告”页面的右上角单击“添加”所创建的报告会添加到默认的信息板。

## 共享信息板 {#shareddashboards}

共享讨论区是公司内其他用户与您共享的报告合集。您添加到共享讨论区的所有报告均将自动与有权访问该讨论区的其他用户共享。

您可以通过以下两种方式共享讨论区：

* 通过在&#x200B;**[!UICONTROL 共享对象]**&#x200B;字段中输入与之共享仪表板的用户。
* 在下拉列表中选择“编辑讨论区”，然后输入用于共享信息板的用户详细信息。

>[!NOTE]
>
>经理在共享信息板中只能查看其团队成员的报告。

## 下载 {#downloads}

导出的信息板报告工作表提供了详细信息，而不是报告摘要。 下载的报告现采用学习者成绩单的格式。

## 创建报告 {#report}

1. 单击左侧窗格中的“报告”。此时会显示报告摘要页面。

   >[!NOTE]
   >
   >默认情况下，示例讨论区选项卡中至少会显示三个示例报告。您只能查看这些示例报告以了解如何创建和自定义报告。

1. 在页面右上角，单击&#x200B;**[!UICONTROL “添加”]**。
1. 在&#x200B;**[!UICONTROL “添加报告”]**&#x200B;对话框的“类型”下拉列表中，您可选择任一预定义报告，也可以选择&#x200B;**[!UICONTROL “自定义”]**。如果选择预定义报告，则可以看到各表单项已预先填充。您可更改部分字段，然后单击&#x200B;**[!UICONTROL “保存”]**。该报告即会添加至您的默认信息板中。

   ![](assets/create-report.png)
   *创建报告*

   在&#x200B;**[!UICONTROL “报告类型”]**&#x200B;中，可以选择预定义的报告集或选择自定义的值。以下所示报告为预定义报告集的一部分：

   * 已指定和已习得的技能
   * 已注册和已完成的课程
   * 课程效果
   * 已注册和已完成的学习计划
   * 每个课程花费的学习时间
   * 每季度花费的学习时间
   * 认证完成

1. 从下拉列表选项中选择报告的 **[!UICONTROL Y 轴]**。对于某些选定标准，您可以从“状态”选项中选择一个或多个状态。例如，对于课程注册统计主要条件，状态可以是已完成、未完成、已注册。主要范围数据在报告中以条形图的形式展现。

   ![](assets/axes-for-reports.png)
   *报表轴*

1. 从下拉列表选项中选择报告的次要 **[!UICONTROL Y 轴]**&#x200B;条件/范围。例如，对于学习计划注册选项，在“状态”下拉列表中选择一个或多个状态。次要范围数据以线形图的形式展现。
1. 从下拉选项中为报告选择适当的X&#x200B;**轴**&#x200B;条件。 如果 X 轴已选定为日期，则可以使用按天、月、季度和年对 X 轴条件进行分组。
1. 在“时间跨度”部分，从下拉列表中选择对应的选项。可用选项包括：

   * 最近一个月
   * 季度
   * 年
   * 迄今一季度（最近 90 天）
   * 迄今一年（最近 365 天）
   * 日期范围。提供日期字段&#x200B;**[!UICONTROL “开始日期”]**&#x200B;和&#x200B;**[!UICONTROL “结束日期”]**&#x200B;的值。

   ![](assets/time-filter-for-report.png)

1. **过滤器部分**

   过滤器会根据您选择的报告类型，显示在“添加报告”对话框的底部。部分突出的过滤器如下所示。

   * **经理：**&#x200B;您可以根据层级选择任一经理。对于部分经理，可能会有下属经理，并且会有多个员工向每个下属经理进行汇报。
   * **个人资料：**&#x200B;选择员工的指派情况。这有助于根据员工的个人资料/指派查看报告。例如，计算机科学家、工程师。
   * **用户组：**&#x200B;选择要从中过滤报告的用户组。Adobe Learning Manager 通过用户功能检索针对帐户定义的用户组。
   * **课程：**&#x200B;您可在下拉列表中选择任意课程来过滤报告。

   展开此部分并选择所需过滤器。

   ![](assets/choose-filters.png)
   *选择筛选器*

1. 单击&#x200B;**[!UICONTROL 保存]**&#x200B;以完成创建报告。

   ![](assets/sample-report.png)
   *示例报告*

## 编辑报告 {#editareport}

在报表上，单击下拉箭头，然后选择选项&#x200B;**[!UICONTROL 编辑报表]**。

![](assets/edit-a-report-1.png)
*编辑报告*

对报告进行必要的更改。要保存更改，请单击&#x200B;**[!UICONTROL “保存”]**。

## 将报告移动至信息板 {#moveareporttoadashboard}

选择此项可将当前报告移动至现有信息板。要移动报告，请单击&#x200B;**[!UICONTROL “移动至信息板”]**&#x200B;选项。

![](assets/move-a-report.png)
*将报表移动到仪表板*

选择要将报告移动至的信息板，然后单击&#x200B;**[!UICONTROL “移动”]**。

## 创建报告副本 {#createacopyofareport}

要创建报表副本，请选择选项&#x200B;**[!UICONTROL 创建副本]**。

![](assets/copy-a-report.png)
*创建报表副本*

选择要将报告复制到的信息板。要开始复制，请单击&#x200B;**[!UICONTROL “复制”]**。

## 删除报告 {#deleteareport}

要删除报告，请选择&#x200B;**[!UICONTROL “删除报告”]**&#x200B;选项。删除后的报告无法还原，该过程不可逆。因此，删除报告时务请谨慎。

![](assets/delete-a-report.png)
*删除报告*

## 下载报告 {#downloadareport}

要下载报告，请选择&#x200B;**[!UICONTROL “下载报告”]**&#x200B;选项。

![](assets/download-a-report.png)
*下载报告*

## 调整报告大小 {#resizeareport}

您可将报告的大小调整为 1×1（中等）和 1×2（大）。该操作可方便您查看报告详情。此外，您还可轻松平移和缩放这些报告。

## 过滤器 {#filters}

过滤器会根据您选择的报告类型，显示在底部的&#x200B;**[!UICONTROL “添加”]**&#x200B;报告对话框中。部分突出的过滤器如下所示。

**经理：**&#x200B;您可以根据层级选择任一经理。部分经理可能会领导下属经理，并且每个下属经理也会领导多名员工。

**个人资料：**&#x200B;选择员工的指派情况。这有助于根据员工的个人资料/指派查看报告。例如，计算机科学家、工程师。

**用户组：**&#x200B;选择要从中过滤报告的用户组。Adobe Learning Manager 通过用户功能检索针对帐户定义的用户组。

**课程**&#x200B;您可以在下拉列表中选择任意课程来过滤报告。

![](assets/sample-report-admin.png)
*筛选报告*

在图例的上方，您可以看到一个缩放框。在图例的上方，您可以看到一个缩放框。将光标移动至其上方，单击并将十字形拖放到缩放框图形区域的任意部分以进行放大。

您可以在图表栏中以直线的形式查看次 Y 轴值。例如，在上述示例中，您可以看到效果值以灰色线显示在图表中。

## 用户组报告 {#user-group-reporting}

跟踪用户组(例如部门、外部合作伙伴和角色)的表现，并与其他用户组或学习目标进行比较。

### 用户组 {#usergroups}

要根据用户组生成报告，请从下拉选项列表中选择&#x200B;**[!UICONTROL X轴用户组]**，如下面的屏幕截图所示。

![](assets/user-group-reports.png)
*用户组报告*

要选择用户组，请键入组名称。根据所输入的内容，会显示建议的组。在显示的组列表中，选择所需用户组。

您还可通过预键入搜索选择多个用户组。

保存并生成该报告后，如果选择了多个用户组，则生成的报告中会包含 X 轴内条形图表中每个相邻的所有用户组。

此用户组报告可让您将一个部门/角色的表现与其他对象进行比较，从而评估其学习成就。

### 自定义用户组/用户属性 {#customusergroupsuserattributes}

您还可以使用 Adobe Learning Manager 中的添加用户/用户组功能来创建自定义用户组。创建用户组后，您可以借助属性列表（例如位置、分支等）生成这些自定义用户组的报告。

在x轴中，选择用户属性选项，然后从属性旁边的&#x200B;**选择**&#x200B;下拉列表中选择属性。 要根据这些属性创建自定义用户组报告，您还必须在筛选器中选择相应的用户组。

## 查看报告 {#viewingreports}

在“报告”页面，您可以查看所有报告。您可以单击每个报告右上角的减号 (-) 图标来最小化每个报告。单击 (+) 图标可再次查看报告。

## 快速查看不同日期 {#quickviewwithdifferentdates}

您可以更改任意报告的日期范围/值并快速查看不同日期，而无需修改和保存报告。单击日期范围（如QTD）旁边的上一年的编辑图标（如下图快照中的箭头所示）。 要确认更改，请从弹出菜单中选择新值，然后单击刻度线。您可以单击 X 标记来取消更改。

>[!NOTE]
>
>您用来查看报告的数据值是临时性的。选择下载选项时，报告的该视图是无法下载的。这只是临时视图。

![](assets/learner-count-report.png)
*查看学习者计数*

## 快速查看不同经理 {#quickviewwithdifferentmanagers}

如果有多个经理向您汇报，您可以快速查看每个经理的报告。要显示每个经理的唯一报告，请从下拉列表中选择经理姓名。

>[!NOTE]
>
>您用来查看报告的经理值是临时性的。选择下载选项时，报告的该视图是无法下载的。这只是临时视图。

## 查看课程报告 {#viewcoursereports}

您可以按照以下步骤查看特定于每门课程的报告：

1. 在“报告”页面的“我的仪表板”选项卡中，单击&#x200B;**[!UICONTROL 查看课程报告]**&#x200B;链接。\
   此时会显示弹出对话框。此时会显示一个文本输入字段，您可以在其中输入所需的课程，此时在下拉列表中会显示建议的课程名称。 从显示的列表中选择课程。

   ![](assets/view-course-report-300x117.png)

   *查看课程报告*

1. 从下拉列表中选择您选择的课程，然后单击“显示”。
1. 您将被重定向到所选课程的测验分数结果页面，以查看特定于课程的报告。

**编辑/移动至讨论区/创建副本/删除/调整报告大小**

要查看下拉选项（例如编辑/移动至信息板/创建副本/删除/调整大小），请单击每个报告右上角的下拉箭头。

![](assets/edit-options-dashboard-300x126.png)

*编辑/移动到讨论区/创建副本/删除/调整报告大小*

**[!UICONTROL 编辑]**&#x200B;要在修改数据时返回初始值，请单击“重置”。 修改值后请单击“保存”。

**[!UICONTROL 移动到仪表板]**&#x200B;您可以将当前报表移动到另一个仪表板，该仪表板是从仪表板列表中选择的。

**[!UICONTROL 创建副本]**&#x200B;您可以将报告复制到同一个或另一个仪表板，该仪表板是从仪表板列表中选择的。

**[!UICONTROL 删除]**&#x200B;单击“删除”以删除该报告。 在您删除报告前，会显示警告/确认消息。

**[!UICONTROL 调整大小]**&#x200B;您可以用1×1（中）和2×2（大）大小调整报表的大小。

## 生成和查看配对帐户的报告 {#generateandviewreportsforpeeraccount}

管理员除了可生成自身帐户的报告外，还可以生成和查看其已设置的配对帐户的报告。

如果已建立与另一个用户的配对帐户，则可以从&#x200B;**[!UICONTROL “报告”]**&#x200B;页面查看该配对帐户的报告。创建报告时，您会找到&#x200B;**[!UICONTROL “选择帐户”]**&#x200B;字段。从下拉列表中（其中列出了您所关联的所有配对帐户），选择要查看其共享报告的帐户。

创建配对帐户时，如果未选择“共享目录”选项，则无法在此列表中查看该配对帐户。

![](assets/acc1-jpg.png)
*管理配对帐户的报告*

1. 选择此报告的 x 轴和 y 轴，然后选择此报告的日期。
1. 请注意过滤器字段，“共享目录”按钮是自动启用的。此为必须操作。如未启用“共享目录”，则表示无法生成或查看配对帐户的报告。
1. 从“共享目录”下方的下拉列表中，选择要查看其报告的共享目录。
1. 单击&#x200B;[!UICONTROL **“保存”**]。

   ![](assets/acc2.png)
   *为配对帐户选择共享目录*

1. 单击&#x200B;**[!UICONTROL 保存]**&#x200B;后，您可以在默认仪表板中查看报告的图形表示。 在此信息板中，可进一步按照经理来过滤特定配对帐户的报告。
1. 如果您的目录有任何更改，则该更改会立即反映在配对方生成的报告和信息板中。然而，配对方修改目录时，更改不会自动显示在您的信息板中。
1. 如果您希望您的信息板自动更新，则配对方必须向您发送新的配对请求。

   >[!NOTE]
   >
   >经理无法查看配对报告。

## 常见问题解答 {#frequentlyaskedquestions}

+++如何与经理共享自定义信息板？

创建信息板时，请输入名称和说明。 如要与经理共享，请在&#x200B;**[!UICONTROL 共享对象]**&#x200B;字段中输入经理的名字。

![](assets/share-dashboard-manager.png)
*共享仪表板*
+++
