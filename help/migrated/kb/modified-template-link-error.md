---
jcr-language: en_us
title: 在 Adobe Learning Manager 中，修改模板后触发的电子邮件链接会引发错误
description: 在Adobe Learning Manager中，修改模板后触发的电子邮件链接会引发错误
contentowner: nluke
preview: true
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 73%

---



# 在 Adobe Learning Manager 中，修改模板后触发的电子邮件链接会引发错误

## 问题

单击自动化电子邮件/欢迎电子邮件/注册电子邮件的链接时出错。

**错误**

HTTP 状态 400 - 请求错误

![](assets/email-404.png)

## 原因

错误自定义电子邮件模板时，通常会发生这种情况。

**解决方案**

为避免因自定义而出现的与断开链接相关的任何错误，请按以下步骤操作：

1. 以管理员身份登录。
1. 在左侧面板中，单击&#x200B;**[!UICONTROL 电子邮件模板]**。

1. 导航至所需模板，然后单击进行修改。

   此时会打开&#x200B;**“模板预览”**&#x200B;窗口。

   ![](assets/email-template.png)

   编辑电子邮件模板时请注意以下几点：

   * 建议在 Adobe Learning Manager 界面中修改电子邮件模板。
   * 将修改后的模板复制粘贴到记事本/Word 文件中，以存储所做更改的副本。
   * 避免替换模板中以蓝色突出显示的动态文本。 例如，“**OrganizationName**”、“**学习者**”、“**单击此处**”、“**CertificateName**”等。

1. 单击&#x200B;**[!UICONTROL 保存]**&#x200B;以确认应用于模板的更改。
1. 触发电子邮件，以验证链接是否符合预期效果。
1. 单击修改后模板的&#x200B;**“恢复为原始”**&#x200B;选项，恢复为原始设置。
