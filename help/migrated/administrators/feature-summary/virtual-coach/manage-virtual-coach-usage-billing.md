---
description: 了解Learning Manager管理员如何激活Virtual Coach、监控MAU积分使用情况以及下载学习者绩效报告
jcr-language: en_us
title: 管理虚拟引导的使用和计费
exl-id: 1f8f6465-51c3-4670-a1c7-9a7dfb091452
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%
---

# 管理虚拟引导的使用和计费

激活虚拟辅导、监控每月活动用户(MAU)信用消耗，并以Adobe Learning Manager管理员的身份下载学习者绩效报告。

## 为您的帐户激活虚拟辅导 {#activatevirtualcoach}

虚拟引导可用作Adobe Learning Manager的加载项。 购买后，配置会生成一个激活密钥，并将此密钥通过电子邮件发送给帐户管理员。

1. 以管理员身份登录Adobe Learning Manager 。
2. 从左侧导航窗格中导航到&#x200B;**帐单**&#x200B;页面。
3. 在&#x200B;**虚拟教程**&#x200B;部分中，输入通过电子邮件收到的激活密钥。

   ![](/help/migrated/administrators/feature-summary/assets/virtual_coach12.png)
   *在“帐单”页面的“虚拟指导”部分输入激活密钥以启用该功能。*

4. 选择&#x200B;**应用**。 已为您的帐户启用虚拟辅导。

激活后，您将收到应用程序内通知，确认该功能已启用。 四个角色扮演示例场景会自动添加到&#x200B;**内容库**&#x200B;中，以便作者可以立即开始。

>[!NOTE]
>
>激活密钥在设置过程中自动生成，并通过电子邮件共享。 如果您没有激活密钥，请联系您的Adobe Learning Manager客户成功经理。

## 查看MAU贷方余额

每月活动用户(MAU)积分统计每月使用虚拟教程的唯一学习者数。

1. 导航至&#x200B;**帐单**&#x200B;页面。
2. 在&#x200B;**虚拟辅导**&#x200B;部分中，选择&#x200B;**查看使用情况详细信息**。

   ![](/help/migrated/administrators/feature-summary/assets/virtual-coach22.png)

3. 使用&#x200B;**选择时段**&#x200B;下拉列表选择要查看的日期范围。

   **整体使用情况**&#x200B;表显示：

   - **可用**：已购买的MAU积分总数。
   - **已使用**：到目前为止已使用的积分。
   - **剩余**：剩余合同期的可用积分。

   **每月使用情况**&#x200B;表按日历月显示唯一活跃学习者数。

   ![](/help/migrated/administrators/feature-summary/assets/virtual-coach23.png)

4. 选择&#x200B;**下载详细报告**&#x200B;以导出完整使用情况数据。

   ![](/help/migrated/administrators/feature-summary/assets/virtual-coach-report-mau-billing-5.png)

## MAU积分的使用方式

学习者在日历月启动虚拟引导会话时，系统会消耗MAU积分。 同一学习者在同月完成的其他会话不会使用其他积分。 于合约期末尚未动用之信贷失效，且并无结转。

| 情景 | 消耗的MAU |
|---|---|
| 一名学习者在1月完成了5个课程 | 1 |
| 该学习者在1月和2月都使用虚拟辅导 | 2（每月1个） |
| 100名学习者各自在1月完成1个课程 | 100 |

每个日历月为每个唯一学习者计算&#x200B;*个MAU积分，无论每个学习者启动多少个会话。*

**示例：单个学习者、多个会话。** Sarah在1月启动了5次虚拟引导会话。 她被计为当月的唯一用户，因此，无论她练习多少次，都会消耗1个MAU。

**示例：同一学习者，多个月。** Sarah在1月（3个会话）和2月（2个会话）都使用虚拟辅导。 每个日历月分开计算，因此消耗了2个MAU：1月消耗1个，2月消耗1个。

**示例：多个学习者，同月。** 100名销售代表在1月份都会启动一次虚拟引导会议。 每个单独的学习者当月计为一个MAU，因此消耗了100个MAU。

**示例：随时间推移的团队练习。** 您的团队有50名成员，全年都使用虚拟教练。 在50个练习中只有5个是当月使用5个MAU；在所有50个练习都再次使用的月份中，除了当月返回学习者时已使用的内存之外，还有0个MAU，因为每个学习者每个日历月仅被计数一次，无论他们在其中练习多少次。

若要了解虚拟引导报告，请导航到[虚拟引导报告](/help/migrated/administrators/feature-summary/virtual-coach/virtual-coach-reports.md)。
