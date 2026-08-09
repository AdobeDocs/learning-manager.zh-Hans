---
description: 了解Content Composer如何处理Adobe Learning Manager中的课程更新 — 重新发布如何创建新的模块版本，以及ALM作者如何更新现有课程以使用最新版本。
jcr-language: en_us
title: Adobe Learning Manager中的模块版本控制
source-git-commit: ea6d296fa99686136ab08d756a20570a4681d704
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---


# Adobe Learning Manager中的模块版本控制

原始资料会随时间变化 — 策略会得到修订， SOP会获得新版本，宣传资料会得到更新。 内容书写器和ALM会作为版本更改而不是就地编辑来处理刷新，因此当您更新基础模块时，以前发布的课程会继续工作。

重新发布时，Adobe Learning Manager会将现有模块上传为内容库中的新版本，并将模块的版本号增加1。

1. 在Content Composer中，更新源文件并重新生成受影响的课程（请参阅在源材料更改时更新课程），然后重新发布。

2. 发布更新不会覆盖现有模块 — 它会在ALM内容库中与模块一起添加一个新版本。

3. ALM作者需要明确更新使用模块的每个ALM课程，以指向新版本；现有课程将继续引用构建它们的版本，直到ALM作者进行该项更改。

4. 在早期版本下已完成课程的学习者可保留其现有完成记录。 新版本适用于在更新ALM课程后注册的学习者。

重新发布之前，复习在Content Composer中重新生成的课程。 再生可以调整受影响课程中先前编辑的文本、图像或测试问题。
