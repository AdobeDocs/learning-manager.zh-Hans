---
jcr-language: en_us
title: 无法查看日历
description: 当管理员尝试编辑外部注册配置文件的到期日期并单击日历以编辑到期日期时，日历不会显示。
contentowner: saghosh
source-git-commit: 8b29ac996962e7ce8fbda51f3421c9a5f248fcf6
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---



# 无法查看日历

## 问题

在编辑外部配置文件的到期日期时，您无法查看日历。

## 描述

当管理员尝试编辑外部注册配置文件的到期日期并单击日历以编辑到期日期时，日历不会显示。

## 原因

出现此问题的原因如下：

* 浏览器的缩放级别超过100%。
* 显示设置中的缩放和布局超过100%。

## 分辨率

### 浏览器

1. 启动浏览器。
1. 登录AdobeLearning Manager。
1. 在地址栏中，单击缩放图标。
1. 点击 **[!UICONTROL 重置]**.
1. 更改注册配置文件的到期日期。

### 显示设置

1. 点击 **[!UICONTROL 开始]** > **[!UICONTROL 设置]** > **[!UICONTROL 系统]**.
1. 点击 **[!UICONTROL 显示器]**.
1. 在 **[!UICONTROL 缩放和布局]** 部分，使用下拉列表。 将设置更改为100%。

   ![](assets/scale-layout.png)

   *更改显示设置*

1. 重新启动计算机。
