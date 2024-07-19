---
jcr-language: en_us
title: 有关停用学习计划的问题
description: 在Adobe Learning Manager中停用学习计划的问题
contentowner: nluke
exl-id: 706cafe3-2650-4837-9dee-e381a4a711f9
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 55%

---

# 有关停用学习计划的问题

## 问题

学习计划将自动停用。

## 原因

在某些情况下，学习计划已停用，而管理员/作者未明确停用学习计划。

出现此问题的原因是，学习计划是一系列课程的合集。 如果高阶培训中的任何课程包含已停用的实例或课程实例停用，则高阶培训便会停用。

## 解决方法

如需检查包含已停用实例的课程，请执行以下步骤：

1. 以管理员身份登录并启动相关的学习计划。

1. 单击&#x200B;**[!UICONTROL 实例]** > **C源**。 该页面列出了此学习计划中包含的所有课程。 您将能够看到包含已停用实例的课程。

   ![](assets/retired-instance.png)

   *查看所有课程的列表*

1. 在您确定已停用的课程实例后，单击&#x200B;**[!UICONTROL 课程]** > **[!UICONTROL 打开课程]**。

1. 单击&#x200B;**[!UICONTROL 实例]**。 在报废实例上，单击&#x200B;**[!UICONTROL 编辑]**，然后将完成日期编辑为您希望该实例报废的将来日期。

   ![](assets/completion-date.png)

   *编辑课程的完成日期*

1. 完成后，单击下拉列表，如下图所示。 然后单击“**[!UICONTROL 重开实例]**”。

   ![](assets/re-open-instance.png)

   *重新打开课程实例*

1. 访问相关的学习计划。 单击&#x200B;**[!UICONTROL 实例]**&#x200B;并执行上一步以重新打开学习计划实例。
