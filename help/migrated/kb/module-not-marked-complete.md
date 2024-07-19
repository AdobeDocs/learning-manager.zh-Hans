---
jcr-language: en_us
title: 即使学习者已在 Adobe Learning Manager 中完成课程，模块也会被标记为未完成
description: 即使学习者在 Adobe Learning Manager 中已完成课程，系统仍会将模块标记为未完成。
contentowner: nluke
exl-id: c0f14f2e-733a-4b4f-a2c2-4c0b33a15fa1
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 53%

---

# 即使学习者已在 Adobe Learning Manager 中完成课程，模块也会被标记为未完成

## 问题

即使学习者在 Adobe Learning Manager 中已完成课程，系统仍会将模块标记为未完成。

## 原因

SCORM 2004定义成功和完成标准，并分别发送两者的状态说明。

例如，假设内容设置的&#x200B;**完成标准**&#x200B;为100%幻灯片查看次数，并且&#x200B;**成功标准**&#x200B;设置为“通过测试”。

如果学习者完成课程，但是其测试不及格， 在这种情况下，尽管课程进度为100%，但因学习者未达到&#x200B;**成功标准**，因此系统将此模块标记为未完成。

## 解决方案

此问题与项目设置的报告&#x200B;**首选项**&#x200B;有关。 作者必须对为课程设置的完成和成功标准进行验证。

如有任何必要的更改，作者可以使用Adobe Captivate Classic等内容创作工具进行更改。 更改之后，作者可以更新相应模块。

![](assets/scorm.png)

*查看CaptivateClassic报告首选项*
