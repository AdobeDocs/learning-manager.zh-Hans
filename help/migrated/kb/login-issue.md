---
jcr-language: en_us
title: Adobe Learning Manager 登录问题
description: AdobeLearning Manager中的登录问题
contentowner: nluke
source-git-commit: ec79aa3dd6225cc424721afb50702963c1b125eb
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 87%

---



# Adobe Learning Manager 登录问题

## 问题

无法登录 Adobe Learning Manager。

## 错误

尝试登录 Adobe Learning Manager 时，系统显示以下错误消息：

![](assets/cp-error.png)

*过期会话的错误消息*

## 原因

当用户通过 SSO 登录时，其会创建存储在浏览器中的会话 Cookie。 其还允许用户登录其他应用程序。 大多数 SSO 配置为 24 小时后注销。 用户必须为新会话再次接受身份验证。

在某些情况下，用户会因过期的 SSO Cookie 而无法访问系统。 这些 Cookie 将转发到 Adobe Learning Manager 以进行身份验证。如果用户长时间未关闭浏览器或未注销，会话也不会结束。

AdobeLearning Manager拒绝会导致错误的过期Cookie。

## 解决方法

如果过期 Cookie 遭 Adobe Learning Manager 拒绝，请尝试以下选项：

1. 清除浏览器 Cookie 及缓存。 如需了解详情，请查看此[文档](unable-log-in-learning-manager.md)。

   IDP 管理员也可以定义为在特定设置时间后强制注销。 此步骤将再次验证用户以开始新会话。

还有其他原因可导致此错误，只不过上述的这个原因比较常见。

## 参考链接：

[Microsoft：存留期中的条件访问会话](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)
