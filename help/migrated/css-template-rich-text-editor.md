---
jcr-language: en_us
title: 适用于富文本编辑器的CSS模板
description: 适用于富文本编辑器的CSS模板
contentowner: saghosh
preview: true
source-git-commit: 9325abb9cda8c8a019c9d72c1944a8284f38f83e
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---



# 适用于富文本编辑器的CSS模板

## 为什么需要CSS？

富文本由HTML标记组成。 按原样呈现标记将导致浏览器应用默认样式。 这通常与公司的风格指南不符。 需要CSS才能符合准则。

## 默认样式

附加的CSS样式表包含Learning Manager应用的样式。 我们已根据大多数用例对该样式进行调整。 下载附加的CSS文件，并按照您的习惯和构建系统将其导入Web应用程序。 所定义的CSS类的命名空间位于ql-editor类下，不会干扰您现有的样式。

## 自定义样式

默认样式可能无法满足每个人的需求。 可以通过覆盖提供的CSS来完成自定义。 所有样式均作为后代选择器包装在ql-editor下。 使用的类如下：

* **缩进**： li.ql-indent-$number. $number从1到9不等
* **大小**： ql-size-small， ql-size-large， ql-size-huge
* **对齐方式**： ql-align-center、ql-align-justify、ql-align-right
* **颜色**： ql-color-$color。 $color =白色、红色、橙色、黄色、绿色、蓝色、紫色
* **背景**： ql-bg-$color。 $color =黑色、红色、橙色、黄色、绿色、蓝色、紫色
* **html标记**： p， ol， ul， pre， blockquote， h1， h2， h3， h4， h5， h6

[用于自定义的CSS文件。](assets/ql-headless.css)
