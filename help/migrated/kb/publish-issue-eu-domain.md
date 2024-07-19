---
jcr-language: en_us
title: 无法发布到 Adobe Learning Manager 欧盟域
description: 无法从Adobe Captivate发布到Adobe Learning Manager中的Adobe Learning Manager欧盟域。
contentowner: nluke
exl-id: fb8ae1af-9902-4901-8263-fb3ebff98fbc
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 83%

---

# 无法发布到 Adobe Learning Manager 欧盟域 {#unable-to-publish-to-learning-manager-eu-domain}

## 问题

无法从 Adobe Captivate 发布到 Adobe Learning Manager 欧盟域。

## 错误

未找到帐户

## 描述

作者尝试将 Adobe Captivate 中的课程发布到 Adobe Learning Manager 的情况时有发生。该操作无法执行，出现错误消息“未找到帐户”。

## 原因

出现此问题的原因在于 Adobe Captivate 默认配置为将内容发布到 Adobe Learning Manager 的美国域。

## 解决方案：

注意事项：

* 如果已打开 Adobe Captivate 应用程序，请将其关闭。
* 您需要拥有计算机的管理员访问权限才能执行以下步骤。 如果您没有管理员访问权限，请联系您的 IT 团队寻求帮助。

执行以下操作：

1. 转至 Adobe Captivate 安装路径。

   例如，`kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64` (2019是Captivate版本。 如果您使用的是其他版本的 Adobe Captivate，则安装路径也有所不同）。

1. 将配置文件 **AdobeCaptivate.ini** 复制到您的桌面。

   ![](assets/cp-captivate.ini.png)
   *查看配置文件*

1. 在桌面记事本中打开已复制的文件。
1. 将LearningManagerBaseUrl = `https://learningmanager.adobe.com/inappstarter`的值更改为LearningManagerBaseUrl = `https://learningmanagereu.adobe.com/inappstarter`

   ![](assets/cp-primebaseurl.png)
   *查看PrimeBaseURL*

1. 保存对记事本所做的更改。
1. 复制您已编辑保存的文件，并将其粘贴回文件路径。 替换`kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64`中的原始文件
1. 完成后，启动 Adobe Captivate 并尝试将其发布至 Adobe Learning Manager。
