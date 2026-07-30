---
description: 本文档汇总了Adobe Learning Manager 2026年8月报告变更的内容。 它涵盖了“学习者成绩单”、“培训”、“注册”、“轮候表”、“出勤”、“内容审核”以及“用户报告”中的新增和更新列。 它还介绍了自适应课程行为、gradebook评分、外部学习记录、Gen AI信用报告、根认证跟踪、时间戳标准化和API作者更新。
jcr-language: en_us
title: 报告Adobe Learning Manager 2026年8月版中的更改
source-git-commit: 5c32d300f6e66e154a5c993a0d9701254ac8b4ce
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 2%

---


# 报告Adobe Learning Manager 2026年8月版中的更改

Adobe Learning Manager 2026年8月版引入了有关gradebook、外部学习、Gen AI积分使用情况等的报告增强功能。 本文概述了此版本中管理员可用的新列、报告和行为更改。

## 所做的更改

报告更新涵盖八个功能区域：评分簿评分、外部学习、增量用户导出、Gen AI积分使用情况、根认证跟踪和Webhook时间戳对齐。 这些更改对以下报告的影响最大：

- 学习者成绩单(LT)
- 培训报告
- 注册报告
- 轮候表报告
- 内容审核报告

大多数更新都会引入新列。 一些机构引入了新的报告类型。 少数内容改变了现有数据建模或格式化的方式。

<!--
## Adaptive course reporting changes

### Training report

Three new columns in the Training report support adaptive course behavior.

| **Column**               | **Description**                                          | **Supported Values**                                                   |
|--------------------------|----------------------------------------------------------|------------------------------------------------------------------------|
| Adaptive Learning Object | Identifies whether a course is adaptive                  | true (adaptive), false (non-adaptive)                                  |
| Visibility User Groups   | Lists user groups that can view each module              | One or more user group names (for example, All Learners, UG-Australia) |
| Mandatory                | Indicates whether a module is mandatory for a user group | User group names for which the module is mandatory; blank = optional   |

You can combine **Visibility User Groups** and **Mandatory** to interpret adaptive completion rules directly in the report. For example, a module may be visible to **All Learners** but mandatory only for the **Administrator group**.


### Learner Transcript

A new **Previous Completions** column captures historical completion data when adaptive logic triggers recompletion.

| **Sub-field**         | **Description**                         |
|-----------------------|-----------------------------------------|
| completionRefreshDate | Timestamp when the completion was reset |
| completedDate         | Previous completion timestamp           |
| progressAtRefresh     | Learner progress before reset           |
| gradeAtRefresh        | Learner score at the time of reset      |

The Learner Transcript now supports multiple completion cycles. When a recompletion event occurs, for example, due to course updates or new mandatory modules, the previous completion moves to the **Previous Completions** column. The current completion remains in the standard transcript fields.

### Enrollment report

A new **Waitlisted** column indicates whether a learner is waitlisted in any module within a course.

| **Value** | **Meaning**                                             |
|-----------|---------------------------------------------------------|
| true      | The learner is waitlisted in one or more modules        |
| false     | Learner has confirmed enrollment in all visible modules |

### Waitlist report

Two new columns and an enhanced status-detail support module enable waitlist tracking at the module level.

| **Column**      | **Description**                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Module**      | Name of the module (classroom or virtual classroom session) where the learner is waitlisted. Appears after the Instance Status column. |
| **Module ID**   | Identifier of the module where the learner is waitlisted. Appears after the Module column.                                             |
| **Embedded In** | The learning path name and ID of any learning path that contains this course. Blank if the course is not part of a learning path.      |

The Waitlist report has shifted from a course-level model to a module session–level model. A learner can now be enrolled in some modules and waitlisted in others. The report also supports waitlist tracking within Flex learning paths, where seat limits are enforced at the module level.

### LP Enrollment report

The Learning Path Enrollment report also receives a new **Remarks** column. When a learner is in a waitlisted state on any classroom or virtual classroom session within the courses that make up the learning path, the Remarks column shows **Waitlisted**. When all sessions are confirmed, the column is blank.

### Attendance report

The **Learner status** column now distinguishes between confirmed and waitlisted learners.

| **Value**  | **Meaning**                            |
|------------|----------------------------------------|
| Confirmed  | The learner has an allocated seat      |
| Waitlisted | The learner is pending seat allocation |

-->

## Gradebook报告更改

### 学习者成绩单

新的&#x200B;**权重**&#x200B;列表示每个可评分模块对课程总分的贡献。

| **值** | **描述** |
|----------------------------------------------|------------------------------------------------------|
| 数字百分比（例如，20、30、50） | 模块对课程分数的贡献 |
| 空白 | 模块不可烧录（例如，PDF或视频） |

### 内容审核报告

两个新事件捕获了gradebook配置更改。

| **事件** | **触发时间** | **捕获的数据** |
|-----------------------|-----------------------------------------------------------------|----------------------------------------------------------|
| 已更新Gradebook | 在课程级别启用、禁用或修改Gradebook | 更改分级簿状态；分级配置更新 |
| 模块权重已更新 | 已修改分配给模块的权重 | 模块标识符；更新的加权值 |

“学习者成绩单”反映了最新权重。 内容审核报告会跟踪历史更改。 他们一起为您提供了当前评分逻辑及其演化的全貌。

## 外部学习报告更改

### 学习者成绩单

新增了三列来支持外部学习记录。

| **列** | **描述** |
|------------------------|-----------------------------------------------------------------------------------------------------|
| 外部学习名称 | 学习者提交的外部学习活动的名称 |
| 自定义字段 | 为外部学习配置的每个自定义字段一列（文本、数字、复选框或下拉列表） |
| 完成评论 | 经理在批准或拒绝期间输入的备注 |

**注意：**&#x200B;在“学习者成绩单”（学习者自助视图）中，列布局与“管理员学习者成绩单”的布局不同：

- 在现有&#x200B;**模块**&#x200B;列之后立即添加&#x200B;**外部学习名称**。

- 在现有&#x200B;**审阅者的注释**&#x200B;列之后立即添加&#x200B;**完成注释**。

- 在成绩单末尾附加自定义字段列（每个配置的自定义字段一个）。

在“管理员学习者成绩单”中，“外部学习名称”和“完成注释”等所有新列会附加到末尾，其后是自定义字段列。

### “学习者成绩单”中的“类型”列

外部学习条目现在会与“管理员LT”中的现有学习对象（课程、学习路径、认证）一起显示。 **类型**&#x200B;列包含便于筛选的新外部学习分类。

外部学习数据会流入学习者成绩单和管理员学习成绩单。 核心字段（如完成日期、状态和分数）映射到现有列。 自定义字段作为附加列附加。

## 增量用户报告更改

新的增量导出模型允许您仅导出数据在指定时间范围内发生更改的用户，而不是每次都生成完整的数据导出。

| **导出模式** | **行为** |
|--------------------|-----------------------------------------------------------------|
| 完全导出 | 返回帐户中的所有用户 |
| 增量导出 | 仅返回在指定日期范围内发生更改的用户 |

要使用增量导出，请按&#x200B;**开始日期**&#x200B;和&#x200B;**结束日期**&#x200B;进行筛选以定义更改窗口。 现在，使用数据平台管道生成用户报告，并以分块形式返回输出以支持大型帐户。

## Gen AI信用报告

新的积分信息板和两个报告可让管理员了解Gen AI积分使用情况。

### 积分信息板

仪表板会在帐户级别显示以下度量。

| **指标** | **描述** |
|-------------------|---------------------------------------------------|
| 已购积分 | 为帐户配置的积分总数 |
| 已用积分 | 在AI支持的功能上消耗的积分 |
| 剩余积分 | 使用后的可用积分 |
| 按功能使用情况 | 按个人AI功能划分的积分消耗 |

### 新报告

| **举报** | **描述** |
|----------------------|---------------------------------------------------------------------------------------------|
| 每月使用情况报告 | 按月份、功能和已用积分汇总积分使用情况 |
| 审核记录报告 | 提供用户级别的详细信息：用户标识符、功能名称、已用积分和时间戳 |

## 其他行为变化

### 根认证：根培训ID

在&#x200B;**管理员学习者成绩单**&#x200B;和&#x200B;**学习者成绩单**（学习者自助视图）的末尾都添加了一个新的&#x200B;**根培训ID**&#x200B;列。 它捕获唯一标识符，该标识符将证书的所有重复实例链接到单个根实体。 这允许将认证的所有循环实例与单个根ID相关联，以进行跟踪和筛选。

### Webhook和学习者成绩单时间戳标准化

Webhook时间戳现在与学习者成绩单格式保持一致。 现在，Webhook负载的&#x200B;**数据对象**&#x200B;中的每个日期和时间字段的秒值都设置为00，提供了与学习者成绩单报告一致的分钟级粒度。 这样在比较Webhook数据与学习者成绩单数据时，无需标准化时间戳格式。

### 共享课程API响应中的作者信息

通过目录共享将课程从一个Adobe Learning Manager帐户共享到另一个帐户时，API的学习对象(LO)响应现在仅返回源帐户中的原始作者详细信息。 以前，接受帐户的管理员在其帐户的API响应中显示为课程作者

此更改仅影响配对（接收）帐户。 在接收帐户中查询共享课程的学习对象详细信息端点时，作者名称字段现在反映的是源帐户中的原始作者，而不是接收帐户的管理员。

在源帐户中查询学习对象时，作者详细信息的显示方式没有变化。

**注意：**&#x200B;如果您的集成依赖于共享课程学习对象API响应中的authorNames字段，请验证更新的作者数据是否不会中断任何假定接收帐户的管理员名称将显示在此字段中的下游逻辑。
