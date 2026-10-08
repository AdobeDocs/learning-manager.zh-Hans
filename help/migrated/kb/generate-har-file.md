---
description: 阅读以下内容，了解如何在 Google Chrome 中生成 HAR 文件。
jcr-language: en_us
title: 生成 HAR 文件
contentowner: dvenkate
exl-id: 99fe78e8-b5e7-40a7-b9a5-efc2382de993
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 65%
---
# 生成 HAR 文件

阅读以下内容，了解如何在 Google Chrome 中生成 HAR 文件。

要生成 HAR 文件，请执行以下步骤：

1. 打开 Google Chrome 窗口，然后打开一个新选项卡。
1. 打开页面的开发者工具，右键单击并选择“检查”。
1. 打开&#x200B;**[!UICONTROL 网络]**&#x200B;选项卡。 请确保红色记录按钮处于活动状态。 启用&#x200B;**[!UICONTROL 保留日志]**&#x200B;复选框。

   ![](assets/preserve-log-checkbox.png)

   *选中“网络”选项卡中的“保留日志”复选框*

1. 使用凭据登录 [Adobe Learning Manager](https://learningmanager.adobe.com/acapindex.html) 并参加课程学习。 执行所有将会导致问题的操作。
1. 在开发人员工具中，右键单击并选择&#x200B;**将全部内容保存为HAR**。

   在某些版本的Google Chrome中，您可能需要选择&#x200B;**[!UICONTROL 复制]** > **[!UICONTROL 全部复制为HAR]**。

   ![](assets/copy-hra.png)

   *复制所有HAR文件*

1. 将复制的内容粘贴到记事本文件中。 将其作为&#x200B;**logs.har**&#x200B;保存到桌面，然后通过电子邮件发送给Adobe。
