---
description: 本文档包含的基本故障诊断技巧可以解决您在将数据和内容从现有 LMS 迁移到 Adobe Learning Manager 的过程中可能会遇到的一些典型问题。
jcr-language: en_us
title: 迁移问题疑难解答
contentowner: jayakarr
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 45%

---



# 迁移问题疑难解答

本文档包含的基本故障诊断技巧可以解决您在将数据和内容从现有 LMS 迁移到 Adobe Learning Manager 的过程中可能会遇到的一些典型问题。

## 常规迁移问题 {#genericmigrationissues}

### 无法登录到 FTP 文件夹或内容文件夹 {#unabletologintoftpfolderorcontentfolder}

确保您已在 FTP 和 Box 服务中创建帐户。当您创建迁移项目时，系统会要求您对这两项服务进行设置。创建服务后，您会收到来自 Exavault 和 Box 的电子邮件，提示您重置或设置密码。如果不记得密码，可通过访问Exavault和Box网站重置密码。

### 单击“刷新”按钮后，仍未显示作业。 {#jobsarenotreflectedevenafterclickingrefreshbutton}

* 确保 CSV 文件被上传到 Exavault FTP 中正确的文件夹。正确的路径结构如下所示：

`code Account>Project>Sprint location`

* 确保 CSV 文件名称符合 CSV 规范名称：

   * course.csv
   * course_instance.csv
   * course_module.csv
   * enrollment.csv
   * module.csv
   * module_version.csv
   * user_course_grade.csv

### 作业显示失败和错误记录 {#failuresareshownforjobswitherrorrecords}

1. 单击&#x200B;**下载错误记录**&#x200B;链接可下载错误日志
1. 根据报告的错误更正原始 CSV，然后
1. 使用修改后的CSV重新运行Sprint。

当更改数量小于记录总数时，最好在一个新的Sprint中运行修改后的CSV。

### 停止 Sprint 迁移后，仍无法登录 Adobe Learning Manager 应用程序 {#unabletologintocaptivateprimeapplicationevenafterstoppingthesprintmigration}

Sprint 停止运行或完成运行后，可能需要 10-15 分钟解锁帐户。请在15分钟后尝试访问该应用程序。

### 即使在触发“停止”后，某些迁移作业也会显示“正在进行”状态。 {#someofthemigrationjobsdisplayinprogressstatusevenafterstopistriggered}

当所有作业处于“进行中”状态时，可能需要10-15分钟才能停止执行。 请在10分钟后重新检查状态。

### 无法创建 Sprint，因为该按钮已禁用 {#unabletocreateasprintasthebuttonisdisabled}

在创建Sprint之前，请确保将当前Sprint标记为完成。 点击 **[!UICONTROL 将Sprint标记为完成]** ，以完成Sprint迁移。

### 无法将“迁移项目”标记为完成，因为该按钮已禁用 {#unabletomarkamigrationprojectascompleteasthebuttonisdisabled}

在标记迁移项目完成之前，请确保将当前Sprint标记为完成。 点击 **[!UICONTROL 将Sprint标记为完成]** ，以完成Sprint迁移。

## CSV问题 {#csvissues}

### module_version.csv 文件迁移失败且内容尚未迁移 {#moduleversioncsvfilemigrationisfailingandcontentisnotmigratedyet}

确保内容在内容文件夹（指定迁移项目、Sprint路径下的Box帐户）中可用。 此外，确保已选择该选项 **是** 为了 **是否会迁移此Sprint的内容？** Sprint创建页面中的问题。

如果您忘了选择&#x200B;**是**，并在此 Sprint 中继续操作，则必须等到完成此 Sprint 后，才能进行选择。创建另一个Sprint并确保单击 **[!UICONTROL 是]**.

### enrollment.csv或user_course_grade.csv记录会失败，并显示错误消息：“Not a valid Learning Manager ID” {#enrollmentcsvorusercoursegradecsvrecordsfailwithanerrormessagenotavalidprimeid}

确保提供的电子邮件 ID 为用户 ID 的一部分，assignedByUserID 字段属于有效的 Adobe Learning Manager 用户。否则，请添加用户，创建新的 Sprint，并选中&#x200B;**同步用户**&#x200B;选项。如果用户不属于组织，请使用“添加用户CSV”规范，在Learning Manager中将该用户添加为已删除用户。 以下是添加已删除用户的示例CSV规范，仅供参考。

[Users.csv](assets/users.zip) 请参阅 **CSV规范和示例CSV** 第节内容 [迁移手册](../integration-admin/feature-summary/migration-manual.md) 下载一整套的CSV规范和示例CSV文件。

### 已迁移课程的课程显示为空白或播放的模块不正确 {#coursesappearblankorincorrectmodulesplayforamigratedcourse}

确保 **moduleOrderInCourse** 课程的键值以 **0** 并且是连续的。 courseModuleType的顺序应为PRETEST、TESTOUT、CONTENT

此外，请确保两个版本的“活动”、“教室”和“虚拟教室”未与现有课程关联。

### 收到一则消息：“模块已与现有课程关联” {#receivingamessageasmoduleisalreadylinkedwithanexistingcourse}

Adobe Learning Manager 不允许将活动/虚拟教室/教室模块与多门课程关联。确保模块未与任何其他课程链接。

### 即使课程与不同模块版本关联，所有课程仍会显示最新版本的活动/虚拟教室/教室模块 {#allthecoursesshowthelatestversionofactivityvcclassroommoduleseventhoughthecoursesarelinkedwithdifferentmoduleversions}

Adobe Learning Manager 不支持对活动、教室和虚拟教室模块进行版本控制。如果您通过moduleVersion.csv文件提供版本，则会更新现有文件，而不是创建新版本。

### 已迁移的活动/虚拟教室/教室模块未显示所需的持续时间 {#desireddurationdoesnotappearforamigratedactivityvcclassroommodule}

所需的持续时间不是活动/虚拟教室/教室模块的有效条目。

### 超链接URL无法在Learning Manager中打开 {#hyperlinkurldoesntopenupincaptivateprime}

确保提供的链接已预先修正“http://&#39;”或“https://&#39;”

### moduleVersion迁移失败，出现“找不到文件”错误 {#moduleversionmigrationfailswithfilenotfounderrors}

确保内容文件夹中存在引用的文件且已成功迁移。

### moduleVersion迁移失败，并显示错误消息：“发生内部错误 — 对于模块： x和moduleVersion ： y” {#moduleversionmigrationfailswithanerrormessageasaninternalerrorhasoccurredformodulexandmoduleversiony}

重新运行Sprint以解决该问题。
