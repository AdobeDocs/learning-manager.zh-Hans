---
description: 阅读本文，了解如何配置与所有学习对象相关事件的电子邮件模板。
jcr-language: en_us
title: 电子邮件模板
source-git-commit: fda58bc18bee6d21ee904a442884e4759587d053
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 89%

---



# 电子邮件模板

阅读本文，了解如何配置与所有学习对象相关事件的电子邮件模板。

Adobe Learning Manager 应用程序根据事件向多个用户角色发送电子邮件通知。

作为作者，您可以自定义电子邮件模板，例如添加或修改内容以及向用户发送学员、经理和作者活动触发的各种事件的通知。 例如，每当学员注册您的课程时，您都可以发送自定义电子邮件。 在注册时，学员将自动收到课程特定的电子邮件。

您还可以禁用电子邮件模板选项，选择不发送特定事件的电子邮件通知。

## 设置电子邮件通知 {#settingemailnotifications}

1. 在“作者”应用程序中，单击要为其配置电子邮件模板的学习对象。 例如，“课程”。
1. 在“学习对象”页面中，单击要配置电子邮件设置的课程、认证或学习计划。
1. 在学习对象详细信息页面中，单击“电子邮件模板”。

   您可以查看可用于所选学习对象的模板列表。

   ![](assets/email-templates-forlearningprograms.png)
   *模板列表*

1. 单击事件名称以在预览模式下查看模板。

   ![](assets/preview-the-emailtemplateforyourlearningobject.png)

   *查看模板预览*

   您可以单击模板正文中的文本以自定义每个模板。 如要在文本中插入变量，可单击快照中显示的相应图标。 将鼠标悬停在每个图标上即可查看名称。

   ![](assets/insert-variable.png)
   *插入变量*

   以下变量可用：

   * LPName
   * LPCompletionDeadline
   * LearnerName
   * LearnerEmail
   * CourseName
   * CourseDescription
   * CourseCompletionDeadline
   * CourseSkillDetails
   * CourseBadge

   您可单击模板上方的“恢复为原始”链接，将邮件重置为默认内容。

   正如模板顶部显示的那样，您可以根据电子邮件通知的类型为多个角色（经理、学习者等）自定义模板。

1. 单击模板页面底部的“保存”。
1. 在“电子邮件模板”页面中，单击“是/否”圆形切换按钮可发送或禁用通知。

![](assets/email-notification-e1437624109719.png)
*启用或禁用电子邮件通知*

如果每个事件名称的通知按钮中的圆圈靠近“是”（以蓝色阴影为背景），则表示通知已启用。 如果为灰色阴影且圆圈靠近“否”，则表示通知已禁用。

如果在课程级别配置了电子邮件模板，则该模板优先于该特定课程的管理员级别设置。
