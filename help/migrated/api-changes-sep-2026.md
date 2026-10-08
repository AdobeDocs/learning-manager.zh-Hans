---
description: 用于列出、检索、注册和删除Adobe Learning Manager中的个性化学习路径的面向学习者的公共API端点，以及用于检查给定学习者是否可以通过分配给他们的目录直接访问一个或多个学习对象的API端点。
jcr-language: en_us
title: 2026年9月API更改
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '1374'
ht-degree: 3%
---

# Adobe Learning Manager 2026年9月版中的API更改

## 用于检查学习对象的目录访问权限的API

确定当前学习者是否可以直接访问一个或多个学习对象的目录，而不管学习者是通过学习路径还是通过认证访问这些内容。

### API的目的

当学习者打开学习路径或认证时，即使没有通过目录直接为特定课程分配特定课程，也可以浏览其中的各个课程。 这支持内容发现：学习者可以先探索学习路径中包含的内容，然后再决定是否继续学习。

但是，能够以这种方式查看课程不应自动意味着学习者可以注册该课程。 注册应取决于学习者是否对该特定课程具有直接目录访问权限，而不仅仅是通过包含学习路径的间接访问权限。

对于给定的学习者，通过此API可检查是否可以通过分配给他们的目录直接访问一个或多个学习对象。 搜索结果可用于控制注册相关的UI，例如，仅在确认直接目录访问时显示“注册”选项，同时使课程页面本身在两种情况下均可查看。

### 端点

`GET /primeapi/v2/learningObjects/isMemberOfVisibleCatalogs`

| 属性 | 值 |
|---|---|
| **作用域** | 学习者读取权限 |
| **响应格式** | application/vnd.api+json |

### 查询参数

| 参数 | 必填项 | 类型 | 描述 |
|---|---|---|---|
| ids | 是 | 字符串或数组 | 要检查的一个或多个学习对象ID。 接受单个ID或以逗号分隔的列表。 每个请求最多10个ID。 |

### 示例请求

```
GET /primeapi/v2/learningObjects/isMemberOfVisibleCatalogs?ids=course%3A2400159%2Ccourse%3A2400160%2Ccourse%3A2400161%2Ccourse%3A2400162
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

>[!NOTE]
>
>学习对象ID必须采用URL编码。 ID（如course：2400159）中的冒号编码为%3A，而分隔多个ID的逗号编码为%2C。

### 示例响应 — 200 OK

```json
{
  "course:2400162": false,
  "course:2400161": false,
  "course:2400160": true,
  "course:2400159": true
}
```

| 值 | 含义 |
|---|---|
| true | 呼叫的学习者可直接访问此学习对象。 |
| false | 呼叫学习者无法通过目录直接使用该学习对象。 如果可以通过其有权访问的学习路径或认证进行访问，学习者仍然可以查看它。 |

### 响应代码

| 状态 | 含义 |
|---|---|
| 200 | 请求成功。 响应包含每个请求ID的结果。 |
| 400 | 一般错误请求错误。 例如，提供的ID超过10个，或者ID格式不正确。 |
| 401 | 请求缺少有效的学习者凭据，或由于凭据无效而导致访问被拒绝。 |

### 错误响应示例

```json
{
  "status": "BAD_REQUEST",
  "title": "Bad request. Check url, params and headers",
  "source": {
    "info": "Either LO id is blank or not as per public api specification"
  }
}
```

### 在集成中使用此API

常见的用例是学习者通过从学习路径导航而到达的课程页面。 您希望课程页面本身仍可访问以进行发现，而仅在学习者可以直接访问该课程的目录时，才显示&#x200B;**注册**&#x200B;操作。

1. 加载课程页面时，使用此课程的学习对象ID调用此端点。
2. 如果对该ID的响应返回true，则显示&#x200B;**注册**&#x200B;选项。
3. 如果响应返回false，请保持课程页面可查看、标题、描述和课程详细信息，但隐藏&#x200B;**注册**&#x200B;选项。

## 管理员审核记录报告的作业API {#apiaudittrailreport}

### API的目的

“管理员审查追踪报告”列出对
Adobe Learning Manager帐户。 例如，更改基础知识、集成或
给定日期范围内的高级帐户设置。 生成“审计追踪”报告需要查询和聚合所请求日期范围和设置类型的配置更改记录。 根据范围的大小和更改量，这可能会超过同步HTTP请求的时间限制，这会给客户端或网关超时带来风险。

为避免发生这种情况，将通过通用作业API异步生成报告：

1. **创建作业。** 管理员提交请求，具体指定报告类型、日期范围和设置类型。 该API会立即返回作业ID，而无需等待编译报告。

2. **轮询作业。** 管理员会通过作业的ID定期检索作业以检查其状态。 作业完成后，响应将包含结果或对它的引用。

### 基本URL和约定

| 项目 | 值 |
|---|---|
| 基本路径 | `/primeapi/v2` |
| 内容类型 | `application/vnd.api+json;charset=UTF-8` (JSON:API) |
| 身份验证 | 持有者OAuth令牌，范围为帐户管理员 |
| 帐户上下文 | `x-acap-account`标头标识呼叫管理员的帐户 |
| 轮询 | 不强制执行固定时间间隔；轮询“获取作业状态”终结点，直到`status`不再是`QUEUED`或`IN_PROGRESS`为止 |

### ID

创建作业时返回的作业`id`是不透明的字符串(例如，
`4593`). 始终传回从创建过程中收到的确切`id`值
轮询状态时响应。 永远不要构建或解析它。

### 身份验证范围

每个端点都需要一个具有以下作用域的OAuth令牌，以及
呼叫用户必须拥有帐户管理员角色：

- `admin:write`创建报告作业（需要`ROLE_ADMIN`个）
- `admin:read`读取作业的状态和结果（需要`ROLE_ADMIN`个）

由帐户上没有`ROLE_ADMIN`的呼叫者发出的请求是
被拒绝；请参阅[错误处理](/help/migrated/api-changes-sep-2026.md#error-handling)

### 端点

#### 创建审计线索报告作业

`POST /primeapi/v2/jobs`

创建异步作业以生成“配置更改审计追踪”报告
指定日期范围和设置类型。 响应将立即返回
具有处于`QUEUED`状态的作业资源；报表本身在
背景。

作用域： `admin:write`

| 参数 | 在 | 必填项 | 描述 |
|---|---|---|---|
| `jobType` | 正文 | 是 | 此报表必须是`generateConfigChangeAuditReport` |
| `payload.fromDate` | 正文 | 是 | 报告窗口的开头，ISO-8601，带偏移量，例如`2026-09-15T00:00:00.000+05:30` |
| `payload.toDate` | 正文 | 是 | 报告窗口结尾，ISO-8601，带偏移量，例如`2026-09-23T23:59:59.000+05:30` |
| `payload.settingTypes` | 正文 | 是 | 要包含的一个或多个设置类别的数组；支持的值为`Basics`、`Integrations`和`Advanced` |

请求正文示例

```json
{
  "data": {
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "payload": {
        "fromDate": "2026-09-15T00:00:00.000+05:30",
        "toDate": "2026-09-23T23:59:59.000+05:30",
        "settingTypes": ["Basics", "Integrations", "Advanced"]
      }
    }
  }
}
```

响应： `202 Created`。 响应正文是其初始版本中的任务资源
`QUEUED`状态。

```json
{
  "data": {
    "id": "4593",
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "status": "QUEUED",
      "dateCreated": "2026-09-23T18:12:04.000+05:30"
    }
  }
}
```

>[!NOTE]
>
>跨越超大日期范围的`fromDate`/`toDate`窗口或
>请求具有长更改历史记录的帐户的所有设置类型，可以
>处理时间较长。 轮询获取作业状态终结点，而不是
>假定报告在固定延迟后已准备就绪。

#### 获取审计跟踪报告作业的状态

`GET /primeapi/v2/jobs/{id}`

返回先前创建的作业的当前状态。 虽然这份工作是
仍在运行，`attributes.status`为`QUEUED`或`IN_PROGRESS`，并且
`attributes.result`不存在。 作业完成后，`attributes.status`将
`COMPLETED`，报表位置在`attributes.result`中，或
`FAILED`，失败详细信息位于`attributes.error`。

作用域： `admin:read`

| 参数 | 在 | 必填项 | 描述 |
|---|---|---|---|
| `id` | 路径 | 是 | 创建作业时返回作业ID |

作业仍在运行时响应的示例

```json
{
  "data": {
    "id": "4593",
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "status": "IN_PROGRESS",
      "dateCreated": "2026-09-23T18:12:04.000+05:30"
    }
  }
}
```

作业完成后的示例响应

```json
{
  "data": {
    "id": "4593",
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "status": "COMPLETED",
      "dateCreated": "2026-09-23T18:12:04.000+05:30",
      "dateCompleted": "2026-09-23T18:12:41.000+05:30",
      "result": {
        "downloadUrl": "https://learningmanager.adobe.com/primeapi/v2/jobs/4593/download",
        "expiresAt": "2026-09-24T18:12:41.000+05:30"
      }
    }
  }
}
```

### 资源架构

#### 作业属性

| 字段 | 类型 | 描述 |
|---|---|---|
| `id` | 字符串 | 作业ID不透明 |
| `jobType` | 字符串 | 此报告的`generateConfigChangeAuditReport` |
| `status` | 字符串 | `QUEUED`、`IN_PROGRESS`、`COMPLETED`或`FAILED` |
| `dateCreated` | 字符串(ISO-8601) | 作业创建时间 |
| `dateCompleted` | 字符串(ISO-8601) | 作业完成时；`status`出现一次是`COMPLETED`或`FAILED` |
| `payload` | 对象 | 创建作业时使用的请求参数（嵌入 — 请参阅下文） |
| `result` | 对象 | 下载已完成报告的位置；仅在`status`为`COMPLETED`（嵌入 — 请参阅下文）时存在 |
| `error` | 对象 | 失败详细信息；仅在`status`为`FAILED`时存在 |

#### 有效负载（嵌入，在创建请求内）

| 字段 | 描述 |
|---|---|
| `fromDate` | 报告窗口开始 |
| `toDate` | 报告窗口结束 |
| `settingTypes` | 设置包括在报表中的类别： `Basics`、`Integrations`、`Advanced` |

#### 结果（嵌入，在已完成作业中）

| 字段 | 描述 |
|---|---|
| `downloadUrl` | 可从中下载所生成报告的已签名URL |
| `expiresAt` | 当`downloadUrl`停止有效时；请求刷新状态检查以在此时间之后获取新链接 |

### 错误处理 {#audit-trail-report-error-handling}

以下代码适用于这些端点：

| HTTP状态 | 错误代码 | 发生时间 |
|---|---|---|
| 400 | `BAD_REQUEST` | `toDate`早于`fromDate`、`settingTypes`为空或包含不受支持的值，或者日期无效ISO-8601 — 仅创建终结点 |
| 401 | `UNAUTHORIZED_ACCESS` | 令牌缺失、无效或已过期 |
| 403 | `FORBIDDEN` | 调用方没有保留帐户上的`ROLE_ADMIN` |
| 400 | `OBJECT_DOESNT_EXIST` | 按ID获取：作业不存在或ID格式不正确 — 两种情况都会折叠到此同一响应中 |

错误响应示例

```json
{
  "status": "BAD_REQUEST",
  "title": "Bad request. Check url, params and headers",
  "source": {
    "info": "toDate must be on or after fromDate"
  }
}
```

### 在集成中使用此API

一个常见的用例是管理员在
帐户设置屏幕。

1. 当管理员选择日期范围和一个或多个设置类型且
确认，用这些值调用创建作业终结点。
2. 存储返回的作业`id`，并在以下位置轮询获取作业状态终结点：
合理的时间间隔（例如，每隔几秒）。
3. 当`status`为`QUEUED`或`IN_PROGRESS`时，继续显示进度状态
在UI中。
4. 当`status`变为`COMPLETED`时，请使用`result.downloadUrl`让
管理员在`expiresAt`次通过之前下载报告。
5. 当`status`变为`FAILED`时，将`error`呈现给管理员并允许他们
重试。
