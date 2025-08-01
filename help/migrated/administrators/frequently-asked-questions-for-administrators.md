---
jcr-language: en_us
title: 管理员常见问题解答
description: Adobe Learning Manager管理员常见问题解答
contentowner: manochan
exl-id: 8b113a4e-73f4-4cd5-982a-cefdf5388e91
source-git-commit: 0dade561e53e46f879e22b53835b42d20b089b31
workflow-type: tm+mt
source-wordcount: '2517'
ht-degree: 52%

---

# 管理员常见问题解答

<table>
 <tbody>
  <tr>
   <td><img src="assets/administrator2.png"></td>
   <td>
    <p>阅读以了解 Adobe Learning Manager 中与管理员角色相关联的常见问题解答。 </p></td>
  </tr>
 </tbody>
</table>

+++我可以批量添加用户吗？ 该如何操作？

是的，您可以使用 CSV 上传功能批量添加用户。 有关详细信息，请参阅此[文章](/help/migrated/administrators/feature-summary/add-users-user-groups.md#bulk-upload-internal-users)。

+++

+++在为学习者创建登录时，如果输入的电子邮件ID有误，该如何更正？

为修复用户登录，您必须在 Adobe Learning Manager 中导入 CSV。本页底部附有示例 CSV 文件，供您参考。 电子邮件是个人唯一标识符，您无法对其进行编辑。 请执行以下步骤：

1. 在CSV中添加具有正确电子邮件ID的同一用户，将其电子邮件ID添加到示例CSV中的“员工经理的电子邮件”列，确保其仍然是其他用户的经理。
1. 向 CSV 中添加您帐户中的其他用户（包括您自己）
1. 利用 Adobe Learning Manager 管理员应用 ->“用户”->“添加”->“导入 CSV”导入此文件
1. 根据对话框中的提示，将所有字段映射到相应的 CSV 列。
1. 单击“保存”。

应在“学习者”页面添加用户。

[Learning Manager示例CSV.csv](https://helpx.adobe.com/content/dam/help/en/captivate_prime/learning-manager-sample-csv.zip)

+++

+++如何设置提醒？

您可以在 Adobe Learning Manager 1.0 版本中创建通知。有关详细信息，请参阅[通知问题](/help/migrated/administrators/feature-summary/user-notifications.md)。

+++

+++如何添加课程证书？

Adobe Learning Manager 不提供课程证书。但是，管理员可以单击左侧面板中的“徽章”选项卡，为每门课程创建徽章。 当管理员将学习者注册到课程时，还可以将徽章与课程相关联。

+++

+++如何导入证书的签名？

Adobe Learning Manager 尚不具有导入认证签名或徽章的功能。

+++

+++我可以设置课程日历吗？ 该如何操作？

Adobe Learning Manager 1.0版本中没有任何设置课程日历的规定。

+++

+++如何直接注册轮候学习者？

当任意教室课程名额有限时，学习者会根据其注册顺序进行轮候。管理员可以为任意名额有限的教室课程选择轮候学习者并分配名额。 管理员分配名额后，学习者就能立即注册课程。

1. 以管理员身份登录后，单击左侧窗格中的“课程”。
1. 从可用课程列表中，单击您选择的任意教室课程的名称。 此时会出现一个新页面，其中包含课程的详细信息。
1. 单击课程详细信息页面左侧窗格中的“轮候表”。 此时页面上会显示轮候学习者名单。
1. 选择学习者并单击“分配名额”，直接将学习者注册到名额有限的课程。

有关更多信息，请参阅[轮候和出席](/help/migrated/administrators/feature-summary/waitlist-attendance-management.md)功能。

+++

+++如何记录教室模块学习者的出席情况？

是的，您可以按照以下步骤记录出席情况：

1. 以管理员身份登录后，单击左侧窗格中的“课程”。
1. 从可用课程列表中，单击您选择的任意教室模块/课程的名称。 此时会出现一个新页面，其中包含课程的详细信息。
1. 选择学习者，然后单击“保存”以记录课程的完成情况。

如果课程包含多个模块，而学习者仅完成了其中一个模块。您可以选择单个模块并单击“保存”，以此标记学习者的课程完成情况。 如果学习者完成了课程中的所有模块，您可以单击“全选”选项，然后单击“保存”。

有关更多信息，请参阅[轮候和出席](/help/migrated/administrators/feature-summary/waitlist-attendance-management.md)功能。

+++

+++如何添加L3反馈选项？

您可以在将学习者注册到课程时添加 L3 反馈。 请按照以下步骤添加 L3 反馈问题：

1. 以管理员身份登录后，单击左侧窗格中的“课程”。此时右侧页面会显示所有课程的列表。
1. 单击要为其添加L3反馈的课程磁贴
1. 单击左侧窗格中的“实例默认值”。
1. 单击“L3行为变化反馈”旁的切换按钮上的圆圈将其选中。
1. 在 L3 问题下的文本区域中添加 L3 反馈问题。

+++

+++如何为经理指派的课程搜寻经理指派？

作为管理员，您可以按照以下步骤为课程搜寻经理指派：

1. 单击左侧窗格中的“课程”
1. 将鼠标悬停在经理指派的任意课程上，然后单击&#x200B;**[!UICONTROL 搜寻经理指派]**。

1. 在实例列表中，单击&#x200B;**[!UICONTROL 由经理指派]**&#x200B;链接，然后单击&#x200B;**[!UICONTROL 添加经理]**&#x200B;链接。

1. 添加经理姓名和规定名额数，然后单击刻度线以保存更改。

在创建课程时，作者选择的课程类型为“由经理指派”。

+++

+++如何将学习者注册到特定课程？

请按照以下步骤将学习者注册到课程：

1. 以管理员身份登录后，单击左侧窗格中的“课程”。此时右侧页面会显示所有课程的列表。
1. 选择要为其添加学习者的课程，并将鼠标悬停在该课程上。
1. 单击“注册学习者”并添加学习者姓名。 **注意：**&#x200B;您可以一次添加一名或多名学习者。

+++

+++如何将学习者分配至特定技能？

请按照以下步骤将学习者分配至能力：

1. 以管理员身份登录后，单击左侧窗格中的&#x200B;**[!UICONTROL 技能]**。
1. 单击相应能力的复选框，选择一项或多项技能，然后单击页面右上角的&#x200B;**[!UICONTROL 操作]**&#x200B;下拉列表。
1. 单击“分配给用户”。
1. 开始输入用户姓名，从下拉列表中选择，然后单击&#x200B;**[!UICONTROL 保存]**。

   >[!NOTE]
   >
   >您可以单击“添加更多用户”并重复第4步，为技能注册多名学习者。

+++

+++如何创建学习计划会话？

要创建学习计划，请执行以下步骤：

1. 单击左侧窗格中的“学习计划” 。 此时会显示“学习计划”页面，包括现有的学习计划列表。
1. 单击页面右上角的“添加”。\
   输入计划名称、概述、描述，然后单击“保存”。
1. 单击左侧窗格中的“课程”。
1. 单击每个课程磁贴上的“+”即可添加一门或多门课程。

   >[!NOTE]
   >
   >您需要发布学习计划，才能注册学习者或实例。

1. 单击左侧窗格中的“实例”，然后单击页面右上角的&#x200B;**[!UICONTROL “添加新实例”]**&#x200B;以添加实例详细信息。

有关学习计划的详细信息，请参阅[学习计划功能。](/help/migrated/administrators/feature-summary/learning-programs.md)

+++

+++如何修改或自定义所有角色的报告？

单击各个报告右上角的下拉箭头以编辑/修改报告。 完成更改后单击“保存”并查看修改后的报告。

+++

+++如何修改课程、学习计划和公司资料？

即使课程或学习计划已经发布，您依然可以对其进行编辑。 有关更多信息，请参阅[课程](/help/migrated/administrators/feature-summary/courses.md)和[学习计划](/help/migrated/administrators/feature-summary/learning-programs.md)帮助内容。

要修改公司资料，请单击左侧窗格中的&#x200B;**[!UICONTROL “设置”]**，然后单击页面右上角的&#x200B;**[!UICONTROL “更改”]**。

+++

+++如何搜索课程？

以管理员身份登录后，单击左侧窗格中的“课程”。此时会显示所有可用课程的列表。

您可以通过两种方式来搜索课程：

1. 单击右上角显示的搜索图标。此时会显示搜索字段。输入课程名称或任何与课程相关的关键词来查找您的课程。
1. 使用过滤器过滤课程列表。

您可以单击各个选项按状态（例如“全部”、“已发布”和“已弃用”）过滤课程。 您还可以单击“能力”并进行选择，然后根据能力进行搜索。

根据您的选择，可以查看过滤后的课程列表并选择所需课程。

+++

+++我可以更改应用程序的主题吗？ 该如何操作？

是的，您可以根据公司要求更改Learning Manager应用程序的主题和品牌推广。 系统中提供一组五个代表性图像，用于在将颜色主题更改应用到应用程序之前对其进行预览。 单击图像左右两侧的“&lt;“和”>”符号可以浏览并预览这些图像。

单击左侧窗格中的&#x200B;**[!UICONTROL 品牌推广]**&#x200B;以更新所在组织的名称、更改相关子域、日志样式和主题。 单击每个主题旁边的&#x200B;**[!UICONTROL “编辑”]**&#x200B;以修改内容。

有关更多信息，请参阅[颜色主题和品牌推广帮助](/help/migrated/administrators/feature-summary/themes.md)。

+++

+++如何设置课程徽章？

1. 以管理员身份登录后，单击左侧窗格中的“徽章”。
1. 单击显示页面右上角的“添加”。
1. 添加徽章名称。
1. 要上传徽章，请单击“上传徽章”，然后单击“保存”。

+++

+++如何设置课程的游戏点数？

您可以按照以下步骤为学习者设置游戏点数：

1. 以管理员身份登录后，单击“游戏”。 此时会出现一个页面，其中列有铜级、银级、金级和白金级，以及达到相应级别所需的点数。 系统会提供任务列表和完成任务获得的相应点数。
1. 单击各项任务旁边的“编辑”图标以设置/修改点数。

有关更多信息，请参阅[游戏功能](/help/migrated/administrators/feature-summary/gamification.md)。

+++

+++如何为经理和学习者创建报告？

您可以按照以下步骤创建报告：

1. 单击左侧窗格中的“报告”。此时会显示报告摘要页面。
1. 在“报告”页面上，单击右上角的&#x200B;**[!UICONTROL “添加”]**。

   此时会显示&#x200B;**[!UICONTROL 添加报告]**&#x200B;对话框。

1. 填写所有必填字段，然后单击“保存”。

只有管理员和经理才能创建或查看报告。 有关详细信息，请参阅[报告功能](/help/migrated/administrators/feature-summary/reports.md)。

+++

+++如何转变为学习者、经理和作者角色？

您无需退出帐户，即可将帐户登录切换为如学习者、经理和作者等其他角色。

1. 单击页面右上角个人资料图片旁边的下拉箭头。\
   此时会弹出菜单。
1. 选择各个可用角色以访问相应的角色帐户。

+++

+++如何为用户添加通知？

经理、作者和学习者可以查看与课程活动相关的通知。 管理员可以按照以下步骤为所有用户启用/禁用通知：

1. 单击左侧窗格中的“电子邮件模板”，然后依次选择“常规”、“用户注册”、“完成”和“反馈”选项卡。
1. 从下列事件中，单击每个事件旁的“否”/“是”切换按钮，然后选择“是”以启用通知。 单击“否”以禁用针对特定事件发送通知。

+++

+++如何允许课程外部注册？

Adobe Learning Manager 提供的工具可将公司的外部部门成员或外部员工注册到应用程序。

1. 单击左侧窗格中的&#x200B;**[!UICONTROL 用户]**。
1. 单击左侧窗格中的“**[!UICONTROL 外部]**”。
1. 单击页面右上角的&#x200B;**[!UICONTROL “添加”]**。

   此时会显示“添加用户”对话框。

1. 添加个人资料姓名、经理电子邮件、已规定的名额、到期日信息。 您还可以在外部个人资料中添加图像。
1. 单击&#x200B;**[!UICONTROL “保存”]**。

管理员可以复制注册 URL 并将其发送给外部注册组。 外部用户可以注册、登录 Adobe Learning Manager 应用程序并访问其课程。

+++

+++如何为L1反馈添加调查表？

创建反馈调查表，供学习者在完成课程后使用。 默认情况下，系统将提供三个示例问题。 请按照以下步骤创建调查表。

1. 单击左侧窗格中的“反馈”。 此时会出现“反馈调查表”窗口。
1. 单击&#x200B;**[!UICONTROL 编辑]**&#x200B;以添加/修改调查表。

您可以添加一组调查表；如果不再需要这些调查表，可选择不显示。 单击复选框以启用/禁用特定问题。

+++

+++如何设置技能和级别？

1. 单击“管理员”窗口左侧窗格中的“能力”。
1. 单击“添加”以添加新能力。
1. 添加各级别相应的能力名称、描述和积分。

   默认情况下，每项能力都有一个积分为 0 的级别。

1. 单击“[!UICONTROL **添加级别**]”为每个能力添加新级别，然后单击“保存”。 您最多只能添加 5 个级别。

保存能力后，您将无法从能力中删除级别。 管理员还可以将学习者分配至特定的能力和级别。

+++

+++如何为公司课程设置计费系统？

1. 单击左侧窗格中的&#x200B;[!UICONTROL **“帐单”**]。

   此时页面上会显示帐单信息。

1. 单击“[!UICONTROL **订阅**]”选项卡。
1. 在“学习者礼包”字段中输入要订购的礼包数，然后单击页面右上角的“下单”。

   根据公司中学习者人数选择礼包数，然后下单。 如需了解如何推进采购订单流程，请向[learningmanagersales@adobe.com](mailto:learningmanagersales@adobe.com)发送电子邮件。

1. 输入联系信息、选择信用卡类型并提供信用卡的详细信息，然后单击“完成订单”。

有关详细信息，请参阅[帐单管理](/help/migrated/administrators/feature-summary/billing-management.md)功能。

+++

+++我可以自定义证书设计吗？ 该如何操作？

在Adobe Learning Manager中，您可以通过颁发徽章来识别学习者。 有关更多信息，请参阅徽章功能。  另请参阅认证功能。

+++

+++如何设置我的公司资料？

1. 以管理员身份登录后，单击左侧窗格中的&#x200B;**[!UICONTROL 公司信息]**。
1. 单击页面中的各个选项，添加公司资料、子域和徽标。

+++

+++如何添加课程？

要添加课程，您需要将角色切换为“作者”。 您只能根据可用课程的状态（如&#x200B;**[!UICONTROL 完成]**、**[!UICONTROL 已发布]**&#x200B;和&#x200B;**[!UICONTROL 已弃用]**）查看可用课程列表。

要查看课程，请单击左侧窗格中的&#x200B;**[!UICONTROL 课程]**。 有关更多信息，请参阅[创建课程](/help/migrated/administrators/feature-summary/courses.md)

+++

+++如何向应用程序添加不同的角色？

要添加新用户，请执行以下步骤：

1. 以管理员身份登录后，单击左侧窗格中的“用户”。要添加用户，您还可以单击窗口左侧窗格中的“开始使用”，然后单击“添加用户”。
1. 要添加新用户，请单击页面右上角的“添加”。

默认情况下，系统为所有新用户分配学习者角色。 您可以单击页面右上角的&#x200B;**[!UICONTROL 操作]**，然后选择&#x200B;**[!UICONTROL 分配角色]** > **[!UICONTROL 设为作者]**&#x200B;或&#x200B;**[!UICONTROL 设为管理员]**，为学习者分配管理员或作者角色。

有关添加学习者、作者和管理员的详细信息，请参阅[添加新用户](/help/migrated/administrators/feature-summary/add-users-user-groups.md)功能。

+++

+++如何更改学习者的背景图像？

请联系Learning Manager支持团队。

+++

+++在哪里可以找到我的Learning Manager帐户ID？

您可以从打开 Adobe Learning Manager 的浏览器获取帐户 ID。

*/app/admin？i_qp_user_id=12761637&amp;**accountId=6849***

+++

+++是否有我可以提取的报告，或者有人可以为我提取的报告，可以显示学习管理系统中所有课程的列表？

是的，您可以提取包含LMS中所有课程、学习计划和认证的&#x200B;**[!UICONTROL 培训报告]**。 要下载报告，请按照以下步骤操作：

1. 以管理员身份登录。
2. 单击&#x200B;**[!UICONTROL 报告]** > **[!UICONTROL 自定义报告]** > **[!UICONTROL Excel报告]** > **[!UICONTROL 培训报告]**。
3. 从下拉列表中选择&#x200B;**[!UICONTROL 所有培训]**。
4. 单击&#x200B;**[!UICONTROL 下载]**。

+++

+++我可以在哪里下载该应用程序的桌面版本？

请按照以下步骤下载桌面版本：

1. 以管理员身份登录。
2. 单击&#x200B;**[!UICONTROL 社交学习]** > **[!UICONTROL 设置]**。
3. 在&#x200B;**[!UICONTROL 下载配置]**&#x200B;下，根据您的操作系统单击超链接。

+++
