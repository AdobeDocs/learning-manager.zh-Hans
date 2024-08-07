---
jcr-language: en_us
title: 添加教室位置
description: 管理员现可设置教室位置库。 对于每个教室位置，管理员可以设置包括位置名称、名额限制以及位置 URL 等附加信息在内的元数据。 然后，作者和管理员可以使用这些预配置的教室位置来设置讲师主导的培训活动（教室模块）。
contentowner: saghosh
exl-id: 51a1e38f-d4e2-4c19-bbf7-6696505c0dfd
source-git-commit: 8cb8a95812c97b0b59a2ae5188500cfafe09bd27
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 54%

---

# 教室

## 概述

管理员现可设置教室位置库。 对于每个教室位置，管理员可以设置包括位置名称、名额限制以及位置 URL 等附加信息在内的元数据。 然后，作者和管理员可以使用这些预配置的教室位置来设置讲师主导的培训活动（教室模块）。

可以通过以下两种方式添加教室位置。

## 使用 UI 添加教室

您可以使用UI添加教室位置：

1. 在管理员应用程序（面向管理员角色的UI）中，单击&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 教室位置]**。

1. 单击&#x200B;**[!UICONTROL 添加]** > **[!UICONTROL 新位置]**。

1. 在&#x200B;**[!UICONTROL “教室位置”]**&#x200B;对话框中，输入以下详细信息：

   * 键入&#x200B;**[!UICONTROL 位置名称]**。 请使用唯一名称； 否则，Adobe Learning Manager 会显示错误消息。
   * 在&#x200B;**[!UICONTROL “位置信息”]**&#x200B;字段中输入位置描述。 该字段为可选项。
   * 输入&#x200B;**[!UICONTROL “位置 URL”]**。 学习者可以在教室详细信息中看到此信息。 如有需要，此 URL 也可以是地图位置 URL。 这是一个可选字段。
   * 键入并选择&#x200B;**[!UICONTROL 位置区域]**。 此字段为可选字段。
   * 在&#x200B;**[!UICONTROL “名额限制”]**&#x200B;字段中输入可用名额数。 此字段表示教室的座席容量。 实际创建讲师主导的培训活动时，可更改此值。

   ![](assets/add-classroom-location.png)

   *添加教室位置*

添加位置后，**[!UICONTROL 设置]** > **[!UICONTROL 教室位置]**&#x200B;页面会列出会议室：

![](assets/list-meeting-rooms.png)

*查看所有会议室*

该列表包含以下字段：

**[!UICONTROL 位置名称]** — 教室位置的名称。

**[!UICONTROL 未来会话]** — 相应位置即将举行的活动数。 单击编号，即可在对话框中查看详细信息。

![](assets/sessions-list.png)

*查看将来的会话*

对话框会显示每个会话的详细信息，包括会话名称、含有该会话的培训名称和会话日程安排。 显示的时间与学习者的系统时区一致。

当教室未用于任何会话或教室与过去会话相关联时，**[!UICONTROL 未来会话]**&#x200B;字段会显示&#x200B;**零**。

**[!UICONTROL 名额限制]** — 显示教室的名额容量。

**位置URL** — 创建教室位置时提供的URL。

**位置信息** — 创建教室时提供的教室信息。

### 编辑教室位置

要编辑教室位置，请执行以下步骤：

1. 在管理员应用程序（面向管理员角色的UI）中，选择&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 教室位置]**。

1. 将鼠标悬停在要编辑的所需教室位置上。

1. 选择&#x200B;**[!UICONTROL 编辑教室位置]**&#x200B;图标。

1. 修改教室位置并选择&#x200B;**[!UICONTROL 保存]**。

## 使用CSV添加教室

您还可以导入包含教室信息的 CSV，以此添加一个或多个教室位置。

在&#x200B;**[!UICONTROL 管理员应用]** > **[!UICONTROL 设置]** > **[!UICONTROL 教室位置]** > **[!UICONTROL 添加]**&#x200B;中，单击&#x200B;**[!UICONTROL 批量导入位置]**&#x200B;按钮。 浏览至包含 CSV 文件的位置，然后选择该文件。

CSV 文件使用以下字段存储一个或多个教室位置的相关详细信息：

* name
* info
* url
* 地区
* seatLimit

您可以自定义标题。

CSV 文件必须按照此处指定的顺序包含所有列。

系统导入 CSV 文件后，会将这些位置添加到库中。

## 搜索教室

要搜索课堂，请选择虚拟教室课程，然后转到&#x200B;**[!UICONTROL 实例]** > **[!UICONTROL 会话]**。 作者或管理员可以输入位置名称，以查看显示的相关结果。 然后，他们可以从显示的结果中选择一个位置。 如果在预先键入结果中未显示任何位置，则用户仍然可以添加新的教室位置名称。 请注意，使用会话创建工作流程创建的位置名称不会添加到由管理员创建的位置库中。

添加教室后，学习平台还会显示教室是否已在所述时间段被预订， 甚至还会建议备选时间段。 因此，如果作者决定使用同一教室位置，可以相应调整会议时间。

![](assets/classroom-search.png)

*搜索教室*

## 管理员

作为管理员，您可以管理讲师和课程实例。

### 设置讲师：

在管理员应用程序的&#x200B;**[!UICONTROL 设置]** > **[!UICONTROL 常规]**&#x200B;下，管理员可以找到&#x200B;**[!UICONTROL 讲师管理]**&#x200B;选项。 此功能可确保只有预先批准、指定为讲师的用户才能添加到会话中。

要指定讲师，请执行以下步骤：

1. 转到&#x200B;**[!UICONTROL 入门]**&#x200B;页面，然后在左侧窗格中选择&#x200B;**[!UICONTROL 用户]**。

1. 选择所需的用户。

1. 通过选择&#x200B;**[!UICONTROL 操作]** > **[!UICONTROL 分配角色]**，为该用户分配讲师角色。

### 正在取消会话：

在&#x200B;**[!UICONTROL 课程实例]**&#x200B;页面上，管理员可以取消一个或多个会话。 取消会话后，系统会删除所有会话详细信息，但保留名额限制。

此外，管理员还可以：

* **[!UICONTROL 查看注册情况]**：获取每个会话的注册和轮候学习者信息。
* **[!UICONTROL 取消注册学习者]**：从包含已取消会话的课程中移除学习者，而不更改其注册状态。
* **[!UICONTROL 出席管理]**：标记会话的出席情况，即使会话被取消。
* **[!UICONTROL 课程完成]**：即使会话已取消，管理员也可以将课程标记为完成。
* **[!UICONTROL 重新计划]**：为以后的日期安排已取消的会话，并在重新计划期间添加讲师。

请注意，取消后，学习者仍会注册培训实例。 其注册状态（如已确认、轮候和等待经理批准）保持不变。 此功能非常有用，因为管理员日后可以设置和重新安排已取消的会话。

## 作者

如果管理员选择&#x200B;**[!UICONTROL 讲师管理]**&#x200B;选项，则作者只能搜索具有讲师角色的用户并将其添加到教室会话、虚拟教室会话、检查清单以及文件提交模块中。

此外，作者还可以执行以下操作：

* 添加和删除现有会话的讲师。
* 向已有一名或多名讲师的现有会话中添加讲师。

因此，在管理员启用&#x200B;**[!UICONTROL 讲师管理]**&#x200B;选项后，只能将具有讲师角色的用户添加为讲师。

>[!NOTE]
>
>此功能不适用于使用会话CSV文件迁移会话的情况。 在这种情况下，可以将不具有讲师角色的用户添加为讲师。

在&#x200B;**[!UICONTROL 课程实例]**&#x200B;页面上，作者可以取消一个或多个会话。 取消会话后，系统会删除所有会话详细信息，但保留名额限制。

因此，作者可以使用&#x200B;**[!UICONTROL 取消会话]**&#x200B;链接，取消相同或不同课程实例中的一个或多个教室会话或虚拟教室会话。

## 仅限于预先确定的讲师名单

目前，在创建教室或虚拟教室会话时，用户可以将任何已注册用户添加为讲师。 在此版本中，该功能保持不变。

但是，管理员现有一个附加选项，可以进一步控制将哪些人员指定为学习平台上的讲师， 从而避免在创建会话时意外添加新讲师。

## 取消现有会话

如有需要，作者或管理员可以取消会话并进行重新安排。

用户取消会话时，系统会向所有已注册的学习者和讲师发送会议取消电子邮件， 其中包含更新之后的会话详细信息。

取消会话时，可借助名为&#x200B;**[!UICONTROL “会话取消”]**&#x200B;的模板。

在&#x200B;**[!UICONTROL “课程实例”]**&#x200B;页面中，课程实例下列出的每个会话都包含可取消会话的选项。

![](assets/cancel-session.png)

*取消现有会话*

单击&#x200B;**[!UICONTROL “取消会话”]**&#x200B;链接时，系统会显示警告消息。

在警告消息对话框中，如果单击&#x200B;**[!UICONTROL “继续”]**，系统会取消会话。

取消会话后，系统还会清除以下详细信息：

* 会话开始日期
* 会话结束日期
* 会话开始时间
* 会话结束时间
* 已添加到会话中的讲师
* 虚拟教室 URL
* 已添加到会话中的位置/地点
* 讲师已添加的轮候表限制
