---
jcr-language: en_us
title: 批量添加用户
description: 了解如何一次添加多个用户。
contentowner: saghosh
source-git-commit: 0534bd52c80b77d985cfe715f74054f3aabac9a2
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 24%

---



# 批量添加用户

在本培训中，您将了解如何通过CSV批量添加用户。

[![按钮](feature-summary/assets/launch-training-button.png)](https://learningmanager.adobe.com/app/learner?accountId=98632&amp;sdid=51TC8QS1&amp;mv=display&amp;mv2=display#/course/7555555)

如果您无法启动培训，请写信至 <almacademy@adobe.com>.

## 如何添加多个用户

您可以按照以下步骤一次添加多个用户：

1. 点击 **[!UICONTROL 用户]** 在管理员登录的左侧窗格中，单击 **[!UICONTROL 添加]** > **[!UICONTROL 上传csv]**. 此时会显示弹出对话框。

1. 您可以使用 .csv 文件添加多个用户。 点击 **[!UICONTROL 导入]** 并在计算机中选择/打开.csv文件。

1. 导入文件后，在首次上传 .csv 文件时，将 .csv 文件的内容映射到应用程序标签。

   在后续上传文件时，均需考虑标签之前的设置。 点击 **[!UICONTROL 保存]** 完成数据映射后单击 **[!UICONTROL 添加]** 上传映射的.csv文件。

1. 点击 **[!UICONTROL 保存]** 完成数据映射后单击 **[!UICONTROL 添加]** 上传映射的.csv文件。

## 包含必填字段的 CSV 上传 {#csvuploadwithmandatoryfields}

在CSV中，用户个人资料和经理电子邮件ID并不是必填项。 只有用户名和用户的电子邮件ID才是必填字段。

在这种情况下，系统会默认将您公司的管理员视为用户的经理， 默认情况下，将员工视为用户的个人资料。

**示例CSV**

Learning Manager示例CSV包含以下必填字段。
[Sample-CSV-name-email.zip](assets/sample-csv-name-email.zip)

## 包含所有字段的 CSV 上传 {#csvuploadwithallthefields}

在为任何员工添加经理电子邮件ID之前，请确保首先将经理添加为CSV中的员工。 例如，在以下快照中，请参阅员工姓名 Howard Walters：

![](assets/csv-example.png)

*要上传的CSV模板*

此外，组织的管理员可以将自己添加为员工，并将经理的电子邮件ID作为root提及。

**示例CSV**

Learning Manager示例CSV如下图所示，其中包含所有字段。
[learning-manager-sample-csv.zip](assets/learning-manager-sample-csv.zip).

请参阅  [使用CSV上传](/help/migrated/administrators/feature-summary/add-users-user-groups.md) 功能帮助内容，了解更多信息。
