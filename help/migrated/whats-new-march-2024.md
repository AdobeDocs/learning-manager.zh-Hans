---
description: 了解 Adobe Learning Manager 2024 年 3 月版中的新功能和增强功能
jcr-language: en_us
title: 新功能摘要
contentowner: jayakarr
exl-id: 603f1f1c-bf8d-4807-b9f7-b10ded19a91e
source-git-commit: c833d92533b7fbf5a87c980d8b5e088185d02ef5
workflow-type: tm+mt
source-wordcount: '3903'
ht-degree: 1%

---

# 新功能摘要 {#new-features-summary}

了解 Adobe Learning Manager 2024 年 3 月版中的新增功能和增强功能。

了解一些最新的 Adobe Learning Manager 功能，例如：

1. 从外部来源导入技能
1. 多重品牌支持
1. 清单重新评估-活动模块
1. 白标移动学习应用程序

>[!NOTE]
>
>观看此 [网络研讨会](https://learningmanager.adobe.com/app/learner?accountId=98632#/course/9212121) ，详细了解此版本中的新增功能。


## 此版本中新增的功能 {#whatsnewandchanged}

### 从外部来源导入技能

使用各自的连接器从内容提供商（如 LinkedIn 和 Go1）导入技能。 此增强功能是提高学习管理器与外部技能云和人才管理系统集成能力的目标的一部分。 导入的技能将添加到学习管理器中管理员定义的技能中，并在课程创建工作流程中可供作者使用。 还对整个平台的技能搜索功能进行了增强，以便在帐户具有大量技能时提供更好的搜索体验。

查看 [导入技能](administrators/feature-summary/import-skills-external-sources.md) 以了解更多信息。

### 自定义品牌

您现在可以根据帐户中可用的用户组自定义某些 UI 元素，即组织名称、徽标和 UI 主题。 例如，具有多个部门的组织可以设置要为每个部门显示的自定义徽标和 UI 主题。

>[!NOTE]
>
>此多重品牌功能不适用于管理员视图。 他们将始终在其帐户中看到组织级别的品牌。 这是因为这是一项面向学习者的功能，管理员可能不希望在自己的帐户中加入该功能。

有关详细信息，请查看 [多个自定义品牌](administrators/feature-summary/themes.md#multiple-branding) 。


## 针对拥有庞大用户群的帐户所做的更改

### 管理员 - 课程或学习路径页面

如果注册了大量学习者加入课程，例如，超过 50,000 人，则不会显示学习者列表。 您可以在搜索&#x200B;*学习者搜索栏中搜索学习者*，也可以选择&#x200B;**搜索栏顶部的“下载**”链接来下载学习者列表。

### 管理员 - 学习者页面

搜索任何用户时，“ **下载学习者** ”和 **“导出** ”选项会下载相同的报告。 同时，在搜索用户组时，您现在可以从该用户组下载过滤后的用户。 搜索用户组时，
“ **下载学习者列表** ”更改为 **“下载用户组** 的学习者列表” **“导出** ”选项会再次下载整个列表。

### “管理员 - 用户”页面

#### 内部用户

例如，如果用户数超过 50,000，则会显示一条消息，要求下载数据以供以后进行更详细的分析。 搜索栏现在突出显示，并以“*名称、电子邮件 |UUID。*

>[!NOTE]
>
>仅当为帐户启用了 UUID 时，才会显示 UUID。

#### 外部用户

对于外部用户，相同的行为也适用。 如果用户数量很大，您可以下载用户，还可以在搜索&#x200B;*后以名称，电子邮件|UUID。*

#### “用户清理”页面

在“用户清理”页面上，对于已删除的用户，我们移除了“删除&#x200B;**日期”的**&#x200B;排序功能。您只能对 UUID 进行排序。

### 管理员实例页面

#### 课程或学习路径

如果注册人数很大，Adobe Learning Manager 将不会显示学习者人数。 相反，会显示一个图标，您可以选择该图标，查看学习者数量并导航到“学习者”页面。

学习者数量将显示为近似值。 例如，如果学习者数量超过 50,000，则该值将显示为 50K+。

### 管理员 - L1/L3 页面

在 L1 反馈页面上，如果课程注册数量很大，则不会显示学习者列表。 相反，您可以导出用户列表以供以后进行更详细的分析。

搜索支持提前键入，结果仅限于所选实例。

#### 出勤和得分页面

在页面上，当您搜索用户时，将在所有可用实例中执行搜索。 但是，结果针对所选实例。

在“出勤”页面，如果您搜索某个用户组，且该用户组中的用户数超过 10,000 且无论注册人数如何，则只能执行批量操作。 您将无法查看用户列表。

如果用户组中的用户数少于 10,000，则您可以执行单个用户级操作以及批量级别操作。 在这种情况下，不会禁用用户列表。

### 管理员 - 认证页面

在当前版本的 Adobe Learning Manager 中，如果有大量用户注册了认证，您将无法查看未注册的学习者，因为“ **状态** ”下拉列表处于禁用状态。

在此版本的 Adobe Learning Manager 中，如果注册用户数量很大，则“**状态**”下拉列表仅显示两个选项 -**“已注册”和**“**未注册**”。默认情况下，“已注册”**选项**&#x200B;处于选中状态。如果您选择“未注册”****，将显示未注册的学习者列表。

#### 用户组变更

对于某个用户组，如果用户组中的用户数少于 50,000，则“ **状态** ”下拉列表将显示所有选项 - 已认证、已分配和即将过期。

如果用户组中的用户数量很大，则根据新设计，“ **状态** ”下拉列表仅显示两个选项 - **已注册** 和 **未注册**。

### 比较表

<table>
    <tbody>
        <tr>
            <td><b>页面</b></td>
            <td><b>阈值更改之前</b></td>
            <td><b>阈值更改后</b></td>
        </tr>
        <tr>
            <td>管理员 - 课程实例</td>
            <td>实例按设计方式显示，如下所示：
            <ul>
                <li>模块</li>
                <li>已注册的学习者</li>
                <li>会话</li>
                <li>徽章</li>
                <li>已启用 L1 反馈</li>
                <li>通知警报</li>
                <li>游戏点数</li>
                <li>二维码</li>
                <li>学习路径扩展</li>
            </ul>
            <td>
                <ul>
                    <li>如果注册人数超过预定义的阈值，ALM 将不会显示计数;它会用图标替换计数，单击该图标时会显示实际的学习者数量以及一个用于转到学习者页面的链接。</li>
                    <li>注册人数将以近似格式显示。 例如，如果数字超过 50,000，则在课程级别中计数将显示为 50K+。</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>管理员 - 学习者页面</td>
            <td>
                    <ul>
                        <li>将显示每个实例的学习者列表。</li>
                        <li>您可以搜索已注册课程的用户或用户组。</li>
                        <li>导出的报告不包含任何用户组过滤器。</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>实例选择被禁用。</li>
                    <li>除一种情况外，下载学习者列表还会下载相同的数据。 如果您搜索用户组，然后选择“下载学习者列表”，则会下载该用户组数据。</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>管理员 - L1/L3 反馈页面</td>
            <td>
                <p>现有行为无变化</p>
            </td>
            <td>
                <ul>
                    <li>实例选择被禁用。</li>
                    <li>如果课程注册量超过 50K，ALM 不会列出学习者，而仅显示搜索栏。 如果注册人数少于 50K，ALM 会同时显示学习者列表和搜索栏。</li>
                    <li>默认情况下，商品信息处于停用状态。</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>管理员 - 出勤和得分页面</td>
            <td>
                <p>现有行为无变化</p>
            </td>
            <td>
                <ul>
                    <li>搜索用户时禁用实例选择。</li>
                    <li>例如，如果用户数超过 50,000，则会有一条额外的消息用于下载数据，以便稍后进行更详细的分析。 搜索栏现在突出显示，并以“名称、电子邮件 |UUID。</li>
                    <li>如果用户组中的用户数（无论是否注册）均少于 10,000，则您可以执行单个用户级操作以及批量级别操作。 在这种情况下，不会禁用用户列表。</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>管理员 - L2 测验分数页面</td>
            <td>
                    <ul>
                        <li>还实现了用户搜索。</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>还实现了用户搜索。 在 LO 级别进行预键入搜索时，列表将筛选为当前选定的实例。</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>“管理员 - 用户”页面（内部、外部）</td>
            <td>
                    <ul>
                        <li>搜索用户时会显示电子邮件 ID。</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>例如，如果用户数超过 50,000，则会显示一条附加消息，用于下载数据以供以后进行更详细的分析。 搜索栏现在突出显示，并以“名称、电子邮件 |UUID。</li>
                    <li>在“用户清理”页面上，对于已删除的用户，我们移除了“删除日期”的排序功能。 您只能对 UUID 进行排序。</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>讲师 - 提交</td>
            <td>
                    <ul>
                        <li>要提交的模块的分页。</li>
                        <li>作为教师，您现在可以按照状态、结束审阅、待提交、通过和失败等方式过滤学习者提交的文件。 </li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>在该实例中，您只能搜索用户，而不能搜索用户组。</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>将预览作为学习者页面计数</td>
            <td>
                    <ul>
                        <li>计数包括来自更高订单注册的数据。</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>计数排除来自高阶注册的数据。</li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

## 高级搜索功能

在此版本中，我们增强了搜索体验。 搜索结果不仅基于元数据，还基于语义和内容内搜索，以根据精度、新近度和相关内容得出结果。

此更改反映在以下方面：

* 目录和我的学习页面：已移除将鼠标悬停在课程、学习路径和认证上的操作。
* 搜索栏的外观。
* 在学习应用程序中添加了筛选器标记。

要启用搜索功能，请联系 Adobe Learning Manager 的CSAM团队。

## 用户界面更改 {#ui-changes}

### 课程创建页面

将课程映射到技能级别时，技能列表是搜索优先的。 换句话说，搜索技能，您将看到与搜索词匹配的技能列表。

### 用户组

#### 管理员：学习者页面

搜索任何用户时，“ **下载学习者** ”和 **“导出** ”选项会下载相同的报告。 同时，在搜索用户组时，您现在可以从该用户组下载过滤后的用户。 搜索用户组时，“ **下载学习者”列表** 会更改为 **“下载用户组** 的学习者列表” **“导出** ”选项会再次下载整个列表。

## 对报告的更改

* 培训报告中的标签和技能列更改为标签和技能。
* 添加了报告 [游戏审核跟踪](administrators/feature-summary/reports.md#gamification-audit-trail)。
* 如果某个帐户包含超过 280000 名分配到某项技能的学习者，则技能学习者报告会以压缩 csv 形式下载。如果帐户的学习者少于 250000 人，则会以 CSV 的形式下载相同的报告。在“管理员”页面上，选择“管理员>**技能”>“**&#x200B;学习者技能”>******。** ****&#x200B;报告将下载为 CSV。
* “ [会话摘要”报告](administrators/feature-summary/reports.md#session-summary-report) 有两个新列 - 位置信息和位置区域。

## 对教室创建的更改

根据 [管理员设置](administrators/feature-summary/classroom.md#classroom-settings)，作者的您可以 [创建、修改和删除位置](administrators/feature-summary/classroom.md#add-classroom-location)。

>[!NOTE]
>
>添加位置和目录标签时，作者（在课程创建页面中）和管理员（在实例页面中）将分别看到自动填充的位置和目录标签列表。

作为管理员，您可以对作者修改或删除教室位置施加限制。 查看 [“课堂”设置](administrators/feature-summary/classroom.md#classroom-settings) 了解更多信息。

## 对灵活学习路径的更改

所有帐户（旧帐户和新帐户）都将在学习者应用程序中开始操作，包括注册截止日期、取消注册截止日期和名额限制，以实现灵活的学习路径。学习者现在可以注册灵活学习路径，而无需选择任何课程实例。

## 学习计划的新触发条件

学习计划设置页面中添加了新的触发器。 作者和管理员现在可以在学习者未通过课程模块时触发操作。

有关详细信息，请查看 [学习计划](administrators/feature-summary/learning-plans.md) 。

## 新提交状态

作为教师，您现在可以按照状态、结束审阅、待提交、通过和失败等方式过滤学习者提交的文件。

有关详细信息，请查看 [提交状态](instructors/feature-summary/learners.md#filter-file-submissions) 。

## 核对清单增强功能

在 Adobe Learning Manager 2024 年 3 月版中，对清单工作流程进行了以下增强：

### 禁止核对清单失败的进度

创建核对清单时，作者可以在“必填核对表”部分中选择 **“启用** ”。 如果学习者未通过检查表，则无法继续学习模块。 他们只有在通过清单后才能继续。

然后，清单审阅者（即讲师或经理）可以检查清单的状态。 审阅者还可以不按顺序查看学习者的清单。

### 重新评估清单

创建核对清单时，作者可以在“重新评估”部分中选择 **“启用** ”。 这样，经理或讲师可以重新评估学习者，直到他们通过核对表为止。

如果模块是必需的，则默认情况下会选中“重新评估”复选框。

启用重新评估后，讲师或经理还可以将核对清单的状态从“失败”更改为“通过”。

在核对清单页面上，讲师可以看到处于“待处理”状态的学习者数量。 作为讲师，您可以评估学习者并通过或不及格。 如果学习者处于失败状态，您只能在未启用重新评估时查看核对清单。

这意味着在创建清单时， **未在“重新评估”部分中选中“启用** ”复选框。 如果选中此复选框，则您可以在讲师清单页面上看到“查看/重新评估”按钮。

选择此按钮后，您可以重新评估学习者，并将其标记为通过或失败。

>[!NOTE]
>
>这两个功能 - 重新评估和将清单设置为强制性 - 仅适用于新创建的模块。 课程发布后，无法打开/关闭这些设置。


有关详细信息，请参阅 [创建清单](authors/feature-summary/courses.md#checklist-fail) 。

## 其他增强功能

### 与会话相关的电子邮件通知

在 Adobe Learning Manager 的早期版本中，学习者在以下情况下未发送与会话相关的电子邮件、更新会话详细信息、会话邀请和会话提醒：

* 学习者已完成课程，
* 将新会话添加到课程中，或者
* 对现有会话进行了更改。

在 Adobe Learning Manager 2024 年 3 月版中，新增了以下内容：

* 课程详细信息已更新，会话邀请也已更新（针对学习者和讲师）
   * 对于未来的会话，将弃用更新会话详细信息&#x200B;**以及**&#x200B;已注册学习者和当前讲师的会话邀请&#x200B;**的电子邮件**。对于过去的会话，包含 **已注册学习者和当前讲师的“会话详细信息”已更新** 以及 **“会话邀请** ”的电子邮件将保持不变。
* 提醒电子邮件（适用于管理员和学习者）
   * 对于将来的会话，将仅 **发送会话提醒** 电子邮件。

>[!NOTE]
>
>邮件不依赖于会话和课程的完成情况。


### AEM 引用站点更改

在 AEM 参考站点中，我们添加了对将管理员刷新令牌添加到学习者访问令牌的支持。

### 对讲师隐藏提交的内容

学习者使用文件提交工作流程上传文件后，如果教师未对提交内容执行任何操作（批准或拒绝），则提交 URL 会在预定义的天数后从视图中隐藏。 请联系 Adobe Learning Manager 的CSAM团队以设置或更改天数。

### 产品术语变更

我们已将“实例”和&#x200B;*“学习者*”*列*&#x200B;添加到产品术语词汇表中。

### 移动应用变更

在此移动应用程序版本中，学习者可以安排和管理逾期课程提醒。 单击过期的提醒通知后，您可以访问以下选项：

* 取消
* 转到课程
* 3天后再提醒我
* 一周后再提醒我

在 Android 上：单击推送通知会将您转到“ **课程概述** ”页面。在 iOS 上：单击推送通知会将您定向到应用程序的主页。 这是 iOS 中的已知限制。

### Salesforce 上学习者应用程序中的核对清单更改

如果学习者未通过核对表，则无法继续下一模块或课程。 选中“必修清单”复选框后，如果学习者未通过清单，则无法继续学习课程。

与 Web 应用程序一样，如果学习者未通过 Salesforce 应用程序上的核对清单，他们将看到一条消息，并且不会继续操作。

### Connect VC 中的更改

在 Adobe Learning Manager 的当前版本中，当学习者注册 Connect VC 会话但未满足完成条件时，其会被标记为 **“未参加** ”。

在此版本中，状态更改为“ **尚未标记**”。

### Adobe Learning Manager 中的白标

Adobe Learning Manager 移动应用程序现在支持白标，这意味着您现在可以以自己的品牌发布应用程序。

有关详细信息，请查看 Adobe Learning Manager 移动应用程序](white-label.md)中的[白标。

### 迁移 CSV 中的新列

在此版本中，以下迁移 CSV 中新增了一列可选列 uniqueLoId。

* certification.csv
* course.csv
* learning_program.csv

>[!NOTE]
>
>**唯一 LoId** 列是可选的。


如果您执行迁移以更新现有课程或学习计划或认证，则具有 **唯一 LOId**&#x200B;的课程或学习计划或认证会被添加到作者应用程序中。

迁移时，您必须更新 **课程或学习计划或认证的 CSV 中的唯一 LOId** 值，即使它是可选列也是如此。

**如果在执行迁移之前未添加 uniqueLoId** 列，同时更新具有 **uniqueLOId**&#x200B;的现有课程或学习计划或认证，则在迁移后，**唯一 LOId** 值将被 NULL 值覆盖。

>[!NOTE]
>
>唯一 **LoId** 列不适用于工作辅助 CSV。


>[!IMPORTANT]
>
>列值在整个帐户中必须是唯一的。 您不能将同一值用于课程或认证。

从迁移手册](integration-admin/feature-summary/migration-manual.md#csv-specifications-and-sample-csvs)下载 [CSV。


### 应用评级

学习者可以对 Adobe Learning Manager 应用程序提供反馈，以进一步增强应用程序体验。 如果学习者的评分为 4 星或更多，则会显示一个弹出窗口，要求学习者在 Play 商店或 App Store 上对应用程序进行评分。

### Bluejeans 已于 2024 年 2 月达到生命周期结束 （EOL）

我们想通知您，Bluejeans 已于 2024 年 2 月结束其生命周期 （EOL）。 2024 年 2 月之后，Bluejeans 将不再收到更新或支持。 我们的CSAM和支持团队将协助您解决在此过渡期间可能遇到的任何问题或疑虑。

在 Adobe Learning Manager](integration-admin/feature-summary/connectors.md) 中查看[连接器，了解有关配置连接器的更多信息。

### 对登录访问报告的更改

“登录访问”报告将仅针对过去五个季度提供。 如果任何集成管理员请求按需下载统一导出并选中登录访问权限&#x200B;**，** Adobe Learning Manager 将显示一条错误消息。但是，这对其他报告没有影响。

### ADFS 变更

ADFS 中的“员工类型”和“员工 ID”字段现在可以在 Adobe Learning Manager 上根据映射使用。

## 此版本中的 API 更改

### 学习者 API

在此版本中，我们添加了 API 支持，供学习者在用户组级别查看品牌徽标和个性化主题。

API /account 和 /user？include=account 返回四个字段，这些字段被覆盖，特定于属于 logoUrl、logoStyle 和 themeData 的用户的活动字段。

### 新属性

learningObjectResource 中的新属性 isExpiredSubmit，用于显示资源中的提交是否已过期。

* GET /account API：返回新属性 **expireSubmitDuration** X，其中 X 是设置的天数。 如果未设置，将返回 0
* GET /LO API 与资源包括新属性 **isExpiredSubmit**“ True 或 False。
   * 如果提交已过期且未显示“submitUrl”，则为 True。
   * 如果为 False，则提交未过期，并提取“submitUrl”。

### 清单中的 API 更改

一门课程可以由多个模块组成，其中清单是其中的一种模块。 此清单模块由讲师进行评估，可以根据评估将其标记为“失败”或“成功”。

但在这两种情况下，核对清单状态均标记为已完成，这样，课程也会标记为已完成。

在此版本中，LO API 包含参数 *“是清单必需的*”。 如果值为 True，则清单是必需的。

### 支持多种区域设置

管理员现在可以下载自己选择的语言版本的 L1 反馈报告。 但是，目前还无法下载 Power BI 的 L1 反馈报告。 在 API 请求中，使用 preferredLocale 参数指定您选择的区域设置。

### 实例摘要计数的变化

这适用于教室/VC 课程注册人数超过 1000 的帐户。

如果该数字小于 1000，则注册将使缓存失效，并在 GET 摘要 API 调用中返回更新的值，例如注册数、完成数和 seatLimit。

如果为此功能启用了帐户，并且注册数超过 1000，则会从缓存中检索这些值。

### 已弃用的路径

目前，学习管理器 API 遵循图形数据结构，允许您通过包含遍历 API 模型来获取数据。 尽管您最多可以遍历 7 个级别的 API，但使用单个 API 调用获取数据的计算成本很高。

我们建议所有现有客户和新客户多次拨打小额电话，而不是一次大电话。 此方法将防止在调用中加载不需要的数据。

#### 弃用了哪些路径

以下路径已弃用：

* /learningObjects
   * 弃用的路径：
      * enrollment.loInstance.loResources.resources
      * instances.loResources.resources
   * 现有路径：
      * enrollment.loInstance
      * instances.loResources
* /学习对象/{id}
   * 弃用路径：
      * enrollment.instances.subLoInstances.learningObject
   * 现有路径：
      * enrollment.instances.subLoInstances
* /入学 人数
   * 弃用路径：
      * loInstance.learningObject.enrollment
   * 新路径：
      * loInstance.learningObject
* /学习对象/{id}
   * 弃用路径：
      * instance.subLoInstances.learningObject.enrollment.loResourceGrades
   * 新路径：
      * instance.subLoInstances

### 作业 API 的登录访问和用户审核报告存档更改

在此版本中，作业 API 将保留最多五个季度的登录访问报告和六个月的用户审核报告。 如果要下载早于此时间段的数据，则必须传递 archive 参数，指定季度和年份。 请参阅示例有效负载。

```
{
    "data": {
        "type": "job",
        "attributes": {
            "description": "description of your choice",
            "jobType": "generateLoginAccessReport",
            "payload": {
                "fromDate": "2023-04-01T18:30:00.000Z",
                "toDate": "2023-04-30T18:30:00.000Z",
                "archive": {
                    "quarter": "4",
                    "year": "2021"
                }
            }
        }
    }
}
```

如果您尝试下载 **超过五个季度的登录访问** 报告，则会显示一条错误消息。 如果您尝试下载 **超过六个月的用户审核** 报告，则会显示类似的错误消息。

### 已弃用的 API

在 Adobe Learning Manager](api-deprecations-list.md) 中查看 [API 弃用情况，获取产品中所有已弃用 API 的累积列表。

## 本次更新中修复的错误 {#bug-fixes}

* 学习者注册了一门课程，然后尝试注册另一门课程时，系统会显示一条警告消息。
* 用户组即使在被删除后，也会显示在搜索中。
* 当用户触发大量数据的大量学习者成绩单时，学习者成绩单队列将被阻止，并阻止新请求。
* 如果子帐户请求其父帐户共享报表，则父帐户无法这样做。
* 课程和学习路径中的 URL 会重定向到不正确的位置。
* 学习者单击目录页面上的课程链接时，间歇性地查看其他课程的课程实例。
* “ **取消注册** ”按钮在首次注册后未按预期显示，但该按钮在刷新后显示。
* 您无法保存名称中包含空格的内容或测验。
* 在经理批准的课程中，您可以重新注册用户组中的学习者。
* 在某些情况下，如果您尝试添加其他活动字段，则会显示错误消息“无法保存活动字段”。
* 文本以课程名称溢出，位于“相关课程”部分中的课程卡内。
* 切换实例并将学习者注册到实例后，旧实例仍会存在于 Outlook 日历中。
* 配对帐户中的学习者尝试选择课程缩略图时，系统会显示错误消息。
* 学习者注册课程时，会收到多条注册通知。
* 如果用户手动更改在连接器中创建的目录的名称，则会创建新目录，并将课程发布到不正确的目录。
* 属于非活动帐户的用户仍会收到订阅电子邮件。

### API 相关的错误修复

* API GET/users 不会检索经理的详细信息。
* 在帐户中，用户是通过计划的 FTP 用户在计划的停机时间内导入创建的。
* 在移动应用程序或沉浸式模式中，删除或停用课程实例并选择下一个活动实例后， **将显示注册兴趣** 按钮而不是 **注册**。
* 当配对帐户中的学习者尝试使用学习对象 API 选择课程缩略图时，会显示错误“403 禁止访问”。

## 系统要求

查看 [Adobe Learning Manager 系统要求](system-requirements.md)。

## Adobe Learning Manager 的早期版本

* [2023 年 11 月版](whats-new-november-2023.md)
* [2023 年 7 月版](whats-new-2023-july.md)