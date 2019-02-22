---
description: 待校订
---

# 透明度（Transparency）

## 透明度

在这里，我们将展示如何在3ds Max中为标准，物理和glTF兼容的PBR材料启用透明度。

### 混合VS蒙面

作为实时3D引擎，Verge3D提供了两种处理透明对象的主要方法：alpha混合和alpha裁剪（通常使用图像蒙版）。混合可以将半透明前景色与背景色相结合，使用前景色的alpha作为混合因子。另一方面，剪切只是丢弃所有像素小于某个预定阈值（通常为0.5）的像素。![](https://www.soft8soft.com/docs/files/transparency-common/blending-vs-clipping.jpg)

混合可实现平滑过渡，通常看起来更好但计算上比剪裁更昂贵。当多边形看起来以错误的顺序呈现时，它也可能产生z排序伪像。剪切最适合可视化许多小物体（例如草或树叶）。它还会产生硬边，没有任何可能混叠的过渡。

在材质设置中 使用**Alpha模式**下拉列表在混合和蒙版之间进行选择。![](https://www.soft8soft.com/docs/files/transparency-max/alpha-mode.jpg)

### Alpha Add（又名No Depth Writes）

Verge3D还提供了一种特殊模式，用于在渲染时禁用写入深度缓冲区。这导致多边形被排除在像素深度比较之外。这些多边形以加性方式合成，有时可以帮助摆脱混合伪像。![](https://www.soft8soft.com/docs/files/transparency-common/no-depth-writes.jpg)

在材料设置的**Alpha模式**下拉列表中 选择**添加**以启用添加剂混合。

### 标准材料的透明度

可以使用材质设置中的**不透明度**调整标准材质的**透明度**。![](https://www.soft8soft.com/docs/files/transparency-max/standard-simple.jpg)

标准材料 的**不透明度**输入可用于创建有趣的依赖关系，以获得更好的真实感。![](https://www.soft8soft.com/docs/files/transparency-max/standard-falloff.jpg)

其alpha通道中具有透明度信息的图像可用作输入。也可以使用单独的alpha图像。![](https://www.soft8soft.com/docs/files/transparency-max/texture-settings-standard.jpg)

使用**Alpha模式**下拉列表在透明模式之间进行选择。

### 物理材料的透明度

可以使用相同名称的材料设置调整物理材料的透明度。![](https://www.soft8soft.com/docs/files/transparency-max/physical-transparency.jpg)

可以使用地图和图像的任意组合通过“ **透明度图”**输入来影响透明度。![](https://www.soft8soft.com/docs/files/transparency-max/physical-transparency-with-map.jpg)

使用**Alpha模式**下拉列表在透明模式之间进行选择。

### 符合glTF标准的PBR材料的透明度

为了实现此类材质的透明度，应使用与物理材质的**透明度贴图**输入相关联的单独 alpha贴图。![](https://www.soft8soft.com/docs/files/transparency-max/gltf-pbr-transparency.jpg)

使用**Alpha模式**下拉列表在透明模式之间进行选择。

