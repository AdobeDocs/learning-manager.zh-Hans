---
description: 每个ALM支持的连接器的概述
jcr-language: en_us
title: 概述支持ALM的连接器
contentowner: mmanuel
source-git-commit: bd80ca31ff633e21ec81e717772e43989f0d9aae
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 6%

---


# Adobe Learning Manager连接器

## 简介

Adobe Learning Manager (ALM)提供了一整套连接器，能够与第三方应用程序和企业系统无缝集成。 这些连接器在学习管理系统和外部平台之间充当桥梁，有助于实现自动数据同步、用户管理、内容导入和学习记录导出。

本文档可作为您了解和选择适用于您组织的学习生态系统的连接器的完整参考指南。 无论您是希望与HR系统、电子商务平台、虚拟会议工具集成，还是希望与业务智能解决方案集成。

有关Adobe Learning Manager支持的连接器的完整列表，请参阅左侧目录中的本文正下方嵌套的连接器文章。

>[!NOTE]
>
>此功能在FedRAMP授权的环境中有部分可用。 有关详细信息，请参阅[FedRAMP环境中的功能可用性](/help/migrated/feature-availability-in-fedramp-authorized-environment.md)。

>[!NOTE]
>
>在2022年11月版Adobe Learning Manager中，Zoom已于2023年6月前弃用[JWT身份验证](https://developers.zoom.us/docs/internal-apps/s2s-oauth/)。 因此，带 JWT 的 Zoom 连接器将继续运行至 6 月，但我们建议用户创建服务器到服务器 OAuth 应用程序，以替换帐户中的功能。 默认情况下，所有新连接都将拥有 Zoom OAuth 身份验证。

## 连接器类别

Adobe Learning Manager连接器可根据其主要用途和集成功能分为几个功能类别：

| 类别 | 目的 | 示例连接器 |
|---------|--------|-------------------|
| 数据传输 | 基于文件的数据交换和批量操作 | FTP、自定义FTP、Box |
| 虚拟教室 | 实时培训和会议集成 | Microsoft Teams，缩放， Adobe Connect |
| 企业系统 | HR和业务系统集成 | Workday、Salesforce、ADFS |
| 内容平台 | 外部学习内容集成 | linkedIn Learning， Harvard ManageMentor， getAbstract |
| Analytics &amp; BI | 报告和数据可视化 | Power BI、培训数据访问 |
| 身份验证 | 身份管理和安全 | ADFS（SSO功能） |
| 电子商务和营销 | 销售和营销集成 | Adobe Commerce，Marketo Engage |

## 数据传输和文件管理连接器

这些连接器通过文件传输协议促进自动数据交换，支持批量操作和系统到系统的通信。

### Adobe Learning Manager FTP连接器

FTP连接器使组织可以使用广泛采用的文件传输协议在Adobe Learning Manager和外部系统之间自动执行数据同步。 此连接器支持安全变体，包括SFTP（SSH文件传输协议）和FTPS（FTP安全），以增强安全性。

#### 关键功能：

- 在Adobe Learning Manager和远程服务器之间上传和下载文件。
- 自动交换用户信息和培训记录。
- 支持安全文件传输协议(SFTP、FTPS)。
- 批量处理大型数据集。

有关详细信息，请参阅[FTP连接器](/help/migrated/integration-admin/feature-summary/ftp-connector.md)。

### 自定义FTP连接器

自定义FTP连接器提供了更完善的文件传输功能，支持结构化数据格式和xAPI语句交换。 此连接器专为需要更精细地控制其数据交换过程的组织而设计。

#### 关键功能：

- 通过结构化CSV文件导入和导出用户数据。
- 处理学习记录和xAPI语句。
- 自动从指定的FTP文件夹处理文件。
- 增强了用于敏感数据传输的安全功能。

有关详细信息，请参阅[自定义FTP连接器](/help/migrated/integration-admin/feature-summary/custom-ftp-connector.md)。

### Box 连接器

Box连接器利用Box的云存储平台，便于外部系统和Adobe Learning Manager之间的无缝数据同步。 对于已在使用Box进行文件管理的组织，此连接器尤为有用。

#### 关键功能：

- 基于云的文件存储和同步。
- 自动化CSV数据处理。
- 与现有Box工作流程集成。
- 来自指定文件夹的实时数据更新。

有关更多信息，请参阅 [Box 连接器](/help/migrated/integration-admin/feature-summary/box-connector.md)。

## 虚拟教室和会议连接器

这些连接器将Adobe Learning Manager与流行的视频会议和虚拟会议平台集成，可实现实时培训课程的无缝交付。

### Microsoft Teams 连接器

Microsoft Teams连接器通过直接与Teams的会议功能集成，将Adobe Learning Manager转变为一个全面的虚拟教室解决方案。 对于使用Microsoft 365生态系统的组织，此连接器必不可少。

#### 关键功能：

- 直接从Adobe Learning Manager安排虚拟教室会话。
- 自动创建和管理团队会议。
- 无单独会议链接的无缝学习者访问。

有关详细信息，请参阅[MS Teams连接器](/help/migrated/integration-admin/feature-summary/install-microsoft-teams-connector.md)。

### Zoom连接器

Zoom连接器使组织可以直接在其Adobe Learning Manager环境中利用Zoom强大的视频会议功能，为讲师和学习者提供无缝体验。

#### 关键功能：

- Adobe Learning Manager中的Direct Zoom会议安排。
- 自动化会议链接生成和分发。
- 实时考勤监控。
- 录制管理和播放集成。
- 分组讨论室支持交互式会话。

有关详细信息，请参阅[Zoom连接器](/help/migrated/integration-admin/feature-summary/zoom-connector.md)。

### Adobe Connect连接器

Adobe Connect连接器可与Adobe自己的虚拟教室平台深度集成，提供交互式在线学习体验的高级功能。

#### 关键功能：

- 高级交互式功能（投票、测验、分组讨论）。
- 高质量的屏幕共享和演示工具。
- 全面的会话录制和回放。
- 针对移动设备优化的虚拟教室体验。

有关详细信息，请参阅[Adobe Connect连接器](/help/migrated/integration-admin/feature-summary/adobe-connect-connector.md)。

## 企业系统集成连接器

这些连接器使Adobe Learning Manager能够与核心业务系统集成，从而促进自动用户管理和组织数据同步。

### Workday 连接器

Workday连接器可在您的HR系统和学习管理平台之间建立无缝桥梁，确保员工记录、组织结构和角色分配在这两个系统之间保持同步。

#### 关键功能：

- 从Workday自动配置用户。
- 实时员工数据同步。
- 组织层次结构映射。
- 基于角色的学习分配自动化。

有关详细信息，请参阅[Workday连接器](/help/migrated/integration-admin/feature-summary/workday-connector.md)。

### Salesforce 连接器

Salesforce连接器使组织能够将其客户关系管理系统与学习计划集成，从而为销售培训、客户教育和绩效跟踪创造机会。

#### 关键功能：

- 自动从Salesforce导入用户。
- 自定义数据字段映射。
- 学习记录导出至Salesforce。
- 销售业绩与培训完成情况的相关性。
- 客户教育计划管理。

有关详细信息，请参阅[Salesforce连接器](/help/migrated/integration-admin/feature-summary/salesforce-connector.md)。

### ADFS （Active Directory联合身份验证服务）连接器

ADFS连接器使组织能够实现企业级身份验证和授权，从而允许用户使用其现有的Active Directory凭据访问Adobe Learning Manager。

#### 关键功能：

- 单点登录(SSO)实施
- 企业安全合规性
- 无缝用户身份验证
- 自动导入用户
- 能够安排
- 筛选功能

有关详细信息，请参阅[ADFS连接器](/help/migrated/integration-admin/feature-summary/adfs-connector.md)。

## 内容和学习平台连接器

这些连接器通过集成外部内容库和专业学习平台来扩展您的学习目录。

### LinkedIn 学习连接器

通过LinkedIn Learning连接器可访问LinkedIn丰富的专业发展课程库，企业可以利用业界领先的外部内容来补充其内部培训。

#### 关键功能：

- 访问LinkedIn学习的完整课程目录。
- 自动课程发现和导入。
- Adobe Learning Manager中的学习者进度跟踪。

有关详细信息，请参阅[LinkedIn连接器](/help/migrated/integration-admin/feature-summary/linkedin-learning-connector.md)。

### Harvard ManageMentor 连接器

Harvard ManageMentor连接器将世界一流的领导力和管理培训内容直接引入您的Adobe Learning Manager环境中，让您能够访问哈佛商学院的著名教育资源。

#### 关键功能：

- 高级哈佛商学院内容访问权限。
- 管理和领导能力开发模块。
- 无缝内容导入和整理。

有关详细信息，请参阅[Harvard ManageMentor连接器](/help/migrated/integration-admin/feature-summary/harvard-managementor-connector.md)。

### getAbstract连接器

getAbstract连接器提供了对简明业务书籍摘要和专业见解的访问，使企业能够利用可理解的内容格式提供持续学习。

#### 关键功能：

- 访问商业书籍摘要和见解。
- 使用情况数据跟踪和报告。
- 自动完成记录创建。

有关详细信息，请参阅[getAbstract连接器](/help/migrated/integration-admin/feature-summary/getabstract-connector.md)。

## Business intelligence and analytics连接器

这些连接器通过将学习数据与外部分析平台集成来实现高级报告、数据可视化和商业智能功能。

### Power BI 连接器

Power BI连接器通过将学习指标自动与Microsoft强大的商业智能平台同步，将您的学习数据转换为可操作的商业见解。

#### 关键功能：

- 实时学习数据同步。
- 自定义信息板创建和管理。
- 高级数据可视化和报告。
- 集成学习者成绩单和技能报告。

有关更多信息，请参阅 [Power BI 连接器](/help/migrated/integration-admin/feature-summary/power-bi-connector.md)。

### 培训数据访问连接器

通过培训数据访问连接器，组织可以通过为培训数据和课程信息提供API访问来创建自定义学习界面和无头学习体验。

**关键功能：**

- 对课程和学习路径数据的公共API访问。
- 自定义用户界面开发支持。
- 无头学习体验创建。
- 高级搜索和筛选功能。

有关详细信息，请参阅[培训数据访问连接器](/help/migrated/integration-admin/feature-summary/training-data-access-connector.md)。

## 电子商务和营销连接器

这些连接器实现了学习内容的货币化并与营销自动化平台集成。

### Adobe Commerce 连接器

Adobe Commerce连接器可将Adobe Learning Manager转变为全面的学习商务平台，使组织可通过完全集成的电子商务体验销售课程、认证和培训计划。

**关键功能：**

- 电子商务平台无缝集成。
- 课程目录和定价管理。
- 自动支付处理和注册。

有关详细信息，请参阅[Adobe Commerce连接器](/help/migrated/integration-admin/feature-summary/adobe-commerce-connector.md)。

### Marketo Engage 连接器

该Marketo Engage连接器在学习活动和营销活动之间创造了强大的协同效应，使公司能够利用教育参与来培养潜在客户和发展客户。

#### 关键功能：

- 自动创建和更新潜在客户。
- 跟踪学习活动以获取营销见解。
- 课程注册和完成事件触发器。

有关详细信息，请参阅[Marketo Engage连接器](/help/migrated/integration-admin/feature-summary/marketo-engage-connector.md)。
