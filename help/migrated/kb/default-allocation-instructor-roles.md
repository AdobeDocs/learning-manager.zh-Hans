---
jcr-language: en_us
title: 在 Adobe Learning Manager 中，系统默认为用户组分配讲师角色
description: 在 Adobe Learning Manager 中，系统默认为用户组分配讲师角色
contentowner: nluke
preview: true
source-git-commit: 66dfaaaf723382eada39e2be29dfd49b795107a0
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 48%

---



# 在 Adobe Learning Manager 中，系统默认为用户组分配讲师角色

## 问题

系统会向已分配到会话的所有用户分配讲师角色。

## 描述

在某些情况下，一个会话可能需要多名讲师，或者管理员/作者会为会话分配用户组。 这将导致用户组中的所有用户都被分配为讲师角色。

## 原因

由于在用户组中批量分配用户时无法细分角色，因此会向所有用户分配讲师角色。

## 解决方案

创建自定义用户组，筛选分配到会话的用户角色。 要删除用户组中已分配的讲师角色，请执行以下操作：

1. 以管理员身份登录。 在左侧面板中，单击&#x200B;**[!UICONTROL 电子邮件模板]**。
1. 为避免因要进行的更改而触发电子邮件，请单击“**[!UICONTROL 禁用全部]**”。

   ![](assets/instructor-disable-all.png)

1. 导航到&#x200B;**用户** > **用户组**。 单击“**[!UICONTROL 添加]**”。

   ![](assets/instructor-usergroups.png)

1. 在“添加用户组”窗口中创建自定义用户组，如下所示：

   * 在&#x200B;**[!UICONTROL 名称]**&#x200B;字段中输入自定义组的名称。
   * 在&#x200B;**[!UICONTROL 包含学习者]**&#x200B;字段中，添加要为其筛选讲师的用户组。
   * 在“**[!UICONTROL 排除学习者]**”字段中，添加要为其保留讲师角色的用户。

   ![](assets/instructor-add-ug.png)

   上述步骤可创建要添加到包含集中的用户列表，同时删除排除集中提及的特定用户（讲师）。

1. 单击&#x200B;**[!UICONTROL 保存]**&#x200B;所做的更改。
1. 通过转到&#x200B;**[!UICONTROL “用户”]**>“**[!UICONTROL ”内部]**，搜索创建的自定义用户组。

   ![](assets/instructor-custom-ug.png)

1. 单击复选框以选择组中的所有用户。

   ![](assets/instructor-bulk-ug.png)

1. 单击“**[!UICONTROL 操作]**”>“**[!UICONTROL 删除角色]**”>“**[!UICONTROL 删除讲师]**”。

确保在完成上述操作之后，重新启用在第2步中禁用的所有电子邮件触发器。
