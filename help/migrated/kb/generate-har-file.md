---
description: 阅读以下内容，了解如何在 Google Chrome 中生成 HAR 文件。
jcr-language: en_us
title: 生成 HAR 文件
contentowner: dvenkate
source-git-commit: ec79aa3dd6225cc424721afb50702963c1b125eb
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 57%

---



# 生成 HAR 文件

阅读以下内容，了解如何在 Google Chrome 中生成 HAR 文件。

要生成 HAR 文件，请执行以下步骤：

1. 打开 Google Chrome 窗口，然后打开一个新选项卡。
1. 打开页面的开发者工具，右键单击并选择“检查”。
1. 打开&#x200B;**[!UICONTROL 网络]**&#x200B;选项卡。确保红色记录按钮处于活动状态。 启用 **[!UICONTROL 保留日志]** 复选框。

   ![](assets/preserve-log-checkbox.png)

   *选中网络选项卡中的保留日志复选框*

1. 使用凭据登录 [Adobe Learning Manager](https://learningmanager.adobe.com/acapindex.html) 并参加课程学习。执行所有将会导致问题的操作。
1. 在开发者工具中，右键单击并选择 **将全部内容保存为HAR**.

   在某些版本的Google Chrome中，您可能需要选择 **[!UICONTROL 复制]** > **[!UICONTROL 全部复制为HAR]**.

   ![](assets/copy-hra.png)

   *复制所有HAR文件*

1. 将复制的内容粘贴到记事本文件中。将其另存到桌面 **logs.har** 并通过电子邮件将其发送给Adobe。
