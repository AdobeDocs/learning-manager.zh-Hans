---
description: 了解学习者提前关闭浏览器时，Go1完成Webhook如何帮助Adobe Learning Manager捕捉课程完成情况
jcr-language: en_us
title: 使用Webhook进行Go1完成跟踪
exl-id: 25c9c401-905f-4408-89ac-ac630a45a0c7
source-git-commit: aaea92d190b8ab22ce9f08c309faf5caa0b58a69
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%
---

# 使用Webhook进行Go1完成跟踪

## 概述

Adobe Learning Manager现在支持基于Webhook的Go1内容完成跟踪。 此增强功能可提高Go1和Learning Manager之间课程完成同步的可靠性。 即使学习者在完成课程后立即退出课程播放器，也会捕获完成事件。

当学习者完成Go1课程时，Go1使用Webhook将课程完成通知发送给Learning Manager。 Learning Manager会独立于学习者的浏览器会话接收和处理这些完成事件。

Go1也会重试Webhook交付，直至Learning Manager确认收到完成事件。 这有助于防止学习记录缺失或不完整。

## 此增强功能解决的问题

以前，完成跟踪是依赖Go1播放器和Learning Manager之间的通信，而学习者的浏览器会话仍处于活动状态。 如果学习者在完成状态完全处理之前关闭浏览器窗口或导航离开，则完成记录可能会丢失。

因此：

* 课程完成情况可能不会出现在学习者成绩单中。
* 管理员可以发现实际完成数与记录完成数之间的差异。
* 无法自动恢复缺失的完成事件。

## 事件工作流

1. 学习者启动并完成Go1课程。
1. Go1记录完成。
1. Go1将完成Webhook发送至Learning Manager。
1. Learning Manager会验证并接受完成事件。
1. Learning Manager会更新学习者的完成状态。
1. 如果Learning Manager未确认事件，则Go1会自动重试发送。

## 常见问题解答

**此更改是否需要管理员配置**

不，此更改不需要任何管理员配置。

**现有Go1课程是否受到影响**

不，现有的Go1课程不受影响。 增强功能改进了Go1内容的完成同步。

**如果学习者提早关闭浏览器会发生什么**

Go1独立于学习者的浏览器会话发送完成Webhook。 即使学习者退出课程播放器，Go1也会不断重试交付，直至Learning Manager确认完成事件。
