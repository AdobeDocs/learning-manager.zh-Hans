---
title: 从 Adobe FTP Manager 过渡
description: Adobe Learning Manager支持使用AWS传输系列的SFTP协议的新连接器。 可以将任何开源 FTP 客户端替换为 Adobe FTP Manager。
exl-id: c5674e61-9e3d-45e5-9f3c-e0aa15ec2dac
source-git-commit: 566716404c1cff34108e39014e14416d65088a80
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 68%

---

# 从 Adobe FTP Manager 过渡

Adobe Learning Manager 支持使用 AWS Transfer 系列 SFTP 协议的新连接器。

可以将任何开源 FTP 客户端替换为 Adobe FTP Manager。

[此处](https://docs.aws.amazon.com/transfer/latest/userguide/transfer-file.html)列出了 AWS 推荐的部分 FTP 客户端：

* FileZilla（Windows、macOS 和 Linux）
* OpenSSH（macOS 和 Linux）- 注意：此客户端仅适用于已启用安全外壳 (SSH) 文件传输协议 (SFTP) 的服务器。
* WinSCP（仅限 Microsoft Windows）
* Cyberduck（Windows、macOS 和 Linux）

## 配置基于AWS的FTP连接器

您必须在集成管理员上配置新的基于AWS的FTP连接器。

![连接器图像](assets/alm-ftp.png)
*选择FTP选项*

连接后，您可以看到“连接详细信息”页面。

![连接详细信息页面](assets/connection-name.png)
*查看连接详细信息页面*

有三个身份验证选项：

### 通过生成新的 SSH 密钥来创建身份验证

如果要在系统中生成 SSH 密钥，则可以这样做。 单击“生成SSH密钥”。

私钥将下载到您的计算机，公钥保存在我们的服务中。 单击“连接”后，将创建以公钥和私钥作为身份验证的FTP用户。

您已创建FTP连接。

### 使用现有 SSH 密钥创建身份验证

如果您已有SSH密钥，请将公钥粘贴到&#x200B;**[!UICONTROL FTP公钥]**&#x200B;字段中，然后单击“连接”。

![SSH密钥](assets/ssh-keys.png)
*粘贴密钥*

### 使用密码创建基本身份验证

这是基本的身份验证机制。 选择第一个选项，**[!UICONTROL 使用密码创建基本身份验证]**。 输入密码，然后单击&#x200B;**[!UICONTROL 连接]**。

这样就会建立一个连接。

## 下一步

### 设置 FTP 客户端

使用下载的密钥或现有的密钥或密码在 FTP 客户端（前面一节中推荐的客户端）上设置连接。

### 测试导出示例

* 在 FTP 客户端中，将 ExaVault FTP 的位置更改为新的 FTP 位置。 新域是`http://almftp.adobelearningmanager.com/`。
* 您还必须将IP `18.195.107.67`列入白名单。
* 完成身份验证后，您必须使用外部 FTP 客户端或自动化脚本在新的 FTP 位置之间上载和下载几个示例文件。
* 您必须将数据从旧位置传输到新位置。
* 连接器的数据保留策略保持不变。 ExaVault 还支持包括官方策略在内的部分数据保留策略。 此类数据保留策略将不可用于新连接器。 检查您的连接器是否使用了官方支持的策略之外的任何数据保留策略。

### 迁移项目后续

| 状态 | 推荐 |
|---|---|
| 新迁移 | 无法从旧 FTP 启动新迁移。 必须使用新的 FTP 进行新迁移。 如需有关此方面的更多支持，请联系客户成功团队。 |
| 正在迁移 | 创建Sprint：您可以继续使用旧版FTP，但我们建议使用新版FTP。 对于任何无法转移的现有Sprint，请联系客户成功团队。 |
| 已关闭的迁移 | 无操作。 |

## 使用 Filezilla FTP 客户端连接到 Adobe Learning Manager

1. 连接到新的 ALM FTP 连接器。 单击“连接”。

   ![连接图像](assets/connect-client.png)
   *连接到新的ALM FTP连接器*

1. 要通过密码进行基本身份验证，从而实现连接，请输入域名、FTP 用户名，并设置符合密码验证标准的密码。 单击“连接”。 系统将新建 FTP 连接，用户可以通过任何 SFTP 客户端加以访问。

   ![ftp设置](assets/connect-settings.png)
   *通过密码进行基本身份验证*

1. 安装任意 SFTP 客户端，例如 File Zilla。 启动“文件Zilla”，然后单击左上角的“打开站点管理器”。

   ![SFTP客户端](assets/sftp-client-install.png)
   *通过SFTP客户端连接*

1. 单击&#x200B;**[!UICONTROL “新建网站”]**&#x200B;以新建站点。 根据需要为站点重命名。

   ![新站点](assets/new-site.png)
   *创建站点*

1. 从“连接器凭据”页映射详细资料。

   * 选择“SFTP - SSH文件传输协议”协议
   * 将主机设为 FTP 域
   * 将登录类型设置为“请求密码”
   * 将用户设为 FTP 用户名

1. 单击“连接”。

   ![凭据](assets/connector-credentials.png)
   *输入凭据*

   >[!NOTE]
   >
   >在 FileZilla 客户端中执行此步骤。

1. 输入密码。

   （可选）选中“记住密码”复选框以记住密码。

   ![密码](assets/password.png)
   *输入密码*

   （可选）选中&#x200B;**[!UICONTROL 始终信任此主机]**&#x200B;复选框以信任该主机。

1. 单击“确定”。

   ![未知的主机密钥](assets/unknown-host-key.png)
   *主机密钥*

1. 在顶部检查连接的状态和进度。

   左半部分为本地站点，右半部分为远程站点。

   如要将文件从本地移动到远程，请完成以下操作（反之亦然）：

   * 您可以拖放文件。
   * 双击文件。

   ![连接状态](assets/connection-status-progress.png)
   *检查连接状态*

您可以随时更改和更新身份验证类型。

其他身份验证方法为使用 SSH 密钥：

将公钥粘贴到文本框以使用现有 SSH 密钥。 单击“连接”/“保存”。

若要生成新的SSH密钥，请单击“**[!UICONTROL 生成SSH密钥]**”按钮。 系统将下载私钥。 单击&#x200B;**[!UICONTROL “连接/保存”]**。

![生成ssh密钥](assets/ssh-key.png)
*生成SSH密钥*

映射详细信息。 将登录类型选为密钥文件。 选择私钥文件。

单击&#x200B;**[!UICONTROL “连接”]**。

## ExaVault 弃用后续

在弃用 ExaVault 后，所有正在进行的现有迁移项目都将过渡到新的 FTP 作为源位置。 然后，您必须在配置新的 FTP 连接器后才能继续完成迁移。

## 迁移 Sprint 的建议

在创建迁移项目时，Adobe 建议使用新的 AWS SFTP 连接器创建项目，以避免在后期将 Sprint 从 Exavault 迁移到 AWS。

如果正在进行迁移，请关闭当前使用Exavault作为数据源的Sprint。 创建 AWS SFTP 连接、测试设置，然后联系客户成功团队，以切换到新的 AWS SFTP 数据源。 切换后，在同一迁移项目中新建一个 Sprint。 此时将在新位置创建Sprint文件夹，您可以上传迁移CSV以继续该活动。

**迁移项目无法关闭的情况**

* 对于从外部旧系统迁移到 Adobe Learning Manager 的课程，系统会在当前项目中完成课程 ID 映射。 仅当您想要更新同一项目中的相同课程时才可以这样做。 关闭项目后，您将无法修改其详细信息。
* 对于基于 API 的迁移项目，您不得关闭项目。