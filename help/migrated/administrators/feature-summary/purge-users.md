---
description: 了解有关在 Adobe Learning Manager 中清除用户数据的更多信息。
jcr-language: en_us
title: 清除用户
contentowner: dvenkate
exl-id: 4449146c-6247-44fb-b695-a12023c31dc6
source-git-commit: 7c21986eff480f15cb788cf9a1cb51644bc083c8
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 52%

---

# 清除用户

了解有关在 Adobe Learning Manager 中清除用户数据的更多信息。

## 概述 {#overview}

使用清除用户功能可从 Adobe Learning Manager 中删除用户的个人身份信息和学习记录。请注意，“删除”和“清除用户”是两种不同的功能。 您可以还原已删除的用户，但无法还原与已清除用户关联的所有用户数据和学习记录。

清除用户操作可能会产生以下结果：

* 如果清除用户，则导入日志中的链接不起作用，无法避免下载旧CSV文件并将用户数据重新带回系统。
* 如果已清除作者，其姓名将被替换为清除该用户的管理员姓名。
* 如果讲师被清除，则系统会从会话中删除这些讲师。 管理员必须为此类会话更换/添加讲师。
* 在 Adobe Learning Manager 中清除用户不会删除任何外部应用程序（第三方系统或您编写的其他应用程序）中的用户。请与外部应用程序所有者联系，以将用户从此类应用程序中删除。
* 如果连接器的配置设置中引用了遭清除的用户，则会禁用连接器。 连接器需要由管理员重新配置才能恢复。

<!---### Manage users

In this training, you will learn how to assign and remove roles, send a welcome email, and delete and purge users. 

[![button](assets/launch-training-button.png)](https://learningmanager.adobe.com/app/learner?accountId=98632&sdid=4X3B8VJ2&mv=display&mv2=display#/course/7555586)

If you're unable to launch the training, write to <almacademy@adobe.com>.-->

## 如何清除用户

要清除用户，请执行以下步骤：

1. 作为管理员，请从左侧窗格中选择&#x200B;**[!UICONTROL “用户”]**。 此操作将打开&#x200B;**[!UICONTROL “内部用户”]**&#x200B;页面。
1. 删除要清除的用户。 要删除，请使用复选框选择一个或多个用户。 打开&#x200B;**[!UICONTROL 操作]**&#x200B;下拉列表并选择&#x200B;**[!UICONTROL 删除用户]**。
1. 在左侧窗格中，选择&#x200B;**[!UICONTROL “用户清理”]**。 系统将显示&#x200B;**[!UICONTROL “用户清理”]**&#x200B;页面，其中包含已删除用户的列表。 使用单选按钮选择要清除的用户。 一次只能清除一个用户。

   ![](assets/purge-1.png)

   *选择要清除的用户*

1. 打开&#x200B;**[!UICONTROL 操作]**&#x200B;下拉菜单，然后选择&#x200B;**[!UICONTROL 清除用户]**。

   ![](assets/purge-2.png)

   *选择“清除用户”选项*

1. 屏幕中将出现一个对话框，要求您予以确认。 清除后，与选定用户关联的所有用户数据和学习记录都将永久删除。 清除后，操作无法还原。 要确认，请单击“**[!UICONTROL 清除]**”。

   ![](assets/purge-3.png)

   *清除用户后的确认消息*

1. 确认并单击“清除”后，系统将接受清除请求。 操作完成后，您会收到通知。 系统也会向您提供清除请求 ID。 您可以向 CSM 提供此 ID 以跟踪请求。

>[!NOTE]
>
>将被删除的用户添加回系统后，之前的角色（例如管理员、经理、作者、讲师等）将不会保留。系统会将他们与学习者角色一起添加。

## 批量清除用户

您可以选择前 50 位用户，并一次性清除。 该操作允许管理员一次选择50个用户并一起清除。 当管理员希望批量清除用户时，此功能非常有用。 检查已选中准备清理的用户始终是最佳做法。 要确保只清理正确的用户组，这非常重要。

![](assets/bulk-purge-users.png)

*批量清除用户*

## 在清除之前筛选已删除的用户

Adobe Learning Manager允许管理员永久删除已从平台中删除的用户。 这一过程称为清除，可帮助组织维护干净的学习者数据库、遵守数据保留策略，并防止对用户数据的任何未经授权的访问。
这对于维护数据卫生和确保从系统中删除旧的未使用用户数据特别有用。
清除用户对于遵守数据隐私准则或通过删除冗余记录来维护经过整理的数据存储区至关重要。

### 按月筛选已删除的用户

您可以通过选择特定月份来过滤已删除的用户，然后永久删除这些用户。

要使用删除月份过滤已删除的用户，请执行以下操作：

1. 在管理员主页中选择&#x200B;**[!UICONTROL 用户]**，然后选择&#x200B;**[!UICONTROL 用户清理]**。
2. 选择&#x200B;**[!UICONTROL 选择删除月]**&#x200B;日期选取器并选择日期。

   ![](assets/deletion-date.png)
   _选择删除用户的月份_

   此时会显示所选月份中删除的用户的列表。

   ![](assets/list-of-user-deleted.png)
   _所选月份显示的已删除用户列表_

### 按月对已删除的用户进行排序

您可以按过滤用户的&#x200B;**[!UICONTROL 唯一用户ID]**&#x200B;和&#x200B;**[!UICONTROL 删除日期]**&#x200B;对过滤后的用户进行排序。

1. 在已删除用户列表中，根据用户ID或删除日期对用户进行排序。

   ![](assets/sort-by-date.png)
   _按唯一用户ID筛选的用户列表_

2. 选择一个或多个用户。
3. 选择&#x200B;**[!UICONTROL 操作]**，然后选择&#x200B;**[!UICONTROL 清除用户]**。
4. 在确认消息上选择“清除”以从Adobe Learning Manager中永久删除用户记录。

   ![](assets/select-purge.png)
   _在永久清除用户之前进行最终确认_

>[!NOTE]
>
>清除用户会永久删除其数据。 在继续之前，请仔细检查您的选择。

+++了解“清除用户”操作的结果

<table>
 <tbody>
  <tr>
   <th><strong>使用 Adobe Learning Manager 用户界面清除 — 企业版</strong></th>
   <th> </th>
  </tr>
  <tr>
   <td>从发起请求的企业帐户中删除选定用户。<br></td>
   <td>是</td>
  </tr>
  <tr>
   <td>从其电子邮件 adobe_id 与选定用户电子邮件匹配的所有试用帐户中删除所有用户。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>从其电子邮件 adobe_id 与选定用户电子邮件匹配的所有试用帐户中，删除所有身为该试用帐户创建者的用户。</td>
   <td>否</td>
  </tr>
  <tr>
   <td>从发起请求的企业帐户和所有试用帐户的所有其他字段中删除用户的电子邮件。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>通知发起人确认删除。</td>
   <td>是</td>
  </tr>
  <tr>
   <td><strong>使用“Learning Manager UI — 非企业版”清除</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>从发起请求的试用帐户中删除选定用户。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>从其电子邮件 adobe_id 与选定用户电子邮件匹配的所有试用帐户中删除所有用户。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>从其电子邮件 adobe_id 与选定用户电子邮件匹配的所有试用帐户中，删除所有身为该试用帐户创建者的用户。</td>
   <td>否</td>
  </tr>
  <tr>
   <td>从所有试用帐户的所有其他字段中删除用户的电子邮件。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>通知发起人确认删除。</td>
   <td>是</td>
  </tr>
  <tr>
   <td><strong>“清除其他用户 — 企业版”（非内部或外部Learning Manager用户的个人）</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>从发起请求的企业帐户和所有试用帐户的所有其他字段中删除选定用户。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>从帐户中删除用户。</td>
   <td>否</td>
  </tr>
  <tr>
   <td>通知发起人确认删除。 </td>
   <td>是</td>
  </tr>
  <tr>
   <td><strong>清除</strong> <strong>其他用户 — 非企业版（非内部或外部Learning Manager用户的个人）</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>从所有试用帐户的所有其他字段中删除选定的用户。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>从帐户中删除用户。</td>
   <td>否</td>
  </tr>
  <tr>
   <td>通知发起人确认删除。</td>
   <td>是</td>
  </tr>
  <tr>
   <td><strong>使用“Adobe IMS — 企业版”清除</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>将请求通知企业管理员。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>检查电子邮件字段以发送通知。</td>
   <td>否</td>
  </tr>
  <tr>
   <td><strong>使用“AdobeIMS — 非企业版”清除</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>从所有试用帐户中删除拥有您所提供的 AdobeID/电子邮件的所有用户。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>如果试用帐户的创建者拥有您所提供的电子邮件/AdobeId，则删除该帐户的所有用户。</td>
   <td>是</td>
  </tr>
  <tr>
   <td>从所有试用帐户的所有其他字段中，删除选定的电子邮件 ID。</td>
   <td>是</td>
  </tr>
 </tbody>
</table>

+++

## 常见问题解答 {#frequentlyaskedquestions}

+++完成清除请求需要多少天？

清除用户的请求最多需要 30 天才能完成。
+++

+++能否在Adobe Learning Manager中执行批量清除？

是，您可以批量执行清除。但是，您一次只能批量清除 50 位用户。
+++

+++我可以恢复已清除的用户吗？

讨论区创建的帖子数清除后，所有用户数据将被永久删除且无法恢复。

+++
