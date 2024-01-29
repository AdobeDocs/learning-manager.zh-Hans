---
description: 本文档包含的疑难解答基本技巧可以解决您在将数据和内容从现有LMS迁移到Learning Manager时可能遇到的一些典型问题。
jcr-language: en_us
title: 迁移问题疑难解答
contentowner: jayakarr
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 0%

---



# 迁移问题疑难解答

本文档包含的疑难解答基本技巧可以解决您在将数据和内容从现有LMS迁移到Learning Manager时可能遇到的一些典型问题。

## 一般迁移问题 {#genericmigrationissues}

### 无法登录到FTP文件夹或内容文件夹 {#unabletologintoftpfolderorcontentfolder}

确保已在FTP和Box服务中创建您的帐户。 创建迁移项目时，您需要设置这两个服务。 创建服务后，您会收到来自Exavault和Box的电子邮件，提示您重置或设置密码。 如果不记得密码，可通过访问Exavault和Box网站重置密码。

### 单击“刷新”按钮后，仍未显示作业 {#jobsarenotreflectedevenafterclickingrefreshbutton}

* 确保将CSV文件上传到Exavault FTP中的正确文件夹。 路径结构应如下所示：

`code Account>Project>Sprint location`

* 确保CSV文件的文件名符合CSV规范名称：

   * course.csv
   * course_instance.csv
   * course_module.csv
   * enrollment.csv
   * module.csv
   * module_version.csv
   * user_course_grade.csv

### 作业显示失败和错误记录 {#failuresareshownforjobswitherrorrecords}

1. 单击以下载错误日志 **下载错误记录** 链接
1. 根据报告的错误更正原始CSV，然后
1. 使用修改后的CSV重新运行Sprint。

当更改数量小于记录总数时，最好在一个新的Sprint中运行修改后的CSV。

### 即使在停止Sprint迁移后，也无法登录Learning Manager应用程序 {#unabletologintocaptivateprimeapplicationevenafterstoppingthesprintmigration}

Sprint停止运行或完成运行后，可能需要10-15分钟解锁帐户。 请在15分钟后尝试访问该应用程序。

### 即使在触发“停止”后，某些迁移作业也会显示“正在进行”状态。 {#someofthemigrationjobsdisplayinprogressstatusevenafterstopistriggered}

当所有作业处于“进行中”状态时，可能需要10-15分钟才能停止执行。 请在10分钟后重新检查状态。

### 无法创建Sprint，因为该按钮已禁用 {#unabletocreateasprintasthebuttonisdisabled}

在创建Sprint之前，请确保将当前Sprint标记为完成。 点击 **[!UICONTROL 将Sprint标记为完成]** ，以完成Sprint迁移。

### 无法将“迁移项目”标记为完成，因为该按钮已禁用 {#unabletomarkamigrationprojectascompleteasthebuttonisdisabled}

在标记迁移项目完成之前，请确保将当前Sprint标记为完成。 点击 **[!UICONTROL 将Sprint标记为完成]** ，以完成Sprint迁移。

## CSV问题 {#csvissues}

### module_version.csv文件迁移失败且内容尚未迁移 {#moduleversioncsvfilemigrationisfailingandcontentisnotmigratedyet}

确保内容在内容文件夹（指定迁移项目、Sprint路径下的Box帐户）中可用。 此外，确保已选择该选项 **是** 为了 **是否会迁移此Sprint的内容？** Sprint创建页面中的问题。

如果忘记选择 **是**，并在此Sprint中继续操作，则必须等到完成此Sprint后，才能进行操作。 创建另一个Sprint并确保单击 **[!UICONTROL 是]**.

### enrollment.csv或user_course_grade.csv记录会失败，并显示错误消息：“Not a valid Learning Manager ID” {#enrollmentcsvorusercoursegradecsvrecordsfailwithanerrormessagenotavalidprimeid}

确保作为用户ID、assignedByUserID字段的一部分提供的电子邮件ID属于有效的Learning Manager用户。 否则，请添加用户，并使用创建新的Sprint **同步用户** 已选择选项。 如果用户不属于组织，请使用“添加用户CSV”规范，在Learning Manager中将该用户添加为已删除用户。 以下是添加已删除用户的示例CSV规范，仅供参考。

[Users.csv](assets/users.zip) 请参阅 **CSV规范和示例CSV** 第节内容 [迁移手册](../integration-admin/feature-summary/migration-manual.md) 下载一整套的CSV规范和示例CSV文件。

### 已迁移课程的课程显示为空白或播放的模块不正确 {#coursesappearblankorincorrectmodulesplayforamigratedcourse}

确保 **moduleOrderInCourse** 课程的键值以 **0** 并且是连续的。 courseModuleType的顺序应为PRETEST、TESTOUT、CONTENT

此外，请确保两个版本的“活动”、“教室”和“虚拟教室”未与现有课程关联。

### 收到一则消息：“模块已与现有课程关联” {#receivingamessageasmoduleisalreadylinkedwithanexistingcourse}

Learning Manager不允许将活动/虚拟教室/教室模块链接到多个课程。 确保模块未与任何其他课程链接。

### 即使课程与不同的模块版本关联，所有课程仍会显示最新版本的活动/虚拟教室/教室模块 {#allthecoursesshowthelatestversionofactivityvcclassroommoduleseventhoughthecoursesarelinkedwithdifferentmoduleversions}

Learning Manager不支持对活动、教室和虚拟教室模块进行版本控制。 如果您通过moduleVersion.csv文件提供版本，则会更新现有文件，而不是创建新版本。

### 已迁移的活动/虚拟教室/教室模块未显示所需的持续时间 {#desireddurationdoesnotappearforamigratedactivityvcclassroommodule}

所需的持续时间不是活动/虚拟教室/教室模块的有效条目。

### 超链接URL无法在Learning Manager中打开 {#hyperlinkurldoesntopenupincaptivateprime}

确保提供的链接已预先修正“http://&#39;”或“https://&#39;”

### moduleVersion迁移失败，出现“找不到文件”错误 {#moduleversionmigrationfailswithfilenotfounderrors}

确保内容文件夹中存在引用的文件且已成功迁移。

### moduleVersion迁移失败，并显示错误消息：“发生内部错误 — 对于模块： x和moduleVersion ： y” {#moduleversionmigrationfailswithanerrormessageasaninternalerrorhasoccurredformodulexandmoduleversiony}

重新运行Sprint以解决该问题。
