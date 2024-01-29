---
jcr-language: en_us
title: Learning Manager中的登录问题
description: AdobeLearning Manager中的登录问题
contentowner: nluke
source-git-commit: ec79aa3dd6225cc424721afb50702963c1b125eb
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---



# Learning Manager中的登录问题

## 问题

无法登录AdobeLearning Manager。

## 错误

尝试登录AdobeLearning Manager时，系统显示以下错误消息：

![](assets/cp-error.png)

*过期会话的错误消息*

## 原因

当用户通过SSO登录时，它会创建一个存储在浏览器中的会话Cookie。 用户还可以通过它登录到其他应用程序。 大多数SSO配置为24小时后注销。 用户必须为新会话再次进行身份验证。

在某些情况下，用户因过期的SSO Cookie无法访问系统。 这些Cookie将转发到AdobeLearning Manager以进行身份验证。 如果用户长时间未关闭浏览器或未注销，会话也不会结束。

AdobeLearning Manager拒绝会导致错误的过期Cookie。

## 分辨率

如果AdobeLearning Manager拒绝过期Cookie，请尝试以下选项：

1. 清除浏览器Cookie和缓存。 有关更多信息，请参阅此文档 [文档](unable-log-in-learning-manager.md).

   或者，IDP管理员可以定义为在特定设置时间后强制注销。 此步骤将再次验证用户以开始新会话。

还有其他原因可导致此错误，但上述一个原因比较常见。

## 参考链接：

[Microsoft：存留期中的条件访问会话](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)
