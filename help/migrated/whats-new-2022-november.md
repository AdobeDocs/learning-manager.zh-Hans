---
title: 此版本（2022年11月）的新增功能
description: 了解AdobeLearning Manager中的新功能和增强功能
hidefromtoc: true
source-git-commit: 1da0911a4d0c2ae5cb01bbb2b7955675b0dfcdde
workflow-type: tm+mt
source-wordcount: '1994'
ht-degree: 0%

---

# 此版本（2022年11月）的新增功能

<!--
IN-PROGRESS

<https://helpx.adobe.com/learning-manager/whats-new-nov-2022.html>
-->

## 多个SSO配置

AdobeLearning Manager目前支持内部用户一种登录方法和外部用户一种登录方法。 如果客户的员工及其自己的客户和渠道合作伙伴使用相同的帐户，则此种登录方法会造成限制。

为了支持多种类型的用户组登录到平台，AdobeLearning Manager现在通过多个SSO配置支持内部和外部用户以多种方式实现登录。

有关详细信息，请参阅 [多个SSO登录](/help/migrated/administrators/feature-summary/multiple-sso-logins.md).

## 支持未登录功能

AdobeLearning Manager的原生门户现在支持未登录访问培训门户。

学习者现在可以发现并访问培训站点、查看各种可用的课程和内容，并决定登录以使用课程。

利用此功能，我们可更轻松地创建面向客户的学习门户，学习者无需初始登录即可浏览各种课程。

有关详细信息，请参阅 [学习者的未登录体验](/help/migrated/administrators/feature-summary/non-logged-in-experience-learners.md).

## 培训概述页面增强功能

“培训概述”页面现在可以显示更新的UI，学习者因此会在使用课程时获得更好的体验。

其他增强功能包括：

* 为培训添加书签。
* 相关课程推荐。
* 课程和学习路径的学习路径信息。
* 可单击的作者姓名。
* 方便导航的面包屑。

## 培训概述页面增强功能

“培训概述”页面现在可以显示更新的UI，学习者因此会在使用课程时获得更好的体验。

其他增强功能包括：

* 为培训添加书签。
* 相关课程推荐。
* 课程和学习路径的学习路径信息。
* 可单击的作者姓名。
* 方便导航的面包屑。

## 作者个人资料页面

作者个人资料页面会显示由特定作者创建的所有培训。

学习者可以轻松找到作者特定的信息以及作者创建的所有培训。

## 已添加书签的培训

学习者可以在课程磁贴或概述页面保存（使用“保存”按钮）培训或为其添加书签。 所有已添加书签的课程均在学习者主页上展示。

## 自定义播放器

在此版本中，您可以自定义流体播放器以匹配课程的品牌推广要求。

您可以根据内容要求显示和隐藏各种播放器设置和选项，并根据内容类型向学习者授予控制权限。 您可以将此更改应用于本机实现和无头实现。

您可以更改的各种选项包括：

* 切换目录
* 注释
* 语言
* 速度
* 题注
* 音量
* 播放控件

## 学习者和经理模拟

管理员可以启动模拟会话，在此会话中，他们可代表其帐户中担任学习者和经理角色的任何用户登录。

有关详细信息，请参阅 [学习者和经理模拟](/help/migrated/administrators/feature-summary/impersonation-learner-manager.md).

## 其他增强功能

### 电子邮件的审核日志

管理员现在可以通过电子邮件审核跟踪报告，访问系统发送的所有电子邮件日志。

此日志会捕获过去30天内发送的所有与电子邮件相关的数据，并且每天都会刷新。 此外，报告包含送达状态、发送者、接收者、主题和内容元数据等信息。

从“报告”>“自定义报告”>“Excel报告”>“电子邮件报告”中下载报告。 此时会显示一条通知，您可以通过该通知下载报告。

此报告包含以下字段：

* 电子邮件触发时间（UTC时区）
* 上次事件状态时间（UTC时区）
* 交付状态
* 收件人电子邮件
* 发件人用户ID
* 电子邮件主题
* 实体类型
* 实体名称
* 实体ID

### 轮候学习者通知

当作者添加新实例时，他可以触发一封电子邮件，通知轮候学习者其他实例。 学习者会收到一封有关变更的电子邮件。

### 实例级电子邮件模板

您可以为每个培训实例自定义电子邮件。

只要获得添加新实例的授权，作者或管理员便可以编辑单个实例的模板。

例如，如果课程具有不同的受众类型，您可以相应地更改电子邮件模板。

![电子邮件模板](assets/email-template.png)

模板的优先级如下所示：

1. 实例级模板
2. 培训级别模板
3. 帐户级别模板

### 接受提交时讲师的评论

讲师现在可以在接受学习者提交的内容时添加评论。 提交内容获得讲师批准后，学习者便会收到电子邮件通知和应用内通知（如已启用）。 管理员和学习者都能在学习者成绩单中看到与提交内容相关的评论。

### 与搜索相关的增强功能

现在会显示学习者最近的搜索历史记录，帮助学习者查看之前所有的搜索记录。

搜索结果在所有正式和非正式学习（社交学习）中保持一致。 搜索结果包括培训、社交学习和内容市场匹配。

搜索重点更突出，更具针对性，您可以在三个位置查看搜索结果：正式学习、社交学习和内容市场。

![搜索](assets/search-image.png)

#### 短语驱动搜索

在此版本的AdobeLearning Manager中，我们将“预先输入”搜索替换为短语驱动搜索。

#### 最近的搜索

学习者仅可查看当前会话中他们最近的搜索。

### 内容市场免费课程目录

内容市场为学习者提供了一套现成的高质量精选免费课程目录，内含50节免费课程。

### 支持印度尼西亚语

现在，Bahasa Indonesia已作为界面语言添加到学习者和经理应用程序中。

### “作者”字段必填

创建课程时，“作者”字段为必填字段。

### 内容市场更改

* 内容市场会为新创建的试用帐户列出50节免费课程的新目录，以供用户查看。
* 学习者现在可以查看搜索结果的数量以及用来重定向到内容市场的链接嵌入数。

### 移动沉浸式更改

在此版本中，移动沉浸式Web用户可以执行以下任务：

* 创建 — 投票帖子
* 编辑帖子 — 所有类型、RTE
* 电子商务工作流程。
* 预览模块：学习者将拥有移动沉浸式体验中的模块预览功能。 此更改使得学习者可以在注册课程之前预览模块。
* 复制URL。
* 删除讨论区。

### Zoom连接器更改

我们将于2023年6月弃用JWT应用类型。 我们建议您创建服务器到服务器OAuth或OAuth应用程序，以替换帐户中JWT应用程序的功能。

### 游戏报告

在此版本中，您可以访问显示已启用游戏功能的各种课程的报告。

### 通过CSV导入语言首选项

导入CSV文件时，CSV文件中会包含“界面语言”、“内容语言”和“时区”三个字段。

管理员还可以导出包含上述相同字段的报告。

* 界面语言
* 内容语言
* 时区

除管理员外，自定义管理员也可以导出此报告。

![语言报告](assets/language-report.png)

#### 对本地化的影响

* 列名称不能本地化，且必须保持原样（界面语言、内容语言、时区）。
* 区域设置代码不区分大小写。
* 虽然在提供国家/地区代码方面没有限制，但您只能指定语言代码。 例如，“it_IT”和“it”都有效。
* 如果由于区域设置代码不正确而导致报告中存在任何差异，csv会照常继续处理，并且不会影响csv中的其他记录。 如果用户的区域设置不正确，则区域设置首选项不会更新。 随后将更新其余数据。

## API更改和增强

### VC连接器

如果使用管理员电子邮件ID配置VC连接器，则该特定管理员必须具有下列权限：

* 创建会议
* 更新会议
* 获取出勤报告

创建或更新VC会议时，讲师必须在会议预定结束时间前30分钟内结束会议。

### 书签

添加了以下API以便在“培训概述”页面上为课程添加书签：

* 获取所有书签： `primeapi/v2/bookmarks`
* 创建书签： `primeapi/v2/learningObjects/{id}/bookmark`
* 删除书签： `primeapi/v2/learningObjects/{id}/bookmark`

### 通过迁移支持多区域设置元数据和内容

对于平台中支持的所有类型的培训（课程、学习路径、模块、认证和工作辅助），现在支持通过CSV文件完成多语言迁移，该文件会使用额外的列来支持其他语言。

#### 先决条件

以集成管理员身份创建迁移项目，然后与ALM支持团队共享迁移项目ID，以便可以从后端启用多区域设置标志。

#### 多区域设置迁移对象的范围

* 模块
* 课程
* 模块版本
* 认证
* 学习计划
* 工作辅助
* 工作辅助版本

#### CSV规范

AdobeLearning Manager提供了一组标准CSV规范，用于支持多区域设置的迁移。 最佳做法是，在开始迁移过程之前先完整了解这些CSV规范。 公司的集成管理员可对现有的数据格式进行分析和映射，以便与Learning Manager提供的CSV模板项相匹配。

#### 支持多区域设置的更改

* module_version.csv和course_module.csv中不支持module_version列。
* 无法在同一运行中更新module_version（在同一运行中，无法迁移带有同一模块的两个版本的模块）。
* 从module_version.csv将内容或元数据更新视为模块版本更新。
* 无法支持通过job_aid_version.csv进行Job_Aid_Version更新

### 撤销身份验证令牌和Cookie

首次登录无头LMS应用程序时会保留refresh_token。 之后，refresh_token用于为其客户端应用程序生成access_token以进行API调用。 同样，内容播放使用Oauth端点生成Cookie以管理播放，其中涉及多个内容文件以及这些文件使用Cookie调用的API调用。 oauth生成的Cookie与access_token的有效期相同，均为7天。 生成Cookie后，无法清除它，这与典型的Web应用程序注销不同。 Oauth Cookie和Web应用程序Cookie是两个不同的Cookie，彼此之间并不识别。

因此，为了清除Cookie，我们引入了一个新的端点，它可以撤消refresh_token、Cookie以及Cookie和刷新令牌。

**详细信息**

**端点**

`POST oauth/o/revoke`

**查询参数**

* `cookie=true|false`  — 表示需要撤销Cookie
* `refresh_token=true|false`  — 表示刷新

**请求正文**

撤消refresh_token或（refresh_token和Cookie）所需的正文

```
{
      "client_id": <>,
      "client_secret": <>,
      "refresh_token": <>
}
Body required for revoking oauth cookie only
{
      "access_token": <>
}
```

### 公开API

在此版本中，我们公开了多个API。

| API | 类型 | 描述 |
|---|---|---|
| /social/search | GET | 在社交网站中搜索。 |
| /announcements | GET | 在分配给学习者的刊头上获取有关公告的详细信息。 |
| /announcements/`{id}` | GET | 在分配给学习者的刊头上获取有关公告的详细信息。 |
| /learningObject/`{id}`/loResources/{loResourcesId} | GET | 上传loResource文件的URL，上传此类资源类型为“Activity”的文件时需提交文件。 |
| /jobAid/`{jobAidId}`/jobAidDownloaded | GET | 设置工作辅助下载报告。 |
| /bulkimport/startrun | POST | 运行批量导入。 |
| /bulkimport/cansync | GET | 同步批量导入。 |
| /search | GET | DELETEMEBOB |
| /uploadInfo | GET | 获取与内容更新相关的信息。 |
| /uploadSigner | GET | 获取to_sign内容的签名。 |
| /avatar | POST | 将学习者的头像图像更新为新图像。 |
| /avatar | DELETE | 删除学习者的头像图像。 |

### Salesforce应用

该 **忽略高阶学习对象** 必须在Salesforce应用中启用该选项，才能同时查看所有课程、学习计划和证书。

### 用于播放器自定义的API

在此版本中，我们提供了用于自定义播放器的API。 您可以：

* 启动或加载播放器。
* 导航到特定模块。
* 切换目录。
* 更改语言。
* 关闭播放器。
* 播放、暂停、前进、后退、搜寻、更改音量或更改速度。
* 捕捉从播放器发出的事件。

### 显示学习者的轮候表位置

GET/enrollments/{id}对于指定注册，学习对象API下的/waitlistPosition API会检索用户的轮候表位置。

### 外部认证中的完成日期提交

/primeapi/v2/learningObjects/certification：xxxxx API的“completionDateSameAsApprovalDate”属性会表明证书是否为学习者启用了“认证完成日期”以及true/false标志。

### 获取学习对象预览数据

/preview/learningObjects/GET{id} 添加API以获取有关学习对象的预览信息。

### 在配置文件内移动外部用户

该 `PUT primeapi/v2/externalProfiles/{currentep}/users/{userid}?` 通过指定新的externalProfile id，调用有助于将用户移动到另一个外部个人资料。

### 将用户添加到外部个人资料

该 `POST /externalProfiles/{id}/users` 将外部用户添加到外部个人资料中。

## 发行说明

如需了解Learning Manager网页版应用程序和设备应用程序的当前和往期版本，请参阅 [发行说明](/help/migrated/release-note/release-notes.md).

## 错误修复

如要查看本次更新中修复的错误，请参阅 [修复的错误列表](release-note/release-notes.md#bugs-fixed-in-this-release).

## 系统要求

[Learning Manager系统要求](/help/migrated/system-requirements.md)
