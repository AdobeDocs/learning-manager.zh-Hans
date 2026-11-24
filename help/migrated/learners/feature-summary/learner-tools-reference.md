---
description: 查找学习者可以使用Adobe Learning Manager模型上下文协议服务器执行哪些操作，以及哪些工具支持每项功能。
jcr-language: en_us
title: 模型上下文协议服务器的学习者工具
exl-id: 4509b984-d0ba-4b7e-a0bb-803aa235fd1e
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 0%
---

# 模型上下文协议服务器的学习者工具

## 概述

在学习者连接后，每项功能均以登录学习者的身份运行。 请求仅返回学习者可在Adobe Learning Manager中访问的内容。 详细了解[连接您的AI客户端](/help/migrated/learners/feature-summary/connect-ai-client-to-alm-learner.md)。

## 学习者功能

| **功能** | **学习者可以做些什么** | **示例请求** |
|----|----|----|
| 搜索学习内容 | 查找课程、认证和学习路径 | 有哪些领导力课程？ |
| 查看注册 | 检查注册和相应学习 | 我的哪些课程即将过期？ |
| 提出学习问题 | 从学习内容中获取答案 | 在FedRAMP中，供应链风险管理意味着什么？ |
| 生成学习路径 | 创建个性化的学习路径 | 帮助我查找提升项目管理技能的课程。 |
| 保存学习路径 | 保存生成的学习路径 | 保存此学习路径。 |

## 支持的MCP工具

Adobe Learning Manager MCP服务器公开以下学习者工具。

| **工具名称** | **描述** |
|----|----|
| search_learning_items | 在目录中搜索课程、学习路径、认证、工作辅助、徽章、技能、目录和标签。 按学习者状态、技能、标签、目录、交付格式、价格和语言筛选。 对于主题问题，请使用answer_learning_content_question。 示例：“初学者蟒蛇课程”。 |
| list_my_learning_enrollments | 列出学习者的已注册、进行中和已完成的课程、学习路径、认证和工作辅助，以及状态、进度和截止日期。 按学习对象类型或完成状态筛选。 结果首先显示最近的注册。 示例：“What is during now？” |
| get_learning_object | 按ID获取课程、学习路径、认证或工作辅助的完整详细信息，并可选择包含实例、技能和子学习对象。 从search_learning_items或list_my_learning_enrollments获取ID。 |
| get_my_learning_profile | 获取学习者的个人资料，包括帐户和经理详细信息。 有关注册和进度，请使用list_my_learning_enrollments。 |
| answer_learning_content_question | 根据学习材料回答有关学习内容的问题，并引述到源学习对象。 总结一个学习对象，或针对覆盖范围、深度、先决条件和受众并排比较两个对象。 要查找或列出内容，请使用search_learning_items或list_my_learning_enrollments。 示例：“说明TCP与UDP，如我的网络课程中所述。” |
| personalized_learning_path | 推荐与学习者的目标、主题和需求相匹配的课程。 将批准路径保存到学习者帐户。 列出已保存的路径，或按ID获取一个路径的详细信息。 |

>[!IMPORTANT]
>
>显示的工具名称仅供参考，可能会因客户端实现而异。
