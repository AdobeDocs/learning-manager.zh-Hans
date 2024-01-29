---
description: 本文档包含的疑难解答基本技巧可以解决您在安装和使用AdobeLearning Manager桌面应用程序时遇到的一些典型问题。
jcr-language: en_us
title: AdobeLearning Manager桌面应用程序问题故障诊断
contentowner: kuppan
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '1447'
ht-degree: 0%

---



# AdobeLearning Manager桌面应用程序问题故障诊断

本文档包含的疑难解答基本技巧可以解决您在安装和使用AdobeLearning Manager桌面应用程序时遇到的一些典型问题。

## 我无法执行以下操作 {#iamunabletodothefollowing}

+++无法下载Adobe版Learning Manager桌面应用程序

1. 检查Internet连接和防火墙设置。
1. 在社交学习中，单击 **[!UICONTROL 新建帖子]** 创建帖子。 如果您没有板块，请先创建一个板块。
1. 单击以下显示的任何帖子按钮选项，以创建“屏幕截图”、“录制音频”、“录制视频”、“Learning Manager图库”等内容。 系统会将您重定向至AdobeLearning Manager桌面应用程序页面，您可以在该页面中下载适用于桌面的AdobeLearning Manager桌面应用程序。
1. 您需要拥有有效AdobeLearning Manager帐户，且该帐户的社交学习功能已由管理员启用。 您的管理员可能还通过Web浏览器禁用了下载。 有关下载AdobeLearning Manager桌面应用程序的更多信息，请联系您的AdobeLearning Manager管理员。

+++

+++无法安装AdobeLearning Manager桌面应用程序

1. 确保您的系统满足最低系统要求。 请参阅 [AdobeLearning Manager桌面应用程序系统要求](../learners/adobe-learning-manager-app-for-desktop/adobe-learning-manager-desktop-app-system-requirements.md).
1. 清除以前安装的AdobeLearning Manager桌面应用程序。 有关详细信息，请参阅  [如何清理以前的安装](#howtocleanuppreviousinstallationsofadobelearningmanagerdesktopapp) 了解更多信息。
1. 有关安装过程中的错误，请参见 [如何查找应用程序日志](#howtofindapplicationlogs). 请联系您的AdobeLearning Manager桌面应用程序管理员以获取更多帮助。

+++

+++我无法启动AdobeLearning Manager桌面应用程序

1. 确保已下载并安装AdobeLearning Manager桌面应用程序。
1. 在社交学习中，单击 **[!UICONTROL 新建帖子]** （如果您没有板块，则创建一个板块。） 单击以下显示的任何一个帖子按钮选项 — 拍摄屏幕截图、音频录制、视频录制、AdobeLearning Manager图库。 系统会将您重定向至可从中启动AdobeLearning Manager桌面应用程序的页面。
1. 如果应用程序未启动，您也可以从Windows上的“开始”菜单或Mac OS X上的“启动板”启动它。

+++

+++我无法在AdobeLearning Manager桌面应用程序中登录我的帐户

1. 确保已连接到Internet，并且防火墙设置不会阻止AdobeLearning Manager桌面应用程序。
1. 确保您拥有已启用社交学习的有效AdobeLearning Manager学习者帐户。
1. 如果仍无法登录，请退出并重新启动AdobeLearning Manager桌面应用程序，然后重试。
1. 如需更多帮助，请联系您的AdobeLearning Manager管理员。

+++

+++我无法在AdobeLearning Manager桌面应用程序中看到我的网络摄像头/麦克风

1. 确保您的网络摄像头/麦克风已正确插入系统且运行正常。
1. 确保您已安装网络摄像头/麦克风的最新驱动程序。 如果没有专用驱动程序，某些设备将无法正常运行。
1. 重置应用程序首选项，然后重新启动AdobeLearning Manager桌面应用程序并重试。 有关详细信息，请参阅 [如何重置应用程序首选项](#howtoresetapplicationpreferences).
1. 如果您使用的是Mac OS X Mojave 10.14，请授予AdobeLearning Manager桌面应用程序访问网络摄像头/麦克风的权限。 有关详细信息，请参阅 [如何在OSX Mojave上设置网络摄像头/麦克风权限](#howtosetwebcammicrophonepermissionsonMacOSXMojave).

+++

+++我无法从AdobeLearning Manager桌面应用程序发布帖子

1. 确保您拥有已由AdobeLearning Manager管理员启用社交学习的有效AdobeLearning Manager学习者帐户。
1. 重置应用程序首选项，然后重新启动AdobeLearning Manager桌面应用程序并重试。 有关更多信息，请参阅 [如何重置应用程序首选项](#howtoresetapplicationpreferences).
1. 对于发布时出现的错误，请启用高级日志记录。 有关详细信息，请参阅 [如何启用高级日志记录](#howtoenableadvancedlogging)，重新启动AdobeLearning Manager桌面应用程序，并重复上述导致错误的步骤。 将最新的应用程序日志发送给AdobeLearning Manager管理员以获取帮助。 有关详细信息，请参阅 [如何查找应用程序日志](#howtofindapplicationlogs).

+++

+++我无法查看或打开我的旧项目

1. 您只能在创建项目的计算机查看使用AdobeLearning Manager帐户创建的项目。
1. 重置应用程序首选项，然后重新启动AdobeLearning Manager桌面应用程序并重试。 有关帮助，请参阅 [如何重置应用程序首选项](#howtoresetapplicationpreferences).
1. 对于打开项目时出现的错误，请启用高级日志记录。 有关详细信息，请参阅 [如何启用高级日志记录](#howtoenableadvancedlogging). 重新启动AdobeLearning Manager桌面应用程序，并重复导致错误的步骤。 将最新的应用程序日志发送给AdobeLearning Manager管理员以获取帮助。 有关详细信息，请参阅 [如何查找应用程序日志](#howtofindapplicationlogs).

+++

## 如何重置应用程序首选项？ {#howtoresetapplicationpreferences}

### Windows {#windows}

1. 要打开“运行”对话框，请按 **Windows + R** 钥匙。
1. 类型 `**%APPDATA%\\..\\Local\\Adobe\\Learning Manager 1.0**` 并按Enter键。
1. 删除名为的文件 **preferences.json** 和 **preferences.xml**.

### MAC OS X {#macosx}

1. 打开Finder。
1. 要打开 **转到“ ”** 文件夹对话框，请按 **Cmd + Shift + G** 钥匙。
1. 类型 `**~/Library/Application Support/Adobe/Learning Manager 1.0**` 并按Enter键。
1. 删除名为的文件 **preferences.json** 和 **preferences.xml**.

## 如何查找应用程序日志？ {#howtofindapplicationlogs}

### Windows {#application-logs}

1. 要打开“运行”对话框，请按 **Windows + R** 钥匙。
1. 类型 `**%TEMP%\\elthor**` 并按Enter键。
1. 文件夹排序依据 **修改日期** 并打开最近的文件夹。 此文件夹包含最新的应用程序日志。

### MAC OS X {#MacOSX-1}

1. 打开 **Finder**.
1. 要打开 **转到文件夹** 对话框，请按 **Cmd + Shift + G** 钥匙。
1. 类型”**/var/folders**&quot;（不带引号），然后按Enter。
1. 搜索“”**elthor**”并打开文件夹。
1. 按**修改日期**对文件夹进行排序，并打开最近的文件夹。 此文件夹包含最新的应用程序日志。

## 如何启用高级日志记录？ {#howtoenableadvancedlogging}

### Windows {#Windows-1}

1. 要打开“运行”对话框，请按 **Windows键+ R**.****
1. 类型”**%APPDATA%\\.\\Local\\Adobe\\Learning Manager 1.0**&quot;（不带引号），然后按Enter。****
1. 备份文件 **preferences.json**，然后在文本编辑器中打开它。****
1. 搜索密钥 **调试模式** 并将此键的value属性更改为“**true**&quot;（不带引号）。

### MAC OS X {#MacOSX-2}

1. 打开Finder。
1. 要打开 **转到文件夹** 对话，按 **Cmd + Shift + G**.
1. 类型”**~/Library/Application Support/Adobe/Learning Manager 1.0**&quot;（不带引号），然后按Enter。
1. 备份文件 **preferences.json**，然后在文本编辑器中打开它。
1. 搜索密钥 **调试模式** 并将此键的value属性更改为“**true**&quot;（不带引号）

## 如何在Mac OS X Mojave上设置网络摄像头/麦克风权限？ {#howtosetwebcammicrophonepermissionsonmacosxmojave}

1. 点击 **[!UICONTROL 系统首选项]** 图标。
1. 点击 **[!UICONTROL 安全性与隐私]** > **[!UICONTROL 隐私].**
1. 点击 **[!UICONTROL 网络摄像头和麦克风选项]** 并确保已选中AdobeLearning Manager复选框。 如果未看到AdobeLearning Manager选项，请先安装并启动AdobeLearning Manager桌面应用程序。

## 如何清理AdobeLearning Manager桌面应用程序的更新缓存？ {#howtocleanupadobecaptivateprimefordesktopupdatescache}

### Windows {#clean-previous-installation}

1. 要打开“运行”对话框，请按 **Windows键+ R**.
1. 类型 `**%APPDATA%\\..\\Local\\Adobe\\Learning Manager 1.0**` 并按Enter键。
1. 删除名为 **更新**.

### MAC OS X {#MacOSX-3}

1. 打开Finder。
1. 要打开 **转到文件夹** 对话，按 **Cmd + Shift + G**.
1. 类型 `**~/Library/Application Support/Adobe/Learning Manager 1.0**` 并按Enter键。
1. 删除名为 **更新**.

## 如何清理AdobeLearning Manager桌面应用程序的临时文件夹？ {#howtocleanupadobecaptivateprimefordesktoptempfolder}

### Windows {#clean-previous-installation-1}

1. 要打开“运行”对话框，请按 **Windows键+ R**.
1. 类型”**%TEMP%**&quot;（不带引号），然后按Enter。
1. 删除名为“”的文件夹&#x200B;**elthor**”。

### MAC OS X {#MacOSX-4}

1. 打开Finder。
1. 要打开 **转到文件夹** 对话，按 **Cmd + Shift + G** 钥匙。
1. 类型”**/var/folders**&quot;（不带引号），然后按Enter。
1. 搜索“”**elthor**”进行搜索。
1. 删除名为“”的文件夹&#x200B;**elthor**”。

## 如何找到AdobeLearning Manager桌面版项目？ {#howtolocateadobecaptivateprimefordesktopprojects}

### Windows {#Windows-2}

1. 要打开“运行”对话框，请按 **Windows键+ R**.
1. 类型”**~/Documents/MyAdobeLearning Manager项目**&quot;（不带引号），然后按Enter。
1. 您或AdobeLearning Manager管理员可能已更改默认项目文件夹位置。 请联系您的管理员以获取有关查找和清理项目的更多帮助。

### MAC OS X {#MacOSX-5}

1. 打开Finder。
1. 要打开 **转到文件夹** 对话，按 **Cmd + Shift + G** 钥匙。
1. 类型”**~/Documents/MyAdobeLearning Manager项目**&quot;（不带引号），然后按Enter。

   您或AdobeLearning Manager管理员可能已更改默认项目文件夹位置。 请联系您的管理员以获取有关查找和清理项目的更多帮助。

## 如何清除以前安装的AdobeLearning Manager桌面应用程序？ {#howtocleanuppreviousinstallationsofadobelearningmanagerdesktopapp}

### Windows {#Windows-3}

1. 要打开 **运行对话框，**&#x200B;按&#x200B;**Windows键+ R**.
1. 键入regedit并搜索&#39;&#39;**HKEY_LOCAL_MACHINE \\SOFTWARE\\Classes\\Installer\\**&quot;（不带引号）或&quot;**HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData\\S-1-5-18\\Products\\**&quot;（不带引号），然后按Enter。
1. 找到名为“AdobeLearning Manager”的文件夹，然后找到以前安装的应用程序。 删除注册表项。  按F3键可以找到该键。

### MAC OS X {#MacOSX-6}

从以下路径&#39;&#39;移动文件&#x200B;**/Applications/AdobeLearning Manager/Users/Shared/Adobe/Learning Manager Assets/1.0**”扔垃圾，然后清空垃圾。
