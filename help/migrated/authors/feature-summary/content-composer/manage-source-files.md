---
description: 上传现有文档、策略或资料包，以便将AI置于组织的内容中。 选择是仅对这些文件进行生成，还是让AI补充其一般知识。
jcr-language: en_us
title: 管理源文件
source-git-commit: 229e407621281978f94783c3e9320c237c314fc3
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---


# 管理源文件

通过&#x200B;**管理源**，您可以控制Content Composer用来生成课程的内容。 将您自己的文档添加到课程中，然后选择是将AI限制为仅包含该内容，还是使其根据自己的知识补充您的材料。 如果您未添加任何文档，内容编辑器会使用AI模型的现有知识生成课程。

## 使用源材料生成课程

1. 在聊天面板或工具栏中选择&#x200B;**管理源**&#x200B;或&#x200B;**添加文件**。
   ![](../assets/5_brief_manage_sources_prompt_updated.png)

2. 将文件拖到对话框中或选择&#x200B;**+添加源文件**进行浏览。 您可以添加多个源文件。
   ![](../assets/6_manage_sources_no_files_added_updated.png)

3. 选择&#x200B;**限制输出到文件中的内容**。 这允许Content Composer仅使用源内容生成课程。 如果未选中此选项，内容编辑器也会使用Web创建课程。
   ![](../assets/7_manage_sources_file_uploading_restrict_output_updated.png)

支持的格式：

| **格式** | **最大大小** |
|-------------------------|--------------|
| PDF | 100 MB |
| Markdown (.md) | 100 MB |
| PowerPoint (.ppt/.pptx) | 100 MB |
| MS Word (.doc/.docx) | 100 MB |
| 文本文件(.txt) | 100 MB |

选择&#x200B;**继续**&#x200B;以生成课程大纲。

### 生成无源材质

在没有源文件作为参考文档时，请执行以下步骤来生成课程大纲。

1. 选择&#x200B;**管理源**。 将打开&#x200B;**管理源**&#x200B;对话框。

2. 选择&#x200B;**我没有任何源材料 — 生成没有源文件的课程**，以允许AI根据其一般知识生成内容。 如果未选择此选项，则在上传文件时，AI仅将生成的内容限制为已上传的文档。![](../assets/8_manage_sources_no_source_material_option_updated.png)

3. 选择&#x200B;**继续**&#x200B;以生成课程大纲。

### 在源材料更改时更新课程

生成课程后（修订策略、获取SOP新版本或更新推销文档），源文档可能会过期。 使用此工作流程可使课程恢复为与当前材料一致的课程。

1. 从聊天面板或工具栏中选择&#x200B;**管理源**&#x200B;以重新打开对话框。

2. 使用&#x200B;**+添加源文件**&#x200B;添加新的或修订的文件。

3. 删除或替换任何过时的文件，以便源列表仅反映当前素材。

4. 选择继续以保存更新的源列表。

5. 在Content Composer中重新生成受影响的课程，查看更改，然后重新发布课程。 重新发布操作会将更新作为新模块版本发送到Adobe Learning Manager — 请参阅ALM中的模块版本。

### 确认文件上传

    ！[](../assets/9_manage_sources_file_ingested_confirmation_updated.png)

附加文件后，工具栏中的文件图标会显示徽章计数。 助理确认上传并提供&#x200B;**生成大纲**&#x200B;快捷方式。 选择它，或在顶部工具栏中选择&#x200B;**生成大纲**。
