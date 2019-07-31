---
description: Transparency ——fastest已校订
---

# 透明度

在这里，我们将展示如何在3ds Max中为标准\(Standard\)，物理\(Physical\)和glTF兼容的PBR\(glTF-compliant PBR\)等材质启用透明度。

### 混合VS蒙版

作为实时3D引擎，Verge3D提供了两种处理透明对象的主要方法：**Alpha混合\(alpha blending\)**和**Alpha剪裁\(Alpha clipping、通常使用图像蒙版）**。**混合\(Alpha blending\)**可以将半透明前景色与背景色相结合，使用前景色的alpha作为混合因子。对应的，**剪裁\(Alpha clipping\)**只是丢弃所有像素小于某个预定阈值（通常为0.5）的像素。

![](https://www.soft8soft.com/docs/files/transparency-common/blending-vs-clipping.jpg)

**混合**可实现平滑过渡，通常看起来更好但计算量比**剪裁**更多。当多边形看起来以错误的顺序呈现时，它也可能产生z排序伪像。**裁剪**最适合可剪裁许多小物体（例如草或树叶）。它还会产生硬边，没有任何可能混叠的过渡。

在材质设置中 使用**Alpha模式**下拉列表在混合和蒙版之间进行选择。

![](https://www.soft8soft.com/docs/files/transparency-max/alpha-mode.jpg)

### Alpha Add（又名无深度写入）

Verge3D还提供了一种特殊模式，用于在渲染时禁用写入深度缓冲区。这导致多边形被排除在像素深度比较之外。这些多边形以Add方式合成，有时可以帮助摆脱混合伪像。

![](https://www.soft8soft.com/docs/files/transparency-common/no-depth-writes.jpg)

在**材质设置\(material settings\)**的**Alpha模式\(** **Alpha Mode\)**下拉列表中 选择**添加\(Add\)**以启用添加**混合**。

### 标准材质的透明度\(Transparency for Standard Materials\)

可以使用**材质设置\(material settings\)**中的**不透明度\(Opacity\)**调整标准材质的**透明度\(Transparency\)**。

![](https://www.soft8soft.com/docs/files/transparency-max/standard-simple.jpg)

**标准材质\(standard materials\)**的**不透明度\(Opacity\)**输入可用于创建有趣的依赖关系，以获得更好的真实感。

![](https://www.soft8soft.com/docs/files/transparency-max/standard-falloff.jpg)

其Alpha通道中具有透明度信息的图像可用作输入。也可以使用单独的Alpha图像。

![](https://www.soft8soft.com/docs/files/transparency-max/texture-settings-standard.jpg)

使用**Alpha模式**下拉列表在透明模式之间进行选择。

### 物理材质的透明度\(Transparency for Physical Materials\)

可以使用相同名称的**材质设置\(material settings\)**调整物理材质的透明度，即**透明度\(Transparency\)**设置。

![](https://www.soft8soft.com/docs/files/transparency-max/physical-transparency.jpg)

可以使用贴图和图像的任意组合通过**透明度贴图\(Transparency Map\)**输入来影响透明度。

![](https://www.soft8soft.com/docs/files/transparency-max/physical-transparency-with-map.jpg)

使用**Alpha模式**下拉列表在透明模式之间进行选择。

### 符合glTF标准的PBR材质的透明度\(Transparency for glTF-compliant PBR Materials\)

为了实现此类材质的透明度，应使用与物理材质的**透明度贴图**输入相关联的单独 Alpha贴图。

![](https://www.soft8soft.com/docs/files/transparency-max/gltf-pbr-transparency.jpg)

使用**Alpha模式**下拉列表在透明模式之间进行选择。

