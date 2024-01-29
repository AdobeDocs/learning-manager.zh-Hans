---
jcr-language: en_us
title: 即使学习者已在AdobeLearning Manager中完成课程，模块也会被标记为未完成
description: 即使学习者在AdobeLearning Manager中完成课程，系统也会将模块标记为未完成。
contentowner: nluke
source-git-commit: ec79aa3dd6225cc424721afb50702963c1b125eb
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---



# 即使学习者已在AdobeLearning Manager中完成课程，模块也会被标记为未完成

## 问题

即使学习者在AdobeLearning Manager中完成课程，系统也会将模块标记为未完成。

## 原因

SCORM 2004定义成功和完成标准，并分别发送两者的状态说明。

例如，假设有一个内容集，其中 **完成标准** 100%幻灯片浏览和 **成功标准** 设置为“通过测验”。

学习者完成课程，但未能通过测试。 在这种情况下，尽管课程进度为100%，但因学习者未达到 **成功标准**.

## 解决方案

该问题与报告有关 **偏好设置** 为项目设置。 作者必须对为课程设置的完成和成功标准进行验证。

如有任何必要的更改，作者可以使用Adobe Captivate Classic等内容创作工具进行更改。 然后，作者可以更新相应模块。

![](assets/scorm.png)

*查看CaptivateClassic报告首选项*
