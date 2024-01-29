---
jcr-language: en_us
title: 将AdobeLearning Manager与AEM集成
description: 了解如何将AdobeLearning Manager与Adobe Experience Manager (AEM)集成
contentowner: saghosh
source-git-commit: 0052ccb2f5a8f9617bca2c7bad91c0cd18338b66
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 0%

---



# 将Learning Manager与AEM集成

## 概述 {#overview}

Learning Manager是学习管理系统，具有内置的学习内容管理系统。 用户通过将学习内容上传至Learning Manager来管理其学习内容，以便Learning Manager执行版本控制、课程分配、定义学习者可见性、跟踪使用情况并向管理员报告。

但是，有些用户在资产管理系统上存储和管理其内容。 然后，该内容被重新用于各种其他功能。

学习者应用程序中的各种条带可以嵌入在AEM站点中。 任何登录AEM站点的学习者都可以在这些条图中查看其特定培训数据。

## 下载内容包 {#downloadthecontentpackage}

安装程序以AEM内容包的形式提供。 [***下载包***](https://github.com/adobe/captivate-prime-aem-components/releases).

内容包可以为压缩文件，且与AEM 6.4和AEM 6.5兼容。

## 安装Learning Manager组件 {#installcaptivateprimecomponent}

使用AEM Package Manager安装Learning Manager内容包：

>[!NOTE]
>
>有关安装包的信息，请参阅  [***如何使用包***](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=en#how-to-work-with-packages).

1. 以AEM Author的身份打开AEM Package Manager。

1. 单击按钮 **上传包**.

1. 点击 **[!UICONTROL 浏览]** 并上传内容包。
1. 点击 **[!UICONTROL 上传]**.
1. 上传包后，选择内容包并单击 **[!UICONTROL 安装]**.

   ![](assets/install-package.jpg)

## 生成刷新令牌 {#generatetherefreshtoken}

AEM管理员需要从Learning Manager帐户获取刷新令牌。 Learning Manager集成管理员将生成刷新令牌。

1. 批准AEM Sites特色应用程序。

   点击 **[!UICONTROL 应用程序]** > **[!UICONTROL 特色应用程序]** > **[!UICONTROL Adobe Experience Manager — 站点]**.

   ![](assets/launch-aem.jpg)

1. 点击 **[!UICONTROL 应用程序]** > **[!UICONTROL 特色应用程序]**，并打开AEM站点应用程序。

   复制应用程序ID和描述。

1. 点击 **[!UICONTROL 开发人员资源]** > **[!UICONTROL 访问令牌]**.

   ![](assets/click-tokens.jpg)

1. 输入以下详细信息：

   * 客户端ID，即应用程序ID。
   * 客户端密钥，它出现在“描述”中。

1. 获取OAuth代码。 必须在重定向URI中使用v2 API。
1. 点击 **[!UICONTROL 提交]** 并获取刷新令牌。

## 在AEM中配置小组件 {#configurethewidgetinaem}

对于小组件配置，AEM作者仅需要Learning Manager集成管理员提供的刷新令牌。

您还可以在多个页面中设置多个帐户配置。

1. 点击 **[!UICONTROL 工具]** > **[!UICONTROL Cloud Service]** > **[!UICONTROL CaptivateLearning Manager小组件配置]**.
1. 点击 **[!UICONTROL 创建]**.
1. 在此处输入刷新令牌。 设置其他设置。
1. 对于欧盟地区，主机名应更改为“learningmanagereu”。
1. 保存并关闭配置。
1. 选择一个配置并发布该配置。

## AEM作者 {#aemauthor}

AEM作者必须首先在AEM模板中添加组件

随后AEM作者就可以拖放AdobeLearning Manager组件并进行相应配置。

Learning Manager组件要求在上一步中创建的配置映射到该页面。  作者可以在“页面”下方编辑页面属性以映射配置 **[!UICONTROL 高级]** > **[!UICONTROL 配置]** > **[!UICONTROL 云配置]** 并提供配置路径。 通过这种方式，作者可以为多个Learning Manager帐户创建配置，并将每个帐户映射到不同的站点页面。 如果配置未映射到页面，则组件将以递归方式从主页读取配置，直到找到配置。

## 学习者 {#learner}

学习者可以从页面内参加课程。

为能够访问Learning Manager小组件，学习者应为已登录的AEM用户。 此外，属性 **email** 应位于学习者的rep：User节点的“/profile”节点中。 此电子邮件应与Learning Manager帐户中的电子邮件完全相同。

学习者可以从页面内参加课程。

课程进度也会保存。

提供了以下小组件：

1. 游戏
1. 学习日历
1. 社交小组件
1. 目录小组件
1. 我的学习
1. 基于同伴学习的推荐
1. 管理员创建的Recommendations
1. 根据学习者兴趣推荐

如果没有推荐，该小组件将显示为空白。

## 支持Skyline

Skyline是AEM的云版本。 必须首先从包管理器安装Skyline。 要在AEM中使用Skyline组件，Learning Manager帐户中必须存在用户。 换句话说，用户的电子邮件地址必须存在于帐户中。

## 部署Skyline

有关配置Skyline的步骤，请参见  [GitHub报告](https://github.com/adobe/captivate-prime-aem-components).

## 目录小组件

目录小组件可为用户显示来自特定目录或目录集的培训。 在页面属性的“属性”部分，从列出的选项中选择“目录”。

![](assets/catalog-widget.png)

目录小组件包含以下选项：

* **[!UICONTROL 目录ID]：** 需要显示的培训目录ID（逗号分隔）。
* **[!UICONTROL 排序]：** 培训的排序顺序。 选项有名称、日期、创建日期、注册日期等。
* **[!UICONTROL 学习者状态]：** 返回所有符合以下筛选条件的培训：已注册、已开始、已完成和未注册。 如果排序选项为dateEnrolled、dueDate或dateEnrolled，则不会显示搜索结果。
* **[!UICONTROL 技能名称]：** 用于筛选具体训练的技能。
* **[!UICONTROL 标签名称]：** 用于筛选具体结果的标记。

以下是一些可以自定义的附加组件：

**[!UICONTROL 学习对象类型]：** 根据学习对象的类型进行筛选。 支持的类型包括课程、认证、工作辅助和学习计划。

在AEM中，内容条中卡片的标题最初为空。 在“属性”中，输入widgets.html中的标题名称。

**自定义**

您可以使用widgets.html自定义布局的外观。 您可以更改显示的内容条卡的外观并自定义主题。

在 **[!UICONTROL 常规设置]** 部分，您可以选择内容条卡的主色和副色，并指定用于自定义主题的属性。

```
\{ 
 "globalCssText":"@import url('https://fonts.googleapis.com/css2?family=Grandstander:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');", 
 "fontNames":"Grandstander", 
 "cardLayout":{ 
 "cardLayoutName":"compact", 
 "cardPrimaryColor":"#376BA4", 
 "cardSecondaryColor":"#F98EB0", 
 "startedStateTextColor":"#ffffff", 
 "continueStateTextColor":"#ffffff", 
 "revisitStateTextColor":"#ffffff", 
 "startedStateColor":"#a0a0a0", 
 "continueStateColor":"#f9a122", 
 "revisitedStateColor":"#7fbc64", 
 "textPrimaryColor":"#ffffff", 
 "textSecondaryColor":"#d93f3f", 
 "navIconColor":"#a0a0a0" 
 } 
}
```

### 忽略高阶学习对象注册

如果 **[!UICONTROL 忽略高阶学习对象注册]** 复选框已启用，并且用户直接注册了学习计划或认证，那么在小组件中，该认证或学习计划的课程会呈现给用户。

如果禁用此复选框，则用户尚未直接注册的学习计划或认证中的课程将不会显示。

![](assets/higher-order-lo.png)

然后将该设置应用于小组件。

### 安全性

已添加客户端ID和客户端密钥字段。 此外，刷新令牌将被屏蔽。 在用户创建整个配置后，如果用户再次打开配置进行编辑，或者其他用户打开此配置，则刷新令牌将被屏蔽。
