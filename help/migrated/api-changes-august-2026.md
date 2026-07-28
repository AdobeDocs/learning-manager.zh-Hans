---
description: ALM中的API更改
jcr-language: en_us
title: Adobe Learning Manager 2026年8月版中的API更改
source-git-commit: 857c94b5e9a7460d63a6dacc0beeddd41f362bf9
workflow-type: tm+mt
source-wordcount: '3354'
ht-degree: 3%

---


# Adobe Learning Manager 2026年8月版中的API更改

## Adobe Learning Manager中的用户组管理员API

此版本添加了三个新的管理员范围的公共API端点，用于以编程方式管理自定义用户组。 您可以创建、重命名和删除自定义用户组，而无需使用管理员应用程序，从而使您能够在身份或配置工作流中自动进行组管理。

这些端点仅适用于自定义用户组。 系统管理的组（例如“所有用户”组和自动生成的用户组）在API响应中具有readOnly： true，无法通过这些端点修改或删除。

有关API身份验证要求，请参阅[Adobe Learning Manager API身份验证](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual#authentication-using-oauth-20)。

### 用户组API端点

所有三个端点都需要一个具有写入权限的管理员访问令牌(ROLE_ADMIN)。

| **方法** | **路径** | **操作** | **成功代码** |
|---|---|---|---|
| POST | /primeapi/v2/userGroups | 创建自定义用户组 | 201年已创建 |
| PUT | /primeapi/v2/userGroups/{id} | 更新组的名称或描述 | 200正常 |
| DELETE | /primeapi/v2/userGroups/{id} | 删除自定义用户组 | 204无内容 |

## **公共请求标头**

所有三个端点都需要以下标题。

```
Authorization: Bearer \<access-token\>
X-acap-user: \<user-id\>
X-acap-account: \<account-id\>
X-acap-caller-role: ROLE_ADMIN
Content-Type: application/vnd.api+json
Accept: application/vnd.api+json
```

### **创建用户组**

```
POST /primeapi/v2/userGroups
```

使用初始成员列表创建新的自定义用户组。 该组立即可在管理员应用程序中使用。

#### **请求正文**

```
{
  "name": "Marketing Team",
  "description": "Custom user group for marketing onboarding",
  "data": [
    { "type": "user", "id": "11282373" },
    { "type": "user", "id": "11282374" }
  ]
}
```

#### **请求参数**

| **参数** | **必填** | **类型** | **描述** |
|---------------|--------------|----------|-------------------------------------------------------------------------------------|
| name | 是 | 字符串 | 组的显示名称。 不得为空或仅包含空格。 |
| 描述 | 否 | 字符串 | 组用途的可选说明。 |
| 数据 | 是 | 阵列 | 初始成员列表。 最少1项，最多100项。 |
| data[].type | 是 | 字符串 | 必须是“用户”。 不接受其他资源类型。 |
| data[].id | 是 | 字符串 | 数字用户ID字符串。 用户必须属于该帐户且处于“活动”状态。 |

> **注意：**&#x200B;数据数组仅在创建时用于设置初始成员列表。 要在创建后添加或删除成员，请使用现有用户组成员资格端点。

#### **已创建响应201**

```
{
  "links": {
    "self": "https://<host>/primeapi/v2/userGroups"
  },
  "data": {
    "id": "2769204",
    "type": "userGroup",
    "attributes": {
      "dateCreated": "2026-06-04T14:19:53.000Z",
      "description": "Custom user group for marketing onboarding",
      "name": "Marketing Team",
      "readOnly": false,
      "userCount": 2
    }
  }
}
```

#### **验证规则POST**

| **#** | **验证** | **错误代码** | **触发器** |
|-------|-------------------------------------------------------|----------------------------------------------------------|------------------------------------------------|
| 1 | 名称存在且不为空 | USERGROUP_CREATE_NAME_REQUIRED | 名称被省略或仅包含空格 |
| 2 | 数据包含至少1个用户 | USERGROUP_CREATE_USERS_REQUIRED | 数据不存在或空数组 |
| 3 | 数据包含100个或更少用户 | USERGROUP_USERS_MAX_LIMIT_EXCEEDED | 数据[]中的条目超过100个 |
| 4 | 所有用户ID都是数字字符串 | INVALID_USER_IDS | 在data[].id中找到非数字字符串 |
| 5 | 帐户中存在所有处于“活动”状态的用户 | INVALID_USER_IDS / USERGROUP_CREATE_USERS_NOT_IN_ACCOUNT | 未找到用户或用户未激活 |
| 6 | 帐户未达到自定义组限制 | 400 | 已超出自定义组的帐户级别限制 |

### **更新用户组**

```
PUT /primeapi/v2/userGroups/{id}
```

更新现有自定义用户组的名称和/或说明。 此终结点无法添加或删除组成员。

可以省略任一字段；省略某个字段时，其当前值保持不变。 为说明传递null将清除该说明。 拒绝为名称传递空白字符串。

#### **请求正文**

```json
{
  "name": "Updated Group Name",
  "description": "Updated description text"
}
```

#### **请求参数**

| **参数** | **必填** | **类型** | **描述** |
|---------------|--------------|----------|---------------------------------------------------------------------------|
| name | 是 | 字符串 | 新显示名称。 如果提供，则不能为空。 忽略以保持不变。 |
| 描述 | 否 | 字符串 | 新描述。 传递null以清除。 忽略以保持不变。 |

#### **响应200正常**

```
{
  "data": {
    "type": "userGroup",
    "id": "2767870",
    "attributes": {
      "name": "Updated Group Name",
      "description": "Updated description text",
      "readOnly": false,
      "state": "Active",
      "userCount": 3
    }
  }
}
```

#### **验证规则PUT**

| **#** | **验证** | **错误代码** | **触发器** |
|-------|-------------------------------------|----------------------------------------|----------------------------------------------------------|
| 1 | 数据为空或不存在 | USERGROUP_UPDATE_USERS_NOT_ALLOWED | 调用方在尝试成员资格更改时传递了非null数据 |
| 2 | 提供的名称不为空 | USERGROUP_UPDATE_NAME_BLANK | 名称以仅含空格的字符串形式发送 |
| 3 | 此帐户中存在组 | INVALID_USER_GROUP_ID | 未知的{id}路径参数 |
| 4 | 组尚未删除 | DELETED_USERGROUP | 以前已删除组 |
| 5 | 组readOnly为false | READ_ONLY_USERGROUP | 系统管理的组 |
| 6 | 组是自定义（非系统）类型 | USERGROUP_UPDATE_OPERATION_NOT_ALLOWED | 系统 — 内部组类型 |

### **删除用户组**

```
DELETE /primeapi/v2/userGroups/{id}
```

将指定的自定义用户组标记为已删除。 不会永久删除组记录 — 其状态设置为“已删除” ，这使该记录在管理员应用程序中不可见，并且没有资格在新配置中使用。 无法重复使用组ID。

#### **请求示例**

```
DELETE /primeapi/v2/userGroups/2767870
Authorization: Bearer <access-token>
X-acap-user: <user-id>
X-acap-account: <account-id>
X-acap-caller-role: ROLE_ADMIN
```

#### **响应204无内容**

响应正文为空。

> **注意：** DELETE不是幂等的。 向同一组ID发送第二个DELETE请求将返回400错误，其中包含DELETED_USERGROUP代码 — 而不是204。 将400 DELETED_USERGROUP响应视为已删除该组的确认。 不支持批量删除；每个组都需要一个单独的DELETE请求。

#### **验证规则DELETE**

| **#** | **验证** | **错误代码** | **触发器** |
|-------|-------------------------------------|----------------------------------------|---------------------------------------------------|
| 1 | 此帐户中存在组 | INVALID_USER_GROUP_ID | 未知的{id}路径参数 |
| 2 | 组尚未删除 | DELETED_USERGROUP | 对已处于“已删除”状态的组重复执行DELETE |
| 3 | 组readOnly为false | READ_ONLY_USERGROUP | 系统管理的组 |
| 4 | 组是自定义（非系统）类型 | USERGROUP_UPDATE_OPERATION_NOT_ALLOWED | 系统 — 内部组类型 |

## Adobe Learning Manager中的外部学习API

此版本为外部学习功能添加了五个新的学习者范围API端点。 这些端点允许学习者以编程方式创建、检索和更新外部学习提交内容，例如，从移动应用程序、集成的人力资源系统或自定义学习门户网站进行创建、检索和更新。

通过API的外部学习工作流程反映了“学习者”应用中的工作流程：学习者提交培训详细信息和可选的证明文档，其直属经理会收到一封审核提交内容的通知，批准后，记录会显示在学习者的成绩单中。

所有五个端点均属于学习者范围。 学习者只能访问自己的提交内容 — 如果学习者尝试访问其他学习者的数据，则API会返回错误。

有关API身份验证要求，请参阅[Adobe Learning Manager API身份验证](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual#authentication-using-oauth-20)。

### 外部学习API端点

所有端点都需要一个学习者访问令牌(ROLE_LEARNER)。

| **方法** | **路径** | **操作** | **成功代码** |
|------------|---------------------------------------|----------------------------------|------------------|
| GET | /primeapi/v2/externalLearningSettings | 获取帐户窗体配置 | 200正常 |
| GET | /primeapi/v2/externalLearnings | 列出调用方提交的内容 | 200正常 |
| GET | /primeapi/v2/externalLearnings/{id} | 获取单次提交 | 200正常 |
| POST | /primeapi/v2/externalLearnings | 创建新提交 | 201年已创建 |
| PUT | /primeapi/v2/externalLearnings/{id} | 更新待处理的提交 | 200正常 |

### 常用请求头

```
Authorization: Bearer <access-token>
X-acap-user: <user-id>
X-acap-account: <account-id>
X-acap-caller-role: ROLE_LEARNER
Accept: application/vnd.api+json
Content-Type: application/vnd.api+json (POST and PUT only)
```

### 提交状态生命周期

| **状态** | **设置者** | **含义** | **学习者是否可以更新？** |
|------------|------------------|-----------------------------------------|-----------------------------|
| 待处理 | 创建时的系统 | 正在等待经理审阅 | 是 — 通过PUT |
| APPROVED | 经理 | 接受；显示在学习者成绩单中 | 否 — PUT返回409 |
| 被拒绝 | 经理 | 已拒绝；已附加审阅注释 | 否 — 创建新提交 |

“已批准”和“已拒绝”为终止状态。 无法重新打开被拒绝的提交内容；学习者必须新建提交内容。

### 获取帐户窗体配置

```
GET /primeapi/v2/externalLearningSettings
```

返回帐户级别的表单配置。 在呈现提交表单之前，请调用此端点。 响应定义要显示的字段、必填字段、数据类型以及管理员配置的所有自定义字段。

在继续之前检查顶层已启用属性，如果为false，“外部学习”功能对此帐户不活动，且提交端点将返回错误。

#### 响应200正常

```
{
  "data": {
    "id": "8627",
    "type": "externalLearningSettings",
    "attributes": {
      "enabled": true,
      "updatedAt": "2026-06-05T06:51:20.000Z",
      "coreFields": [
        { "id": "title", "type": "TEXT", "mandatory": true, "editable": false, "order": 0 },
        { "id": "description_notes", "type": "TEXT", "mandatory": false, "editable": true, "order": 1 },
        { "id": "date", "type": "TIMESTAMP", "mandatory": false, "editable": true, "order": 2 },
        { "id": "score", "type": "NUMBER", "mandatory": true, "editable": true, "order": 3 },
        { "id": "duration", "type": "TEXT", "mandatory": false, "editable": true, "order": 4 },
        { "id": "attachments", "type": "FILE_UPLOAD", "mandatory": true, "editable": true, "order": 5 }
      ],
      "customFields": [
        {
          "id": "960369b2-...",
          "type": "NUMBER",
          "mandatory": true,
          "order": 0,
          "label": { "en_US": "Employee Code" }
        },
        {
          "id": "3c6cc6d9-...",
          "type": "DROPDOWN",
          "mandatory": true,
          "order": 1,
          "label": { "en_US": "Department" },
          "options": [
            { "option_id": "opt_1", "label": { "en_US": "IT" } },
            { "option_id": "opt_2", "label": { "en_US": "HR" } },
            { "option_id": "opt_3", "label": { "en_US": "FIN" } }
          ]
        }
      ]
    }
  }
}
```

#### 核心字段引用

| **字段ID** | **类型** | **默认必填** | **备注** |
|-------------------|-------------|-----------------------|----------------------------------------------------------------------------------------------------------|
| 标题 | 文本 | 是 | 培训名称。 始终在场。 管理员无法禁用。 |
| description_notes | 文本 | 否 | 自由文本描述或注释。 |
| 日期 | 时间戳 | 否 | 日期范围。 值形状： { &quot;start_date&quot;： &quot;<ISO-Z>&quot;， &quot;end_date&quot;： &quot;<ISO-Z>&quot; }. 任一值都可为空。 |
| 分数 | 编号 | 是 | 值形状：{ &quot;achieded_score&quot;： <number>， &quot;max_score&quot;： <number> }. 两个值都必须是数值。 |
| duration | 文本 | 否 | 自由格式字符串，例如“40小时”。 |
| 附件 | FILE_UPLOAD | 是 | 完成证明。 **未**&#x200B;在字段内传递[] — 请改用顶级submissionUrl属性。 |

自定义字段由管理员定义，并在customFields[]中返回。 它们的ID、类型、强制标记、标签和下拉选项因帐户配置而异。

### 列出提交内容

```
GET /primeapi/v2/externalLearnings
```

返回经过身份验证的学习者自己提交的分页列表，按modifiedAt降序排序（最近修改的位于前面）。

#### **查询参数**

| **参数** | **默认值** | **最大** | **描述** |
|---------------|-------------|-------------|-------------------------------------------------------------------------------------------------------|
| 页面[偏移] | 0 | 5000 | 从零开始的记录偏移。 |
| 第[页限制] | 10 | 100 | 每页的记录数。 如果值大于100，则会以静默方式将其固定为100。 |
| ls_qp_status | — | — | 按状态筛选。 忽略所有结果。 有效值： PENDING、APPROVED、REJECTED（不区分大小写）。 |

#### **响应200正常**

```
{
  "links": {
    "next": "/primeapi/v2/externalLearnings?page[offset]=10&page[limit]=10"
  },
  "data": [
    { "id": "1001", "type": "externalLearning", "attributes": { "status": "PENDING", ... } },
    { "id": "1002", "type": "externalLearning", "attributes": { "status": "APPROVED", ... } }
  ]
}
```

### 获取提交内容

```
GET /primeapi/v2/externalLearnings/{id}
```

返回属于已验证学习者的单个提交的完整记录。

#### **响应200正常

```
{
  "data": {
    "id": "1001",
    "type": "externalLearning",
    "attributes": {
      "submissionUrl": "https://<cdn-url>/cert.pdf",
      "title": "Java Fundamentals Certification",
      "status": "PENDING",
      "creationSource": "LEARNER",
      "createdAt": "2026-04-14T08:30:00.000Z",
      "modifiedAt": "2026-04-16T11:45:00.000Z",
      "fields": [ "...resolved against live settings..." ]
    },
    "relationships": {
      "reviewerUser": { "data": null }
    }
  }
}
```

### 创建提交

```
POST /primeapi/v2/externalLearnings
```

创建处于待处理状态的新外部学习提交。 必须包括帐户设置中定义的所有必填字段。 成功POST后，学习者经理会收到平台内通知，内容为审阅提交内容。

### **文件上传**

附件字段的处理与其他字段分开。 不要将其包含在字段[]中。 而是：

1.从ALM文件上传端点获取预签名的S3上传URL。

2.将文件上传到该URL。

3.将生成的URL作为POST请求的顶级submissionUrl属性传递。

#### **请求正文**

```
{
  "data": {
    "type": "externalLearning",
    "attributes": {
      "submissionUrl": "<pre-signed-upload-url>",
      "fields": [
        { "id": "title", "type": "TEXT", "value": "Java Fundamentals Certification" },
        { "id": "description_notes", "type": "TEXT", "value": "Completed via online course platform." },
        { "id": "date", "type": "TIMESTAMP", "value": { "start_date": "2026-05-01T00:00:00.000Z", "end_date": "2026-05-15T00:00:00.000Z" } },
        { "id": "score", "type": "NUMBER", "value": { "achieved_score": 88, "max_score": 100 } },
        { "id": "duration", "type": "TEXT", "value": "40 hours" },
        { "id": "960369b2-...", "type": "NUMBER", "value": "1225" },
        { "id": "3c6cc6d9-...", "type": "DROPDOWN", "value": "opt_3" }
      ]
    }
  }
}
```

#### 字段值形状

| **字段类型** | **值形状** | **示例** |
|----------------|---------------------------------------------------------|----------------------------------------------------------------|
| 文本 | 字符串 | “Java基本面” |
| 编号 | 具有achieve_score和max_score的对象 | { &quot;acheed_score&quot;： 88， &quot;max_score&quot;： 100 } |
| 时间戳 | start_date和end_date的对象（ISO 8601或null） | { &quot;start_date&quot;： &quot;2026-05-01T00:00:00.000Z&quot;， &quot;end_date&quot;： null } |
| 下拉列表 | 帐户设置中的option_id字符串 | &quot;opt_3&quot; |
| FILE_UPLOAD | 不允许在字段[]中访问 — 请使用submissionUrl | — |

#### 验证规则POST

| **#** | **验证** | **触发器** |
|-------|-----------------------------------------------------------------|----------------------------------------------------------|
| 1 | 已为帐户启用外部学习 | 功能标志已禁用 |
| 2 | 字段[]中存在所有必填字段 | 省略了必填字段 |
| 3 | 每个字段ID、类型和值形状都与帐户设置相匹配 | 类型错误或值对象格式错误 |
| 4 | 字段[]中不存在FILE_UPLOAD类型 | 附件已在字段[]中发送，而不是submissionUrl |
| 5 | submissionUrl是有效的S3预签名URL | 创建时拒绝的CDN URL和非S3 URL |
| 6 | attachments.mandatory为true时存在submissionUrl | 需要附件，但缺少submissionUrl |

### 更新提交

```
PUT /primeapi/v2/externalLearnings/{id}
```

更新现有的PENDING提交。 只能更新PENDING提交。 尝试PUTAPPROVED或REJECTED提交内容时会返回409错误。

**此终结点使用完全替换语义。** 在每个PUT请求中提供完整的字段[]数组，而不仅仅是您正在更改的字段。 将清除数组中省略的字段。

#### 学习者可以更新的字段

| **字段/属性** | **学习者可以更新** | **备注** |
|-----------------------|------------------------|----------------------------------------------------------------------------|
| 字段[] | 是 | 完全替换 — 包括所有字段，而不仅仅是更改的字段 |
| submissionurl | 是 | PUT接受CDN URL；POST需要S3预签名URL |
| reviewerUserId | 否 | 由经理操作设置；对学习者只读 |
| reviewedAt | 否 | 由经理操作设置；对学习者只读 |
| reviewerComment | 否 | 由经理操作设置；对学习者只读 |
| 学习 | 否 | 由经理控制：“待定”→“批准”或“拒绝” |
| creationSource | 否 | 针对API创建的提交始终为学习者 |
| createdAt | 否 | 创建时设置；不可变 |

#### 请求正文

```
{
  "data": {
    "type": "externalLearning",
    "attributes": {
      "submissionUrl": "<cdn-url>/cert-v2.pdf",
      "fields": [
        { "id": "title", "type": "TEXT", "value": "Java Fundamentals — Updated" },
        { "id": "description_notes", "type": "TEXT", "value": "Updated notes." },
        { "id": "date", "type": "TIMESTAMP", "value": { "start_date": null, "end_date": null } },
        { "id": "score", "type": "NUMBER", "value": { "achieved_score": 92, "max_score": 100 } },
        { "id": "duration", "type": "TEXT", "value": "42 hours" },
        { "id": "960369b2-...", "type": "NUMBER", "value": "1227" },
        { "id": "3c6cc6d9-...", "type": "DROPDOWN", "value": "opt_2" }
      ]
    }
  }
}
```

## 学习者相关认证ID和LT中根认证ID的API

当循环认证续订时，Adobe Learning Manager会创建认证的新版本并自动将活跃的学习者注册到该版本。 如果您的集成不是依赖Adobe Learning Manager学习者体验，而是直接查询认证数据，则您可以使用此API随时准确地确定定期认证的哪个版本与特定学习者相关。

### API的目的

循环认证会在每次续订时生成新的认证ID。 在本机Adobe Learning Manager学习者体验中，仅显示与每个学习者相关的版本。 学习者迁移到新版本后，旧版本会自动隐藏。

如果您的集成单独检索认证数据（例如，在外部门户上显示认证信息），则可能不会自动应用此筛选。 如果没有它，学习者就可以看到循环认证的所有历史版本，包括与它们不再相关的版本，而不知道该采取什么操作。

此API解决了这一缺口。 如果给定根认证ID，则返回适用于给定学习者的特定认证版本，计入其注册历史记录和任何重复情况。

### 了解认证重复情况

当认证配置为重复时，每次续订都会创建一个具有自己的唯一ID的新认证版本。 所有版本都追溯到最初创建时的原始证书的单个&#x200B;**根证书ID**&#x200B;中。

例如，每个月重复出现的认证可能会在一段时间内生成一系列版本，其中每个新版本在达到重复间隔时自动生成。 发生重复时主动注册的学习者将自动注册到新版本。

由于每个版本都有不同的ID，因此学习者的相关版本取决于其各自的注册时间线：

- 如果学习者在重复之前注册并在下一次重复之前完成认证，则他将在一段时间内完成多个版本。

- 注册循环周期中途的学习者直接注册到他们注册时的任何当前版本。

### 确定相关的认证版本

使用认证版本API确定周期性认证的哪个版本与特定学习者相关。

提供&#x200B;**根认证ID**&#x200B;作为输入。 API会根据以下规则评估学习者的注册历史记录并返回相应的版本：

| **学习者状态** | **API返回的内容** |
|--------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| 学习者尚未注册认证 | 认证的最新可用版本 |
| 学习者当前已注册 | 学习者当前注册的特定版本，考虑自其原始注册以来发生的任何重复情况 |

这意味着根据每个学习者的单独注册历史记录，同时查询同一根认证ID的两个学习者可能会收到不同的结果。

**注意**：在新建版本和迁移注册时，重复期间可能会有一个短暂的窗口，其中API可能返回即将被取代的版本，而不是新创建的版本。

**示例**

考虑每月重复出现的认证，其中四个版本是随着时间推移创建的，因为它们反复出现：

- 注册了第一个版本并在每个循环过程中不断前进的学习者将返回到该版本，他们当前处于活动状态，这反映出了他们自己的完成和循环历史记录，不一定是现有的最新版本。

- 如果学习者尚未注册，系统将返回至最近创建的版本，因为新注册应加入该版本。

集成允许始终将学习者引导至与其相关的认证版本，而不是显示每个历史版本或猜测哪个版本适用。

### API 引用

**获取适用于根认证的认证**

```
GET /primeapi/v2/learningObjects/{loId}/applicableCertification
```

解析适用于当前学习者的认证版本（给定根认证的ID）。 对于已注册的学习者，返回其当前注册的版本。 对于未注册的学习者，这将返回最新的活动版本。

| **属性** | **值** |
|----------------------------------------------------------|--------------------------|
| **作用域** | 学习者读取权限 |
| **速率限制（标准学习者呼叫）** | 每分钟70个请求 |
| **速率限制（提升的或管理员级别的API凭据）** | 每小时500个请求 |
| **响应格式** | application/vnd.api+json |

**注意**：此API一次返回一个学习者的版本信息。 它不返回认证所有版本的列表。

**路径参数**

| **参数** | **必填** | **类型** | **描述** |
|---------------|--------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| loId | 是 | 字符串 | 学习对象的ID，特别是为其请求适用版本的根认证。 这受标准访问权限的限制。 |

**查询参数**

| **参数** | **必填** | **类型** | **描述** |
|---------------|--------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 包括 | 否 | 字符串 | 要包含在解析认证的响应中的相关模型列表（以逗号分隔），例如子学习对象或注册。 使用与其他Adobe Learning Manager学习对象端点相同的包含语法。 |

**示例请求**

```
GET /primeapi/v2/learningObjects/certification%3A167658/applicableCertification?include=subLOs
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

```
curl -X GET --header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://<host>/primeapi/v2/learningObjects/certification%3A167658/applicableCertification?include=subLOs'
```

**注意**： loId值必须采用URL编码。 认证ID（如certification：167658）中的冒号编码为%3A。

**示例响应200 OK**

此响应使用与标准学习对象响应相同的结构，并返回已解决的认证。

**重要提示：**&#x200B;响应中的ID字段为&#x200B;**已解决**&#x200B;认证的ID，这是适用于此学习者的特定版本。 它通常与作为loId传入的根认证ID不同，因为此API的全部用途都是将根ID转换为正确的当前版本。

```
{
  "data": {
    "id": "string",
    "type": "string",
    "attributes": {
      "authorNames": [
        "string"
      ],
      "bannerUrl": "string",
      "catalogs": [
        ...
      ]
    }
  }
}
```

**响应代码**

| **状态** | **含义** |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 200 | 适用的认证已成功解决并作为响应返回。 |
| 400 | 提供的loId不是认证，或者不是根认证。 将原始认证的ID（而不是重复版本）作为loId传递。 |
| 401 / 403 | 该请求缺少有效的学习者凭据，或凭据没有所需的访问权限。 |
| 404 | 无法解析此根认证的有效认证。 例如，因为链中的每个版本都已停用或删除，或者因为认证根本没有记录的根认证引用。 如果成功解析版本，但呼叫的学习者没有该版本的目录访问权限，则也可能会出现404。 |
| 500 | 解析证书时出现意外服务器错误。 重试该请求；如果错误仍然存在，请与支持人员联系。 |

**示例错误响应**

```
{
  "meta": {
    "error": "string",
    "detail": "string"
  }
}
```

**注意：**&#x200B;此API为每个调用解析一个学习者的版本。 它不返回根认证存在的每个版本的列表。

**要点**

- **非循环认证：如果您传递的loId是未配置为循环使用的认证，则API会返回该认证本身。**

- **跳过中间版本：**&#x200B;如果学习者的活动注册直接从早期版本移至更高版本，且两个版本之间没有活动注册，则API仍可正确解析为学习者的实际当前版本。 存在学习者未主动使用的中间版本不会影响解决方案。

- **已删除与已弃用的认证：**&#x200B;已删除的认证版本将从解决中完全排除。 根据认证的状态，可能仍会将其视为已弃用；如果您依赖于仍可解析的特定版本，请确认其当前状态，而不是假定单独退出认证会将其从考虑事项中移除。

- **分辨率具有确定性：**&#x200B;如果学习者的注册数据处于不一致状态（例如，多个注册标记为当前），则API会解析为最新创建的版本，而不会返回不可预知的结果或错误。

**注意**：此API的管理员范围的等效项当前不可用，正在针对未来版本进行评估。

### 在集成中使用此API

常用的用例是一个外部页面或门户，其中列出了学习者可以访问的认证。 而不是直接链接到特定的认证ID，因为某个认证ID可能会在重复出现后过期。 使用根认证ID进行链接，并在学习者选择时解析正确的版本。

1.在任何重复出现之前，使用&#x200B;**根认证ID**&#x200B;首次创建认证时的ID在集成中存储或引用认证。

2.当学习者选择要查看或操作的认证时，请调用GET/primeapi/v2/learningObjects/{loId}/applicableCertification，并将根认证ID作为loId传递。

3.使用响应中返回的认证版本将学习者引导至正确的目的地，无论是注册操作还是当前进度视图。

这样可确保学习者始终使用与其实际注册和进度相匹配的认证版本，即使认证会随时间重复出现并生成新版本也是如此。

## 报告：学习者成绩单中的根培训ID

默认情况下，**根培训ID**&#x200B;列在所有帐户的学习者成绩单中均可用。

| **行类型** | **根培训ID值** |
|-----------------------------------------------------------------|--------------------------------------------------------------------------------|
| 认证已配置为重复出现 | 此版本跟踪到的根认证ID |
| 认证未配置为重复 | 与该行的培训ID相同的值 |
| 包含在认证中的课程 | 父认证的根认证ID，而不是课程自身的ID |
| 不属于任何认证的课程或学习路径 | 与该行的培训ID或嵌入式课程ID的值相同 |

**注意**：对于拥有大量认证的超大型帐户，会分批解析学习者成绩单中的根培训ID值。 这不会改变数据的准确性，但生成非常大的转录文本可能需要更长时间。

此列使您可以对循环认证每个版本的学习者完整历史记录进行分组和报告，而不是将每个循环视为不相关的、独立的记录。 每个循环仍会在学习者成绩单中显示为其自己的行。 “根培训ID”列仅标识哪些行属于同一基础认证。

**注意：**&#x200B;当您需要通过周期性认证跟踪学习者的完整参与历史记录时，请使用“根培训ID”列。

