---
jcr-language: en_us
title: 无法在Learning Manager中搜索课程
description: 学习者无法在Learning Manager中搜索课程。
contentowner: nluke
source-git-commit: 8b29ac996962e7ce8fbda51f3421c9a5f248fcf6
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---



# 无法在Learning Manager中搜索课程

## 问题

学习者无法在Learning Manager中搜索课程。

## 场景1：注册更高级的学习对象

### 摘要

有时会出现这样的情况，学习者搜索课程，但系统并未列出相应课程。 但是，如果学习者已注册学习计划/认证，则可以在“学习对象”中查看课程。

### 为什么会发生这种情况？

在Learning Manager中，当学习者注册学习计划/认证时，即代表注册了学习计划/认证。

因此，学习者无法在其下搜索独立课程 **我的学习**.

但是，学习者无法查看“学习计划/认证”中的课程。

## 场景2：学习者无权访问包含课程的目录。

### 摘要

学习者无法在“目录”或“学习信息板”中搜索课程。

### 为什么会发生这种情况？

在以下情况下会出现此问题：

* 学习者不在包含该课程的目录之中 **或者**
* 该课程不在学习者有权访问的目录之中。

### 分辨率

1. 以管理员身份登录。

1. 点击 **[!UICONTROL 目录]** 并浏览到包含该课程的目录。
1. 点击 **[!UICONTROL 内部共享]** 或 **[!UICONTROL 内容]** （具体取决于上述场景）。

   ![](assets/cp-share-internally.png)

   *内部共享目录*

1. 查看以下场景：

   * 学习者不在目录之中

     要共享目录，请单击 **[!UICONTROL 添加]**，并添加用户所属的用户组。 点击 **[!UICONTROL 保存]**.

     ![](assets/cp-add-user-group.png)

     *添加用户组*

   * 课程不在目录之中

     在“内容”部分，单击 **[!UICONTROL 添加内容]** 然后选择要添加到目录的课程。

     ![](assets/cp-add-content.png)

     *将内容添加到课程*
