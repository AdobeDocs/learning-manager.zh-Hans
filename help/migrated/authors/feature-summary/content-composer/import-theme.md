---
description: 了解如何将自定义主题JSON文件导入Content Composer，以及如何将其保存为“课程主题”面板中可用的新自定义主题。
jcr-language: en_us
title: 导入主题
source-git-commit: f8687710f5b73e8b7cf8d56057cac25483f38cdc
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---


# 导入主题

导入自定义JSON文件，以在Content Composer中将更改应用为新主题。

1. 从工具栏中选择&#x200B;**主题**。

2. 从&#x200B;**课程主题**&#x200B;选项中选择&#x200B;**导入**。
   ![](../assets/48_course_themes_import_button_updated.png)

3. 从计算机中选择自定义的JSON文件。

4. 选择“**另存为新内容**”以创建新的自定义主题。

## 主题JSON结构概述

主题JSON文件有五个主要区域：

| 部分 | 控件 |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 元数据（id、名称、版本、描述、作者、源、isDefault） | 主题标识和显示信息 |
| foundation.palette | 通过var(—tokenName)在整个主题中引用的7种核心颜色令牌（前景色、背景色、重点色、背景细微、次要色、textPrimary、textInverse） |
| foundation.fonts | 标题和正文字体栈栈 |
| foundation.spacing和foundation.radius | 水平/垂直间距缩放和圆角半径令牌 |
| 元素 | 每个文本角色(leashTitle、topicTitle、blockHeading、subheading、question、caption、paragraph、buttonLabel)和每个组件(paragraphBlock、imageBlock、videoBlock、imageGrid、accordion、carousel、flipCard、tab、timeline、assessment)的排版和结构样式 |

由于大多数值使用var(—tokenName)引用调色板标记，因此更新单个标记（如重音符）会自动在引用该标记的每个元素中级联更改。 您不需要搜索单个颜色值。

