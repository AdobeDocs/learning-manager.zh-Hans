---
description: 了解管理员可配置的 Adobe Learning Manager 帐户设置。
jcr-language: en_us
title: 设置
contentowner: manochan
exl-id: a563d955-f67e-4218-88df-625cde673601
source-git-commit: a28ac8f57710c118ca4ad02872fd100c6f24beac
workflow-type: tm+mt
source-wordcount: '3669'
ht-degree: 64%

---

# 设置

了解管理员可配置的 Adobe Learning Manager 帐户设置。

您可以更改管理员个人资料设置并更新自己的帐户设置。View your profile information, add/change profile photo, and modify **[!UICONTROL About me]** content. 更新公司信息，为用户设置登录方法，并通过帐户设置来设置连接集成。

![](assets/settings-admin.png)

## Configure your Adobe Learning Manager

This training captures the basics of account-level settings.

[![按钮](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7476018)


如果您无法启动培训，请写入<almacademy@adobe.com>。

## 帐户设置 {#accountsettings}

要更新组织的帐户设置，请单击左侧窗格中的&#x200B;**[!UICONTROL 设置]**。

**基本信息（公司信息）**

单击该页面上的&#x200B;**[!UICONTROL 更改]**&#x200B;并编辑国家/地区、时区、语言设置和财年设置。

**配置“联系管理员”**

如果要添加或更改公司支持管理员的电子邮件地址，可以单击左侧窗格中的&#x200B;**[!UICONTROL 常规]**&#x200B;进行配置。单击&#x200B;**[!UICONTROL 支持电子邮件ID]**&#x200B;旁边的&#x200B;**[!UICONTROL 更改]**&#x200B;并添加电子邮件ID。 当学习者单击页面页脚处的&#x200B;**[!UICONTROL “联系管理员”]**&#x200B;时，即会向这些管理员发送电子邮件。

添加其他以分号作为分隔符的电子邮件ID。

**登录方法** — 管理员可以选择您的内部或外部用户访问帐户时所用的模式。

* **内部用户：**&#x200B;对于内部用户，您可以将Adobe ID或单点登录设置为登录模式。
* **外部用户：**&#x200B;对于外部用户，您可以设置Adobe ID、单点登录或Learning Manager ID。

如果选择Learning Manager ID，则外部用户可以在创建其Learning Manager用户名和密码后登录此帐户。

>[!NOTE]
>
>如果设置了多个外部配置文件，则所有配置文件都可以具有任何一种登录类型。 例如，如果登录类型为 Adobe ID，则所有用户均必须仅使用 Adobe ID 登录。每位用户均无其自身的登录类型。

您可以使用 Adobe ID 或单点登录，访问 Adobe Learning Manager 应用程序。单点登录机制允许用户仅进行一次身份验证即可多次访问多个应用程序。此项配置对企业并非必需配置。如果公司有基于 SAML 2.0 的 SSO 提供程序，可以用来配置 Adobe Learning Manager 应用程序。此项配置应在公司级别和 Adobe Learning Manager 应用程序级别进行配置。如果选择使用 SSO，请联系 Adobe 支持获取配置说明。

**反馈**

单击左侧窗格中的&#x200B;**[!UICONTROL 反馈]**，设置问卷，获取学习者完成课程后的反馈。有关创建L1和L3反馈的信息，请参阅[课程功能帮助内容](/help/migrated/administrators/feature-summary/courses.md#add-l1-and-l3-feedback)。

**多次尝试**

选择“**[!UICONTROL 设置]**”>“**[!UICONTROL 常规]**”>“**[!UICONTROL 多次尝试]**”。

如果启用“多次尝试”复选框，则作者可以为交互式电子学习课程或模块设置“多次尝试”。选中第二个复选框后，管理员可以默认为任何新创建的交互式电子学习课程设置“无限次尝试”。

![](assets/admin-config.png)

*选中“多次尝试”复选框*

**课程审阅**

在左侧窗格中单击&#x200B;**[!UICONTROL “常规”]**，然后选择“课程审阅”选项以启用“课程审阅”功能。 要了解有关此功能的更多信息，请参阅[课程审阅](courses.md#main-pars_header_1879001177)。

**讨论区**

如果启用“讨论板”复选框，则学习者和讲师可以使用学习者应用程序中“课程”页面的“讨论”选项卡发布课程评论。但是，如果课程级别的设置显示此功能未选中，则课程级别的设置应优先于管理员设置。

**学习者信息板**

在左侧窗格中，单击“学习者信息板”。此页面允许您选择要在学习者页面上显示的小组件。选择要在学习者页面启用的小组件。未选择的小组件将不会显示在学习者页面上。

**Adobe Connect**

单击左侧窗格中的&#x200B;**[!UICONTROL Adobe Connect]**&#x200B;以配置Adobe Connect帐户以主持虚拟教室会话。 有关详细信息，请参阅[Adobe Connect](adobeconnect-integration.md)功能帮助。

## 常规设置 {#general}

启用或禁用以下设置：

<table>
 <tbody>
  <tr>
   <th>
    <p><b>名称</b></p>
    </th>
   <th>
    <p><b>描述</b></p>
   </th>
  </tr>
  <tr>
   <td>显示课程效果</td>
   <td>如果启用，学习者可以在课程磁贴上看到当前的课程效果。 此功能仅适用于课程。 学习计划或证书不支持星级评分。 适用于课程和学习计划，但不适用于认证。</td>
  </tr>
  <tr>
   <td>课程审阅</td>
   <td>如果启用，对课程的所有更改必须需要管理员批准，之后学习者方可看到这些课程。</td>
  </tr>
  <tr>
   <td>讨论区</td>
   <td>如果启用“讨论板”复选框，则学习者和讲师可以使用学习者应用程序中“课程”页面的“讨论”选项卡发布课程评论。但是，如果课程级别的设置显示此功能未选中，则课程级别的设置应优先于管理员设置。</td>
  </tr>
  <tr>
   <td>多次尝试</td>
   <td>如果启用，作者可以为课程模块配置多次尝试。</td>
  </tr>
  <tr>
   <td>探索“技能”选择</td>
   <td>如果启用，学习者可以探索同伴技能和领导技能，并订阅他们选择的技能。</td>
  </tr>
  <tr>
   <td>技能/标签可视性</td>
   <td>向学习者显示所有技能和标签。您可以显示所有技能和标签，也可以显示已分配的技能和标签，或者是学习者可见目录部分中的技能和标签。</td>
  </tr>
  <tr>
   <td>学习对象的唯一 ID</td>
   <td>如果启用，管理员或作者可以为每个学习对象添加唯一 ID。</td>
  </tr>
  <tr>
   <td>显示过滤器面板</td>
   <td>
    <p><a id="filter-panels"></a>控制哪些过滤器面板可供学习者应用程序中的用户使用，以优化他们的搜索结果。 选项如下：</p>
    <ul>
     <li>目录</li>
     <li>类型</li>
     <li>格式化</li>
     <li>持续时间</li>
     <li>技能</li>
     <li>技能级别</li>
     <li>标记</li>
    </ul>
    <p>学习者启动学习者应用程序时，在“我的学习”和“目录”部分中，学习者可以在各自的面板中查看过滤器。</p>
    <p><b>注意： </b>默认情 <b>况 </b>下， <b>“格 </b>式”和“持续时间”会关闭，并且不会在发布后立即显示给学员。管理员应启用这些过滤器。 <br></p></td>
  </tr>
  <tr>
   <td>显示目录列表</td>
   <td>如果启用，学习者可以看到他们可用的所有目录的列表。学习者可以使用它来优化学习对象的显示方式。</td>
  </tr>
  <tr>
   <td>产品术语</td>
   <td>Adobe Learning Manager 具有在整个产品中使用的标准术语。修改术语以符合公司的需要。</td>
  </tr>
  <tr>
   <td>模块版本更新</td>
   <td>配置默认设置，以更新内容。可以为课程页面中的每个内容修改设置。</td>
  </tr>
  <tr>
   <td>自动注册用户</td>
   <td>如果启用，则新导入的用户将自动注册。默认情况下，必须手动注册用户，之后用户才能开始使用 Adobe Learning Manager。</td>
  </tr>
  <tr>
   <td><a id="autodelete"></a>自动删除内部用户</td>
   <td>如果启用，当内部用户在指定的天数内未访问系统时，则会被自动删除。此功能适用于仅具有<b>“学习者”</b>角色的用户。要恢复访问权限，用户必须与管理员联系。<br></td>
  </tr>
  <tr>
   <td>显示目录标签</td>
   <td>如果启用，管理员和作者便可以设置目录标签和值，并将其链接到学习对象。 选择此选项后，作者还可以在目录中添加课程、学习路径、认证或工作辅助。</td>
  </tr>
  <tr>
   <td>学习者可以查看自己的成绩</td>
   <td>如果启用，学习者可以在学习者成绩单中查看自己的分数。</td>
  </tr>
  <tr>
   <td>摘要电子邮件</td>
   <td>
    <p>管理员可启用或禁用向学习者发送邮件的功能。 管理员还可以控制电子邮件的发送频率。</p>
    <ul>
     <li>对于<b>活跃帐户</b>，系统默认禁用摘要电子邮件，但管理员可以手动启用此功能。</li>
     <li>对于<b>试用帐户</b>，摘要电子邮件选项将保持禁用状态，且管理员亦无法启用该选项。</li>
    </ul>
    <p>若已禁用该功能，则：</p>
    <ul>
     <li><b>“摘要电子邮件”</b>选项将失效。</li>
     <li>学习者无法查看摘要电子邮件订阅的用户设置。</li>
    </ul>
    <p> 如果启用该功能，则：</p>
    <ul>
     <li>管理员可以启用及修改摘要电子邮件选项。</li>
     <li>在“学习者”应用程序的<b>“个人资料设置”</b>中，学习者（不在 DND 列表中）可以选择订阅/退订摘要电子邮件。</li>
    </ul></td>
  </tr>
  <tr>
   <td>启用训练卡图标<br></td>
   <td>一经启用，图标就会显示在学习者应用的训练卡上。<br></td>
  </tr>
  <tr>
   <td>页脚链接</td>
   <td>
    <p>添加显示为页脚的链接或电子邮件 ID。您最多可以添加三个页脚链接。</p>
    <p>要自定义页脚上的链接，请执行以下步骤：</p>
    <ol>
     <li>单击<b>“添加更多”</b>，在指定的字段中输入名称和 URL 或电子邮件 ID。使用 http:// 或 https:// 作为 URL 的前缀。</li>
     <li>要在所有区域设置中级联更改，请单击<b>“复制”</b>。这样可确保所有语言都获得此名称和 URL。</li>
     <li>要保存更改，请单击<b>“保存”</b>。您可以看到一条确认更改的弹出消息。单击“确定”后，页脚将填充新添加的链接。</li>
    </ol>
    <p>此外，您还可以：</p>
    <ul>
     <li>单击<b>重置</b>图标以重置<b>帮助</b>和<b>联系管理员</b>字段中的默认值。</li>
     <li>自定义所有语言页脚上的链接。点击<b>“语言”</b>下拉列表，选择语言，并在指定的字段添加<b>“名称”</b>和<b>“URL”</b>。保存更改后，页脚上将显示更新的链接。<br></li>
    </ul></td>
  </tr>
  <tr>
   <td>报告时区<br></td>
   <td>
    <p>Set an account level preference to export the Learning Transcript in the following time zones:</p>
    <ul>
     <li>UTC（默认行为）</li>
     <li>帐户级时区首选项</li>
    </ul>
    <p>使用作业API下载的学习者成绩单还可以下载选定时区中的数据。</p>
    <p><b>注意： </b>默认情况下，发布后的“学习者成绩单”短时间内不会有任何更改。 管理员可通过“管理员”&gt;“设置”&gt;“常规”&gt;“报告时区”来配置此设置。</p></td>
  </tr>
 </tbody>
</table>

<table border="0" cellpadding="0" cellspacing="0" width="1709">
 <tbody>
  <tr>
   <td height="20" width="147">名称</td>
   <td>描述</td>
  </tr>
  <tr>
   <td height="20">显示课程效果</td>
   <td>如果启用，学习者可以在课程磁贴上查看当前的课程效果。</td>
  </tr>
  <tr>
   <td height="20">课程审阅</td>
   <td>如果启用，对课程的所有更改必须需要管理员批准，之后学习者方可看到这些课程。</td>
  </tr>
  <tr>
   <td height="20">讨论区</td>
   <td>如果启用“讨论板”复选框，则学习者和讲师可以使用学习者应用程序中“课程”页面的“讨论”选项卡发布课程评论。但是，如果课程级别的设置显示此功能未选中，则课程级别的设置应优先于管理员设置。</td>
  </tr>
  <tr>
   <td height="20">多次尝试</td>
   <td>如果启用，作者可以为课程模块配置多次尝试。</td>
  </tr>
  <tr>
   <td height="20">探索“技能”选择</td>
   <td>如果启用，学习者可以探索同伴技能和领导技能，并订阅他们选择的技能。</td>
  </tr>
  <tr>
   <td height="20">技能/标签可视性</td>
   <td>向学习者显示所有技能和标签。您可以显示所有技能和标签，也可以显示已分配的技能和标签，或者是学习者可见目录部分中的技能和标签。</td>
  </tr>
  <tr>
   <td height="20">学习对象的唯一 ID</td>
   <td>如果启用，管理员或作者可以为每个学习对象添加唯一 ID。</td>
  </tr>
  <tr>
   <td rowspan="10" height="191">显示过滤器面板</td>
   <td>控制哪些过滤器面板可供学习者应用程序中的用户使用，以优化他们的搜索结果。 选项如下：</td>
  </tr>
  <tr>
   <td height="19">目录</td>
  </tr>
  <tr>
   <td height="19">类型</td>
  </tr>
  <tr>
   <td height="19">格式化</td>
  </tr>
  <tr>
   <td height="19">持续时间</td>
  </tr>
  <tr>
   <td height="19">技能</td>
  </tr>
  <tr>
   <td height="19">技能级别</td>
  </tr>
  <tr>
   <td height="19">标记</td>
  </tr>
  <tr>
   <td height="19">学习者启动学习者应用程序时，在“我的学习”和“目录”部分中，学习者可以在各自的面板中查看过滤器。</td>
  </tr>
  <tr>
   <td height="20">注意：默认情况下， “格式”和“持续时间”会关闭，并且不会在发布后立即显示给学习者。 管理员应启用这些过滤器。 </td>
  </tr>
  <tr>
   <td height="20">显示目录列表</td>
   <td>如果启用，学习者可以看到他们可用的所有目录的列表。学习者可以使用它来优化学习对象的显示方式。</td>
  </tr>
  <tr>
   <td height="20">产品术语</td>
   <td>Adobe Learning Manager 具有在整个产品中使用的标准术语。修改术语以符合公司的需要。</td>
  </tr>
  <tr>
   <td height="20">模块版本更新</td>
   <td>配置默认设置，以更新内容。可以为课程页面中的每个内容修改设置。</td>
  </tr>
  <tr>
   <td height="20">自动注册用户</td>
   <td>如果启用，则新导入的用户将自动注册。默认情况下，必须手动注册用户，之后用户才能开始使用 Adobe Learning Manager。</td>
  </tr>
  <tr>
   <td height="20">自动删除内部用户</td>
   <td>如果启用，当内部用户在指定的天数内未访问系统时，则会被自动删除。此功能适用于仅具有“学习者”角色的用户。 要恢复访问权限，用户必须与管理员联系。</td>
  </tr>
  <tr>
   <td height="20">显示目录标签</td>
   <td>如果启用，管理员和作者可以设置目录标签和值，并将它们链接到学习对象。</td>
  </tr>
  <tr>
   <td height="20">学习者可以查看自己的成绩</td>
   <td>如果启用，学习者可以在学习者成绩单中查看自己的分数。</td>
  </tr>
  <tr>
   <td rowspan="9" height="172">摘要电子邮件</td>
   <td>管理员可启用或禁用向学习者发送邮件的功能。 管理员还可以控制电子邮件的发送频率。</td>
  </tr>
  <tr>
   <td height="19">对于活跃帐户，系统默认禁用摘要电子邮件，但管理员可以手动启用此功能。</td>
  </tr>
  <tr>
   <td height="19">对于试用帐户，摘要电子邮件选项将保持禁用状态，且管理员无法启用该选项。</td>
  </tr>
  <tr>
   <td height="19">若已禁用该功能，则：</td>
  </tr>
  <tr>
   <td height="19">“摘要电子邮件”选项将禁用。</td>
  </tr>
  <tr>
   <td height="19">学习者无法查看摘要电子邮件订阅的用户设置。</td>
  </tr>
  <tr>
   <td height="19"> 如果启用该功能，则：</td>
  </tr>
  <tr>
   <td height="19">管理员可以启用及修改摘要电子邮件选项。</td>
  </tr>
  <tr>
   <td height="20">From the Profile Settings on the learber app, a learner (not in the DND list) can opt to subscribe/unsubscribe to the digest email.</td>
  </tr>
  <tr>
   <td height="20">启用训练卡图标</td>
   <td>一经启用，图标就会显示在学习者应用的训练卡上。</td>
  </tr>
  <tr>
   <td rowspan="8" height="153">页脚链接</td>
   <td>添加显示为页脚的链接或电子邮件 ID。您最多可以添加三个页脚链接。</td>
  </tr>
  <tr>
   <td height="19">要自定义页脚上的链接，请执行以下步骤：</td>
  </tr>
  <tr>
   <td height="19">1. Click Add More, enter the name, and the URL or email id in the fields specified. 使用 http:// 或 https:// 作为 URL 的前缀。</td>
  </tr>
  <tr>
   <td height="19">2. To cascade the change across all locales, click Replicate. 这样可确保所有语言都获得此名称和 URL。</td>
  </tr>
  <tr>
   <td height="19">3.要保存更改，请单击“保存”。 您可以看到一条确认更改的弹出消息。单击“确定”后，页脚将填充新添加的链接。</td>
  </tr>
  <tr>
   <td height="19">此外，您还可以：</td>
  </tr>
  <tr>
   <td height="19">单击“重置”图标以重置“帮助”和“联系管理员”字段中的默认值。</td>
  </tr>
  <tr>
   <td height="20">自定义所有语言页脚上的链接。单击“语言”下拉列表，选择语言，并在指定字段中添加“名称”和“URL”。 保存更改后，页脚上将显示更新的链接。</td>
  </tr>
  <tr>
   <td rowspan="5" height="96">报告时区</td>
   <td> Set an account level preference to export the Learning Transcript in the following time zones:</td>
  </tr>
  <tr>
   <td height="19">UTC（默认行为）</td>
  </tr>
  <tr>
   <td height="19">帐户级时区首选项</td>
  </tr>
  <tr>
   <td height="19">使用作业API下载的学习者成绩单还可以下载选定时区中的数据。</td>
  </tr>
  <tr>
   <td height="20">注意：默认情况下，发布后的“学习者成绩单”短时间内不会有任何更改。 管理员可通过“管理员”&gt;“设置”&gt;“常规”&gt;“报告时区”来配置此设置。</td>
  </tr>
  <tr>
   <td height="19">Badgr 集成</td>
   <td>启用后，学习者将能够上传徽章到 Badgr 网站。 在客户教育方案中，组织希望能够“认证”客户，并让客户可以在社交媒体上展示这些证书。 这会激励学习者参加培训并与他人分享其成就。 </td>
  </tr>
  <tr>
   <td height="135">
    <p>显示评级</p></td>
   <td>
    <ul>
     <li>如果启用<b>“课程效果”</b>选项，学习者将只能看到课程效果值。</li>
     <li>如果启用<b>“星级评分”</b>选项，学习者将只能查看平均星级和已对课程进行评级的学习者人数。<br></li>
    </ul>
    <p>此功能仅适用于课程。 学习计划或证书不支持星级评分。<br><br><b>注意： </b>此更改仅影响学习者应用。 </p>
    <p>更改设置（星级评分/课程效果/禁用显示评级）不会对其他任何应用（管理员、作者、经理、自定义管理员、自定义作者）产生丝毫影响。 </p>
    <p>对于新帐户，<b>显示评级</b>部分将默认启用<b>星级评分</b>选项。</p>
    <p>对于现有帐户，如果帐户以前启用了<b>课程效果</b>选项，则将启用<b>显示评级</b>部分，并选择“课程效果”选项。 如果禁用选项<b>“课程效果”</b>，则<b>“显示评级”</b>部分也将禁用。 启用<b>显示评级</b>部分后，默认情况下将启用<b>星级评分</b>选项。</p></td>
  </tr>
  <tr>
   <td height="19">弃用</td>
   <td>选择以下任一停用选项：<li>弃用后，已注册的学习者可以查看和执行操作，但尚未注册的学习者将失去访问权限。</li><li>弃用后，已注册和未注册的学习者都将失去访问权限。</li><div><b>注意：</b>您可以从概述页面弃用课程、学习路径或认证。</div> </td>
  </tr>
 </tbody>
</table>

<table>
 <tbody>
  <tr>
   <td>
    <p>学习路径</p></td>
   <td>
    <p>如果<b>“启用学习路径的扩展功能”</b>选项已启用，管理员将能够在“学习路径”中加入新的“学习路径”，并将这些“学习路径”与“课程”相结合。该选项不可逆。<br></p></td>
  </tr>
  <tr>
   <td>
    <p>讲师管理<br></p></td>
   <td>
    <p>启用此设置可限制在创建课堂/虚拟教室会话时可以选择的讲师列表。 所有拥有讲师权限的用户只能被指定为任何会话中的讲师。 此限制不适用于迁移工作流程。<br></p>
  </td>
  <tr>
    <td>
      <p>技能导入</p>
    </td>
    <td>
      <p>如果启用，您可以选择外部来源来导入技能。 在初次运行期间，会将现有学习资源的技能导入技能存储库。 对于所有后续导入的学习资源，将只为新导入的项目将技能导入到技能存储库。
      启用该选项后，操作将不可逆。 以后无法禁用或更改为其他源。
      </p>
    </td>
  </tr>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>启用技能导入设置后，帐户布局无法切换到经典视图，即，启用&#x200B;**技能导入**&#x200B;选项后禁用切换到经典帐户。

## 重命名学习对象 {#renaminglearningobjects}

此功能仅提供英语版本。

管理员现在可以重命名 Adobe Learning Manager 中的学习对象。以下是可以重命名的术语。

模块\
课程\
学习计划\
认证\
学习计划\
工作辅助\
目录\
技能\
徽章\
公告\
我的学习\
排行榜\
效果\
先决条件\
前期工作\
核心内容\
测试\
自学\
混合\
教室\
虚拟教室\
活动

## 个人资料设置 {#profilesettings}

1. Click the drop-down arrow at the upper-right corner, adjacent to your photo/account and choose **[!UICONTROL Profile Settings]**.
1. From the pop-up dialog, you can add/change a photo by hovering the mouse and by clicking **[!UICONTROL Edit]** in the profile photo area.
1. Add/modify **[!UICONTROL About]** content by clicking **[!UICONTROL Edit]** adjacent to it.
1. 单击&#x200B;**[!UICONTROL 保存]。**

## 内容文件夹 {#content-folder}

Learning Manager supports private content folders. 管理员可以使用自定义角色配置私有内容文件夹，并向特定的自定义作者提供其访问权限。 请注意，标准作者（也称为“拥有完整权限的作者”）仍有权访问帐户中的所有内容。 Hence Full Authors have access to all folders and all the content.

内容文件夹可由管理员配置。 只有经过配置后，内容文件夹才对作者可见，然后这些作者才可将内容放入一个或多个文件夹中。

To add a content folder, in the Administrator app, click **[!UICONTROL Settings]** > **[!UICONTROL Content Folder]**.

![](assets/manage-content-folders.png)

*更改内容文件夹设置*

### 文件夹

文件夹是内容存储库，也是帐户中具有以下属性的整个内容库的子集：

* 只有管理员才能创建、编辑或删除文件夹。
* 作为仅定义自定义管理员角色的一部分，管理员可以控制对文件夹的访问权限。
* 内容&#x200B;**必须始终至少与一个文件夹关联**。首先，所有内容都将与公共文件夹关联，但之后可作出更改。
* 您可在创建文件夹内容时将其与多个文件夹关联，此操作也可通过复制实现
* 所有文件夹名称在帐户中必须唯一，否则命名文件夹时会出错。

文件夹仅控制内容的可见性，而不会创建内容副本。 因此，因此编辑后的内容会反映在所有关联的文件夹中。

### 公共文件夹

公共文件夹始终存在于帐户中，并且所有内容最初都将属于此文件夹。 稍后，作者可以将内容从此文件夹移动到其他文件夹。 公共文件夹具有以下属性：

* 默认情况下，所有类型的作者都可以访问与此文件夹关联的所有内容。
* 公共文件夹中包含的任何内容都不能归入任何其他文件夹。 反之亦然。

此文件夹不能为可配置角色定义的一部分。 因此，可配置角色定义中不含公共文件夹将不会限制公共文件夹的访问权限。

### 私密文件夹

* 管理员创建的任何文件夹都是私密文件夹。

### 文件夹操作

**添加文件夹**

要添加文件夹，请单击窗口右上角的&#x200B;**[!UICONTROL “添加”]**。

**删除文件夹**

也可以删除文件夹。 选择要删除的文件夹，单击“操作”菜单，然后单击&#x200B;**[!UICONTROL 删除文件夹]**。

>[!NOTE]
>
>当文件夹的所有关联内容也与其他文件夹关联时，可以删除这些文件夹。 如果有内容仅与要删除的文件夹关联，请首先将内容移动到另一个文件夹，然后删除该文件夹。

## 教室位置

管理员可使用此设置创建和配置教室位置库。 作者可选择预配置位置以设置其教室事件。 从库中选择一个位置以自动填充位置信息、URL和名额限制。

作为管理员，您可以：

### 导入位置CSV

通过导入位置 CSV 文件，在您的帐户中添加位置。 CSV 文件必须包含“城市”列。

### 添加位置

添加以下内容：

1. 位置名称：输入教室名称。
2. 位置信息：输入有关位置的信息。
3. 地点区域：输入的值将显示为学习者的“培训地点”过滤器。
4. 位置URL：输入位置的URL。
5. 名额限制：输入教室的座位数量。

![教室位置](assets/location-alm.gif)

*添加教室位置*

您还可以通过 CSV 添加位置。 CSV 必须包含该字段：

* name
* info
* url
* seatlimit
* 地区

<!--![Add classroom locations](assets/add-classroom-csv.png)-->

### 设置 {#admin-classroom-settings}

选择“**编辑**”以更改以下内容：

* **Allow authors to create locations**: Once enabled, all the locations created by authors will be listed under &#39;All Locations&#39; tab. Learners will also see these locations under Catalog and calendar filters.
* **Allow authors to modify and delete locations**:
Once enabled, authors will be able to modify and delete all Classroom locations. The modifications by authors will be reflected across the platform, including reports.

## 常见问题解答 {#frequentlyaskedquestions}

+++如何为内容库创建不同的文件夹？

单击&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 内容文件夹]**。 To add a folder, click **[!UICONTROL Add]** on the upper-right corner, and in the dialog, enter the name and description of the folder.

内容文件夹可由管理员配置。 只有经过配置后，内容文件夹才对作者可见，然后这些作者才可将内容放入一个或多个文件夹中。

有关详细信息，请参阅[“内容文件夹”](settings.md#content-folder)部分。
+++

+++How to add financial year for the account?

在“**[!UICONTROL 设置]**”>“**[!UICONTROL 基本信息]**”中，单击“**[!UICONTROL 更改]**”。 从&#x200B;**[!UICONTROL 财务年度开始日期]**&#x200B;下拉列表中，选择月份。
+++
