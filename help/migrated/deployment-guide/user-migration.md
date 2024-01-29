---
jcr-language: en_us
title: Learning Manager部署指南 — 第2部分
contentowner: sanm
preview: true
source-git-commit: fba5e5ddc1964b485be473bf356806f234688cf4
workflow-type: tm+mt
source-wordcount: '2232'
ht-degree: 0%

---



# Learning Manager部署指南 — 第2部分

## 技术设置 {#technicalsetup}

Learning Manager帐户技术设置主要适用于企业用户。 本文档将介绍如何为企业配置单点登录，以及如何将Learning Manager与第三方连接器集成。

### 配置单点登录 {#configuresinglesignon}

作为Admin Console的系统管理员，您的首要任务之一是定义和设置身份系统，以便根据该系统对最终用户进行身份验证。 当您的组织购买Learning Manager的许可证时，您需要向最终用户提供这些许可证。 为此，您需要想出方法对这些用户进行身份验证。 要为用户配置SSO，请执行以下步骤：

1. 在Learning Manager主页中，单击 **[!UICONTROL **&#x200B;设置&#x200B;**>**&#x200B;登录方法&#x200B;**.]**

   ![](assets/configure-sso-step1.png)

1. 根据您的用户类型，选择以下任意一项 **[!UICONTROL **&#x200B;内部用户&#x200B;**或**&#x200B;外部用户&#x200B;**.]**



1. 从**[!UICONTROL **登录**]**下拉字段，选择 **[!UICONTROL **&#x200B;单点登录&#x200B;**.]**

   ![](assets/configure-sso-step3.png)

1. 要配置单点登录设置，请单击 **[!UICONTROL **&#x200B;更改&#x200B;**.]**

   ![](assets/configure-sso-step4.png)

1. 在 ****[!UICONTROL IDP启动的身份验证URL]**** 字段中，输入服务提供商提供的身份验证URL。



   ![](assets/configure-sso-step5.png)

1. 点击**[!UICONTROL **上传&#x200B;**]**旁边的**[!UICONTROL  **IDP元数据XML文件&#x200B;**]******字段，然后上传XML文件。
1. 点击 **[!UICONTROL **&#x200B;保存&#x200B;**.]**
1. 已成功为您的帐户配置SSO身份验证。 您应能使用SSO登录Learning Manager帐户。

   ***您在Learning Manager中配置的SSO应支持SAML 2.0。***

## 用户数据迁移 {#migrationofuserdata}

作为管理员，当企业购买Learning Manager时，您需要执行的关键步骤之一是迁移。 必须将现有的培训内容和用户数据移动到Learning Manager。 以下迁移工作流程可帮助您利用现代直观的LMS的优势，而不会丢失任何组织的旧数据。

Learning Manager允许您通过逐步向导在迭代Sprint中迁移现有LMS。 您可以完全了解每次Sprint的状态，以确保在将旧数据迁移到AdobeLearning Manager时，学习者不会因此耽误学习进程。

要执行迁移工作流程，您需要具备集成管理员权限。 作为管理员，您可以担任集成管理员的角色，或将此角色分配给其他用户。

**我们可以在Shaleen的帮助下创建一个视觉效果。**

1. 前提条件
1. 评估现有内容和用户数据
1. 从现有LMS导出和映射数据
1. 设置FTP和BOX文件夹以进行迁移
1. 将学习者转移至Learning Manager
1. 将学习内容转移至Learning Manager
1. 将剩余数据转移至Learning Manager



### 前提条件 {#prerequisite}

在开始迁移过程之前，必须执行以下先决条件：

* 从现有LMS中提取数据和内容，并将数据转换为Learning Manager定义的文件格式。
* 使用FTP和BOX连接器导入用户。 集成管理员必须确保在迁移过程之前已配置连接器。



***建议管理员在将数据和内容迁移到Learning Manager生产环境之前，先在试用帐户中尝试迁移过程。 ***

### 评估和导出数据 {#evaluatingandexportingdata}

集成管理员应首先查看当前LMS中的可用数据。 作为集成管理员，您只能迁移以下学习对象：

* 模块
* 课程
* 模块版本
* 课程实例
* 课程模块
* 技能
* 技能级别
* 技能课程
* 认证
* 认证课程
* 认证提交
* 学习计划
* 学习计划课程
* 学习计划实例
* 学习计划课程实例
* 注册
* 认证注册
* 学习计划注册
* 用户课程等级



评估现有数据后，必须使用Learning Manager中的标准CSV规范映射此数据。 下载以下示例 ***csv-specifications.zip*** 包含此迁移所需的七张Excel表格的文件。 这些Excel工作表包含带有说明的规范，便于您了解如何使用.csv文件中的字段映射现有数据。

<!--
<Download link to the zip file>
-->

确保每个.csv文件均包含每个字段的数据，且数据应符合以下规定格式：

<table> 
 <tbody> 
  <tr> 
   <th width="7%" valign="top"><p><strong>不行。</strong></p></th> 
   <th width="29%" valign="top"><p><strong>Excel工作表名称</strong></p></th> 
   <th width="31%" valign="top"><p><strong>内容描述</strong></p></th> 
   <th width="31%" valign="top"><p><strong>注释</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>1</p></td> 
   <td><p>module.xlsx</p></td> 
   <td><p>module.csv的元数据</p></td> 
   <td><p> </p></td> 
  </tr> 
  <tr> 
   <td><p>2</p></td> 
   <td><p>course.xlsx</p></td> 
   <td><p>course.csv的元数据</p></td> 
   <td><p>对每个课程提及一个作者姓名，因为有时迁移后的应用程序无法准确显示多个作者姓名。 </p></td> 
  </tr> 
  <tr> 
   <td><p>3</p></td> 
   <td><p>module_version.xlsx </p></td> 
   <td><p>module_version.csv的元数据</p></td> 
   <td><p>确保提供用于上传内容的Box帐户文件夹的URL路径。 </p></td> 
  </tr> 
  <tr> 
   <td><p>4</p></td> 
   <td><p>course_instance.xlsx</p></td> 
   <td><p>course_instance.csv的元数据 </p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>5</p></td> 
   <td><p>course_module.xlsx</p></td> 
   <td><p>course_module.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>6</p></td> 
   <td><p>skill.xlsx</p></td> 
   <td><p>skill.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>7</p></td> 
   <td><p>skill_level.xlsx</p></td> 
   <td><p>skill_level.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>8</p></td> 
   <td><p>skill_course.xlsx</p></td> 
   <td><p>skill_course.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>9</p></td> 
   <td><p>Certification.xlsx</p></td> 
   <td><p>Certification.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>10</p></td> 
   <td><p>certification_course.xlsx</p></td> 
   <td><p>certification_course.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>11</p></td> 
   <td><p>certification_commit.xlsx</p></td> 
   <td><p>certification_commit.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>12</p></td> 
   <td><p>learning_program.xlsx</p></td> 
   <td><p>learning_program.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>13</p></td> 
   <td><p>learning_program_course.xls </p></td> 
   <td><p>learning_program_course.csv的元数据 </p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>14</p></td> 
   <td><p>learning_program_instance.xlsx </p></td> 
   <td><p>learning_program_instance.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>15</p></td> 
   <td><p>learning_program_instance_course_instance.xlsx </p></td> 
   <td><p>learning_program_instance_course_instance.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>16</p></td> 
   <td><p>enrollments.xlsx</p></td> 
   <td><p>enrollments.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>17</p></td> 
   <td><p>certification_enrollment.xlsx</p></td> 
   <td><p>certification_enrollment.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>18</p></td> 
   <td><p>learning_program_enrollment.xlsx</p></td> 
   <td><p>learning_program_enrollment.csv的元数据</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>19</p></td> 
   <td><p>User_course_grade.xlsx</p></td> 
   <td><p>User_course_grade.csv的元数据</p></td> 
   <td><p>在.csv文件中提供所需的学习者记录数据（即使这些并非必需数据）。 如果没有此信息，即使对.csv进行了迁移处理，Learning Manager应用程序也可能无法反映任何数据。 </p></td> 
  </tr> 
 </tbody> 
</table>

***Learning Manager仅支持UTF 8和32位格式的日期和时间值。 如果CSV文件中指定的日期超出范围（例如2038-07-17T08），则在迁移期间可能会出错:53:21.000Z或1980-04-17T08:13:25.322时。***

### 将数据导入csv文件时的依赖关系 {#dependencieswhileimportingdatatocsvfiles}

将现有数据导入标准csv格式时，请注意以下依赖关系：

* module_version.csv依赖于module.csv
* course_instance.csv依赖于course.csv
* course_module.csv依赖于course.csv、module.csv和module_version.csv
* course_instance.csv依赖于course.csv
* enrollment.csv依赖于course.csv
* user_course_grade.csv依赖于course.csv和module.csv
* skill_course.csv依赖于course.csv
* skill_level.csv依赖于skill.csv
* learning_program_instance.csv依赖于learning program和learning_program_course.csv
* learning_program_course.csv依赖于learning_program.csv
* learning_program_enrollment.csv依赖于learning program和learning_program_instance.csv
* learning_program_instance_course_instance.csv依赖于learning_program.csv、learning_program_instance.csv和course_instance.csv
* certification_course.csv依赖于certification.csv和course.csv
* certification_commit.csv依赖于certification.csv和certification_course.csv
* certification_enrollment.csv依赖于certification.csv、certification_course.csv和certification_enrollment.csv



导出数据后，将.csv文件保存在本地计算机上。 现在可将文件放入FTP或BOX文件夹中。

## 设置FTP和BOX文件夹以进行迁移 {#setupftpandboxfoldersforthemigration}

在规划并开始实际迁移所有内容之前，必须先设置FTP和BOX文件夹。 您需要将.csv文件放入这些文件夹。 在FTP和BOX文件夹中提供.csv文件格式的旧内容后，Learning Manager即会使用这些数据。

### 设置FTP帐户 {#setupanftpaccount}

在集成管理员主页中，单击 **[!UICONTROL **&#x200B;请求CSV FTP文件夹&#x200B;**.]** 在显示的弹出对话框中，输入您的电子邮件ID。 通过联机向导创建Exavault FTP帐户。 创建帐户后，即可在Exavault FTP中查看迁移项目和Sprint项目文件夹。

请参阅ExaVault的项目文件和文件夹的示例快照，如下所示：

![](assets/set-up-an-ftp-account.png)

成功设置FTP文件夹后，系统会显示“FTP文件夹设置已完成”消息。

## 设置BOX帐户 {#setupaboxaccount}

要创建BOX帐户并设置BOX文件夹，请执行以下步骤：

在集成管理员主页中，选择“迁移”。

在“设置”部分，单击“请求Box文件夹” 。

![](assets/set-up-a-box-account.png)

在 ****[!UICONTROL 输入电子邮件]**** 字段中，输入要从中接收连接至Box的登录说明的电子邮件ID。

点击 **[!UICONTROL ** Connect **.]**

您会收到来自Box的电子邮件，其中包含指向共享文件夹的链接。 如果您没有Box帐户，请单击“注册”并创建帐户。 登录说明随后会发送到集成管理员的电子邮件ID。

保存连接后，迁移页面会显示以下消息：“Box文件夹设置已完成”。

## 将内容迁移至Learning Manager {#migratingthecontenttocaptivateprime}

在开始迁移之前，请务必注意以下几点：

* 在任何时间点，一个帐户只能有一个活动的迁移项目。 在任何时间点，每个项目只能有一个活动的Sprint。
* 无法撤消已在执行中的运行。 但是，您可以使用Learning Manager各项功能中的现有删除选项来撤消任何数据或内容迁移。

迁移项目一旦开始，项目即会进入“迁移中”状态。 在此状态下，除集成管理员外，其他任何用户均无法登录Learning Manager。

将培训内容上传到内容文件夹：

在集成管理员主页中，单击 **[!UICONTROL 迁移。]**

在“迁移主页”中，系统显示组织中已创建的迁移项目。

点击**[!UICONTROL **新**]**在页面右上角，用于创建迁移项目。

***如果您尚未创建FTP文件夹，系统将提示您创建一个FTP文件夹Exavault帐户。 在创建迁移项目之前，必须先完成此步骤。 ***

在 ****[!UICONTROL 创建新迁移项目]**** 页面中，指定项目的名称。

![](assets/migrating-the-content-1.png)

为项目和课程目录指定标签，并提供迁移项目的描述。 迁移数据项通过迁移项目标记进行标识。 如果没有特定的课程目录，请从下拉列表中选择默认目录，您使用迁移项目迁移的所有课程均包含在您此时选择的目录中。 如果不选择任何目录，则迁移的所有课程均会包含在默认目录中。

点击 **[!UICONTROL 创建。]**

在“Sprint配置”页面中，为迁移项目创建Sprint。 在Learning Manager迁移过程中，Sprint用于定义已选择从现有LMS迁移的一组迁移项。

![](assets/migrating-the-content-2.png)

指定Sprint的名称，并提供Sprint的描述。

选择 ****[!UICONTROL 自上次运行后已添加或修改的用户复选框]****，将用户列表与Learning Manager应用程序同步。 如果要将内容和数据迁移到Learning Manager应用程序，则可能无需此操作。 但是，如果先前的Sprint迁移与最新的Sprint迁移之间存在时间差，则建议选择同步用户列表。 此步骤可使Learning Manager数据库与您的LMS用户保持同步。

***建议在迁移enrollment.csv和user_course_grade.csv时执行此同步步骤。 此步骤可使Learning Manager数据库与迁移数据库保持同步，并确保所有通过Sprint迁移其记录的用户在迁移数据库中处于可用状态。***

点击 **[!UICONTROL **&#x200B;下一个&#x200B;**.]**

点击**[!UICONTROL **开始**]**使用上传的数据和内容开始进行Sprint迁移。 点击 ****[!UICONTROL 刷新]**** 在开始“Sprint运行”之前，请将FTP和内容文件夹与Learning Manager同步。

![](assets/migrating-the-content-3.png)

您可以点击****[!UICONTROL 停止]****在Sprint迁移过程中的任何时间点，中止Sprint迁移。

系统会针对每个Sprint数据项和内容显示迁移状态。 在迁移Sprint运行过程中，检查迁移的成功项和失败项数。

如果要上传模块内容，请确保在*module_version.csv *文件中提供相应内容文件夹的路径。 如果不执行此步骤，则在迁移期间可能会出错。 例如，如果要上传自学模块内容（例如视频），则需要在*module_version.csv *文件中指定Box URL的相对路径。

以下是迁移过程的示例快照，仅供参考。 如快照所示，您可以查看每个迁移数据项的已处理记录数以及成功和失败项状态。 单击失败项对应的“下载错误记录”即可下载并查看错误日志。 您可以修复CSV中的问题并再次通过FTP上传。

![](assets/migrating-the-content-4.png)

要查看迁移项目的所有Sprint列表，请单击“**”[!UICONTROL **Sprint**]**在左侧导览窗格中。 您可以查看所有Sprint的列表、对每个Sprint执行的运行数、开始日期、持续时间和完成状态，如下面的示例快照所示。

![](assets/migrating-the-content-5.png)

要查看迁移项目的所有Sprint列表，请单击“**”[!UICONTROL **Sprint**]**在左侧导览窗格中。 您可以查看所有Sprint的列表、对每个Sprint执行的运行数、开始日期、持续时间和完成状态，如下面的示例快照所示。

要查看迁移项目的所有Sprint列表，请单击“**”[!UICONTROL **Sprint**]**在左侧导览窗格中。 您可以查看所有Sprint的列表、对每个Sprint执行的运行数、开始日期、持续时间和完成状态，如下面的示例快照所示。

***在将迁移项目标记为“完成”之前，请确保该项目的所有Sprint均已完成。 在将迁移项目标记为“完成”后，您将无法返回该项目并在其中创建任何Sprint。 您无法对该项目进行任何修改。 您只能创建另一个迁移项目，然后向其中添加Sprint。***

在迁移公司旧LMS系统的学习数据和内容后，请验证数据和内容是否正确导入。 验证方法如下：以管理员身份登录，然后对导入的模块和课程数据及内容进行可用性验证

有关迁移的有用资源，请参阅以下内容：

* 迁移问题疑难解答
* CSV上传常见问题解答

