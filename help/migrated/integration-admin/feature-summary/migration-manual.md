---
description: 本参考手册适用于希望将现有LMS迁移到Learning Manager LMS的集成管理员。
jcr-language: en_us
title: 迁移手册
exl-id: bfdd5cd8-dc5c-4de3-8970-6524fed042a8
source-git-commit: 0a5c51c6d56de2c9e2404ba6ddac5a82a62174a5
workflow-type: tm+mt
source-wordcount: '3614'
ht-degree: 72%

---

# 迁移手册

本参考手册适用于希望将现有 LMS 迁移到 Adobe Learning Manager LMS 的集成管理员

<!-- ## Overview {#overview} -->

## 使用场景 {#usagescenario}

大型企业通常都有内部自有或由其他供应商提供的旧版学习管理系统。LMS由企业培训内容和培训数据组成。 企业购买Learning Manager后，可能希望将现有的LMS内容和数据移至Learning Manager，以便您能够利用现代直观的LMS的优势，同时不会丢失任何企业的旧数据。

Adobe Learning Manager 提供了各种必要的工具和规范，可供公司的集成管理员设置并执行相关迁移任务。

即日起，企业管理员可以联系 Adobe 支持团队来访问 Adobe Learning Manager 的迁移功能。要为帐户启用迁移功能，请联系 Adobe Learning Manager 支持团队。

## 迁移过程 {#apidescription}

迁移的先决条件、迁移过程中涉及的关键步骤、迁移Sprint、规范、数据和内容迁移步骤在本部分中介绍如下：

### 先决条件 {#prerequisites}

Adobe Learning Manager 团队希望公司的集成管理员在进行迁移之前先执行以下任务：

* 集成管理员提取现有 LMS 中的数据和内容，并将其转换为 Adobe Learning Manager 定义的文件格式。
* Adobe Learning Manager 不支持在迁移时导入任何用户，并希望公司使用连接器导入用户。Adobe Systems 希望在迁移之前先配置好这些连接器。请参阅 [Learning Manager连接器帮助](connectors.md) 了解更多信息。

Adobe Learning Manager 建议，在将数据和内容迁移到 Adobe Learning Manager 生产环境之前，管理员可以先在试用帐户中测试一下迁移过程。

### 迁移过程中的关键步骤 {#keystepsofmigrationprocess}

将内容和数据从现有LMS迁移到Learning Manager涉及的关键步骤如下：

1. 集成管理员或合作伙伴应对需要迁移的现有 LMS 数据和内容进行评估。
1. 集成管理员应对 Adobe Learning Manager 提供的用于引入数据和内容的工具和规范进行评估。
1. 集成管理员应根据旧版 LMS 的功能编写相应的导出代码或手动从旧版 LMS 导出培训数据和内容。
1. 在导出相关培训数据和内容后，集成管理员应对这些数据和内容进行分析和映射，以符合 Adobe Learning Manager 迁移规范。
1. 集成管理员将使用Learning Manager提供的工具按以下顺序进行迁移：

   1. 将学习者迁移到 Adobe Learning Manager
   1. 将培训内容传输到Learning Manager中
   1. 最后，将培训数据迁移到 Adobe Learning Manager。

公司现在即可在 Adobe Learning Manager LMS 中使用旧版内容了。

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

在 Adobe Learning Manager 中，迁移项目由一个或多个 Sprint 组成。您的帐户可以拥有多个迁移项目。 Adobe Learning Manager 的迁移过程从创建迁移项目开始。

**Sprint**

在 Adobe Learning Manager 迁移过程中，Sprint 用于定义已被选中从现有 LMS 迁移的一组迁移项。迁移项可以是课程模块、学习者记录或一组课程。一个 Sprint 可以包含多个学习数据项。您可以通过每个 Sprint 执行所需的迁移作业。

**Sprint 运行**

“Sprint 运行”是指开始 Sprint 迁移作业的过程。您可以在“Sprint运行”的任何时间点停止“运行”。

**Sprint 重新运行**

您可以在迁移 Sprint 完成后的任何时间点重新执行迁移 Sprint。如果需要在某个 Sprint 项中附加更多数据并将其再次迁移，或者需要更正 CSV 中的错误，便可重新执行或重新运行 Sprint。

**CSV 规范**

Adobe Learning Manager 提供了一套[标准的 CSV 规范](migration-manual.md#main-pars_header_140933605)。最佳做法是，在迁移之前先完整了解这些 CSV 规范。公司的集成管理员可对现有的数据格式进行分析和映射，以便与Learning Manager提供的CSV模板项相匹配。

**迁移项目标签**

Adobe Systems 建议使用一组关键字作为标签，以便在 Adobe Learning Manager 应用程序中轻松识别迁移项目。您可以通过这些标签，在任何时间点在 Adobe Learning Manager 应用程序内部识别您的项目。

**无内容模块**

Adobe Learning Manager 允许上传无内容的模块。Adobe Systems 会将其视为 Adobe Learning Manager 中的无内容模块。如果需要从现有 LMS 迁移某些旧数据而不需要其内容，您可以上传不含任何 URL 引用的 module_version.csv 文件。

## CSV 规范和示例 CSV {#csv}

标准的 CSV 规范如下所示，可用于映射现有的 LMS 迁移数据。单击 csv-specifications 和 sample-csvs 以下载 zip 文件。 下载的csv-specifications.zip包含七个Excel工作表文件。 这些 excel 工作表文件是带有说明的规范，便于您了解 .csv 文件的填写方法。 相应的 .csv 文件中应包含各个字段的数据，而这些数据应符合这些 .xlsx 文件中所述的规定格式。

<table border="1" cellspacing="0" cellpadding="0" width="100%">
 <tbody>
  <tr>
   <th>
    <p><b>序号</b></p></th>
   <th>
    <p><b>文件名</b></p></th>
   <th>
    <p><b>内容描述</b></p></th>
   <th>
    <p>备注</p></th>
  </tr>
  <tr>
   <td>
    <p>1</p></td>
   <td>
    <p>module.xlsx</p></td>
   <td>
    <p>module.csv 的元数据</p></td>
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
    <p>course.csv 的元数据</p></td>
   <td>
    <p>对每个课程提及一个作者姓名，因为许多作者姓名在迁移后的应用程序中有时无法正确显示。 </p></td>
  </tr>
  <tr>
   <td>
    <p>4</p></td>
   <td>
    <p>module_version.xlsx </p></td>
   <td>
    <p>module_version.csv的元数据</p></td>
   <td>
    <p>确保提供用于存放上传内容的 Box 帐户文件夹的 URL 路径。 </p></td>
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
    <p>session.csv 的元数据</p></td>
   <td>
    <p>确保会话 csv 中的每个条目至少与一个“课堂/虚拟课堂”模块相关联</p></td>
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
    <p>skill.csv 的元数据</p></td>
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
    <p>learning_program_instance.csv 的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>17</p></td>
   <td>
    <p>learning_program_instance_course_instance.xlsx </p></td>
   <td>
    <p>learning_program_instance_course_instance.csv 的元数据</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>18</p></td>
   <td>
    <p>job_aid.xlsx</p></td>
   <td>
    <p>job_aid.csv 的元数据</p></td>
   <td>
    <p>所迁移的每个 job_aid 均需拥有一个或多个 job_aid 版本。</p></td>
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
    <p>job_aid_skills.csv 的元数据</p></td>
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
    <p>learning_program_enrollment.csv 的元数据<br><br></p></td>
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
      user_course_grade.csv 的元数据</p></td>
   <td>
    <p>在 .csv 文件中提供所需的学习者记录数据（即使这些并非必需数据）。如果没有此信息，即使对.csv进行了迁移处理，Learning Manager应用程序也可能无法反映任何数据。 sample-csvs.zip文件中包含7个.csv文件，其命名约定同上。</p></td>
  </tr>
 </tbody>
</table>

Adobe Learning Manager 仅支持 UTF 8 和 32 位格式的日期和时间值。如果您在CSV文件中提及超出范围的日期为2038-07-17T08，则在迁移期间可能会出错:53:21.000Z或1980-04-17T08:13:25.322时。

* [sample-csvs.zip](assets/sample-csvs.zip)
* [csv_specifications.zip](assets/csv-specifications.zip)

在导入期间，您需要了解 CSV 文件的以下依赖关系：

* module_version.csv 依赖于 module.csv
* course_instance.csv 依赖于 course.csv
* course_module.csv 依赖于 course.csv、module.csv 和 module_version.csv
* course_instance.csv 依赖于 course.csv
* session.csv 依赖于 course.csv 和 module.csv
* enrollment.csv 依赖于 course.csv
* user_course_grade.csv 依赖于 course.csv 和 module.csv
* skill_course.csv 依赖于 course.csv
* skill_level.csv 依赖于 skill.csv
* learning_program_instance.csv 依赖于 learning_program 和 learning_program_course.csv
* learning_program_course.csv 依赖于 learning_program.csv
* learning_program_enrollment.csv 依赖于 learning_program 和 learning_program_instance.csv
* learning_program_instance_course_instance.csv依赖于learning_program.csv、learning_program_instance.csv和course_instance.csv
* certification_course.csv依赖于certification.csv和course.csv
* certification_commit.csv依赖于certification.csv和certification_course.csv
* certification_enrollment.csv 依赖于 certification.csv、certification_course.csv 和 certification_enrollment.csv

## 迁移程序 {#migrationprocedure}

在开始迁移过程之前，请务必注意以下几点：

* 在任何时间点，每个帐户只能有一个活动的迁移项目。在任何时间点，每个项目只能有一个活动的 Sprint。
* 正在迁移的“运行”无法撤消。然而，您可以使用 Adobe Learning Manager 各项功能中的删除选项来撤消对相关数据或内容的迁移。
* 迁移项目一旦开始，就会进入“迁移中”状态。 在迁移期间，除集成管理员角色之外，其他任何角色均无法登录 Adobe Learning Manager。

### 创建 FTP 和 Box 帐户 {#creatingftpandboxaccounts}

迁移项目规划非常重要。建议将项目分解为多个 Sprint，并明确界定各个 Sprint 中需要迁移的内容。建议在每个 Sprint 完成后，进行一些数据验证，确保该 Sprint 中迁移的数据准确无误，而不要留到整个项目结束时进行一次大规模验证。在开始迁移项目 Sprint 之前，您需要分别向 FTP 和 Box 服务器上传相关的数据和内容 CSV 文件。如果您没有自定义FTP和Box的帐户，则可以创建它们。

<!--**Create FTP account**-->

<!--Click **[!UICONTROL Request for CSV FTP folder]**. A pop-up dialog appears prompting you to enter your e-mail id. Go through online instructions and create an FTP account. As soon as you create your account, you can view your migration project and sprint project folders in FTP. 

A sample snapshot of project files and folder of FTP is shown below for your reference. -->

<!--![](assets/exavault-migration-upload-folders.png)-->

**创建 Box 帐户**

内容上传文件夹的创建与 FTP 文件夹相似，具体如下。单击左侧窗格中的“迁移”，然后在随后显示的页面底部单击“请求内容上传文件夹”。

您会收到 Box 的电子邮件，其中包含指向该共享文件夹的链接。如果没有 Box 帐户，请单击“注册”创建一个。相关登录说明会发送到集成管理员的电子邮件 ID。

**将数据（.csv 文件）上传到 FTP 文件夹或 Box 文件夹**

创建 FTP 或 Box 帐户是创建迁移项目的先决条件。因此，在此阶段，您可以在Learning Manager应用程序中创建迁移项目和Sprint。  请参阅 **数据和内容迁移过程** 部分，以创建迁移项目。

在 FTP 或 Box 帐户中，单击项目文件夹名称，然后单击 Sprint 名称。在 Sprint 文件夹中，您可以上传需要迁移的 .csv 数据文件。要上传，请单击FTP或Box服务器顶部的“上传文件”按钮，然后删除.csv文件。 上传到FTP后的示例快照如下所示，供您参考。

<!--![](assets/exavault-upload.png)-->

您可以返回到Learning Manager迁移项目，然后单击 **[!UICONTROL 刷新]** 并查看在迁移Sprint中列出的所有.csv数据类型。

**将培训内容上传到内容文件夹**

将现有 LMS 中的培训内容上传到 Box 帐户。 如果已创建了“迁移”项目和 Sprint，则 Box 帐户将会填充相应的“迁移”项目和 Sprint 名称。您可以按同一路径上传内容。请参阅 **数据和内容迁移过程** 部分，以创建迁移项目。

您可以拖放内容文件，也可以单击&#x200B;**[!UICONTROL “上传”]**&#x200B;并选择计算机中的文件。如果内容文件过大，在上传时可能会出现一些延迟。 根据文件的大小，将文件上传到Box帐户所用的时间会有所不同。

上传内容后Box帐户的示例快照如下所示，仅供参考：

![](assets/box-account.png)

*Box帐户中的文件*

将文件上传到 Box 帐户后，请确保在 module_version.csv 文件中提供此 Box 内容文件的相对路径。这是指示模块内容路径的必需步骤。

登录 FTP 和 Box 服务器并上传内容后，Adobe Learning Manager 中即会显示相应的 CSV 位置（如以下快照所示）。

![](assets/after-setup.jpg)

*Box帐户中的CSV位置*

## 数据和内容迁移程序 {#dataandcontentmigrationprocedure}

将企业LMS数据和内容迁移到Learning Manager的过程说明如下：

在开始迁移之前，应详细了解迁移过程的先决条件。 请参阅 [CSV规范和示例CSV](migration-manual.md#main-pars_header_140933605) 部分，并为数据和内容迁移准备CSV。

1. 以集成管理员身份登录Learning Manager应用程序，然后单击 **[!UICONTROL 迁移]** 在左侧窗格中。

   此时会显示“迁移项目”主页。 如果公司已经创建了迁移项目，则可以在此页面中查看所有迁移项目的列表。

1. 单击页面右上角的&#x200B;**[!UICONTROL “新建”]**&#x200B;可创建迁移项目。 或者，您也可以单击页面中的&#x200B;**[!UICONTROL “创建迁移项目”]**&#x200B;链接来创建迁移项目。 此时会显示“创建迁移项目”页面。

   如果尚未创建FTP文件夹，系统将提示您在该帐户中创建一个FTP文件夹。 在创建迁移项目之前，必须先完成这一步。

   ![](assets/create-project.png)
   *创建FTP文件夹*

   提供迁移项目的项目名称、项目标签、课程目录和描述。 单击&#x200B;**[!UICONTROL 创建]**。

   迁移数据项将通过此“迁移项目标签”进行识别。 如果没有特定的课程目录，请从下拉列表中选择默认目录。 您使用迁移项目所迁移的所有课程均包含在您此时选择的目录中。如果不选择任何目录，则迁移的所有课程均会包含在默认目录中。

1. 此时会显示 Sprint 配置页面（如以下快照所示）。 您需要为迁移项目创建一个 Sprint。 选择 Sprint 名称并提供简要描述。 如果需要使用此 Sprint 进行内容迁移，则选择“是”。 点击 **[!UICONTROL 下一个]**.

   ![](assets/users-modified-sprint.png)
   *Sprint迁移*

   选中带有标题的复选框 **自上次运行以来已添加或修改用户**，将用户列表与Learning Manager应用程序同步。 如果要向 Adobe Learning Manager 应用程序迁移内容和数据，则可能无需此操作。然而，如果先前迁移的 Sprint 与最新的 Sprint 之间存在时间差，则最好选择同步用户列表。此步骤可使Learning Manager数据库与您的LMS用户保持同步。

   建议在迁移 enrollment.csv 和 user_course_grade.csv 时执行此同步步骤。此步骤可让 Adobe Learning Manager 数据库与您的迁移数据库保持同步，并确保所有通过 Sprint 迁移其记录的用户在迁移数据库中处于可用状态。

1. 您可以对已上传的数据和内容开始 Sprint 迁移了。 点击 **[!UICONTROL 刷新]** “Sprint运行”之前的链接，以便将FTP和内容文件夹与Learning Manager应用程序同步。

   ![](assets/sprint1-filesupload.png)
   *开始Sprint迁移*

   点击 **[!UICONTROL 开始]** 在页面的右上角。 您可以单击 **[!UICONTROL 停止]** 在Sprint迁移过程中的任何时间点，中止Sprint迁移。

   每个 Sprint 数据项和内容均会显示各自的迁移状态。在迁移 Sprint 运行过程中，检查迁移的成功项和失败项数量。

   如果要上传模块内容，请确保在 module_version.csv 中提供相应内容文件夹的路径。 如未执行此步骤，在迁移期间则可能会出错。 例如，如果要上传自学模块内容（例如视频），则需要在 module_version.csv 中指定 Box URL 的相对路径。 对于活动模块内容，可以指定 URL 名称。

   以下是进度对话框示例快照，仅供参考。 如快照所示，您可以查看每个迁移数据项的已处理记录数以及成功和失败项状态。单击失败项对应的“下载错误记录”即可下载和查看错误日志。 您可以修复 CSV 中的问题并再次通过 FTP 上传。

   ![](assets/sample-sprint-progress-status.png)
   *查看Sprint进度*

   如果要查看迁移项目的所有 Sprint 列表，请单击左侧窗格中的 Sprint 列表。您可以查看所有Sprint的列表、每个Sprint执行的运行数、开始日期、持续时间和完成状态，如下面的示例快照所示。

   ![](assets/sprint-list.png)
   *查看Sprint列表*

1. 上传完最新的 CSV 后，您可以单击页面右上角的“重新运行”。“重新运行”会再次处理所有数据项，并忽略未做任何更改的项。如果对 Sprint 的数据项迁移结果感到满意，可单击页面顶部的按钮将该 Sprint 迁移标记为“完成”。 稍后可以对更多数据项执行新的 Sprint。 将 Sprint 标记为“完成”后，则无法“重新运行”。同样，一个迁移项目中可拥有任意数量的 Sprint。 如果对所有Sprint的迁移状态感到满意，则可以通过单击 **将项目标记为完成** “Sprint列表”页面上的链接。

   在将迁移项目标记为“完成”之前，必须确保该项目的所有 Sprint 均已完成。 将迁移项目标记为“完成”后，将无法返回该项目并在其中创建任何 Sprint 或对该项目进行任何修改。您必须另外创建一个迁移项目，然后再向其中添加 Sprint。

## 迁移验证 {#registration}

在对公司旧 LMS 系统的学习数据和内容完成迁移后，您可使用各种学习对象功能对导入的数据和内容进行验证。 例如，您可以管理员身份登录 Adobe Learning Manager 应用程序，然后对导入的模块及课程数据和内容进行可用性验证。

## 在迁移时翻新 {#retrofittinginmigration}

此集成功能可让您将旧版学习管理系统中学习对象的历史数据更新到 Adobe Learning Manager 所创建的活动课程中。

标准的 CSV 规范如下所示，可用于映射现有的 LMS 迁移数据。单击 csv-specifications 和 sample-csvs 以下载 zip 文件。 下载的 csv-specifications.zip 中包含 4 个 Excel 工作表文件。这些 excel 工作表文件是带有说明的规范，便于您了解 .csv 文件的填写方法。 相应的 .csv 文件中应包含各个字段的数据，而这些数据应符合这些 .xlsx 文件中所述的规定格式。

1-enrollment.xlsx 中包含对 retrofit_enrollment.csv 文件所需元数据的描述。

2-certification_enrollment.xlsx 中包含对 retrofit_certification_enrollment.csv 文件所需元数据的描述。

3-learning_program_enrollment.xlsx 中包含对 retrofit_learning_program_enrollment.csv 文件所需元数据的描述。

4-user_course_grades.xlsx — 包含retrofit_user_course_grades.csv文件所需的元数据说明。
[csv-specifications.zip](assets/csv-specifications.zip)

>[!NOTE]
>
>UUID（通用唯一ID）也是迁移csv中的一列。


## 解决迁移问题 {#troubleshootingmigrationissues}

[单击此处](../../kb/troubleshooting-migration.md)了解集成管理员在向 Adobe Learning Manager 应用程序迁移现有 LMS 数据和内容时所遇问题的解决方法/解决方案。

## 用户管理提示 {#usermanagement}

在本主题中，您可以了解有关在 Adobe Learning Manager 中进行用户管理的方法提示。这些概念可帮助您在使用 CSV、连接器和 Adobe Learning Manager 的迁移功能时更好地管理用户。

## Adobe Learning Manager ID {#captivateprimeids}

Adobe Learning Manager 为用户提供两种类型的唯一 ID：

* 电子邮件ID
* UUID（通用唯一 ID）

Adobe Learning Manager 支持 UUID，方便公司对用户帐户进行灵活控制。作为管理员，如果您拥有帐户中用户的UUID，则可以修改该帐户用户的电子邮件ID。

**公司中 UUID 的使用场景**

考虑员工A加入名为Learning Manager的公司作为承包商的情况。 在合同期内，Learning Manager公司不得将A@example.com作为公司电子邮件ID提供，而只能考虑员工的个人电子邮件帐户，例如A@gmail.com。 在合同期结束6个月后，如果同一名员工A加入Learning Manager成为全职员工，则Learning Manager可能希望将他的电子邮件ID更改为公司电子邮件ID：A@example.com。

在上述场景中，拥有UUID访问权限对于公司Learning Manager非常有益。 Learning Manager公司可轻松将员工A的个人电子邮件ID替换为官方电子邮件ID。 与此帐户相关的员工记录则不受此更改的影响。

## 个人用户识别 {#singleuseridentification}

Adobe Learning Manager 会识别并记住个人用户的加入方式，例如：通过自助注册、通过 CSV 上传、或者通过用户界面或 API 添加。

* 如果个人用户是通过用户界面 (UI) 或 API 加入的，您可以通过 UI 或 API 删除此类个人用户。
* 您可以通过 CSV 上传过程进行个人用户更新，但要记住，这些个人用户会被视为 CSV 用户，且 CSV 工作流程适用于此类用户。

## 分配“经理”角色 {#assigningmanagerrole}

您无法在 Adobe Learning Manager 中将“经理”角色直接分配给任何用户。只有在该帐户中将任何用户（例如， Y ）的经理属性设置为X时，用户X才能成为Learning Manager经理。

如果 X 是其他用户（例如 A、B 和 C）的“经理”，则在 X 从公司离职时，您需要确保将 A、B 和 C 的“经理”属性设置为新“经理”。 或者，您也可以暂时将这些用户的“经理”属性设置为“ROOT”，稍后再分配新的“经理”姓名。

有关此主题的更多信息，请参阅以下帮助内容：

* [CSV 上传常见问题解答](/help/migrated/administrators/add-users-in-bulk.md)
* [有关添加用户的功能帮助](/help/migrated/administrators/feature-summary/add-users-user-groups.md)
