---
jcr-language: en_us
title: 无法发布到Learning Manager欧盟域
description: 无法从Adobe Captivate发布到AdobeLearning Manager中的AdobeLearning Manager欧盟域。
contentowner: nluke
source-git-commit: 69ac8f8ce5a0c077f31569571f9d9fbf16ecb943
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---



# 无法发布到Learning Manager欧盟域 {#unable-to-publish-to-learning-manager-eu-domain}

## 问题

无法从Adobe Captivate发布到AdobeLearning Manager欧盟域。

## 错误

未找到帐户

## 描述

作者尝试将课程从Adobe Captivate发布到AdobeLearning Manager的情况时有发生。 但是，他们无法执行此操作，因为他们会看到一条错误消息，“未找到帐户”。

## 原因

出现此问题的原因是，Adobe Captivate默认配置为将Adobe发布到Learning Manager的美国域。

## 解决方案：

注意事项：

* 如果打开，请关闭Adobe Captivate应用程序。
* 您需要具有计算机的管理员访问权限才能执行以下步骤。 如果您没有管理员访问权限，请联系您的IT团队寻求帮助。

请执行以下步骤：

1. 转到Adobe Captivate的安装目录。

   例如，  `kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64` (Captivate版为2019版。 如果您使用的是其他版本的Adobe Captivate，则安装路径也不同)。

1. 复制配置文件 **AdobeCaptivate.ini** 到您的桌面。

   ![](assets/cp-captivate.ini.png)
   *查看配置文件*

1. 在桌面记事本中打开复制的文件。
1. 更改LearningManagerBaseUrl的值= `https://learningmanager.adobe.com/inappstarter` 至LearningManagerBaseUrl = `https://learningmanagereu.adobe.com/inappstarter`

   ![](assets/cp-primebaseurl.png)
   *查看PrimeBaseUrl*

1. 保存对记事本所做的更改。
1. 复制您编辑的已保存文件，并将其粘贴回文件路径。 替换原始文件  `kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64`
1. 完成后，启动Adobe Captivate并尝试将其发布至AdobeLearning Manager。
