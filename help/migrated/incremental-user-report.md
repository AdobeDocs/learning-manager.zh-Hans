---
description: 增量用户报告作业API允许管理员仅导出其数据在指定日期范围内发生更改的用户。 这消除了完全导出用户的需要，并使新用户或更新的用户记录能够更高效地同步。
jcr-language: en_us
title: 增量用户报告（作业API）
source-git-commit: 40c3bcb1b23ad87a502692007f97b3df27b3a7b9
workflow-type: tm+mt
source-wordcount: '1585'
ht-degree: 1%

---


# 增量用户报告（作业API）

## 概述

Adobe Learning Manager的增量用户报告是一项新的作业API功能，通过该功能，管理员和集成开发人员只能导出在指定日期和时间范围内更改了数据的用户。 不必每次都提取完整的用户列表，而是可以请求仅覆盖新用户或已修改用户的目标切片。

本文档涵盖：

- 为什么存在增量报告以及何时使用它
- 该功能的工作原理 — 包括更改跟踪模型
- 用于增量用户报告的新作业API（负载、参数、分页）
- 如何处理大型客户（5,00,000多个用户）
- 跟踪字段与非跟踪字段
- 限制和非目标

## 为什么使用增量报告

本节说明该功能的动机，并帮助您确定增量导出还是完整导出最适合您的集成。

## 完整用户导出时出现问题

当前的完整用户导出（generateUsers作业类型）会在每次执行时返回帐户中的每个用户。 对于大型企业客户，这带来了两个重要问题：

| 客户 | 用户卷 |
|----------|-------------|
| 客户甲 | 210万用户 |
| 客户B | 700万用户 |
| 客户C | 100多万用户 |
| 客户D | 770万用户（迁移） |


&#x200B;* 在这些扩展中，导出管道在提取、处理和存储数据时的CPU利用率约为90%。
&#x200B;* 下游功能板（PowerBI、Salesforce、自定义集成）会在每次运行时重新摄取未更改的用户记录，从而浪费带宽和处理时间。
&#x200B;* 无法询问“自上次导出后哪些用户发生了更改？” 使用当前API。

## 何时使用增量报告

当您需要保持外部系统与Adobe Learning Manager用户数据同步时，请使用增量导出。 典型用例：

&#x200B;* 使企业信息板(PowerBI、Tableau、SFDC)保持与用户配置文件更改同步。
&#x200B;* 为下游身份管理系统提供角色、状态或元数据更改。
&#x200B;* 每晚或每小时运行增量同步管道，而不是完全重装。
&#x200B;* 为拥有数百万用户的帐户降低API负载和数据传输成本。

当您需要授权基线时（例如，在首次设置时或在同步之间出现长间隙后），使用完整导出(generateUsers)。

| 导出模式 | 使用时间…… |
|-------------|-----------|
| 完全导出(generateUsers) | 初始引导；少于5万用户的帐户；错过同步窗口后恢复。 |
| 增量导出(generateUserIncrementalReport) | 常规增量同步；大型客户；仅需要更改记录的管道 |

## 当前完整用户报告

(generateUsers)本节记录现有作业API用户报告以供参考。 如果您已经熟悉此功能，请跳到下一部分。

## 工作原理

通过作业API将当前用户CSV报告作为作业提交。 Snaplogic管道会选取任务，对CAPTIVATE数据库（user、usergroup、usergroup_user表）执行MySQL查询，并生成CSV文件。

## 可用过滤器

有效负载支持三个可选过滤器：

&#x200B;* `expandMetadata` — 传递true以将元数据导出为单独的列。
&#x200B;* `fetchActiveUsers` — 传递true以仅导出活动用户。
&#x200B;* `peerAccountId` — 为配对帐户生成用户报告。

## CSV列

导出的CSV包含以下列：

```
internalUserID, userEmail, customerDefinedUniqueUserId, name, managerEmail,

userType, state, excludedFromGamification, pointsEarned, profile, roles,

dateCreated, lastLoginDate, dateDeleted, uiLocale, contentLocale,

timeZoneCode, userSource, group, AF_location, AF_login, AF_externalaf,

lastSocialActivityDate
```

## 请求负载

作业类型：generateUsers。 仅限管理员角色。

```
{

  "data": {

    "type": "job",

    "attributes": {

      "description": "<description of your choice>",

      "jobType": "generateUsers",

      "payload": {

        "expandMetadata": "<true to export metadata as separate column>",

        "fetchActiveUsers": "<true to export ACTIVE users only>",

        "peerAccountId": "<peerAccountId for peer account report>"

      }

    }

  }

}
```

## 限制

&#x200B;* 无基于日期的筛选 — 每次执行都会导出所有用户。
&#x200B;* 对于大型帐户不可行 — 管道资源耗尽超过100万用户。
&#x200B;* 无增量或增量功能。

## 增量用户报告(generateUserIncrementalReport)

本节介绍了M46中引入的新增量用户报告功能。 这是本文档的主题。

## 什么是增量导出？

增量导出仅返回其跟踪数据在指定的开始和结束日期 — 时间范围内发生更改的用户。 后端存储每个用户的跟踪字段的上次修改时间戳。 在为给定窗口请求报告时，只包括最近更改在该窗口内的用户。

## 更改跟踪模型的工作方式

Adobe Learning Manager会维护上次修改的时间戳，每当用户的任何跟踪字段更改时，该时间戳都会更新。

当您请求包含start_date_time和end_date_time的增量报告时，系统会返回其上次修改时间戳在[start_date_time， end_date_time]内的用户。 如果在窗口内和窗口后都修改了用户（即，在end_date_time之后再次更改了用户），则报告不包括该用户，因为其上次修改的时间戳现在已超出窗口。

>[!NOTE]
>
>这意味着，增量导出会捕获指定窗口中最近更改的用户，而不是该窗口内任何时间点上所接触的所有用户。

## 跟踪更改的字段

如果更改了以下任何字段，则增量报告中会包含用户：

| 字段 | 备注 |
|---|---|
| userEmail | 用户的电子邮件地址 |
| name | 用户的名字 |
| managerId | 用户表存储managerId。 如果managerId发生更改，则该字段将被标记为已更改。 如果只有经理的电子邮件发生更改（同一managerId），则不会将此字段视为已更改。 |
| 类型 | 内部或外部用户分类 |
| 或 | 活动或已删除 |
| 配置文件 | 用户配置文件分配 |
| 角色 | 角色添加或删除 |
| uiLocale | 用户界面区域设置 |
| contentLocale | 内容区域设置 |
| timeZoneCode | 用户时区 |
| 活动字段(AF_*) | 所有已配置的活动字段，例如AF_location、AF_login |
| 元数据 | 所有已配置的元数据字段 |

## 未跟踪更改字段

以下字段将显示在CSV输出中，但不会在其更改时触发增量导出中包含操作：

&#x200B;* excludedFromGamification
&#x200B;* pointsEarned
&#x200B;* lastLoginDate
&#x200B;* dateDeleted
&#x200B;* dateCreated
&#x200B;* userSource
&#x200B;* lastSocialActivityDate

## 输出格式

增量CSV报告与完整用户CSV报告具有相同的列和格式。 所有列（包括所有活动字段和元数据列）均按相同顺序显示，而不管导出用户更改了哪些字段。

>[!NOTE]
>
>如果添加了新的活动字段或删除了现有活动字段，则受此更改影响的所有用户都将显示在下一次增量导出中。 新活动字段中的新列将附加到报告末尾，以便列位置上键入的现有集成不会中断。

## 增量用户报告的新作业API

增量用户报告使用作业API生成一个CSV文件，其中包含其跟踪数据在指定日期和时间窗口中发生更改的用户。 对于大型结果集，请使用本文档后面所述的相同分页模型：在每个请求中提交相同的日期窗口，然后将上一个响应中收到的最后一个用户ID传递为fromUserId ，以便检索下一个区块。

## 作业类型

作业类型： generateUserIncrementalReport

## 请求负载

```
{

    "data": {

        "type": "job",

        "attributes": {

            "description": "description of your choice",

            "jobType": "generateUserIncrementalReport",

            "payload":{

                 "fullExport": <Pass true to export all users. If fullExport is true, fromDate and toDate are ignored>,

                 "expandMetadata": <Pass true to export metadata as separate columns>,

                 "fromDate": <Start of the change window in ISO format, for example 2020-01-01T18:30:00.000Z>,

                 "toDate": <End of the change window in ISO format, for example 2020-01-31T18:30:00.000Z>,

                 "fromUserId": <For paginated requests, pass the last userId received in the previous response>

            }

        }

   }

}
```

## 有效负载参数

| 参数 | 类型 | 描述 |
|---|---|---|
| fromDate | 字符串(ISO 8601) | 增量导出所需。 更改窗口开始。 使用ISO 8601格式。 |
| 结束日期 | 字符串(ISO 8601) | 增量导出所需。 更改窗口结束。 使用ISO 8601格式。 |
| fromUserId | 字符串 | 可选。 对于分页请求，将上一个响应中收到的最后一个用户ID作为fromUserId传递。 对于第一个请求省略此参数。 |
| expandMetadata | 布尔值 | 可选。 如果为true，则将元数据导出为单独的列。 |

对于增量导出，传递`fromDate`和`toDate`以定义更改窗口。 如果结果集大于一个区块，请继续分页，方法是发送相同的`fromDate`和`toDate`，并将上一个响应中的最后一个`userId`传递为`fromUserId`。 如果fullExport为true，则忽略日期窗口并且API生成完整的用户导出。

## 处理大型帐户（50万以上的用户）

使用数据平台管道生成用户报告，并以分块形式返回输出以支持大型帐户。 如果增量导出超过500,000个用户，则报告将分页。

## 分页模式

要检索大型增量导出的所有页面，请在每个请求中传递相同的startDateTime和endDateTime，此外还要传递上一个区块中接收的上一个用户的userId和fromUserId。 该API将返回下一组用户（最多500,000个），用户ID大于传递的fromUserId。

## 分页工作流程

步骤1：不使用fromUserId提交第一个请求。

```
// First request – no fromUserId

{

  "payload": {

    "startDateTime": "2026-05-01T00:00:00Z",

    "endDateTime": "2026-05-31T23:59:59Z"

  }

}
```

步骤2：接收第一个区块（最多500,000个用户）。 请注意响应中的最后一个用户ID。

步骤3：提交下一个请求，传递与fromUserId相同的日期窗口和上一个响应中的最后一个用户ID。

```
// Subsequent request – pass last userId from previous response as fromUserId

{

  "payload": {

    "startDateTime": "2026-05-01T00:00:00Z",

    "endDateTime": "2026-05-31T23:59:59Z",

    "fromUserId": "<last userId from previous response>"

  }

}
```

步骤4：重复此操作，直到响应返回少于500,000条记录，表明您已经到达最后一页。

| 请求 | fromUserId参数 |
|---|---|
| 第一页 | 忽略fromUserId |
| 第二页 | 将第一页中的最后一个用户ID作为fromUserId传递 |
| 第三页 | 将第二页中的最后一个用户ID作为fromUserId传递 |
| ...（继续） | ... |
| 最后一页 | 响应包含的记录少于500,000条 |

>[!NOTE]
>
>确保您的`startDateTime`和`endDateTime`在单个导出运行的所有分页请求中保持相同。 更改日期窗口进行分页处理会产生不一致的结果。

## 限制

有意对增量用户报告进行范围界定。 以下功能超出范围：

&#x200B;* 不是用户审核报告 — 它不列出更改的特定字段。
&#x200B;* 无旧/新值比较 — 报告仅显示当前字段值。
&#x200B;* 无每次更改的时间戳 — 不显示各个字段修改的时间。
&#x200B;* 不指示更改次数 — 用户修改过一次，而用户修改了10次，两者在导出中的显示完全相同。
&#x200B;* 现有报告格式未更改 — CSV列结构与完整用户报告相同。

## 连接器集成

增量用户报告设计用于Adobe Learning Manager连接器（PowerBI、Salesforce等），以作为常规同步管道中完整用户报告的下拉替代项。 这允许现在使用generateUsers的连接器迁移到增量模型，而无需更改下游数据架构。

连接器可以使用增量报告进行增量同步，并回退到完整报告以进行引导或恢复。
