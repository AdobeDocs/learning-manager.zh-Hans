---
jcr-language: en_us
title: AdobeLearning Manager中的API弃用
description: 白色标签是一种用您自己的品牌重塑应用程序或服务，并像原创者一样对其进行自定义的做法。 在AdobeLearning Manager中，您可以在移动应用程序上应用白色标签，这样就可以重新品牌化应用程序，并使您的用户可以使用自己的品牌。
contentowner: saghosh
source-git-commit: 7bd9877aa32c78988a5195116d2a0f25ded05c90
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 0%

---


# AdobeLearning Manager移动应用程序中的白色标签

AdobeLearning Manager移动应用程序现在支持白色标签 — 这意味着您现在可以发布自己的品牌推广应用程序。

## 如何开始准备启动贴有白色标签的应用程序

要部署和管理您自己的带白标签的应用程序，请按照以下步骤操作：

1. 准备资源（如初始屏幕图像）和文本，以便同时用于应用程序和app/play store上的描述。

1. 分配技术资源，该资源能够：

* 正在生成推送通知证书文件。
* 签署ALM团队提供的应用程序二进制文件。
* 上传和管理发布过程。 发布过程要求您的应用程序管理员与app/play store团队之间进行通信，以确保您的应用程序符合所有发布准则。 从ALM中，您将收到完全兼容的应用程序二进制文件。

## 概述

白色标签是一种用您自己的品牌重塑应用程序或服务，并像原创者一样对其进行自定义的做法。 在AdobeLearning Manager中，您可以在移动应用程序上应用白色标签，这样就可以重新品牌化应用程序，并使您的用户可以使用自己的品牌。

## 可自定义的内容

可自定义以下各项：

### 字段

<table>

    <tbody>

    <tr>

   <td>

    <p>帐户ID</p></td>

   <td>

    <p>您帐户的ID。 请注意，属于任何其他帐户的学习者将无法访问带白色标签的应用程序。</p></td>

  </tr>

  <tr>

   <td>

    <p>其他帐户ID</p></td>

   <td>

    <p>如果需要，可添加多个帐户（子域）。 将子域添加为用逗号分隔且不含空格的形式。 例如，acc01、acc02、acc03等等。<br> <b>注：</b> 指定子域时需要添加帐户ID。</br> </p></td>

  </tr>

  <tr>

  <td>

  <p>应用程序名称</p></td>

  <td>

  <p>要用于应用程序的名称。</p></td>

  </tr>

  <tr>

  <td>

  <p>应用程序简称</p></td>

  <td>

  <p>如果应用程序名称较长，则为应用程序提供一个显示在设备上的简称。</p></td>

  </tr>

   <tr>

  <td>

  <p>内部应用程序名称</p></td>

  <td>

  <p>操作系统用来标识应用程序的名称。 通常使用的格式为：com.company-name.product-name。</p></td>

  </tr>

  <tr>

  <td>

  <p>内部应用程序名称 — iOS</p></td>

  <td>

  <p>如果用户使用的是iOS，请使用其他方法命名应用程序。 我们建议为iOS和Android使用相同的名称。</p></td>

  </tr>

  <tr>

  <td>

  <p>应用程序图标</p></td>

  <td>

  <p>应用程序图标为png。 此图标将显示在您的应用程序上。 名称的格式为account-id_appIcon.png。</p></td>

  </tr>

  <tr>

  <td>

  <p>应用程序启动屏幕</p></td>

  <td>

  <p>对于应用程序的启动屏幕，请提供图像(png)，当用户启动应用程序时会显示该图像。 名称的格式为account-id_splashIcon.png。</p></td>

  </tr>

  <tr>

  <td>

  <p>客户端ID和客户端密钥</p></td>

  <td>

  <p>您帐户的集成管理员在注册应用程序时提供详细信息。 集成管理员必须使用以下内容： *学习者：读取，学习者：写入为角色*内部应用程序name://redirect作为重定向URL

  </p></td>

  </tr>

  <tr>

  <td>

  <p>账户标志</p></td>

  <td>

  <p>托管您组织的徽标的URL。 提供内容链接作为帐户徽标。 URL需要进行Web编码。</p></td>

  </tr>

  <tr>

  <td>

  <p>应用程序的App store ID (iOS)</p></td>

  <td>

  <p>实施强制更新所需的ID。 应用程序需要知道学习者应被重定向到App Store才能更新应用程序。</p></td>

  </tr>

   <tr>

  <td>

  <p>应用程序的Google play store id (Android)</p></td>

  <td>

  <p>实施强制更新所需的ID。</p></td>

  </tr>

  <tr>

  <td>

  <p>用于深层链接的主机名</p></td>

  <td>

  <p>要托管深层链接，请使用learningmanager。 如果要使用另一个主机名URL作为深层链接，请提供主机的URL。 例如，learningmanager.adobe.com。</p></td>

  </tr>

    </tbody>

</table>


#### 更新站点关联

如果您使用自定义域或learningmanager\*.adobe.com作为主机，则无需执行任何操作。 但是，如果对URL使用自定义解决方案或特定主机名，请添加站点关联文件。

有关更多信息，请参阅以下链接：

- [Android](https://learningmanager.adobe.com/.well-known/assetlinks.json)

- [iOS](https://learningmanager.adobe.com/.well-known/apple-app-site-association)

## 生成推送通知证书

### iOS上的推送通知证书

在iOS应用程序开发中，推送通知证书是由Apple颁发的加密凭据，允许服务器通过Apple的推送通知服务(APN)将推送通知安全地发送到iOS设备。

在将推送通知发送到iOS设备时，该证书可确保您的服务器（或提供商）与Apple的APN之间的安全通信。

Android和iOS都使用Firebase Cloud Messaging (FCM)作为向设备发送推送通知的服务。

### 如何在iOS上生成证书

请按以下步骤操作：

1. 生成或下载 **推送通知证书** 和私钥(.p12)。 欲了解更多信息，请参见 [Apple开发人员文档](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_certificate-based_connection_to_apns).

1. 下载文件后安装p12文件。 使用密码安装在 **钥匙串访问**.

1. 导航至 **我的证书** 并导出证书。 确保选择MIME类型.cer。

1. 在有p12文件和cer文件可用时，请运行以下命令：

```
- openssl pkcs12 -in privatekey.p12 -out myapnappkey.pem -nodes –clcerts

- openssl x509 -in privatekey.cer -inform DER -out myapnsappcert.pem 

- openssl s_client -connect gateway.sandbox.push.apple.com:2195 -cert myapnsappcert.pem -key myapnappkey.pem 
```

如果可以连接到服务器，则已创建的证书有效。 从myapnappkey.pem文件中，复制证书和私钥值。

1. 联系CSM团队，获取添加到AWS上SNS服务的文件。 用户必须在SNS服务中注册推送通知的条目，这将要求他们共享上面生成的证书以进行验证。

>[!NOTE]
>
>对于Android，用户需要提供他们为Android创建的Firebase项目中的服务器密钥，以便在SNS服务中添加条目。


## 将项目添加到Firebase

### Android

[添加项目](https://learn.microsoft.com/en-us/xamarin/android/data-cloud/google-messaging/firebase-cloud-messaging) 在Firebase中，并检索 ***google-services.json*** 文件。

### iOS

[添加项目](https://firebase.google.com/docs/ios/setup) 到Firebase并检索 ***GoogleService-Info.plist*** 文件。

## 生成已签名的二进制文件

### iOS

```
sh""" xcodebuild -exportArchive -archivePath ./mobile-app-embedding-immersive/build/ios/archive/Runner.xcarchive -exportPath "ipa_path/" -exportOptionsPlist ./deviceAppBuildScripts/${ExportFile} 

mv ipa_path/*.ipa "${env.AppName}_signed.ipa" """ 
```

>[!NOTE]
>
>您需要具备XCode 14.2或更高版本才能构建已签名的二进制文件。


## Android

```
sh""" ~/Library/Android/sdk/build-tools/30.0.3/apksigner sign --ks $storeFile --ks-pass "pass:$store\_password" --ks-key-alias $key\_alias --key-pass "pass:$key\_password" --out app-release-signed.apk -v app-release.apk """
```

>[!NOTE]
>
>您需要使用Android sdk生成工具来生成已签名的二进制文件。

**后续操作**

生成二进制文件后，将二进制文件推送到Play Store或App Store中。

## 如何应用更改

将所需的资源和文件发送给CSM团队。 然后，CSM团队将填写 [窗体](https://forms.office.com/r/bJRRaRBvSh) 进行必要的更改并附加所需的资源。 然后，该团队将进行审查并向工程团队通知相关更改。 然后，工程团队将生成生成版本并与CSM团队共享。

CSM团队将与客户共享该构建。

## 无法自定义的内容

- “更新密码”屏幕
- 创建帐户屏幕