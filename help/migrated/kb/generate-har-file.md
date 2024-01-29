---
description: 继续阅读以了解如何在Google Chrome上生成HAR文件。
jcr-language: en_us
title: 生成HAR文件
contentowner: dvenkate
source-git-commit: ec79aa3dd6225cc424721afb50702963c1b125eb
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 0%

---



# 生成HAR文件

继续阅读以了解如何在Google Chrome上生成HAR文件。

要生成HAR文件，请执行以下步骤：

1. 打开Google Chrome窗口，然后打开一个新的选项卡。
1. 打开页面的开发者工具，单击鼠标右键> Inspect。
1. 打开 **[!UICONTROL 网络]** 选项卡。 确保红色记录按钮处于活动状态。 启用 **[!UICONTROL 保留日志]** 复选框。

   ![](assets/preserve-log-checkbox.png)

   *选中网络选项卡中的保留日志复选框*

1. 登录到 [Learning Manager](https://learningmanager.adobe.com/acapindex.html) 使用您的凭据并参加课程。 执行所有将会导致问题的操作。
1. 在开发者工具中，右键单击并选择 **将全部内容保存为HAR**.

   在某些版本的Google Chrome中，您可能需要选择 **[!UICONTROL 复制]** > **[!UICONTROL 全部复制为HAR]**.

   ![](assets/copy-hra.png)

   *复制所有HAR文件*

1. 将复制的内容粘贴到记事本文件中。 将其另存到桌面 **logs.har** 并通过电子邮件将其发送给Adobe。
