---
description: 查找学习者可在Claude或ChatGPT Enterprise中请求的示例提示，以搜索课程、检查注册和构建学习路径
jcr-language: en_us
title: Adobe Learning Manager学习者提示示例
exl-id: e5d64ac4-03e9-49bc-95d0-bb074d55987f
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 1%
---

# Adobe Learning Manager学习者提示示例

在Claude或ChatGPT Enterprise中使用这些提示搜索课程、检查注册情况并构建学习路径。

首先连接您的AI客户端。 详细了解[将您的AI客户端连接到Adobe Learning Manager](/help/migrated/learners/feature-summary/connect-ai-client-to-alm-learner.md)。 每个提示均映射到[学习者工具引用](/help/migrated/learners/feature-summary/learner-tools-reference.md)中的某个工具。

>[!TIP]
>
>根据需要命名，例如主题、课程状态或截止日期。 特定请求可帮助AI客户端选择正确的工具。

## 注册

| **提示** | **工具** |
|------------------------------------------|------------------------------|
| 我注册了哪些课程？ | list_my_learning_enrollments |
| 我的哪些课程即将过期？ | list_my_learning_enrollments |

## 搜索

| **提示** | **工具** |
|-----------------------------------------|-----------------------|
| 有哪些领导力课程？ | search_learning_items |
| 显示可供我使用的安全培训。 | search_learning_items |

## 知识

| **提示** | **工具** |
|----|----|
| 在FedRAMP中，供应链风险管理意味着什么？ | answer_learning_content_question |
| 解释我的合规性课程中的要求。 | answer_learning_content_question |

## 学习路径

| **提示** | **工具** |
|----|----|
| 帮助我查找一组课程，提升项目管理的技能。 | personalized_learning_path |
| 保存此学习路径。 | personalized_learning_path |
