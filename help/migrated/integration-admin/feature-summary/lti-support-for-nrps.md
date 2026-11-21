---
description: 了解Adobe Learning Manager如何使用NRPS将LTI 1.3平台中的自定义学习者属性作为活动字段同步到学习者配置文件中
jcr-language: en_us
title: 对NRPS的LTI支持
exl-id: 4c972319-b8ce-4f2d-9ccb-1b93c6cc6ac0
source-git-commit: 92be9eb8ece6d083efe595894a492540cd96eead
workflow-type: tm+mt
source-wordcount: '1845'
ht-degree: 0%
---

# 对NRPS的LTI支持

## 概述

Adobe Learning Manager在充当学习工具互操作性(LTI) 1.3工具时支持名称和角色配置服务(NRPS)规范。 学习者从外部学习管理系统（平台）启动Learning Manager时，Learning Manager会从平台检索学习者的会员资格记录。 然后，它将该记录中的自定义属性（如部门或员工ID）作为活动字段复制到学习者的配置文件中。

## 用例

* **自动丰富学习者个人资料。** 无需手动输入数据或单独导入，即可将部门属性、员工ID或自定义元数据等属性从平台导入Learning Manager。
* **分析您的学习者来自哪里。** 捕捉地点属性，例如国家/地区和城市，以构建学习者所在地理区域的图片。 在Learning Manager中使用结果配置文件字段进行分析。
* **保持配置文件数据与源平台一致。** 该平台仍然是真相的来源。 学习者每次启动时，Learning Manager都会刷新这些值。
* **在一个帐户中支持多个平台。** 命名空间前缀使来自不同平台的属性保持独立，即使这些平台使用相同的属性名称也是如此。

通过NRPS自定义字段同步，Learning Manager会在启动时执行以下操作：

1. 检测平台是否支持NRPS。
2. 从平台请求启动学习者的会员资格记录。
3. 从该记录中提取自定义属性。
4. 将属性作为活动字段写入学习者的配置文件。 每个字段名称都带有一个`<namespace>`前缀，因此来自不同平台的属性不会发生冲突。
5. Learning Manager会重复使用已用于分配和等级服务(AGS)的OAuth 2.0客户端凭据令牌。 您无需配置新的令牌终结点。

>[!NOTE]
>
>NRPS是LTI Advantage中的可选规范。 对NRPS和自定义属性的支持因平台而异。 在计划使用此功能之前，请确保您的平台公开NRPS 2.0。

## 主要功能

* **支持NRPS声明：** Learning Manager会检查每次LTI 1.3启动是否存在NRPS声明。 如果未收到声明，则启动会正常继续，不会出现错误，不会对学习者产生影响。
  * 此声明提供以下信息：
    * **成员资格终结点：** `context_memberships_url `标识学习者从中启动ALM的课程或学习上下文的服务URL。
    * **支持的版本：** `service_versions`列出了该端点上可用的NRPS版本。
      此功能支持NRPS 2.0。
  * **共享令牌基础结构：** Learning Manager会将NRPS范围添加到其现有的AGS令牌请求，并重复使用现有的每次注册令牌缓存。
* **将自定义参数同步到学习者配置文件**
  * **命名空间前缀的活动字段：**&#x200B;每个自定义属性都映射到名为`<namespace>_<field_name>`的活动字段。
  * **自动创建字段：**&#x200B;如果没有匹配的活动字段，则Learning Manager会创建类型为&#x200B;**文本**、状态为&#x200B;**活动**&#x200B;的活动字段。
  * **平台作为事实来源：** Learning Manager使用平台中的最新值覆盖现有配置文件值。 学习者和管理员无法编辑这些字段。
  * **非阻塞行为：** NRPS错误不会阻止学习者启动学习内容。
  * **自定义属性的多个源：** Learning Manager可以从NRPS端点和LTI启动令牌中的自定义参数读取自定义属性。 详细了解[启动令牌中的自定义属性](#custom-attributes-in-the-launch-token)。

## 支持的配置

| 项目 | 支持 |
|----------------------------------------------------------------|--------------------------------------------------------------------------|
| Learning Manager角色 | LTI 1.3工具 |
| LTI版本 | LTI 1.3 |
| NRPS服务版本 | 2.0 |
| 平台（符合规范的自定义字段格式） | Moodle、D2L Brightspace、Blackboard（选集）、酒井 |
| 自定义字段类型 | 文本 |
| 触发器 | 每次LTI 1.3发布 |

平台支持取决于NRPS成员记录中使用的自定义字段序列化模式。 可能会同时存在多种模式，但Learning Manager仅会处理当前版本支持的模式。

## 工作原理

### 启动流程

1. 学习者从平台启动Learning Manager。
2. Learning Manager会读取LTI 1.3启动令牌中的NRPS声明。 如果声明列出了NRPS服务版本2.0，则Learning Manager会为会话和LTI上下文（课程）存储`context_memberships_url`。
3. Learning Manager会请求包含NRPS作用域`https://purl.imsglobal.org/spec/lti-nrps/scope/contextmembership.readonly`的访问令牌。
4. Learning Manager使用持有者令牌调用`context_memberships_url?rlid=<lti_user_id>`以检索启动学习者的记录。 如果平台忽略`rlid`筛选器并返回完整名册，则Learning Manager会在`user_id`之前找到该学习者。
5. Learning Manager可从记录中提取自定义字段。
6. Learning Manager会将每个自定义字段映射到活动字段，并将值写入学习者配置文件。
7. 或者，如果自定义参数预先安装了ALM可识别字段`ALMfield`，则ALM还支持在工具启动期间提取要同步到学习者个人资料的自定义参数。

### 自定义字段格式

NRPS 2.0规范将自定义数据定义为成员记录中的`message`数组。 Learning Manager会从该阵列中的LTI自定义声明读取自定义数据。 对于此版本，Learning Manager支持规格合规性模式S表示法。

```json
{
  "user_id": "abc123",
  "message": [
    {
      "https://purl.imsglobal.org/spec/lti/claim/custom": {
        "department": "Engineering",
        "employee_id": "E4567"
      }
    }
  ]
}
```

### 启动令牌中的自定义属性

平台也可以将自定义属性作为LTI启动令牌中的自定义参数发送。 Learning Manager会从启动令牌和NRPS端点收集属性并将其存储在学习者配置文件中。

对于启动令牌中的属性，参数名称必须以Learning Manager所需的前缀`almfield-`开头。 没有前缀，Learning Manager无法将这些参数与其他自定义参数区分开来，也无法导入这些参数。 从NRPS终结点检索的属性不需要此前缀。 只有在ALM的启动令牌中导入自定义参数以标识它应同步到学习者活动字段的字段时，才需要此前缀。

>[!NOTE]
>
>在平台上配置自定义参数之前，请先向Learning Manager代表确认确切所需的前缀。

### 活动字段命名和映射

Learning Manager会将活动字段名称生成为`<namespace>_<field_name>`。 例如，命名空间`https://purl.imsglobal.org/spec/lti/claim/custom`中的`department`字段变为`https://purl.imsglobal.org/spec/lti/claim/custom_department`。

Learning Manager应用以下规则：

* **名称长度：**&#x200B;如果名称超过活动字段名称字符数限制，Learning Manager会先缩短命名空间部分并保留字段名称。
* **名称冲突：**&#x200B;缩短后，Learning Manager会检查是否存在来自其他源的现有活动字段冲突。 如果发生冲突，它会调整缩短长度，直到找到唯一的名称。 如果找不到唯一的名称，则会跳过该字段并记录错误。
* **匹配：**&#x200B;字段名称的匹配不区分大小写。
* **现有和已启用的字段：** Learning Manager会将该值写入学习者的配置文件。
* **现有和已禁用的字段：** Learning Manager会跳过该字段，且未记录错误。
* **没有现有字段：** Learning Manager会创建状态为&#x200B;**活动**&#x200B;的&#x200B;**文本**&#x200B;字段。

### 将值写入配置文件

* 每次启动Learning Manager以检索NRPS数据时，系统都会将所有已解析的自定义字段值写入启动学习者配置文件中。 不会更改其他学习者配置文件。
* 如果某个字段已有值，Learning Manager会使用平台中的最新值覆盖该字段。
* 如果平台值为空或Null，则Learning Manager会保留现有配置文件值。
* 无法写入一个字段不会阻止对其他字段的启动或写入。
* Learning Manager会尽可能将字段更新应用于同一启动事务。
* 学习者无法在其个人资料页面上编辑源自NRPS的字段，管理员无法代表学习者编辑这些值。

## 设置NRPS自定义字段同步

### 先决条件

* 您的平台已在Learning Manager中注册为LTI 1.3工具。 此功能不支持LTI 1.1或LTI 1.2。
* 您的平台支持NRPS服务版本2.0，并公开符合spec规范的`message`格式的自定义属性。
* LTI启动令牌包含`namesroleservice`声明。
* 该声明提供了`context_memberships_url`，用于标识特定于课程的NRPS终结点。
* 声明中的`service_versions`值包括`2.0`。
* 您具有对平台工具注册的管理员访问权限。

### 将NRPS范围授予Learning Manager

包含NRPS范围的新注册无需在Learning Manager中进行其他配置。

包含NRPS范围的新注册无需在Learning Manager中进行进一步更改即可生效。 对于现有注册，平台管理员必须在平台端更新工具注册。

>[!NOTE]
>
>您无需在Learning Manager中更改令牌端点、客户端ID或私钥。 现有AGS配置会被重复使用。 如果平台未授予NRPS范围，Learning Manager会跳过NRPS而不影响AGS或启动。

### 公开平台上的学习者属性

平台可控制哪些学习者属性与其共享。 具体步骤取决于平台。 例如，在Moodle中：

1. 使用LTI 1.3将Learning Manager添加为外部工具。
2. 启用隐私设置，允许平台与工具共享学习者信息。
3. 定义要发送的自定义属性。 您可以使用平台变量或预定义值。
4. 如果还将属性作为启动令牌中的自定义参数发送，请为每个参数名称添加Learning Manager需要的前缀。

>[!NOTE]
>
>仅公开学习用例所需的属性。 Learning Manager将平台视为事实来源，在本版本中不会单独提供同意或隐私控制选项。

### 验证同步

1. 以测试学习者身份从平台启动Learning Manager。
2. 确认启动正常完成。
3. 在Learning Manager管理员应用程序中，打开“活动字段”页面。
4. 确认显示的字段具有命名空间前缀，类型为&#x200B;**Text**，状态为&#x200B;**Active**。
5. 打开测试学习者配置文件，并确认值与平台匹配。
6. 确认源自NRPS的字段为只读。 学习者和管理员均无法手动编辑同步的值。
7. 在更改非空的源值后重新启动，并确认Learning Manager用最新的NRPS值覆盖现有的配置文件值。

>[!TIP]
>
>如果字段存在但被禁用，Learning Manager不会向其写入内容。 如果要填充该字段，请将其启用。

## 错误处理和记录

Learning Manager绝不会因NRPS问题阻止学习者。 它不会重试。 它将记录故障并跳过该启动的NRPS同步。 下次启动将重试。

| 条件 | 结果 |
|------------------------------------------------------------------|-------------------------------------------------------|
| 启动令牌中不存在NRPS声明 | 已跳过NRPS。 发射仍在继续。 |
| 仅存在NRPS服务版本1.0 | 已跳过NRPS。 发射仍在继续。 |
| 令牌请求失败或平台未授予NRPS范围 | 已跳过NRPS。 AGS和发布不受影响。 |
| NRPS调用失败（超时、4xx或5xx） | 将记录错误。 发射仍在继续。 |
| 在NRPS响应中找不到学习者 | 字段同步已跳过。 发射仍在继续。 |
| NRPS响应中没有自定义字段 | 跳过了字段同步，未显示错误。 |
| 无法解决字段名称冲突 | 将跳过该字段，并记录错误。 |
| 单个字段写入失败 | 其他字段仍然写入。 发射仍在继续。 |

每个日志条目包括时间戳、平台注册ID、学习者ID和失败原因。 Learning Manager系统管理员可以访问日志。

## 备注

* 仅同步启动学习者的记录。 Learning Manager不会同步完整课程名册。
* 仅支持NRPS服务版本2.0。
* 所有已同步的字段的类型为&#x200B;**文本**。 Learning Manager不会从值推断类型。 不支持数字、日期和布尔值字段类型。
* Learning Manager的作用与LTI工具相同。 它不作为NRPS平台，也不会向其他工具提供名册端点。
* 自定义字段同步在LTI启动期间进行。
