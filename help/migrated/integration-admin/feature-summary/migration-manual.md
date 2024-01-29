---
description: 本参考手册适用于希望将现有LMS迁移到Learning Manager LMS的集成管理员
jcr-language: en_us
title: 迁移手册
source-git-commit: 66dfaaaf723382eada39e2be29dfd49b795107a0
workflow-type: tm+mt
source-wordcount: '3705'
ht-degree: 0%

---



# 迁移手册

本参考手册适用于希望将现有LMS迁移到Learning Manager LMS的集成管理员

## 概述 {#overview}

<table>
 <tbody>
  <tr>
   <td><img src="assets/migration.jpg"></td>
   <td>
    <p><a href="https://business.adobe.com/products/learning-manager/adobe-learning-manager.html">AdobeLearning Manager</a> 是一个由云托管、以学习者为中心的自助式学习管理解决方案。 Adobe功能使拥有现有学习管理系统(LMS)的企业能够将其公司的培训数据和培训内容迁移到Learning Manager LMS应用程序。 </p></td>
  </tr>
 </tbody>
</table>

### 使用场景 {#usagescenario}

通常，大型企业会拥有其内部LMS或任何供应商提供的旧版学习管理系统。 LMS由企业培训内容和培训数据组成。 企业购买Learning Manager后，可能希望将现有的LMS内容和数据移至Learning Manager，以便您能够利用现代直观的LMS的优势，同时不会丢失任何企业的旧数据。

Learning Manager提供了必要的工具和规范，可供公司的集成管理员设置并执行迁移任务。

即日起，企业管理员可联系Adobe支持团队访问Learning Manager的迁移功能。 要为帐户启用迁移功能，请联系AdobeLearning Manager支持团队。

## 迁移过程 {#apidescription}

迁移的先决条件、迁移过程中涉及的关键步骤、迁移Sprint、规范、数据和内容迁移步骤在本部分中介绍如下：

### 先决条件 {#prerequisites}

Learning Manager团队希望在迁移之前由公司的集成管理员执行以下任务：

* 集成管理员可从现有LMS中提取数据和内容，并将数据转换为Learning Manager定义的文件格式。
* Learning Manager不支持在迁移过程中导入用户，组织应使用连接器导入用户。 Adobe Systems希望在迁移之前先配置好这些连接器。 请参阅 [Learning Manager连接器帮助](connectors.md) 了解更多信息。

Learning Manager建议管理员在将数据和内容迁移到Learning Manager生产环境之前，先在试用帐户中尝试迁移过程。

### 迁移流程的关键步骤 {#keystepsofmigrationprocess}

将内容和数据从现有LMS迁移到Learning Manager涉及的关键步骤如下：

1. 集成管理员或合作伙伴应对需要迁移的现有LMS数据和内容进行评估。
1. 集成管理员将评估Learning Manager为获取数据和内容提供的工具和规范。
1. 集成管理员根据旧LMS提供的功能，编写代码或执行手动工作以从旧LMS导出培训数据和内容。
1. 培训数据和内容可用后，集成管理员会分析和映射数据及内容，以符合Learning Manager迁移规格。
1. 集成管理员将使用Learning Manager提供的工具按以下顺序进行迁移：

   1. 将学习者转接到Learning Manager
   1. 将培训内容传输到Learning Manager中
   1. 最后，将培训数据传输到Learning Manager。

公司可以开始搭配使用Learning Manager LMS和旧版内容。

### 迁移对象的范围 {#scopeofmigrationobjects}

您只能迁移以下学习对象的内容：

* 模块
* 徽章
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
* 工作辅助
* 工作辅助版本
* 工作辅助课程
* 工作辅助技能
* 注册
* 认证注册
* 学习计划注册
* 工作辅助注册
* 用户课程等级



### 迁移的关键概念 {#keyconceptsofmigration}

为了便于您快速参考，我们简要介绍了Learning Manager迁移过程的一些关键概念，如下所示：

**迁移项目**

在Learning Manager中，迁移项目包含一个或多个Sprint。 您的帐户还可以有多个迁移项目。 Learning Manager中的迁移过程从创建迁移项目开始。

**Sprint**

在Learning Manager迁移过程中，Sprint用于定义已选择从现有LMS迁移的一组迁移项。 迁移项目可以是课程模块、学习者记录或一组课程。 您可以在一个Sprint中包含多个学习数据项。 可以在每个Sprint中执行迁移作业。

**Sprint运行**

Sprint运行是启动Sprint迁移作业的过程。 您可以在运行的任何时间点停止Sprint运行。

**Sprint重新运行**

可在任何时间点完成迁移Sprint后重新执行。 当您想要将Sprint项中的数据追加到应用程序中并再次将其迁移到应用程序中或在CSV中更正错误时，会发生重新执行或重新运行Sprint的情况。

**CSV规范**

Learning Manager为您提供了一组 [标准CSV规范](migration-manual.md#main-pars_header_140933605). 最佳做法是，在开始迁移过程之前先完整了解这些CSV规范。 公司的集成管理员可对现有的数据格式进行分析和映射，以便与Learning Manager提供的CSV模板项相匹配。

**迁移项目标签**

Adobe Systems建议使用一组关键字作为标签，以便在Learning Manager应用程序中轻松识别迁移项目。 这些标记使您能够随时在Learning Manager应用程序内部识别项目。

**无内容模块**

Learning Manager允许您上传无内容的模块。 Adobe Systems将其视为Learning Manager中一个无内容的模块。 如果您希望从现有LMS迁移一些旧版数据而不需要任何内容，则可以上传无URL引用的module_version.csv文件。

## CSV规范和示例CSV {#csv}

在下面找到标准CSV规范，您可将其用于与现有LMS迁移数据进行映射。 单击csv-specifications和sample-csv以下载zip文件。 下载的csv-specifications.zip包含七个Excel工作表文件。 这些Excel工作表文件是带有说明的规范，可帮助您了解如何填写.csv文件。 相应的.csv文件应包含每个字段的数据，其格式应符合这些.xlsx文件中的说明。

<table border="1" cellspacing="0" cellpadding="0" width="100%">
 <tbody>
  <tr>
   <th>
    <p><b>Sl.no</b></p></th>
   <th>
    <p><b>文件名</b></p></th>
   <th>
    <p><b>内容说明</b></p></th>
   <th>
    <p>注释</p></th>
  </tr>
  <tr>
   <td>
    <p>1</p></td>
   <td>
    <p>module.xlsx</p></td>
   <td>
    <p>module.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>2</p></td>
   <td>
    <p>badge.xlsx</p></td>
   <td>
    <p>badge.xlsx的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>3</p></td>
   <td>
    <p>course.xlsx</p></td>
   <td>
    <p>course.csv的元数据</p></td>
   <td>
    <p>对每个课程提及一个作者姓名，因为有时迁移后的应用程序无法准确显示多个作者姓名。 </p></td>
  </tr>
  <tr>
   <td>
    <p>4</p></td>
   <td>
    <p>module_version.xlsx </p></td>
   <td>
    <p>module_version.csv的元数据</p></td>
   <td>
    <p>确保提供用于上传内容的Box帐户文件夹的URL路径。 </p></td>
  </tr>
  <tr>
   <td>
    <p>5</p></td>
   <td>
    <p>course_instance.xlsx</p></td>
   <td>
    <p>course_instance.csv的元数据 </p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>6</p></td>
   <td>
    <p>session.xlsx</p></td>
   <td>
    <p>session.csv的元数据</p></td>
   <td>
    <p>确保会话csv中的每个条目都与至少一个教室/虚拟教室模块相关联</p></td>
  </tr>
  <tr>
   <td>
    <p>7</p></td>
   <td>
    <p>course_module.xlsx</p></td>
   <td>
    <p>course_module.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>8</p></td>
   <td>
    <p>skill.xlsx</p></td>
   <td>
    <p>skill.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>9</p></td>
   <td>
    <p>skill_level.xlsx</p></td>
   <td>
    <p>skill_level.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>10</p></td>
   <td>
    <p>skill_course.xlsx</p></td>
   <td>
    <p>skill_course.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>11</p></td>
   <td>
    <p>certification.xlsx</p></td>
   <td>
    <p>Certification.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>12</p></td>
   <td>
    <p>certification_course.xlsx</p></td>
   <td>
    <p>certification_course.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>13</p></td>
   <td>
    <p>certification_commit.xlsx</p></td>
   <td>
    <p>certification_commit.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>14</p></td>
   <td>
    <p>learning_program.xlsx</p></td>
   <td>
    <p>learning_program.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>15</p></td>
   <td>
    <p>learning_program_course.xls </p></td>
   <td>
    <p>learning_program_course.csv的元数据 </p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>16</p></td>
   <td>
    <p>learning_program_instance.xlsx </p></td>
   <td>
    <p>learning_program_instance.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>17</p></td>
   <td>
    <p>learning_program_instance_course_instance.xlsx </p></td>
   <td>
    <p>learning_program_instance_course_instance.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>18</p></td>
   <td>
    <p>job_aid.xlsx</p></td>
   <td>
    <p>job_aid.csv的元数据</p></td>
   <td>
    <p>每个job_aid迁移后都需要有一个或多个job_aid版本。</p></td>
  </tr>
  <tr>
   <td>
    <p>19</p></td>
   <td>
    <p>Job_aid_version.xlsx</p></td>
   <td>
    <p>job_aid_version.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>20</p></td>
   <td>
    <p>job_aid_course.xlsx</p></td>
   <td>
    <p>job_aid_course.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>21</p></td>
   <td>
    <p>job_aid_skills.xlsx</p></td>
   <td>
    <p>job_aid_skills.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>22</p></td>
   <td>
    <p>enrollments.xlsx</p></td>
   <td>
    <p>enrollments.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>23</p></td>
   <td>
    <p>certification_enrollement.xlsx</p></td>
   <td>
    <p>certification_enrollement.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>24</p></td>
   <td>
    <p>learning_program_enrollment.xlsx</p></td>
   <td>
    <p>learning_program_enrollment.csv的元数据<br><br></p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>25</p></td>
   <td>
    <p>job_aid_enrollment.xlsx</p></td>
   <td>
    <p>job_aid_enrollment.csv的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>26</p></td>
   <td>
    <p>user_course_grade.xlsx</p></td>
   <td>
    <p><br>
      user_course_grade.csv的元数据</p></td>
   <td>
    <p>在.csv文件中提供所需的学习者记录数据（即使这些并非必需数据）。 如果没有此信息，即使对.csv进行了迁移处理，Learning Manager应用程序也可能无法反映任何数据。 sample-csvs.zip文件中包含7个.csv文件，其命名约定同上。</p></td>
  </tr>
 </tbody>
</table>

Learning Manager仅支持UTF 8和32位格式的日期和时间值。 如果您在CSV文件中提及超出范围的日期为2038-07-17T08，则在迁移期间可能会出错:53:21.000Z或1980-04-17T08:13:25.322时。
[sample-csvs.zip](assets/sample-csvs.zip) [csv_specifications.zip](assets/csv-specifications.zip)在导入过程中，您需要了解对CSV文件的以下依赖项：

* module_version.csv依赖于module.csv
* course_instance.csv依赖于course.csv
* course_module.csv依赖于course.csv、module.csv和module_version.csv
* course_instance.csv依赖于course.csv
* session.csv依赖于course.csv和module.csv
* enrollment.csv依赖于course.csv
* user_course_grade.csv依赖于course.csv和module.csv
* skill_course.csv依赖于course.csv
* skill_level.csv依赖于skill.csv
* learning_program_instance.csv依赖于learning_program和learning_program_course.csv
* learning_program_course.csv依赖于learning_program.csv
* learning_program_enrollment.csv依赖于learning_program和learning_program_instance.csv
* learning_program_instance_course_instance.csv依赖于learning_program.csv、learning_program_instance.csv和course_instance.csv
* certification_course.csv依赖于certification.csv和course.csv
* certification_commit.csv依赖于certification.csv和certification_course.csv
* certification_enrollment.csv依赖于certification.csv、certification_course.csv和certification_enrollment.csv

## 迁移过程 {#migrationprocedure}

在开始迁移过程之前，请务必注意以下几点：

* 在任何时间点，一个帐户只能有一个活动的迁移项目。 在任何时间点，每个项目只能有一个活动的Sprint。
* 无法撤消已在迁移进程中的运行。 但是，您可以使用Learning Manager各项功能中的现有删除选项来撤消任何数据或内容迁移。
* 迁移项目一旦开始，就会进入“迁移中”状态。 在迁移期间，除集成管理员角色外，其他任何角色均无法登录Learning Manager。

### 创建FTP和Box帐户 {#creatingftpandboxaccounts}

规划迁移项目非常重要。 建议您将项目拆分为多个Sprint，并清楚地确定要在每个Sprint中迁移的内容。 在每次冲刺后进行一些验证也许是个好主意，以对在该Sprint中迁移的数据有信心，而不是在项目结束时进行一个宏大的验证阶段。 在迁移项目中启动Sprint之前，您需要分别在FTP和Box服务器中上传数据和内容CSV文件。 如果您没有自定义FTP和Box的帐户，则可以创建它们。

**创建FTP帐户**

点击 **[!UICONTROL 请求CSV FTP文件夹]**. 此时会显示弹出对话框，提示您输入电子邮件ID。 浏览联机说明并创建FTP帐户。 创建帐户后，即可在FTP中查看迁移项目和Sprint项目文件夹。

下面显示了FTP的项目文件和文件夹的示例快照，供您参考。

<!--![](assets/exavault-migration-upload-folders.png)-->

**创建Box帐户**

请按照创建FTP文件夹中类似的过程，创建内容上传文件夹。 单击左侧窗格中的“迁移” ，然后在出现的页面底部单击“请求内容上传文件夹” 。

您会收到来自Box的电子邮件，其中包含指向共享文件夹的链接。 如果您没有Box帐户，请单击“注册”并创建帐户。 登录说明将发送到集成管理员电子邮件ID。

**将数据（.csv文件）上传到FTP文件夹或Box文件夹**

创建FTP或Box帐户是创建迁移项目的先决条件。 因此，在此阶段，您可以在Learning Manager应用程序中创建迁移项目和Sprint。  请参阅 **数据和内容迁移过程** 部分，以创建迁移项目。

在FTP或Box帐户中，单击项目文件夹名称，然后单击Sprint名称。 在Sprint文件夹中，您可以上传要迁移的.csv数据文件。 要上传，请单击FTP或Box服务器顶部的“上传文件”按钮，然后删除.csv文件。 上传到FTP后的示例快照如下所示，供您参考。

<!--![](assets/exavault-upload.png)-->

您可以返回到Learning Manager迁移项目，然后单击 **[!UICONTROL 刷新]** 并查看在迁移Sprint中列出的所有.csv数据类型。

**将培训内容上传到内容文件夹**

将现有LMS的培训内容上传到您的Box帐户。 如果您已创建迁移项目和Sprint，则Box帐户将填充迁移项目和Sprint名称。 您可以在同一路径中上传内容。 请参阅 **数据和内容迁移过程** 部分，以创建迁移项目。

可以拖放内容文件，也可以单击 **[!UICONTROL 上传]** 然后从桌面选择文件。 如果内容的文件大小很大，则上传文件时可能会遇到一些时间滞后。 根据文件的大小，将文件上传到Box帐户所用的时间会有所不同。

上传内容后Box帐户的示例快照如下所示，仅供参考：

![](assets/box-account.png)

*Box帐户中的文件*

将文件上传到Box帐户后，请确保在module_version.csv文件中提及此Box内容文件的相对路径。 这是指明模块内容路径的必要步骤。

登录FTP和Box服务器并上传内容后，CSV位置即会显示在Learning Manager的以下快照中。

![](assets/after-setup.jpg)

*Box帐户中的CSV位置*

## 数据和内容迁移过程 {#dataandcontentmigrationprocedure}

将企业LMS数据和内容迁移到Learning Manager的过程说明如下：

在开始迁移之前，请先了解迁移过程的先决条件。 请参阅 [CSV规范和示例CSV](migration-manual.md#main-pars_header_140933605) 部分，并为数据和内容迁移准备CSV。

1. 以集成管理员身份登录Learning Manager应用程序，然后单击 **[!UICONTROL 迁移]** 在左侧窗格中。

   此时会显示“迁移项目”主页。 如果您的组织已创建迁移项目，则可以在此页面中查看所有迁移项目的列表。

1. 点击 **[!UICONTROL 新]** ，以创建迁移项目。 或者，您可以单击 **[!UICONTROL 创建迁移项目]** 页面上用于创建迁移项目的链接。 此时会显示“创建迁移项目”页面。

   如果尚未创建FTP文件夹，系统将提示您在该帐户中创建一个FTP文件夹。 在创建迁移项目之前，必须先完成此步骤。

   ![](assets/create-project.png)
   *创建FTP文件夹*

   提供迁移项目的项目名称、项目标记、课程目录和描述。 点击 **[!UICONTROL 创建]**.

   迁移数据项将通过此迁移项目标记进行标识。 如果没有特定的课程目录，请从下拉列表中选择默认目录。 您使用迁移项目迁移的所有课程均包含在您此时选择的目录中。 如果不选择任何目录，则迁移的所有课程均会包含在默认目录中。

1. 此时会显示Sprint配置页面，如下面的快照所示。 您需要将Sprint创建为迁移项目的一部分。 选择Sprint名称并提供Sprint的简要说明。 如果您要在此Sprint中迁移内容，可选择是。 点击 **[!UICONTROL 下一个]**.

   ![](assets/users-modified-sprint.png)
   *Sprint迁移*

   选中带有标题的复选框 **自上次运行以来已添加或修改用户**，将用户列表与Learning Manager应用程序同步。 如果要将内容和数据迁移到Learning Manager应用程序，则可能无需此操作。 但是，如果先前的Sprint迁移与最新的Sprint迁移之间存在时间差，则最佳实践是选择同步用户列表。 此步骤可使Learning Manager数据库与您的LMS用户保持同步。

   建议在迁移enrollment.csv和user_course_grade.csv时执行此同步步骤。 此步骤可使Learning Manager数据库与迁移数据库保持同步，并确保所有通过Sprint迁移其记录的用户在迁移数据库中处于可用状态。

1. 您可以使用上传的数据和内容开始进行Sprint迁移。 点击 **[!UICONTROL 刷新]** “Sprint运行”之前的链接，以便将FTP和内容文件夹与Learning Manager应用程序同步。

   ![](assets/sprint1-filesupload.png)
   *开始Sprint迁移*

   点击 **[!UICONTROL 开始]** 在页面的右上角。 您可以单击 **[!UICONTROL 停止]** 在Sprint迁移过程中的任何时间点，中止Sprint迁移。

   迁移状态会显示在每个Sprint数据项和内容上。 在迁移Sprint运行过程中，检查迁移的成功项和失败项数。

   如果要上传模块内容，请确保在module_version.csv中提供了内容文件夹的路径。 如果不执行此步骤，则在迁移期间可能会出错。 例如，如果要上传自学模块内容（例如视频），则需要在module_version.csv中指定Box URL的相对路径。 对于活动模块内容，您可以指定URL名称。

   下面提供了进度对话框的示例快照，供您参考。 如快照所示，您可以查看每个迁移数据项的已处理记录数以及成功和失败项状态。 单击失败项对应的“下载错误记录”即可下载并查看错误日志。 您可以修复CSV中的问题并再次通过FTP上传。

   ![](assets/sample-sprint-progress-status.png)
   *查看Sprint进度*

   如果要查看迁移项目的所有Sprint列表，请单击左侧窗格中的Sprint列表。 您可以查看所有Sprint的列表、每个Sprint执行的运行数、开始日期、持续时间和完成状态，如下面的示例快照所示。

   ![](assets/sprint-list.png)
   *查看Sprint列表*

1. 上传最新的更新CSV后，您可以单击页面右上角的“重新运行” 。 重新运行会再次处理所有数据项，并忽略没有任何更改的项。 在Sprint中完成数据项的迁移后，可以单击页面顶部的按钮，将Spring迁移标记为完成。 稍后可以使用更多数据项启动新的Sprint。 将Sprint标记为完成之后，您将无法再次重新运行它。 同样，在迁移项目中，您可以有任意数量的Sprint。 如果对所有Sprint的迁移状态感到满意，则可以通过单击 **将项目标记为完成** “Sprint列表”页面上的链接。

   在将迁移项目标记为“完成”之前，您必须确保该项目的所有Sprint均已完成。 在将迁移项目标记为“完成”后，您将无法返回该项目并在其中创建任何Sprint，也无法对该项目进行任何修改。 您必须创建另一个迁移项目，并向其中添加Sprint。

## 迁移验证 {#registration}

在迁移公司旧版LMS中的学习数据和内容后，您可以使用各种学习对象功能验证导入的数据和内容。 例如，您可以管理员身份登录Learning Manager应用程序，并验证导入的模块和课程数据及内容是否可用。

## 迁移改造 {#retrofittinginmigration}

通过此集成功能，您可以将旧版学习管理系统中的学习对象的历史数据更新为在Learning Manager中创建的活动课程。

在下面找到标准CSV规范，您可将其用于与现有LMS迁移数据进行映射。 单击csv-specifications和sample-csv以下载zip文件。 下载的csv-specifications.zip包含四个Excel工作表文件。 这些Excel工作表文件是带有说明的规范，可帮助您了解如何填写.csv文件。 相应的.csv文件应包含每个字段的数据，其格式应符合这些.xlsx文件中的说明。

1-enrollment.xlsx — 包含retrofit_enrollment.csv文件所需的元数据的说明。

2-certification_enrollment.xlsx — 包含retrofit_certification_enrollment.csv文件所需元数据的说明。

3-learning_program_enrollment.xlsx — 包含retrofit_learning_program_enrollment.csv文件所需的元数据说明。

4-user_course_grades.xlsx — 包含retrofit_user_course_grades.csv文件所需的元数据说明。
[csv-specifications.zip](assets/csv-specifications.zip)

## 迁移问题疑难解答 {#troubleshootingmigrationissues}

[单击此处](../../kb/troubleshooting-migration.md) 了解集成管理员在将数据和内容从现有LMS迁移到Learning Manager应用程序时所面临的问题的解决方法/解决方案。

## 用户管理提示 {#usermanagement}

在本主题中，您可以找到一些提示，以了解如何在Learning Manager中考虑和管理用户。 这些概念有助于您在使用Learning Manager的CSV导入、连接器和迁移功能的同时更好地管理用户。

## Learning Manager Id {#captivateprimeids}

Learning Manager为用户提供了两种类型的唯一ID：

* 电子邮件ID
* UUID（通用唯一Id）

Learning Manager支持UUID，从而让组织可以灵活地控制用户帐户。 作为管理员，如果您拥有帐户中用户的UUID，则可以修改该帐户用户的电子邮件ID。

**组织中UUID的使用场景**

考虑员工A加入名为Learning Manager的公司作为承包商的情况。 在合同期内，Learning Manager公司不得将A@example.com作为公司电子邮件ID提供，而只能考虑员工的个人电子邮件帐户，例如A@gmail.com。 在合同期结束6个月后，如果同一名员工A加入Learning Manager成为全职员工，则Learning Manager可能希望将他的电子邮件ID更改为公司电子邮件ID：A@example.com。

在上述场景中，拥有UUID访问权限对于公司Learning Manager非常有益。 Learning Manager公司可轻松将员工A的个人电子邮件ID替换为官方电子邮件ID。 员工与此帐户相关的记录不受此更改的影响。

## 单用户识别 {#singleuseridentification}

Learning Manager可识别并记住如何添加单个用户，例如，使用自助注册、使用CSV上传或使用用户界面或API添加单个用户。

* 如果使用用户界面(UI)或通过API添加单个用户，则可以使用UI或通过API删除此类单个用户。
* 您可以使用CSV上传流程更新单个用户，但需要记住，这些单个用户将被视为CSV用户，并且CSV工作流程适用于此类用户。

## 分配经理角色 {#assigningmanagerrole}

您不能直接为Learning Manager中的任何用户分配经理角色。 只有在该帐户中将任何用户（例如， Y ）的经理属性设置为X时，用户X才能成为Learning Manager经理。

在假设X是用户的经理（如A、B和C）的情况下，如果X离开组织，则需要确保A、B和C的“经理”属性设置为新的经理。 或者，也可以暂时将这些用户的Manager属性设置为ROOT，并在以后使用新的Manager名称进行分配。

有关此主题的更多信息，请参阅以下帮助内容：

* [CSV上传常见问题解答](/help/migrated/administrators/add-users-in-bulk.md)
* [有关添加用户的功能帮助](/help/migrated/administrators/feature-summary/add-users-user-groups.md)

