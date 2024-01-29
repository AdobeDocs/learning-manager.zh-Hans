---
jcr-language: en_us
title: 无法在AdobeLearning Manager中查看文件提交
description: 讲师无法查看学员在提交活动模块中上传的文件。
contentowner: nluke
source-git-commit: 8b29ac996962e7ce8fbda51f3421c9a5f248fcf6
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---



# 无法在AdobeLearning Manager中查看文件提交

## 问题

讲师无法查看学员已上传的文件提交。

## 描述

讲师无法查看学习者上传到 **提交活动模块**.

例如，学员注册参加了一个实例，该实例名为 **测试实例** ，如下所示：

![](assets/test-instance.png)

*查看实例*

然后，学习者打开课程，并在“活动”模块中上传文件。

讲师尝试批准提交内容时无法成功操作。

![](assets/activity.png)

*在“活动”模块中上传文件*

## 原因

如果学员注册参加的课程实例中没有讲师，则会出现此问题。

## 分辨率

要检查是否已在课程实例中添加讲师，请执行以下步骤：

1. 导航至课程设置。
1. 在 **管理** 部分，单击 **[!UICONTROL 实例].**
1. 在学员注册参加的实例中，单击 **[!UICONTROL 会话]**.

   ![](assets/check-instructor.png)

   *在实例中选择会话*

   没有为此会话指定讲师。

1. 点击 **[!UICONTROL 编辑]**. 添加可以批准文件提交的讲师。

   ![](assets/assign-instructor.png)

   *添加讲师*
1. 保存更改。

