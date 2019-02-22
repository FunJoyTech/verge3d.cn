---
description: 待校订
---

# 阴影（Shadows）

## 阴影

下面介绍在Verge3D for Blender中设置漂亮实时阴影的设置和最佳实践。![](https://www.soft8soft.com/docs/files/shadows-blender/shadows-example.jpg)

### 全局设置

由于计算量很大，默认情况下禁用阴影。您可以在Verge3D设置面板的“渲染”选项卡下启用它们。![](https://www.soft8soft.com/docs/files/shadows-blender/shadow-settings-global-blender.jpg)  


在同一面板上，**Map Type**允许您选择阴影渲染算法 - 您可以使用此开关在速度和平滑度之间进行交换。阴影质量增加，性能按照**Basic**，**PCF**，**Soft PCF**选项的顺序递减。

**Map Side**表示在阴影过程中渲染多边形的哪一侧。在设置**偏差**时应考虑选择此选项（见下文）。

### 每灯设置

可以使用Blender的原生**阴影**面板为每个单独的灯启用/禁用**阴影**。不支持此面板中的任何其他设置。![](https://www.soft8soft.com/docs/files/shadows-blender/shadow-settings-perlight-blender.jpg)  


在**Verge3D设置**面板上可以找到一些每灯设置。**Size / FOV**，**Near**和**Far**可用于调整阴影音量（越少越好）。**半径**控制模糊比，**地图大小**- 阴影纹理有多大（速度和质量之间的交易）。

**偏见**可以是正面的也可以是负面的。选择什么取决于上面提到的**Map Side**设置。如果**正面**被选中，正面**偏置**应该足够了（相反，**背面** -负）。调整**偏见**直到你摆脱自我阴影瑕疵和/或彼此平移效果。

您还可以查看以下[视频，](https://www.youtube.com/watch?v=BqK5ZK0W4xc)了解如何在Blender中设置阴影。

