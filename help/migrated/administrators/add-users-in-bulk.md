---
jcr-language: en_us
title: 批量添加用户
description: 了解如何一次添加多个用户。
contentowner: saghosh
exl-id: c3309ce5-8764-452e-82d5-5637c23c661b
source-git-commit: 96602899dd76eae14a6b7e1808d529756657e7b8
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 22%

---

# 批量添加用户

>[!INFO]
>
>在本培训中，您将了解如何通过CSV批量添加用户。<br><br>[![按钮](feature-summary/assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555555)</br></br>

如果您无法启动培训，请写入<almacademy@adobe.com>。

## 如何添加多个用户

您可以按照以下步骤一次添加多个用户：

1. 在管理员登录中单击左侧窗格的&#x200B;**[!UICONTROL 用户]**，然后单击&#x200B;**[!UICONTROL 添加]** > **[!UICONTROL 上传csv]**。 此时会显示弹出对话框。

1. 您可以使用 .csv 文件添加多个用户。 单击“**[!UICONTROL 导入]**”，然后从计算机中选择/打开.csv文件。

1. 导入文件后，在首次上传 .csv 文件时，将 .csv 文件的内容映射到应用程序标签。

   在后续上传文件时，均需考虑标签之前的设置。 完成数据映射后单击“**[!UICONTROL 保存]**”，然后单击“**[!UICONTROL 添加]**”以上传映射的.csv文件。

1. 完成数据映射后单击“**[!UICONTROL 保存]**”，然后单击“**[!UICONTROL 添加]**”以上传映射的.csv文件。

## 包含必填字段的 CSV 上传 {#csvuploadwithmandatoryfields}

在CSV中，用户个人资料和经理电子邮件ID并不是必填项。 只有用户名和用户的电子邮件ID才是必填字段。

在这种情况下，系统会默认将您公司的管理员视为用户的经理， 默认情况下，将员工视为用户的个人资料。

>[!NOTE]
>
>要添加新用户，请创建一个包含其详细信息的新CSV文件并将其上传。 不支持更新和重新上传现有CSV文件。

**示例CSV**

Learning Manager示例CSV包含以下必填字段。
[Sample-CSV-name-email.zip](assets/sample-csv-name-email.zip)

## 包含所有字段的 CSV 上传 {#csvuploadwithallthefields}

在为任何员工添加经理电子邮件ID之前，请确保首先将经理添加为CSV中的员工。 例如，在以下快照中，请参阅员工姓名 Howard Walters：

![](assets/csv-example.png)

*要上传的CSV模板*

此外，组织的管理员可以将&#x200B;**自己**&#x200B;添加为员工，并将其经理的电子邮件ID作为root提及。

**示例CSV**

Learning Manager示例CSV如下图所示，其中包含所有字段。
[learning-manager-sample-csv.zip](assets/learning-manager-sample-csv.zip)。

有关详细信息，请参阅[使用CSV上传](/help/migrated/administrators/feature-summary/add-users-user-groups.md)功能帮助内容。
