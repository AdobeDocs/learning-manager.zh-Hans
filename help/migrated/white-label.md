---
jcr-language: en_us
title: AdobeLearning Manager移动应用程序中的白色标签
description: 白色标签是一种用您自己的品牌重塑应用程序或服务，并像原创者一样对其进行自定义的做法。 在Adobe Learning Manager中，可将白色标签应用于移动应用程序，以便重新品牌化应用程序并使您的用户可使用自己的品牌。
contentowner: saghosh
exl-id: f37c86e6-d4e3-4095-9e9d-7a5cd0d45e43
source-git-commit: 977799953123eafbbaf22732c79be4b8ea2e3e1a
workflow-type: tm+mt
source-wordcount: '1375'
ht-degree: 0%

---

# AdobeLearning Manager移动应用程序中的白色标签

Adobe Learning Manager移动应用程序现在支持白色标签 — 这意味着您现在可以按自己的品牌发布该应用程序。

## 如何开始准备启动贴有白色标签的应用程序

要部署和管理您自己的带白标签的应用程序，请按照以下步骤操作：

1. 准备资源（如初始屏幕图像）和文本，以便同时用于应用程序和app/play store上的描述。

1. 分配技术资源，该资源能够：

   * 正在生成推送通知证书文件。
   * 签署ALM团队提供的应用程序二进制文件。
   * 上传和管理发布过程。 发布过程要求您的应用程序管理员与app/play store团队之间进行通信，以确保您的应用程序符合所有发布准则。 从ALM中，您将收到完全兼容的应用程序二进制文件。

## 概述

白色标签是一种用您自己的品牌重塑应用程序或服务，并像原创者一样对其进行自定义的做法。 在Adobe Learning Manager中，可将白色标签应用于移动应用程序，以便重新品牌化应用程序并使您的用户可使用自己的品牌。

## 可自定义的内容

可自定义以下各项：

### 字段

<table>

 <tbody>

  <tr>

   <td>

    <p>帐户ID</p>

   </td>

   <td>

    <p>您帐户的ID。 请注意，属于任何其他帐户的学习者将无法访问带白色标签的应用程序。</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>其他帐户ID</p>

   </td>

   <td>

    <p>如果需要，可添加多个帐户（子域）。 将子域添加为用逗号分隔且不含空格的形式。 例如，acc01、acc02、acc03等等。<br> <b>注意：</b>指定子域时需要添加帐户ID。</br> </p>

   </td>

  </tr>

  <tr>

   <td>

    <p>应用程序名称</p></td>

   <td>

    <p>要用于应用程序的名称。</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>应用程序简称</p>

   </td>

   <td>

    <p>如果应用程序名称较长，则为应用程序提供一个显示在设备上的简称。</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>内部应用程序名称</p></td>

   <td>

    <p>操作系统用来标识应用程序的名称。 通常使用的格式为：com.company-name.product-name。</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>内部应用程序名称 — iOS</p>

   </td>

   <td>

    <p>如果用户使用的是iOS，请使用其他方法命名应用程序。 我们建议为iOS和Android使用相同的名称。</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>应用程序图标</p>

   </td>

   <td>

    <p>应用程序图标为png。 此图标将显示在您的应用程序上。 名称的格式为account-id_appIcon.png。 应用程序图标的尺寸为512 × 512像素。<div>请注意，Apple不允许在应用程序图标中使用Alpha渠道。 因此，请确保在提交资源之前移除资源中的Alpha渠道。</div></p>

   </td>

  </tr>

  <tr>

   <td>

    <p>应用程序启动屏幕</p></td>

   <td>

    <p>对于应用程序的启动屏幕，请提供图像(png)，当用户启动应用程序时会显示该图像。 名称的格式为account-id_splashIcon.png。 方形初始屏幕的尺寸为1052 × 1052像素，圆形初始屏幕的尺寸为768 x 768像素。</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>客户端ID和客户端密钥</p>

   </td>

   <td>

    <p>您帐户的集成管理员在注册应用程序时提供详细信息。 集成管理员必须使用以下内容：<ul><li>学习者：读取，学习者：写入为角色</li><li>内部应用程序name://redirect作为重定向URL</li></ul></p>

   </td>

  </tr>

  <tr>

   <td>

    <p>账户标志</p>

   </td>

   <td>

    <p>托管您组织的徽标的URL。 提供内容链接作为帐户徽标。 URL需要进行Web编码。</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>应用程序的App store ID (iOS)</p>

   </td>

   <td>

    <p>实施强制更新所需的ID。 应用程序需要知道学习者应被重定向到App Store才能更新应用程序。</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>应用程序的Google play store id (Android)</p>

   </td>

   <td>

    <p>实施强制更新所需的ID。</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>用于深层链接的主机名</p>

   </td>

   <td>

    <p>要托管深层链接，请使用learningmanager。 如果要使用另一个主机名URL作为深层链接，请提供主机的URL。 例如，learningmanager.adobe.com。</p>

   </td>

  </tr>

 </tbody>

</table>

>[!NOTE]
>
>向您的CSAM提供数据，以便他们可以将数据添加到您的自定义应用程序二进制文件中。


#### 更新站点关联以处理自定义深度链接

如果您使用自定义域或learningmanager\*.adobe.com作为主机，则无需执行任何操作。 但是，如果对URL使用自定义解决方案或特定主机名，请添加站点关联文件。

>[!CAUTION]
>
>如果文件不存在，则深度链接将不起作用。 确保文件存在。


有关更多信息，请参阅以下链接：

* [Android](https://learningmanager.adobe.com/.well-known/assetlinks.json)
* [iOS](https://learningmanager.adobe.com/.well-known/apple-app-site-association)

## 生成推送通知

向Android和iOS应用程序发送推送通知需要两种不同的机制。

* 对于iOS，请生成推送通知证书。
* 对于Android，请提供从Firebase项目生成的服务器密钥。

按照以下说明在Firebase中设置项目：

### 在iOS上推送通知

在iOS应用程序开发中，推送通知证书是由Apple颁发的加密凭据，允许服务器通过Apple的推送通知服务(APN)将推送通知安全地发送到iOS设备。

在将推送通知发送到iOS设备时，该证书可确保您的服务器（或提供商）与Apple的APN之间的安全通信。

Android和iOS都使用Firebase Cloud Messaging (FCM)作为向设备发送推送通知的服务。

### 如何在iOS上生成证书

请按以下步骤操作：

1. 生成或下载&#x200B;**推送通知证书**&#x200B;和私钥(.p12)。 有关详细信息，请参阅[Apple开发人员文档](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_certificate-based_connection_to_apns)。

1. 下载文件后安装p12文件。 使用密码安装在&#x200B;**钥匙串访问**&#x200B;中。

1. 导航到&#x200B;**我的证书**&#x200B;并导出证书。 确保选择MIME类型.cer。

1. 在有p12文件和cer文件可用时，请运行以下命令：

```
- openssl pkcs12 -in privatekey.p12 -out myapnappkey.pem -nodes –clcerts

- openssl x509 -in privatekey.cer -inform DER -out myapnsappcert.pem 

- openssl s_client -connect gateway.sandbox.push.apple.com:2195 -cert myapnsappcert.pem -key myapnappkey.pem 
```

如果可以连接到服务器，则已创建的证书有效。 从myapnappkey.pem文件中，复制证书和私钥值。

### 在Android上推送通知

对于Android，用户需要提供来自Firebase项目的services.json文件，以便在SNS服务中添加条目。

在Firebase中创建项目，并将services.json文件共享给CSM团队。 SNS中基于令牌的条目需要此文件。 请注意，不再使用服务器密钥。 请参阅[在Firebase中创建项目](#create-project-in-firebase)。

要下载services.json文件，请执行以下步骤：

1. 登录到&#x200B;**Firebase**&#x200B;控制台。
1. 转到&#x200B;**项目设置**&#x200B;并选择&#x200B;**云消息**。
1. 查找&#x200B;**Firebase Cloud Messaging API**&#x200B;并选择&#x200B;**管理服务帐户**。
1. 在&#x200B;**服务帐户**&#x200B;页面中，选择左侧面板中的&#x200B;**服务帐户**。
1. 查找您的项目条目，然后选择“操作”下的“**管理详细信息**”。

   >[!NOTE]
   >
   >   项目条目格式将为&lt;-accountname->@appspot.gserviceaccount.com。

1. 转到&#x200B;**密钥**&#x200B;选项卡，然后选择&#x200B;**添加密钥**。
1. 如果没有密钥，请选择&#x200B;**创建新密钥**，然后选择&#x200B;**JSON**&#x200B;作为密钥类型。 这将生成并下载JSON文件。
1. 如果已有密钥，请选择&#x200B;**上传现有密钥**，粘贴该密钥，然后上传。 这将生成并下载JSON文件。

<!-- Set up a project in Firebase and share the server key with the CSAM.-->

联系CSM团队并共享JSON文件，以将条目添加到AWS上的SNS服务。 用户必须在SNS服务中注册推送通知的条目，这将要求他们共享上面生成的证书以进行验证。

## 在Firebase中创建项目 {#create-project-in-firebase}

### Android

将您在上述步骤中创建的相同项目重新用于推送通知。

[在Firebase中添加项目](https://learn.microsoft.com/en-us/xamarin/android/data-cloud/google-messaging/firebase-cloud-messaging)并检索&#x200B;***google-services.json***&#x200B;文件。

### iOS

[将项目](https://firebase.google.com/docs/ios/setup)添加到Firebase并检索&#x200B;***GoogleService-Info.plist***&#x200B;文件。

>[!IMPORTANT]
>
>将文件发送到Adobe Learning Manager CSAM团队，以包含在应用程序二进制文件的构建中。


## 生成已签名的二进制文件

### iOS

```
sh""" xcodebuild -exportArchive -archivePath Runner.xcarchive -exportPath "ipa_path/" -exportOptionsPlist {ExportFile} 

mv ipa_path/*.ipa "${env.AppName}_signed.ipa" """ 
```

>[!NOTE]
>
>您需要具备XCode 15.2或更高版本才能构建已签名的二进制文件。


## Android

```
sh""" ~/Library/Android/sdk/build-tools/30.0.3/apksigner sign --ks $storeFile --ks-pass "pass:$store\_password" --ks-key-alias $key\_alias --key-pass "pass:$key\_password" --out app-release-signed.apk -v app-release.apk """
```

>[!NOTE]
>
>您需要使用Android sdk生成工具来生成已签名的二进制文件。

**后续内容**

生成二进制文件后，将二进制文件推送到Play Store或App Store中。

## 如何应用更改

将所需的资源和文件发送给CSM团队。 然后，CSM团队使用所需的更改填写[表单](https://forms.office.com/r/bJRRaRBvSh)并附加所需的资源。 然后，该团队将进行审查并向工程团队通知相关更改。 然后，工程团队将生成生成版本并与CSM团队共享。

CSM团队将与客户共享该构建。

## 无法自定义的内容

* “更新密码”屏幕
* 创建帐户屏幕
