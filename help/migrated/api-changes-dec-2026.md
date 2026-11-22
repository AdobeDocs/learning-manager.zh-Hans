---
description: 了解如何使用讨论区订阅设置和订阅者API配置摘要电子邮件和管理讨论区订阅者
jcr-language: en_us
title: 2026年11月API更改
exl-id: 9b2d3856-810c-4352-bf18-667f698d4d70
source-git-commit: 4234f3cc3b9d77a7f9d197d2df2160ec62edd6d6
workflow-type: tm+mt
source-wordcount: '5724'
ht-degree: 4%
---

# 2026年12月API更改

## 用于讨论区讲师通知的API {#api-discussion-board-instructors}

本文介绍了支持讨论区讲师通知的新API。 可使用它们为讲师和同类经理订阅讨论区，并控制摘要电子邮件中显示的活动。

### API序列 {#api-sequence}

这些API分为两组。 `boardSubscriptionSettings` API在帐户级别工作。 订阅者API在讨论区级别工作。 按以下顺序使用API：

| 步骤 | API | 目的 | 范围 |
|---|---|---|---|
| 1 | [`POST /boardSubscriptionSettings`](#api-create-settings) | 设置帐户级别设置。 | `admin:write` |
| 2 | [`PATCH /boardSubscriptionSettings`](#api-update-settings) | 更新帐户级别设置。 | `admin:write` |
| 3 | [`GET /boardSubscriptionSettings`](#api-get-settings) | 检索帐户级别设置。 | `admin:read` |
| 4 | [`GET /boards/{id}/subscribers`](#api-get-subscribers) | 获取订阅讨论区的用户列表。 | `admin:read` |
| 5 | [`POST /boards/{id}/subscribers`](#api-subscribe-users) | 为用户订阅讨论区。 | `admin:write` |
| 6 | [`DELETE /boards/{id}/subscribers/{userId}`](#api-unsubscribe-user) | 取消订阅讨论区的用户。 | `admin:write` |

### 身份验证和权限

任何通过OAuth进行身份验证且具有`admin:read`和`admin:write`作用域的人都可以调用这些API。 API使用以下OAuth范围：

* `admin:read`：列出订阅者和读取通知设置（`GET`个请求）。
* `admin:write`：创建或更改通知设置，以及添加或删除订阅者（`POST`、`PATCH`和`DELETE`个请求）。

>[!NOTE]
>
>发送通知后，将再次检查讨论区访问权限。 如果订户无法访问板，则跳过该板的传送，但保留订阅。 如果访问返回，则恢复传递。

### 限制和注意事项

* 可以添加的订阅者数量受限制。
* 摘要作为单个电子邮件发送，没有分页，电子邮件正文有大小限制。 对于活动量大的讨论区，请选择一个摘要频率，使每封电子邮件都易于管理，例如每6小时一次。
* 摘要链接仅对登录的用户打开帖子、评论或回复。

## 用于创建帐户级别设置的API {#api-create-settings}

### API的目的 {#purpose-create-settings}

首次使用此API为讨论区订阅通知设置帐户级别设置。 这些设置控制如何在整个帐户中生成通知摘要：

* 哪些讨论区事件会生成通知。
* 发送摘要电子邮件的频率。
* 是否包括帖子、评论、回复和投票。

要在之后更改设置，请使用[`PATCH /boardSubscriptionSettings`](#api-update-settings)。

### 端点 {#endpoint-create-settings}

```http
POST /primeapi/v2/boardSubscriptionSettings
```

| 属性 | 值 |
|---|---|
| 范围 | `admin:write` |
| 请求格式 | `application/vnd.api+json;charset=UTF-8` |
| 响应格式 | `application/vnd.api+json;charset=UTF-8` |

### 请求正文 {#request-body-create-settings}

将设置作为`boardSubscriptionSettings`资源的属性发送。

| 字段 | 类型 | 描述 |
|---|---|---|
| `notifyNewPost` | 布尔值 | 是否在将新帖子添加到讨论区时通知订户。 |
| `notifyComment` | 布尔值 | 将评论添加到帖子时是否通知订户。 |
| `notifyReply` | 布尔值 | 在评论中添加回复时是否通知订户。 |
| `digestFrequencyHours` | 整数 | 发送摘要电子邮件的频率（以小时为单位）。 有效值的范围从1到168（一周）。 例如，24个用户发送每日摘要，168个用户发送每周摘要。 |

### 示例请求 {#example-request-create-settings}

```bash
curl -X POST \
--header 'Content-Type: application/vnd.api+json;charset=UTF-8' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
-d '{
  "data": {
    "type": "boardSubscriptionSettings",
    "attributes": {
      "notifyNewPost": true,
      "notifyComment": true,
      "notifyReply": true,
      "digestFrequencyHours": 24
    }
  }
}' \
'https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings'
```

### 示例响应 — 201已创建 {#example-response-create-settings}

```json
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings"
  },
  "data": {
    "id": "1010",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "digestFrequencyHours": 24,
      "notifyComment": true,
      "notifyNewPost": true,
      "notifyReply": true
    }
  }
}
```

### 响应代码 {#response-codes-create-settings}

| 状态 | 含义 |
|---|---|
| 201 | 请求成功。 已创建帐户级别设置。 |
| 400 | 一般错误请求错误。 |
| 401 | 请求缺少有效的凭据，或由于凭据无效而拒绝访问。 |

## 用于更新帐户级别设置的API {#api-update-settings}

### API的目的 {#purpose-update-settings}

使用此API更新您使用[`POST /boardSubscriptionSettings`](#api-create-settings)创建的帐户级别设置。 例如，更改摘要频率或打开或关闭事件类型。

### 端点 {#endpoint-update-settings}

```http
PATCH /primeapi/v2/boardSubscriptionSettings
```

| 属性 | 值 |
|---|---|
| 范围 | `admin:write` |
| 请求格式 | `application/vnd.api+json;charset=UTF-8` |
| 响应格式 | `application/vnd.api+json;charset=UTF-8` |

### 请求正文 {#request-body-update-settings}

使用与创建API相同的格式发送要更改的属性： `notifyNewPost`、`notifyComment`、`notifyReply`和`digestFrequencyHours`。 不发送的属性保留其当前值。 有关每个属性的说明，请参阅用于创建帐户级别设置的[API](#api-create-settings)。

### 示例请求 {#example-request-update-settings}

```bash
curl -X PATCH \
--header 'Content-Type: application/vnd.api+json;charset=UTF-8' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
-d '{
  "data": {
    "type": "boardSubscriptionSettings",
    "attributes": {
      "notifyReply": true,
      "digestFrequencyHours": 12
    }
  }
}' \
'https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings'
```

### 示例响应 — 200 OK {#example-response-update-settings}

```json
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings"
  },
  "data": {
    "id": "1010",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "digestFrequencyHours": 12,
      "notifyComment": true,
      "notifyNewPost": true,
      "notifyReply": true
    }
  }
}
```

### 响应代码 {#response-codes-update-settings}

| 状态 | 含义 |
|---|---|
| 200 | 请求成功。 帐户级别设置已更新，响应包含当前设置。 |
| 400 | 一般错误请求错误。 |
| 401 | 请求缺少有效的凭据，或由于凭据无效而拒绝访问。 |

## 用于检索帐户级别设置的API {#api-get-settings}

### API的目的 {#purpose-get-settings}

当用户订阅讨论区时，Adobe Learning Manager可以通过摘要电子邮件通知他们该讨论区中的活动。 帐户级别设置用于确定触发通知的活动类型以及发送摘要的频率。

此API允许您检索这些设置。 使用它可显示应用程序中的当前通知配置，或在构建依赖于它们的功能之前验证设置。

### 端点 {#endpoint-get-settings}

```http
GET /primeapi/v2/boardSubscriptionSettings
```

| 属性 | 值 |
|---|---|
| 范围 | `admin:read` |
| 响应格式 | `application/vnd.api+json;charset=UTF-8` |

### 示例请求 {#example-request-get-settings}

```bash
curl -X GET \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings'
```

### 示例响应 — 200 OK {#example-response-get-settings}

```json
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings"
  },
  "data": {
    "id": "1010",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "digestFrequencyHours": 24,
      "notifyComment": true,
      "notifyNewPost": true,
      "notifyReply": true
    }
  }
}
```

### 资源架构 {#resource-schema-get-settings}

**`boardSubscriptionSettings`个属性**

| 字段 | 类型 | 描述 |
|---|---|---|
| `notifyNewPost` | 布尔值 | 是否在将新帖子添加到讨论区时通知订户。 |
| `notifyComment` | 布尔值 | 将评论添加到帖子时是否通知订户。 |
| `notifyReply` | 布尔值 | 在评论中添加回复时是否通知订户。 |
| `digestFrequencyHours` | 整数 | 发送摘要电子邮件的频率（以小时为单位）。 有效值的范围从1到168（一周）。 使用此值告诉用户摘要电子邮件的期望频率。 例如，当值为24时显示“每日”，当值为168时显示“每周”。 |

### 响应代码 {#response-codes-get-settings}

| 状态 | 含义 |
|---|---|
| 200 | 请求成功。 响应包含帐户级别讨论区订阅设置。 |
| 400 | 一般错误请求错误。 |
| 401 | 请求缺少有效的凭据，或由于凭据无效而拒绝访问。 |

### 在集成中使用此API {#integration-get-settings}

一个常见的用例是“通知首选项”屏幕，该屏幕显示了如何为帐户配置讨论区订阅电子邮件。

1. 加载应用程序的通知首选项屏幕时，调用`GET /boardSubscriptionSettings`。
1. 使用回应中的值，显示触发通知的活动类型以及发送摘要电子邮件的频率。

## 用于检索讨论区订阅者的API {#api-get-subscribers}

### API的目的 {#purpose-get-subscribers}

检索订阅特定讨论区的用户列表。 预订讨论区的用户会收到有关讨论区中新活动的通知。 此API返回当前订阅给定讨论区的用户，以及有关每个订阅的创建时间和创建者的详细信息。

使用此API可以在应用程序中显示订户列表，审计谁接收了讨论区的更新，或将讨论区订阅数据与外部系统同步。

响应会分页。 使用`page[offset]`和`page[limit]`查询参数在大型订户列表中移动。 返回的数据受调用用户在请求讨论区上的权限约束。

### 端点 {#endpoint-get-subscribers}

```http
GET /primeapi/v2/boards/{id}/subscribers
```

| 属性 | 值 |
|---|---|
| 范围 | `admin:read` |
| 响应格式 | `application/vnd.api+json;charset=UTF-8` |

### 参数 {#parameters-get-subscribers}

| 参数 | 在 | 必填项 | 默认 | 描述 |
|---|---|---|---|---|
| `id` | 路径 | 是 | 无 | 要检索其订户的讨论区的ID。 访问受调用方在讨论区上的权限约束。 |
| `page[offset]` | 查询 | 否 | 0 | 要返回的记录的起始位置。 |
| `page[limit]` | 查询 | 否 | 10 | 每页返回的订户数。 允许的最大值为200。 |

### 示例请求 {#example-request-get-subscribers}

```bash
curl -X GET \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://learningmanager.adobe.com/primeapi/v2/boards/1234/subscribers?page[offset]=0&page[limit]=50'
```

### 示例响应 — 200 OK {#example-response-get-subscribers}

```json
{
  "data": [
    {
      "id": "1234:5678",
      "type": "boardSubscriber",
      "attributes": {
        "boardId": 1234,
        "dateSubscribed": 1757000000000,
        "subscribedByUserId": 5678,
        "user": {
          "id": "5678",
          "name": "Jane Doe",
          "email": "jane.doe@example.com",
          "avatarUrl": "https://example.com/avatars/5678.png",
          "bio": "Learning enthusiast",
          "contentLocale": "en-US",
          "uiLocale": "en-US",
          "timeZoneCode": "PST",
          "userType": "INTERNAL",
          "state": "ACTIVE",
          "profile": "Learner",
          "roles": ["Learner"],
          "gamificationEnabled": true,
          "pointsEarned": 120,
          "pointsRedeemed": 20,
          "enrollOnClick": true,
          "preferredResolution": "720p",
          "lastLoginDate": "2026-09-23T18:12:04.000Z"
        }
      }
    }
  ]
}
```

### 资源架构 {#resource-schema-get-subscribers}

响应包含新资源`boardSubscriber`。 其属性包括`boardId`、`dateSubscribed`、`subscribedByUserId`和`user`。 嵌入式用户对象具有订户信息，如用户ID、名称、电子邮件、配置文件和角色，以及其他用户元数据。

**`boardSubscriber`个属性**

| 字段 | 类型 | 描述 |
|---|---|---|
| `id` | 字符串 | 订阅ID不透明。 |
| `type` | 字符串 | 资源类型。 |
| `boardId` | 编号 | 用户所订阅的讨论区的ID。 |
| `dateSubscribed` | 编号 | 用户订阅讨论区的时间戳。 |
| `subscribedByUserId` | 编号 | 创建订阅的用户的ID。 |
| `user` | 对象 | 订阅用户的详细信息（已嵌入，请参阅下文）。 |

**`user`（嵌入，在订阅服务器中）**

| 字段 | 类型 | 描述 |
|---|---|---|
| `id` | 字符串 | 不透明的用户ID。 |
| `name` | 字符串 | 用户的显示名称。 |
| `email` | 字符串 | 用户的电子邮件地址。 |
| `avatarUrl` | 字符串 | 用户个人资料图片的URL。 |
| `bio` | 字符串 | 用户简历。 |
| `binUserId` | 字符串 | 用户的内部标识符。 |
| `userUniqueId` | 字符串 | 帐户中用户的唯一标识符。 |
| `userType` | 字符串 | 用户的类型，例如，内部或外部。 |
| `state` | 字符串 | 用户帐户的当前状态。 |
| `profile` | 字符串 | 已分配给用户的配置文件。 |
| `roles` | 字符串数组 | 用户拥有的角色。 |
| `contentLocale` | 字符串 | 用户希望查看其内容的区域设置。 |
| `uiLocale` | 字符串 | 用于用户界面的区域设置。 |
| `timeZoneCode` | 字符串 | 为用户配置的时区。 |
| `preferredResolution` | 字符串 | 用户的首选视频分辨率。 |
| `enrollOnClick` | 布尔值 | 选择学习对象时是否自动注册用户。 |
| `gamificationEnabled` | 布尔值 | 是否为用户启用游戏。 |
| `pointsEarned` | 编号 | 用户获得的游戏总点数。 |
| `pointsRedeemed` | 编号 | 用户兑换的游戏点数总计。 |
| `lastLoginDate` | 字符串 | 用户最近登录的日期和时间。 |
| `fields` | 对象 | 自定义用户字段及其值。 |
| `metadata` | 对象 | 与用户关联的其他元数据。 |

### 响应代码 {#response-codes-get-subscribers}

| 状态 | 含义 |
|---|---|
| 200 | 请求成功。 响应包含讨论区的订户。 |
| 400 | 一般错误请求错误。 例如，讨论区ID或分页值格式不正确。 |
| 401 | 请求缺少有效的凭据，或由于凭据无效而拒绝访问。 |

### 在集成中使用此API {#integration-get-subscribers}

常见的用例是管理员或版主视图，它显示每位收到讨论区更新的人。

1. 视图加载时，请使用此适用于您的版面的讨论区ID和`page[limit]`值（最多200个）调用此端点。
1. 显示每个订阅服务器的`user.name`、`user.email`和`dateSubscribed`值。
1. 如果返回的记录数等于`page[limit]`，则可能会有更多的订阅者。 再次调用终结点，将`page[offset]`增大为页面大小，直到页面返回的记录少于请求的记录为止。

## 用于订阅用户讨论区的API {#api-subscribe-users}

### API的目的 {#purpose-subscribe-users}

为一个或多个用户订阅讨论区，以便他们收到讨论区的摘要电子邮件。 按用户ID、电子邮件地址（解析为帐户中的用户ID）或两者标识用户。 您可以在单个请求中添加多个用户。 请参阅[批量订阅](#bulk-subscriptions)。

### 端点 {#endpoint-subscribe-users}

```http
POST /primeapi/v2/boards/{id}/subscribers
```

| 属性 | 值 |
|---|---|
| 范围 | `admin:write` |
| 请求格式 | `application/vnd.api+json;charset=UTF-8` |
| 响应格式 | `application/vnd.api+json;charset=UTF-8` |

### 参数 {#parameters-subscribe-users}

| 参数 | 在 | 必填项 | 描述 |
|---|---|---|---|
| `id` | 路径 | 是 | 要订阅用户的ID板。 |

### 请求正文 {#request-body-subscribe-users}

将用户作为`boardSubscriberBulkRequest`资源的属性发送。 至少需要`userIds`或`emails`中的一个。

| 字段 | 类型 | 描述 |
|---|---|---|
| `data.attributes.userIds` | 数组 | 要订阅的用户的ID。 |
| `data.attributes.emails` | 字符串数组 | 要订阅的用户的电子邮件地址。 每个地址都被解析为帐户中的用户ID。 |

### 示例请求 {#example-request-subscribe-users}

```bash
curl -X POST \
--header 'Content-Type: application/vnd.api+json;charset=UTF-8' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
-d '{
  "data": {
    "type": "boardSubscriberBulkRequest",
    "attributes": {
      "userIds": [
        1234,
        5678
      ],
      "emails": [
        "abc@xyz.com"
      ]
    }
  }
}' \
'https://learningmanager.adobe.com/primeapi/v2/boards/1010/subscribers'
```

### 示例响应 — 207 Multi-Status {#example-response-subscribe-users}

```json
{
  "added": [
    {
      "userId": "12345",
      "status": "SUCCESS"
    }
  ],
  "failed": [
    {
      "userId": "78910",
      "errorCode": "NO_BOARD_ACCESS"
    }
  ]
}
```

**响应属性**

| 字段 | 类型 | 描述 |
|---|---|---|
| `added` | 阵列 | 已订阅的用户。 每个条目都有一个`userId`和一个`status`。 此处还将已订阅的用户报告为成功。 |
| `failed` | 阵列 | 无法订阅的用户。 每个条目都有一个`userId`和一个`errorCode`，例如`NO_BOARD_ACCESS`。 |

### 响应代码 {#response-codes-subscribe-users}

| 状态 | 含义 |
|---|---|
| 207 | 多状态。 已处理请求，响应将列出`added`和`failed`中每个用户的结果。 |
| 400 | 一般错误请求错误。 |
| 401 | 请求缺少有效的凭据，或由于凭据无效而拒绝访问。 |
| 404 | 找不到所请求的资源，例如审计委员会。 |
| 409 | 讨论区处于非活动状态、已删除或已弃用，因此整个请求将被拒绝。 |

### 批量订阅 {#bulk-subscriptions}

使用批量订阅可在单个请求中将多个用户添加到讨论区。 批量订阅有助于减少管理订阅者所需的API调用数量。 在下列情况下很有用：

* 讲师管理多个同类群组。
* 同类经理需要访问许多讨论区。
* 外部系统批量同步主板订阅。
* 在组群创建期间，需要订阅多名讲师。

#### 批量添加行为

批量请求可以包含用户ID、电子邮件地址，也可以同时包含两者。 每个用户被独立处理。

#### 幂等行为

批量添加是幂等的。 如果用户已订阅讨论区，则请求会成功，不会创建重复订阅，现有订阅将保持不变。 这样，客户端可以安全地重试请求。

#### 部分成功

有些用户可以订阅，而有些用户验证失败。 操作不会失败，因为一个或多个用户无效。

| 大小写 | 结果 |
|---|---|
| 用户存在并可访问该讨论区 | 成功 |
| 用户已订阅 | 成功 |
| 用户无权访问该讨论区 | 失败(`NO_BOARD_ACCESS`) |
| 用户不存在 | 失败 |
| 用户处于非活动状态 | 失败 |
| 已删除用户 | 失败 |

#### 响应格式

批量订阅返回HTTP 207 Multi-Status，每个用户有`added`个结果和`failed`个结果，如[示例响应](#example-response-subscribe-users)所示。

#### 常见的验证失败

* **用户无权访问该讨论区。** 如果用户无法看到讨论区，则为该用户返回`NO_BOARD_ACCESS`。 其余用户将继续正常处理。
* **讨论区处于非活动状态、已删除或已弃用。** 如果讨论区不符合订阅条件，则请求会因HTTP 409冲突而被拒绝。
* **用户无效。** 如果用户帐户不存在、不活动或已删除，则操作将返回该用户的失败条目。

## 用于从讨论区取消订阅用户的API {#api-unsubscribe-user}

### API的目的 {#purpose-unsubscribe-user}

取消订阅讨论区中的用户。 删除订阅后，用户将不再收到该讨论区的通知和摘要电子邮件。

### 端点 {#endpoint-unsubscribe-user}

```http
DELETE /primeapi/v2/boards/{id}/subscribers/{userId}
```

| 属性 | 值 |
|---|---|
| 范围 | `admin:write` |
| 响应格式 | `application/vnd.api+json;charset=UTF-8` |

### 参数 {#parameters-unsubscribe-user}

| 参数 | 在 | 必填项 | 描述 |
|---|---|---|---|
| `id` | 路径 | 是 | 讨论区的ID。 |
| `userId` | 路径 | 是 | 要取消订阅的用户的ID。 |

### 示例请求 {#example-request-unsubscribe-user}

```bash
curl -X DELETE \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://learningmanager.adobe.com/primeapi/v2/boards/1234/subscribers/5678'
```

### 示例响应 — 204 No Content {#example-response-unsubscribe-user}

响应没有正文。

### 响应代码 {#response-codes-unsubscribe-user}

| 状态 | 含义 |
|---|---|
| 204 | 请求成功。 用户已从讨论区取消订阅。 |
| 400 | 一般错误请求错误。 |
| 401 | 请求缺少有效的凭据，或由于凭据无效而拒绝访问。 |
| 404 | 未找到请求的资源，例如讨论区或订阅。 |

## 书签API订购和已停用内容处理 {#bookmark-api-ordering-retired-content}

### API的目的

学习者将想要重新访问的培训添加为书签。 在此更改之前，书签API会不按特定顺序返回书签。 集成（尤其是无头实现）无法首先显示最近保存的书签。 具有许多书签的学习者必须滚动浏览较旧的项目才能找到最近的项目。

已停用学习对象的书签也会保留在列表中。 选择一个导致出现“找不到页面”错误。

此更改以两种方式改进书签API：

* 书签按时间顺序返回，最新在前。
* 不再返回已弃用的学习对象的书签。

未引入新的端点、参数或响应属性。 现有集成将继续运行，且不会发生更改。

### 基本URL和约定

书签API使用以下基本路径和约定：

| 项目 | 值 |
|---|---|
| 基本路径 | `/primeapi/v2` |
| 内容类型 | `application/vnd.api+json` |
| 身份验证 | 具有学习者读取访问权限的OAuth令牌 |
| 默认顺序 | 最新的书签在前 |
| 新参数 | 无 |
| 响应结构 | 未更改 |

### 端点

#### 返回书签的端点

以下端点按新顺序返回书签：

| 端点 | 返回 |
|---|---|
| `GET /primeapi/v2/learningObjects?filter.bookmarks=true` | 学习者已添加书签的学习对象 |
| `GET /primeapi/v2/bookmarks` | 学习者的书签 |

#### 按顺序获取已添加书签的学习对象

`GET /primeapi/v2/learningObjects?filter.bookmarks=true`

<!-- Content Review by Claude: Please confirm the endpoint list. The dev-to-QE hand-off confirms ordering for GET /learningObjects?filter.bookmarks=true. The PRD (ALMER-442) also lists GET /primeapi/v2/bookmarks. Please also confirm the OAuth scope. -->

返回呼叫的学习者已添加书签的学习对象。 最近添加书签的项目在前，最早添加书签的项目在后。

**作用域：**&#x200B;学习者读取权限

终结点接受以下查询参数：

| 参数 | 在 | 必填项 | 描述 |
|---|---|---|---|
| `filter.bookmarks` | 查询 | 是 | 设置为`true`可仅返回学习者已添加书签的学习对象 |

**示例请求**

```http
GET /primeapi/v2/learningObjects?filter.bookmarks=true
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

**示例200 OK响应**

学习者首先在Adobe Analytics中将“开始使用”标记为书签，其次在Adobe Analytics中生成Workspace项目，最后在Workspace中生成“高级分段”。 响应按从最新到最旧的顺序列出它们。 为简洁起见，省略了其他属性。

```json
{
  "data": [
    {
      "id": "course:2400162",
      "type": "learningObject",
      "attributes": {
        "name": "Advanced Segmentation in Adobe Analytics"
      }
    },
    {
      "id": "course:2400160",
      "type": "learningObject",
      "attributes": {
        "name": "Building Workspace Projects"
      }
    },
    {
      "id": "course:2400159",
      "type": "learningObject",
      "attributes": {
        "name": "Getting Started with Adobe Analytics"
      }
    }
  ]
}
```

>[!NOTE]
>
>新顺序是默认行为，适用于所有帐户。

### 书签订购

#### 书签的排序方式

书签按学习者保存日期排序，从最新到最旧。 例如，如果学习者将课程A、课程B和课程C先后加入书签，则响应信息会先列出课程C、课程B再列出课程A。

如果某个已添加书签的学习对象显示在第10位，之后又“未保存”，则该学习对象将首先显示在列表中，成为最近的已添加书签的学习对象。

以前在客户端上排序书签的集成可以删除该逻辑，并按返回顺序显示结果。

### 弃用的内容处理

#### 如何处理已弃用的学习对象

无论学习者是否已注册学习对象，在响应中都不会返回已弃用学习对象的书签。

已标记书签的已弃用学习对象将不会显示，除非学习者注册了该对象。

学习者不会再看到导致“找不到页面”错误的书签。 书签将在结果中隐藏，不会被删除。

### 兼容性

此更改不会破坏现有API使用者：

* 端点及其参数保持不变。
* 响应结构保持不变，不会添加或删除任何属性。
* 只有结果的顺序以及排除已弃用的学习对象不同于以前的行为。

### 在集成中使用此API

无头学习者体验中的常见用例是“保存以备后用”列表。 您希望学习者首先查看他们最近的书签，而不包含已停用内容的链接。

1. 当学习者打开列表时呼叫`GET /primeapi/v2/learningObjects?filter.bookmarks=true`。
2. 按照返回的顺序显示学习对象。 第一个项目是最近添加的书签。
3. 删除作为解决方法添加的任何客户端排序或已弃用的筛选。
4. 使用响应中的项目数显示书签数。 已弃用学习对象的书签不再包含在内。

### 学习者应用程序中的学习者合规性小组件支持多注册实例API {#api-multienrolled-instances-lc-widget}

公共API通过现有注册端点上的可选查询参数支持此行为。 如果忽略该参数，则API会返回与之前相同的结果，因此现有集成（包括无头实现）将继续工作，保持不变。

**端点**

GET/primeapi/v2/enrollments

**查询参数**

includeMultiInstanceEnrollments（可选）

**查询**

https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page\[limit\]=10&filter.loTypes=course&includeHierarchicalEnrollments=false&includeMultiInstanceEnrollments=true&sort=dateEnrolled

**值**

对。 默认情况下为False。

**响应正文**

{

&quot;links&quot;： {

&quot;self&quot;： &quot;[https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page\[limit\]=10&amp;filter.loTypes=course&amp;sort=dateEnrolled&amp;includeHierarchicalEnrollments=false&amp;includeMultiInstanceEnrollments=true](https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page%5blimit%5d=10&filter.loTypes=course&sort=dateEnrolled&includeHierarchicalEnrollments=false&includeMultiInstanceEnrollments=true)&quot;，

&quot;next&quot;： &quot;[https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page\[limit\]=10&amp;filter.loTypes=course&amp;sort=dateEnrolled&amp;includeHierarchicalEnrollments=false&amp;includeMultiInstanceEnrollments=true&amp;page\[cursor\]=eyJb3Vyc2VNdWx0aSI6MCwiam9iQWlkIjowLCJb3Vyc2UiOjEwLCJsLCJzwfybmluZ1Byb2dyYW0iOjAsImNlcnRpZmljYXRpb24iOjB9](https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page%5blimit%5d=10&filter.loTypes=course&sort=dateEnrolled&includeHierarchicalEnrollments=false&includeMultiInstanceEnrollments=true&page%5bcursor%5d=eyJjb3Vyc2VNdWx0aSI6MCwiam9iQWlkIjowLCJjb3Vyc2UiOjEwLCJsZWFybmluZ1Byb2dyYW0iOjAsImNlcnRpZmljYXRpb24iOjB9)&quot;

},

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：15067_30122_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;completionDeadline&quot;： &quot;2026-02-24T10:50:45.000Z&quot;，

&quot;enrollmentSource&quot;： &quot;MGR_APPROVAL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;PENDING_APPROVAL&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：15067&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：15067_30122&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：15067_30122_41715_1_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

},

{

&quot;id&quot;： &quot;course：1108800_1997400_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;enrollmentSource&quot;： &quot;SELF_ENROLL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;PENDING_APPROVAL&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：1108800&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：1108800_1997400&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：1108800_1997400_2174574_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

},

{

&quot;id&quot;： &quot;course：2027668_3707328_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;enrollmentSource&quot;： &quot;MGR_APPROVAL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;PENDING_APPROVAL&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2027668&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2027668_3707328&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：2027668_3707328_2665897_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

},

{

&quot;id&quot;： &quot;course：2030067_3709862_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;enrollmentSource&quot;： &quot;MGR_APPROVAL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;PENDING_APPROVAL&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2030067&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2030067_3709862&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：2030067_3709862_2668467_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

},

{

&quot;id&quot;： &quot;course：3081896_5749155_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;enrollmentSource&quot;： &quot;MGR_APPROVAL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;PENDING_APPROVAL&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：3081896&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：3081896_5749155&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：3081896_5749155_3737554_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

},

{

&quot;id&quot;： &quot;course：3081896_5749155_3737555_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

},

{

&quot;id&quot;： &quot;course：2037893_3717940_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;enrollmentSource&quot;： &quot;MGR_APPROVAL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;PENDING_APPROVAL&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2037893&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2037893_3717940&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：2037893_3717940_3676856_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

},

{

&quot;id&quot;： &quot;course：3049434_5713130_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;completionDeadline&quot;： &quot;2020-05-05T18:29:59.000Z&quot;，

&quot;enrollmentSource&quot;： &quot;MGR_APPROVAL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;PENDING_APPROVAL&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：3049434&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：3049434_5713130&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：3049434_5713130_3693595_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

},

{

&quot;id&quot;： &quot;course：2001397_3679403_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;enrollmentSource&quot;： &quot;MGR_APPROVAL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;PENDING_APPROVAL&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2001397&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2001397_3679403&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：2001397_3679403_2635974_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

},

{

&quot;id&quot;： &quot;course：2037862_3717900_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;enrollmentSource&quot;： &quot;MGR_APPROVAL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;PENDING_APPROVAL&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2037862&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2037862_3717900&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：2037862_3717900_3676816_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

},

{

&quot;id&quot;： &quot;course：2037837_3717863_3400468&quot;，

&quot;type&quot;： &quot;learningObjectInstanceEnrollment&quot;，

&quot;attributes&quot;： {

&quot;completionDeadline&quot;： &quot;2020-02-29T18:29:59.000Z&quot;，

&quot;enrollmentSource&quot;： &quot;SELF_ENROLL&quot;，

&quot;hasPassed&quot;： false，

&quot;progressPercent&quot;： 0，

&quot;score&quot;： 0，

&quot;state&quot;： &quot;OTHER&quot;

},

&quot;relationships&quot;： {

&quot;learner&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;3400468&quot;，

&quot;type&quot;： &quot;user&quot;

}

},

&quot;learningObject&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2037837&quot;，

&quot;type&quot;： &quot;learningObject&quot;

}

},

&quot;loInstance&quot;： {

&quot;data&quot;： {

&quot;id&quot;： &quot;course：2037837_3717863&quot;，

&quot;type&quot;： &quot;learningObjectInstance&quot;

}

},

&quot;loResourceGrades&quot;： {

&quot;data&quot;： \[

{

&quot;id&quot;： &quot;course：2037837_3717863_3597363_0_3400468&quot;，

&quot;type&quot;： &quot;learningObjectResourceGrade&quot;

}

\]

}

}

}

\]

}

## 学习路径注册的上次访问日期 {#api-last-access-date-lp-enrollment}

Adobe Learning Manager可让您在学习路径注册上存储自定义元数据，如上次访问日期。 您可以通过API设置和读取元数据。 这可以帮助您跟踪对已分配的学习路径的时限访问。

## 关于学习路径注册元数据

您已经通过API为课程注册设置上次访问日期。 该日期控制学习者可访问课程的时间。 学习路径注册现在支持通用元数据字段，因此您可以存储上次访问日期或任何其他要跟踪的值。

您无需打开该字段或发送特殊标头。 在您设置该字段之前，该字段为空。

>[!NOTE]
>
>元数据用于您自己的跟踪。 当学习者打开学习路径或其课程时，Adobe Learning Manager不会更新此信息，并且不控制对学习路径的访问。 它也不会传播到路径中的课程。 每个课程都保留自己的上次访问日期，因此同一路径中的课程可以有不同的日期。 继续单独管理课程级别的访问过期。

### 元数据规则 {#metadata-rules}

* 值必须是JSON对象。 字符串、数字、布尔值或数组返回400错误，并显示消息`metadata must be a JSON object`。
* 您可以使用任意键。 Adobe Learning Manager不验证键或值，也不强制使用日期格式。 本文中的示例使用与课程日期相同的格式 — 纪元毫秒。
* PATCH请求将替换整个元数据对象。 它不会与现有值合并，因此会删除您忽略的键。
* 设置`"metadata": null`将清除所有元数据并返回200。
* 具有空`attributes`对象或不带`metadata`键的请求使存储的元数据保持不变。
* 如果未设置元数据，或者在清除元数据后，`metadata`键不在响应中。

## 在现有注册上设置元数据

使用管理令牌。

向以下端点发送PATCH请求，其中`{enrollmentId}`是学习路径注册ID，格式为`learningProgram:<lpId><instanceId><userId>`：

```
PATCH /primeapi/v2/users/{userId}/enrollments/{enrollmentId}
```

使用此请求正文：

```json
{
  "data": {
    "id": "<enrollmentId>",
    "type": "learningObjectInstanceEnrollment",
    "attributes": {
      "metadata": {
        "lastAccessDate": 1745337600000
      }
    }
  }
}
```

### 在注册学习者时设置元数据

使用管理令牌。

发送包含学习POST和实例ID的实例请求。 在请求正文中包含可选的`metadata`对象。

```
POST /primeapi/v2/users/{userId}/enrollments?loId=<lpId>&loInstanceId=<instanceId>
```

* 如果`metadata`不是JSON对象，则请求返回400，且用户未注册。
* 如果用户已注册，则请求将返回200，且不会更改任何内容。 要更改现有注册的元数据，请使用PATCH请求。
* 响应不包括元数据。 发送GET请求以阅读它。

### 检索元数据

您可以使用管理员或学习者令牌检索元数据。 请求因标记类型而异。

| 令牌 | 获取一个注册 | 列出学习路径注册 |
|---|---|---|
| 管理员 | `GET /primeapi/v2/users/{userId}/enrollments/{enrollmentId}` | `GET /primeapi/v2/users/{userId}/enrollments?filter.loTypes=learningProgram` |
| Prime 中的讲师 | `GET /primeapi/v2/enrollments/{enrollmentId}`<br>`GET /primeapi/v2/learningObjects/{id}?include=enrollment` | `GET /primeapi/v2/enrollments?filter.loTypes=learningProgram` |

>[!NOTE]
>
>`include=enrollment`参数仅适用于学习者令牌。 不支持管理员角色。

此响应返回具有学习路径注册的`metadata`对象。

### 在无头门户和外部门户中使用元数据

外部门户和集成使用相同的API调用。 使用与您的门户使用的令牌匹配的请求。

* **显示门户中的值：**&#x200B;从上表中发送令牌类型的GET请求，并从响应中读取`metadata`对象。
* **从外部系统更新值，例如商务平台：**&#x200B;使用管理令牌发送PATCH请求。

## 作业API：使用generateCustomReport导出Report Builder报告 {#api-job-report-builder-exports}

Adobe Learning Manager 2026年12月版将新的作业类型`generateCustomReport`添加到作业API。 通过传递报告ID，可使用它自动导出您在Report Builder中创建的任何报告。

结合Report Builder中新的L2测验数据集，您现在可以：

* 在单个报告中导出多个课程和模块的问题级别(L2)测验数据，而不是为每个课程运行一次`generateQuizReport`。
* 自动执行定期导出，例如，每天增量导出到数据仓库或BI工具。

现有作业类型（包括`generateQuizReport`）保持不变。

### 准备事项

* 您必须是管理员。 `generateCustomReport`作业类型不适用于其他角色。
* 首先创建报告并以Report Builder保存。 对于L2测验数据，请从L2测验数据集构建报告，并包含您需要的问题级别字段，如问题文本、学习者响应、分数、尝试次数和答疑日期。
* 记下报告的ID。 你将其作为`reportId`在请求中传递。

### 创建作业

**端点**

```
POST /primeapi/v2/jobs
```

**请求正文**

```json
{
  "data": {
    "type": "job",
    "attributes": {
      "description": "Daily L2 quiz export",
      "jobType": "generateCustomReport",
      "payload": {
        "reportId": "1478"
      }
    }
  }
}
```

**属性**

| 属性 | 必填项 | 描述 |
|---|---|---|
| `jobType` | 是 | 必须为`generateCustomReport`。 |
| `payload.reportId` | 是 | 保存的Report Builder报告的ID（字符串）。 必须是正数整数，以字符串形式传递，例如`"1478"`。 发送数字、0、负数、小数或空值将返回错误。 |
| `description` | 否 | 您为工作选择的描述。 |
| `callbackUrl` | 否 | 作业完成时调用的URL。 工作方式与其他作业类型相同。 |
| `payload.filters` | 否 | 请参阅以下部分。 |

### 覆盖日期过滤器（可选） {#override-date-filter}

```json
"payload": {
  "reportId": "1478",
  "filters": [
    { "columnName": "L2 Quiz - Response - Timestamp", "operator": "gte", "val": "2026-11-15T00:00:00.000Z" }
  ]
}
```

* 它仅为此运行替换报告的已保存日期过滤器。 导出将涵盖`val`（包括），直到作业运行为止。
* `columnName`使用格式`<Dataset name> - <Field name>`。 它必须与报告中已存在的日期过滤器匹配。 它不区分大小写，但间距和连字符必须完全匹配。
* `operator`是可选的，仅允许`gte`。
* `val`是最近7天内的ISO 8601 UTC时间。 时间被截断为秒。
* 您可以覆盖多个列。 空列表表示使用保存的筛选器。
* 用例：从前一个增量导出结束的地方开始的每日增量导出。

### 创建作业时返回的错误

| 原因 | 消息 |
|---|---|
| 缺少`reportId` | `reportId is required` |
| `reportId`不是正整数字符串 | `reportId must be a positive integer string` |
| 日期不采用ISO格式 | `filters.val must be in ISO format, e.g. 2020-01-01T18:30:00.000Z` |
| 超过7天或以后的日期 | `filters.val must be within the last 7 days` |
| `gte`以外的运算符 | `filters.operator must be gte` |
| 同一列被指定两次 | `Duplicate filter column: <column>` |
| 列不是报告中的过滤器 | `Unsupported custom report filter column: <column>` |
| 同一报告的作业仍在运行 | `There exists an similar job with id = <jobId> which has not finished yet` |

作业运行时，仅会检测到已保存报告定义的问题。 在这种情况下，作业状态将变为`Failed`，并且不返回任何原因。

### 报告要求

如果报告不满足以下条件，则作业失败，并显示错误消息：

* 报告定义包括相关日期过滤器，例如，最近7天。
* 报告中的每个日期过滤器必须涵盖7天或更短时间，而不仅仅是1天。
* 不支持具有设置起始日期和结束日期的固定日期范围，因此作业将失败。
* 没有日期筛选器的报告将失败。 这包括基于无日期字段的数据集构建的报告。

>[!NOTE]
>
>将立即验证POST请求。 使用HTTP 400拒绝无效请求，原因位于`source.info`中。

### 检查作业状态并下载报告

**端点**

```
GET /primeapi/v2/jobs/{jobId}
```

响应使用与其他作业类型相同的结构。 作业完成后，`status.code`为`Completed`，`status.data.s3Url`包含下载链接。

```json
{
  "data": {
    "type": "job",
    "id": "12345",
    "attributes": {
      "jobType": "generateCustomReport",
      "payload": {
        "reportId": "1478"
      },
      "status": {
        "code": "Completed",
        "data": {
          "s3Url": "valid for 7 days"
        }
      }
    }
  }
}
```

API返回`Submitted`、`Completed`和`Failed`。 该文件是名为`report.csv`的单个CSV。

>[!NOTE]
>
>下载URL的有效期为七天。 作业完成后立即下载文件。

>[!IMPORTANT]
>
>任何具有该链接的人员无需登录即可下载该文件。 按照处理链接所包含的数据的方式来处理链接。

**失败的作业示例**

```json
"status": { "code": "Failed" }
```

### 限制

一次只能运行一个报表的一个`generateCustomReport`作业。 第二个请求被拒绝，直到第一个请求完成。

### L2测验报告输出

从Report Builder的L2测验数据集生成报告并使用`generateCustomReport`导出时，输出具有以下特性：

* 输出是名为`report.csv`的单个CSV文件。 模块是文件中的列。 如果选择课程，报告仅返回其测验模块。
* 每行代表学习者在一次尝试中对一个问题的响应。
* 数据按标准Report Builder间隔（大约每15分钟）刷新。
* 日期和时间值采用您帐户的时区。 列标题显示时区，例如，`L2 Quiz - Response - Timestamp (America/Argentina/Salta)`。

### L2测验数据集中的字段

| 类别 | 字段 |
|---|---|
| Prime 中的讲师 | 用户 ID |
| 课程 | 课程ID、课程实例ID、课程名称 |
| 模块 | 模块ID、模块名称、模块版本 |
| 问题 | 问题ID、问题文本、正确答案、互动类型 |
| 响应 | 响应答案，达到的分数，最大可能的分数，正确，响应时间戳 |
| 尝试次数 | 尝试次数 |

>[!NOTE]
>
>L2测验数据集未链接到其他Report Builder数据集。 学习者姓名、电子邮件、经理和自定义属性在此报告中不可用。 若要将某行与学习者进行匹配，请使用“用户ID”。

也可以导出使用`generateCustomReport`在其他Report Builder数据集上构建的报告。 输出中的可用字段取决于数据集。

## 用于创建和管理Zoom连接器的API

在Adobe Learning Manager中使用这些API管理Zoom连接。 您可以检索现有连接、保存Zoom凭据、创建或更新连接、配置用户组和自定义角色的访问权限，以及启用或禁用连接。

### 设置缩放连接器API

设置和管理缩放连接器需要四个API调用。 按以下顺序制作它们：

| 步骤 | API | 功能 |
|---|---|---|
| 1 | `POST /ctr/authcred/uuid/20012` | 保存Zoom凭据。 |
| 2 | `POST /ctr/app/esconnect` | 创建“缩放”连接或更新现有连接。 |
| 3 | `PUT /ctr/xtsa/{connectionId}/access` | 设置可以使用连接的用户组和自定义角色。 |
| 4 | `POST /ctr/xtsas/{connectionId}/enable` | 启用或禁用连接。 |

>[!NOTE]
>
>这些API使用已登录的集成管理员会话。 他们不使用API密钥或OAuth令牌。

### 基本URL和约定

Zoom连接器API使用以下约定：

| 项目 | 值 |
|---|---|
| 基本URL | `https://learningmanagerstage1.adobe.com` |
| 内容类型 | `application/json` |
| 身份验证 | 已登录集成管理员的会话 |
| 所需的标头 | `content-type`、`accept`、`x-acap-caller-role: ROLE_INTEGRATIONADMIN`、`x-csrf-token`和`Cookie` |
| 用于缩放的集成目录UUID | `20012` |
| 连接限制 | 50个缩放连接 |

`x-csrf-token`值已作为`csrfToken`嵌入到“集成管理员”页面HTML中。 `Cookie`标头包含已登录管理员的会话Cookie。

### 准备事项

- 以集成管理员身份登录。
- 创建Zoom服务器到服务器OAuth应用程序。 请注意其客户端ID、客户端密钥和帐户ID。 您还需要提供Zoom超级管理员的电子邮件地址。
- 呼叫`GET /ctr/xtsas/canCreateAccount/25`。 如果您可以创建另一个Zoom连接，它将返回`true`。

### 第1步：保存Zoom凭据 {#save-credentials}

在创建或更新连接之前调用此API。 它存储连接器用于连接到Zoom的凭据。

```
POST /ctr/authcred/uuid/20012
```

若要更新现有连接，请添加`connectionId`查询参数：

```
POST /ctr/authcred/uuid/20012?connectionId={connectionId}
```

请求正文是作为JSON文本的凭据。 它是一个包含JSON的JSON字符串，而不是嵌套对象。 包括外引号。

| 键 | 描述 |
|---|---|
| `clientId` | Zoom应用程序的客户端ID。 |
| `clientSecret` | Zoom应用程序的客户端密钥。 此值是敏感的。 |
| `accountId` | 缩放帐户ID。 |
| `superAdmin` | Zoom超级管理员的电子邮件地址。 |

请求正文示例：

```
"{\"clientId\":\"<ZOOM_CLIENT_ID>\", \"clientSecret\":\"<ZOOM_CLIENT_SECRET>\", \"accountId\":\"<ZOOM_ACCOUNT_ID>\", \"superAdmin\":\"<ADMIN_EMAIL>\"}"
```

示例`200 OK`响应：

```json
{
  "code": 0,
  "description": "Success"
}
```

`code: 0`表示已保存凭据。

### 第2步：创建或更新Zoom连接 {#create-connection}

此API可创建Zoom连接。 同一端点还更新现有连接。

```
POST /ctr/app/esconnect
```

请求正文包含以下字段：

| 字段 | 必填项 | 描述 |
|---|---|---|
| `UUID` | 是 | 集成目录UUID。 使用`20012`进行缩放。 |
| `listOfConnections` | 是 | 要创建的连接。 发送一个项目。 |
| `listOfConnections[].name` | 是 | 连接器的显示名称，例如`Zoom_Partner_X`。 |
| `listOfConnections[].tag` | 是 | 创建连接器时发送空字符串(`""`)。 更新一个时省略它。 |
| `listOfConnections[].credentialsJson` | 是 | 凭据为JSON文本。 使用在步骤1中发送的相同字符串。 |
| `listOfConnections[].schedules` | 是 | 同步计划。 发送`objectUUID` 10002、`priority` 1和`type` 1。 |
| `listOfConnections[].id` | 仅更新 | 要更新的连接的ID，例如`3474737`。 |

请求正文示例：

```json
{
  "UUID": 20012,
  "listOfConnections": [
    {
      "name": "Zoom_Example",
      "tag": "",
      "credentialsJson": "{\"clientId\":\"<ZOOM_CLIENT_ID>\", \"clientSecret\":\"<ZOOM_CLIENT_SECRET>\", \"accountId\":\"<ZOOM_ACCOUNT_ID>\", \"superAdmin\":\"<ADMIN_EMAIL>\"}",
      "schedules": [
        { "objectUUID": 10002, "priority": 1, "type": 1 }
      ]
    }
  ]
}
```

示例`200 OK`响应：

```json
[3474737]
```

响应是包含新连接ID的JSON数组。 在步骤3和4以及任何后续呼叫中使用此ID。

### 创建和更新比较

| 差值 | 创建 | 更新 |
|---|---|---|
| `listOfConnections[].id` | 未发送 | 连接Id |
| `listOfConnections[].tag` | `""` | 未发送 |
| 步骤1中的凭据调用 | `POST /ctr/authcred/uuid/20012` | `POST /ctr/authcred/uuid/20012?connectionId={id}` |

### 步骤3：设置可以使用连接的人员 {#set-access}

此API定义哪些用户组和自定义角色可以使用连接。

```
PUT /ctr/xtsa/{connectionId}/access
```

路径对一个连接使用单数`xtsa`。 plural `xtsas`是连接的集合。

请求正文是一个JSON数组。 每个项目都授予对一个用户组或自定义角色的访问权限。

| 字段 | 必填项 | 描述 |
|---|---|---|
| `accessType` | 是 | `USER_GROUP`或`CUSTOM_ROLE`。 |
| `accessId` | 是 | 用户组或自定义角色的ID（字符串）。 |

请求正文示例：

```json
[
  { "accessType": "USER_GROUP", "accessId": "<groupId>" },
  { "accessType": "CUSTOM_ROLE", "accessId": "<roleId>" }
]
```

保存访问列表时，API返回不带正文的`204 No Content`。

>[!NOTE]
>
>该请求将替换整个访问列表。 它没有附加在它后面。 身体外的任何东西都会失去访问权限。 若要删除所有访问权限，请发送空数组(`[]`)。

### 步骤4：启用或禁用连接 {#enable-disable}

此API可打开或关闭连接。 创建连接后，每当需要更改其状态时，都使用它。

```
POST /ctr/xtsas/{connectionId}/enable
```

路径使用复数`xtsas`，例如列表和删除调用。 步骤3中的访问调用使用单数`xtsa`。

| 路径参数 | 类型 | 描述 |
|---|---|---|
| `connectionId` | 编号 | 连接的ID。 它是`GET /ctr/xtsas`返回的`id`，并且在步骤2中返回了ID。 |

请求正文包含以下字段：

| 字段 | 类型 | 必填项 | 描述 |
|---|---|---|---|
| `objectUUID` | 编号 | 是 | 连接的同步对象。 使用`10002`，与您在第2步中的`schedules[].objectUUID`中发送的值相同。 |
| `operation` | 编号 | 是 | 发送`1`。 |
| `val` | 布尔值 | 是 | 连接的新状态。 发送`false`以禁用连接。 发送`true`以启用它。 |

禁用连接的请求正文示例：

```json
{
  "objectUUID": 10002,
  "operation": 1,
  "val": false
}
```

启用连接的请求正文示例：

```json
{
  "objectUUID": 10002,
  "operation": 1,
  "val": true
}
```

禁用连接的请求示例：

```bash
curl -X POST 'https://learningmanagerstage1.adobe.com/ctr/xtsas/<connectionId>/enable' \
  -H 'accept: application/json' \
  -H 'content-type: application/json' \
  -H 'x-acap-caller-role: ROLE_INTEGRATIONADMIN' \
  -H 'x-csrf-token: <CSRF_TOKEN>' \
  -H 'Cookie: <SESSION_COOKIES>' \
  --data '{"objectUUID":10002,"operation":1,"val":false}'
```

要确认新状态，请调用`GET /ctr/xtsas`，按`id`查找连接，并检查其`enabled`标志。

>[!NOTE]
>
>`x-acap-caller-role`标头必须与活动配置文件的角色匹配。 对于这些API，请使用`ROLE_INTEGRATIONADMIN`。

### 创建连接后对其进行管理

您可以对连接ID使用以下调用：

| 目的 | 通话 |
|---|---|
| 启用或禁用连接 | `POST /ctr/xtsas/{connectionId}/enable` |
| 读取一个连接的访问列表 | `GET /ctr/xtsa/{connectionId}/access` |
| 所有Zoom连接的读取权限 | `GET /ctr/xtsas/access?UUID=20012` |
| 列出所有连接。 缩放连接具有`extsysRefId` 25。 | `GET /ctr/xtsas` |
| 查看连接 | `GET /ctr/app/connection/{id}/object/10002` |
| 永久删除连接 | `DELETE /ctr/xtsas/{id}` |

>[!NOTE]
>
>view调用以明文形式返回客户端密钥。 将客户端密钥视为敏感密钥，如果公开，则将其旋转。 不要提交或共享会话Cookie、CSRF令牌或凭据，包括在HAR文件和复制的cURL命令中。

### 在集成中使用这些API

一个常见的用例是自动设置新连接器或合作伙伴的Zoom帐户。

1. 呼叫`GET /ctr/xtsas/canCreateAccount/25`以确认您可以创建另一个连接。
2. 使用Zoom凭据调用`POST /ctr/authcred/uuid/20012`。
3. 使用连接器名称、相同的凭据字符串和同步计划调用`POST /ctr/app/esconnect`。 从响应中读取连接ID。
4. 使用可以使用连接的用户组和自定义角色调用`PUT /ctr/xtsa/{connectionId}/access`。
5. 在将`val`设置为`true`或`false`的情况下调用`POST /ctr/xtsas/{connectionId}/enable`以启用或禁用连接。 然后调用`GET /ctr/xtsas`并检查`enabled`标志以确认状态。
6. 要在以后更改凭据，请对连接ID重复步骤2和3。


