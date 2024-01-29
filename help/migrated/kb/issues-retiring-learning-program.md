---
jcr-language: en_us
title: 有关停用学习计划的问题
description: 在AdobeLearning Manager中停用学习计划的问题
contentowner: nluke
source-git-commit: 66dfaaaf723382eada39e2be29dfd49b795107a0
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 0%

---



# 有关停用学习计划的问题

## 问题

学习计划将自动停用。

## 原因

在某些情况下，学习计划已停用，而管理员/作者未明确停用学习计划。

出现此问题的原因是，学习计划是一系列课程的合集。 如果高阶培训中的任何课程包含已停用的实例或课程实例停用，则高阶培训便会停用。

## 分辨率

要检查包含已停用实例的课程，请执行以下步骤：

1. 以管理员身份登录并启动相关的学习计划。

1. 点击 **[!UICONTROL 实例]** > **C乌尔塞**. 该页面列出了此学习计划中包含的所有课程。 您将能够看到包含已停用实例的课程。

   ![](assets/retired-instance.png)

   *查看所有课程的列表*

1. 在您确定已停用的课程实例后，单击 **[!UICONTROL 课程]** > **[!UICONTROL 打开课程]**.

1. 点击 **[!UICONTROL 实例]**. 在已停用实例上，单击 **[!UICONTROL 编辑]** 然后将完成日期编辑为您希望该实例报废的将来日期。

   ![](assets/completion-date.png)

   *编辑课程的完成日期*

1. 完成后，单击下拉列表，如下图所示。 然后单击 **[!UICONTROL 重新打开实例]**.

   ![](assets/re-open-instance.png)

   *报告课程实例*

1. 访问相关的学习计划。 点击 **[!UICONTROL 实例]** 并执行上一步以重新打开学习计划实例。
