---
description: 内容编辑器主题JSON架构中每个属性的完整参考，包括调色板令牌、字体栈栈、半径和间距令牌、文本角色值、组件属性和评估样式。
jcr-language: en_us
title: Adobe Learning Manager Content Composer主题JSON属性参考
source-git-commit: ea6d296fa99686136ab08d756a20570a4681d704
workflow-type: tm+mt
source-wordcount: '1899'
ht-degree: 5%

---


# Adobe Learning Manager Content Composer主题JSON属性参考

内容编辑器主题JSON文件中每个属性的完整参考，包括说明和示例值。

用于标识和描述主题的顶级字段。

## **元数据**

| **属性** | **类型** | **描述** | **石板值** |
|--------------|----------|----------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| ID | 字符串 | 唯一主题标识符。 小写、仅连字符、无空格或特殊字符。 在内部使用以引用主题。 | “石板” |
| name | 字符串 | “课程主题”面板中显示的显示名称。 | “石板” |
| 版本 | 字符串 | 语义版本号。 将“1.0.0”用于新主题。 | &quot;1.0.0&quot; |
| 描述 | 字符串 | 主题视觉特性的简短描述。 | “温暖、权威的主题，带有奶油背景、Adobe红色调和Roboto Slab + Roboto字体系统” |
| 作者 | 字符串 | 主题创建者或团队的名称。 | “内容编辑器” |
| source | 字符串 | 主题来源。 内置主题为“已发货”。 “自定义”，适用于用户创建的主题。 | “自定义” |
| isDefault | 布尔值 | 此主题是否自动应用于新课程。 在大多数情况下，设置为false。 | false |

## **foundation.palette**

构成主题颜色基础的七种核心颜色令牌。 所有元素值都使用var(—tokenName)而不是硬编码的十六进制值引用这些标记。

| **属性** | **类型** | **描述** | **石板值** |
|------------------|------------|---------------------------------------------------------------------------------------------------------------------------|-----------------|
| 前景 | 十六进制颜色 | 前景主色，用于置于背景上的文本、图标和UI元素。 | #1A1A1A |
| 背景 | 十六进制颜色 | 主课程画布和幻灯片背景颜色。 | #FAF7F2 |
| 着色 | 十六进制颜色 | 应用于按钮、选定状态、进度指示器、课程标题和交互式高光的品牌强调色。 | #E8001C |
| backgroundSubtle | 十六进制颜色 | 卡、面板、导航和组件填充的辅助背景色。 | #F0EBE1 |
| 辅助 | 十六进制颜色 | 边框、分隔线和非活动UI元素颜色。 | #D9D3C9 |
| textPrimary | 十六进制颜色 | 所有标题和正文内容的主文本颜色。 | #1A1A1A |
| textInverse | 十六进制颜色 | 放置在深色或强调色背景上的内容（如强调色上的按钮标签）的文本颜色。 | #FFFFFF |

## **foundation.fonts**

两个字体栈叠将应用于主题中的所有文本角色。 使用var(—font-heading)或var(—font-body)在元素值中进行引用。

| **属性** | **类型** | **描述** | **石板值** |
|--------------|-------------------|------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| 标题 | 字体栈栈字符串 | 课程标题、主题标题和显示标题的字体系列。 包括Web安全回退。 | “佐治亚州Roboto Slab， &#39;Times New Roman&#39;， serif” |
| 正文 | 字体栈栈字符串 | 段落文本、字幕、测试问题和UI标签的字体系列。 包括Web安全回退。 | “Roboto，-apple-system， BlinkMacSystemFont， &#39;Segoe UI&#39;， sans-serif” |

## **foundation.spacing**

用作基线的水平和垂直间距标记。 组件使用horizontalSpacingScale和verticalSpacingScale乘数从这些对象进行缩放。

| **路径** | **类型** | **描述** | **石板值** |
|---------------|----------|-------------------------------------|-----------------|
| horizontal.xs | 像素值 | 最小水平间距单位 | 4px |
| horizontal.s | 像素值 | 小水平间距单位 | 8px |
| horizontal.m | 像素值 | 中等水平间距单位 | 12px |
| horizontal.l | 像素值 | 大水平间距单位 | 16px |
| horizontal.xl | 像素值 | 超大水平间距单位 | 24px |
| vertical.xs | 像素值 | 最小垂直间距单位 | 4px |
| 垂直.s | 像素值 | 小垂直间距单位 | 8px |
| vertical.m | 像素值 | 中等垂直间距单位 | 16px |
| vertical.l | 像素值 | 大垂直间距单位 | 24px |
| vertical.xl | 像素值 | 超大垂直间距单位 | 32px |

## **foundation.radius**

控制组件和卡的圆角化的边框半径令牌。

| **属性** | **类型** | **描述** | **石板值** |
|--------------|----------|---------------------------------------------------------|-----------------|
| 无 | 像素值 | 无圆角 — 尖角。 始终为“0px”。 | 0px |
| s | 像素值 | 小半径，用于细微的圆角化。 | 4px |
| m | 像素值 | 标准卡和组件舍入的中等半径。 | 8px |
| l | 像素值 | 醒目倒圆角的半径较大。 | 16px |
| 完整 | 像素值 | 全心丸或圆形。 始终使用“9999px”。 | 9999px |

## **foundation.logo**

| **属性** | **类型** | **描述** | **石板值** |
|--------------|----------------|----------------------------------------------------------------------------------------------|-----------------|
| 徽标 | 字符串或null | 课程标题中显示的徽标图像的URL或文件路径。 将不带徽标设置为null。 | null |

## **elements.text**

课程中每个命名文本角色的排版属性。 所有角色共享同一组属性。

### **文本角色**

| **角色** | **应用于** |
|--------------|------------------------------------------------------------------------------|
| 课程标题 | 课程打开幻灯片上的主标题 |
| topicTitle | 标题位于每张主题幻灯片的顶部 |
| blockHeading | 内容组件内的标题，例如可折叠面板标题和卡片标题 |
| 副标题 | 主题幻灯片中的副标题 |
| 问题 | 测验和知识检查问题文本 |
| 题注 | 图像和媒体块下方的字幕 |
| 段落 | 内容幻灯片中的正文 |
| buttonLabel | 按钮和行动号召元素上的文本 |

### **共享文本属性**

以下属性适用于上面列出的每个文本角色。

| **属性** | **类型** | **接受的值** | **描述** |
|--------------------|-----------------------|--------------------------------------------------------------------|---------------------------------------------------------|
| fontFamily | CSS变量或字体栈栈 | var(—font-heading)、var(—font-body)或完整的字体栈栈字符串 | 此文本角色的字体系列。 |
| fontSize | 像素值 | 任何像素值 | 字体大小。 |
| fontWeight | 字符串 | 仅“粗体”或“正常” — 不支持数值 | 字体粗细。 |
| fontStyle | 字符串 | “normal”或“italic” | 字体样式。 |
| 颜色 | CSS变量或十六进制 | 通过var(—tokenName)或直接十六进制值的任何调色板标记 | 文本颜色。 |
| textAlign | 字符串 | “left”、“center”或“right” | 水平文本对齐。 |
| letterSpacing | 字符串 | “正常”、像素值或全角字值 | 字符间距。 |
| lineHeight | 字符串 | 百分比或无单位值 | 直线Height。 |
| textDecoration | 字符串 | “none”、“underline”或“line-through” | 文本修饰。 |
| textTransform | 字符串 | “none”、“uppercase”、“lowelcase”或“capitalize” | 文本大小写转换。 |
| paddingInlineStart | 像素值 | 任何像素值 | 应用于文本块的左内边距。 |
| 段落间距 | 像素值 | 任何像素值 | 在文本块中每个段落的下方添加空格。 |

### **文本角色值 — Slate主题**

| **角色** | **fontFamily** | **fontSize** | **fontWeight** | **fontStyle** | **颜色** | **textAlign** | **字母间距** | **lineHeight** | **textTransform** |
|--------------|---------------------|--------------|----------------|---------------|--------------------|---------------|-------------------|----------------|-------------------|
| 课程标题 | var(—font-heading) | 48px | 粗体 | 正常 | var(—textPrimary) | 中心 | -0.01em | 130% | 无 |
| topicTitle | var(—font-heading) | 40px | 正常 | 正常 | var(—textPrimary) | 左 | 0 | 135% | 无 |
| blockHeading | var(—font-heading) | 24px | 粗体 | 正常 | var(—textPrimary) | 左 | 0 | 140% | 无 |
| 副标题 | var(—font-body) | 20px | 粗体 | 正常 | var(—textPrimary) | 左 | 0.01em | 150% | 无 |
| 问题 | var(—font-heading) | 24px | 正常 | 正常 | var(—textPrimary) | 左 | 0 | 150% | 无 |
| 题注 | var(—font-body) | 13px | 正常 | 正常 | var(—textPrimary) | 左 | 0.02em | 170% | 无 |
| 段落 | var(—font-body) | 16px | 正常 | 正常 | var(—textPrimary) | 左 | 0.01em | 190% | 无 |
| buttonLabel | var(—font-body) | 14px | 粗体 | 正常 | var(—textInverse) | 中心 | 0.06埃姆 | 125% | 大写 |

## **元素 — 结构表面**

用于控制课程固定布局曲面的背景和边框的属性。

| **元素** | **属性** | **类型** | **描述** | **石板值** |
|--------------|--------------|-------------------|---------------------------------------------------|----------------------------|
| 画布 | 背景 | CSS变量 | 主课程画布背景颜色 | var(—background) |
| 页眉 | 背景 | CSS变量 | 课程标题栏背景颜色 | var(—background) |
| 页眉 | 边框 | CSS边框字符串 | 课程标题栏的下边框 | 1px solid var(—secondary) |
| 页脚 | 背景 | CSS变量 | 课程页脚栏背景颜色 | var(—background) |
| 页脚 | 边框 | CSS边框字符串 | 课程页脚栏的顶部边框 | 1px solid var(—secondary) |
| leasueHeader | 背景 | CSS变量 | 课程标题区域的背景颜色 | var(—accent) |
| 主题 | 背景 | CSS变量 | 每张主题幻灯片的背景颜色 | var(—background) |
| 主题 | 边框 | CSS边框字符串 | 主题幻灯片容器周围的边框 | 1px solid var(—secondary) |
| 导航 | 背景 | CSS变量 | 课程导览面板的背景颜色 | var(—backgroundSubtle) |
| 导航 | 边框 | CSS边框字符串 | 课程导览面板上的边框 | 1px solid var(—secondary) |
| 按钮 | 背景 | CSS变量 | 主要动作按钮的背景颜色 | var(—accent) |
| 分页 | 背景 | CSS变量 | 分页控件的背景色 | var(—backgroundSubtle) |

## **元素 — 共享组件属性**

以下属性出现在所有内容块组件上：paragraphBlock、videoBlock、imageGrid、accordion、carousel、flipCard和时间轴。

| **属性** | **类型** | **描述** |
|------------------------|-------------------|---------------------------------------------------------------------------------------------------|
| 背景 | CSS变量或颜色 | 组件块的外背景。 通常是“透明”的。 |
| cardBackgroundColor | CSS变量或颜色 | 组件中单个卡的背景填充。 |
| cardBorder | CSS边框字符串 | 每张卡片上都应用了边框。 完整的CSS速记，例如“1px solid var(—secondary)”。 |
| cardShadowOffset | 字符串 | 卡投影的X和Y偏移，例如“0px 2px 6px”。 |
| cardShadowColor | CSS变量或颜色 | 卡投影的颜色。 |
| cardShadowOpacity | 百分比字符串 | 卡片投影的不透明度。 设置为“0%”以移除阴影。 |
| horizontalSpacingScale | 数字字符串 | 应用于此组件的水平间距标记的乘数。 “1”使用默认间距。 |
| verticalSpacingScale | 数字字符串 | 应用于此组件的垂直间距标记的乘数。 “1”使用默认间距。 |
| radiusScale | 数字字符串 | 应用于此组件的半径标记的乘数。 “1”使用默认半径。 |
| nestedAccentColor | CSS变量或颜色 | 组件中嵌套元素的强调色。 仅适用于段落块。 |

### **共享组件值 — 模板主题**

| **组件** | **cardBackgroundColor** | **cardBorder** | **cardShadow不透明度** |
|----------------|-----------------------------|----------------------------|---------------------------|
| 段落块 | var(—backgroundSubtle) | 1px solid var(—secondary) | 8% |
| 视频块 | var(—backgroundSubtle) | 1px solid var(—secondary) | 8% |
| imageGrid | var(—backgroundSubtle) | 1px solid var(—accent) | 8% |
| 可折叠项 | var(—backgroundSubtle) | 1px solid var(—secondary) | 8% |
| 轮播 | var(—backgroundSubtle) | 1px solid var(—secondary) | 8% |
| 翻转卡 | var(—backgroundSubtle) | 1px solid var(—secondary) | 8% |
| 时间线 | var(—backgroundSubtle) | 1px solid var(—secondary) | 8% |

## **元素 — 特定于组件的属性**

各个组件类型特有的属性。

| **组件** | **属性** | **类型** | **描述** | **石板值** |
|----------------|--------------------------|----------|------------------------------------------------------------------|-------------------------|
| 段落块 | nestedAccentColor | CSS变量 | 段落块内嵌套元素的强调色 | var(—accent) |
| 翻转卡 | cardFrontBackgroundColor | CSS变量 | 翻转卡正面的背景色 | var(—backgroundSubtle) |
| 翻转卡 | cardBackBackgroundColor | CSS变量 | 翻转卡背面的背景色 — 显示颜色 | var(—accent) |
| 翻转卡 | arrowColor | CSS变量 | 翻转指示器箭头图标的颜色 | var(—textInverse) |
| 选项卡 | activeBg | CSS变量 | 当前所选选项卡的背景色 | var(—accent) |
| 选项卡 | inactiveBg | CSS变量 | 未选定选项卡的背景颜色 | var(—backgroundSubtle) |
| 选项卡 | containerbg | CSS变量 | 选项卡栏容器的背景色 | var(—backgroundSubtle) |
| 时间线 | trackColor | CSS变量 | 时间轴节点之间连接线的颜色 | var(—secondary) |
| 时间线 | progressCompletedBg | CSS变量 | 已完成的时间轴进度标记的填充颜色 | var(—accent) |
| 时间线 | progressCurrentBorder | CSS变量 | 当前时间轴进度标记的边框颜色 | var(—accent) |
| 时间线 | progressUnreachedBg | CSS变量 | 尚未达到时间轴标记的填充颜色 | var(—secondary) |
| 时间线 | progressUnreachedBorder | CSS变量 | 尚未达到时间轴标记的边框颜色 | var(—backgroundSubtle) |

## **elements.assessment**

测验和知识检查组件的属性。

| **属性** | **类型** | **描述** | **石板值** |
|----------------------------|----------------|------------------------------------------------------------------------------|-------------------------|
| 背景 | CSS变量 | 评估块的外部背景 | 透明 |
| optionTextColor | CSS变量 | 回答选项标签的文本颜色 | var(—textPrimary) |
| optionIndicatorColor | CSS变量 | 单选按钮或复选框指示器的颜色 | var(—accent) |
| optionSelectedColor | CSS变量 | 应用于所选选项指示器的颜色 | var(—accent) |
| optionCheckmarkColor | CSS变量 | 选定选项上显示的复选标记图标的颜色 | var(—textInverse) |
| optionBackgroundColor | CSS变量 | 每个回答选项的背景色 | var(—background) |
| optionHoverBackgroundColor | CSS变量 | 悬停时回答选项的背景色 | var(—backgroundSubtle) |
| buttonBackgroundColor | CSS变量 | “提交”或“检查”应答按钮的背景色 | var(—accent) |
| buttonTextColor | CSS变量 | “提交”或“检查”应答按钮标签的文本颜色 | var(—textInverse) |
| buttonHoverBackgroundColor | CSS变量 | 悬停时按钮的背景颜色 | var(—accent) |
| feedbackCorrectColor | 十六进制颜色 | 正确答案反馈面板的背景色 | #D7F7E1 |
| feedbackIncorrectColor | 十六进制颜色 | 错误答案反馈面板的背景色 | #FFEBE8 |
| feedbackTextColor | 十六进制颜色 | 反馈面板中的文本颜色 | #111111 |
| optionBorderCorrectColor | 十六进制颜色 | 显示答案后，正确答案选项上的边框颜色 | #079355 |
| optionBorderIncorrectColor | 十六进制颜色 | 显示答案后，未正确选择的选项上的边框颜色 | #D73220 |
| horizontalSpacingScale | 数字字符串 | 评估组件中水平间距的乘数 | &quot;1&quot; |
| verticalSpacingScale | 数字字符串 | 评估组件中垂直间距的乘数 | &quot;1&quot; |
| radiusScale | 数字字符串 | 评估组件中边框半径的乘数 | &quot;1&quot; |

## **调色板令牌var()引用**

在元素值中使用这些var()表达式来引用调色板标记。 更新调色板令牌将自动更新使用该调色板令牌的每个元素。

| **表达式** | **引用** |
|-------------------------|-------------------------------------|
| var(—foreground) | foundation.palette.foreground |
| var(—background) | foundation.palette.background |
| var(—accent) | foundation.palette.accent |
| var(—backgroundSubtle) | foundation.palette.backgroundSubtle |
| var(—secondary) | foundation.palette.secondary |
| var(—textPrimary) | foundation.palette.textPrimary |
| var(—textInverse) | foundation.palette.textInverse |
| var(—font-heading) | foundation.fonts.heading |
| var(—font-body) | foundation.fonts.body |

## 主题json的示例

```
{
  "id": "slate",
  "name": "Slate",
  "version": "1.0.0",
  "description": "A warm, authoritative theme with cream background, Adobe red accents, and the Roboto Slab + Roboto type system",
  "author": "Content Composer",
  "source": "custom",
  "isDefault": false,
  "foundation": {
    "palette": {
      "foreground": "#1A1A1A",
      "background": "#FAF7F2",
      "accent": "#E8001C",
      "backgroundSubtle": "#F0EBE1",
      "secondary": "#D9D3C9",
      "textPrimary": "#1A1A1A",
      "textInverse": "#FFFFFF"
    },
    "fonts": {
      "heading": "Roboto Slab, Georgia, 'Times New Roman', serif",
      "body": "Roboto, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif"
    },
    "spacing": {
      "horizontal": {
        "xs": "4px",
        "s": "8px",
        "m": "12px",
        "l": "16px",
        "xl": "24px"
      },
      "vertical": {
        "xs": "4px",
        "s": "8px",
        "m": "16px",
        "l": "24px",
        "xl": "32px"
      }
    },
    "radius": {
      "none": "0px",
      "s": "4px",
      "m": "8px",
      "l": "16px",
      "full": "9999px"
    },
    "logo": null
  },
  "elements": {
    "text": {
      "lessonTitle": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "48px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "center",
        "letterSpacing": "-0.01em",
        "lineHeight": "130%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "topicTitle": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "40px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0",
        "lineHeight": "135%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "blockHeading": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "24px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0",
        "lineHeight": "140%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "subheading": {
        "fontFamily": "var(--font-body)",
        "fontSize": "20px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0.01em",
        "lineHeight": "150%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "question": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "24px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0",
        "lineHeight": "150%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "caption": {
        "fontFamily": "var(--font-body)",
        "fontSize": "13px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0.02em",
        "lineHeight": "170%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "paragraph": {
        "fontFamily": "var(--font-body)",
        "fontSize": "16px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0.01em",
        "lineHeight": "190%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "buttonLabel": {
        "fontFamily": "var(--font-body)",
        "fontSize": "14px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textInverse)",
        "textAlign": "center",
        "letterSpacing": "0.06em",
        "lineHeight": "125%",
        "textDecoration": "none",
        "textTransform": "uppercase",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      }
    },
    "canvas": {
      "background": "var(--background)"
    },
    "header": {
      "background": "var(--background)",
      "border": "1px solid var(--secondary)"
    },
    "footer": {
      "background": "var(--background)",
      "border": "1px solid var(--secondary)"
    },
    "lessonHeader": {
      "background": "var(--accent)"
    },
    "topic": {
      "background": "var(--background)",
      "border": "1px solid var(--secondary)"
    },
    "navigation": {
      "background": "var(--backgroundSubtle)",
      "border": "1px solid var(--secondary)"
    },
    "button": {
      "background": "var(--accent)"
    },
    "pagination": {
      "background": "var(--backgroundSubtle)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "paragraphBlock": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "nestedAccentColor": "var(--accent)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "imageBlock": {
      "background": "transparent",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "videoBlock": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "imageGrid": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--accent)",
      "cardShadowOffset": "0px 2px 8px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "accordion": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "carousel": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "flipCard": {
      "background": "transparent",
      "cardFrontBackgroundColor": "var(--backgroundSubtle)",
      "cardBackBackgroundColor": "var(--accent)",
      "arrowColor": "var(--textInverse)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "tabs": {
      "background": "transparent",
      "activeBg": "var(--accent)",
      "inactiveBg": "var(--backgroundSubtle)",
      "containerBg": "var(--backgroundSubtle)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "timeline": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "trackColor": "var(--secondary)",
      "progressCompletedBg": "var(--accent)",
      "progressCurrentBorder": "var(--accent)",
      "progressUnreachedBg": "var(--secondary)",
      "progressUnreachedBorder": "var(--backgroundSubtle)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "assessment": {
      "background": "transparent",
      "optionTextColor": "var(--textPrimary)",
      "optionIndicatorColor": "var(--accent)",
      "optionSelectedColor": "var(--accent)",
      "optionCheckmarkColor": "var(--textInverse)",
      "optionBackgroundColor": "var(--background)",
      "optionHoverBackgroundColor": "var(--backgroundSubtle)",
      "buttonBackgroundColor": "var(--accent)",
      "buttonTextColor": "var(--textInverse)",
      "buttonHoverBackgroundColor": "var(--accent)",
      "feedbackCorrectColor": "#D7F7E1",
      "feedbackIncorrectColor": "#FFEBE8",
      "feedbackTextColor": "#111111",
      "optionBorderCorrectColor": "#079355",
      "optionBorderIncorrectColor": "#D73220",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    }
  }
}
```
