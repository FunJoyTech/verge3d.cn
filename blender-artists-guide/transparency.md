---
description: Transparency 待校订
---

# 透明度

在这里，我们将展示如何在Blender中为glTF兼容的PBR，Cycles和Eevee材料启用透明度。Blender 2.7不讨论内部材料，因为它们已被弃用，不建议使用。

### 混合VS蒙面

作为实时3D引擎，Verge3D提供了两种处理透明对象的主要方法：alpha混合和alpha裁剪（通常使用图像蒙版）。混合可以将半透明前景色与背景色相结合，使用前景色的alpha作为混合因子。另一方面，剪切只是丢弃所有像素小于某个预定阈值（通常为0.5）的像素。![](https://www.soft8soft.com/docs/files/transparency-common/blending-vs-clipping.jpg)

混合可实现平滑过渡，通常看起来更好但计算上比剪裁更昂贵。当多边形看起来以错误的顺序呈现时，它也可能产生z排序伪像。剪切最适合可视化许多小物体（例如草或树叶）。它还会产生硬边，没有任何可能混叠的过渡。

### Alpha Add（又名No Depth Writes）

Verge3D还提供了一种特殊模式，用于在渲染时禁用写入深度缓冲区。这导致多边形被排除在像素深度比较之外。这些多边形以加性方式合成，有时可以帮助摆脱混合伪像。![](https://www.soft8soft.com/docs/files/transparency-common/no-depth-writes.jpg)

### 渲染顺序（又名Z-index）

Verge3D不对对象内部的多边形进行排序，而是在对象之间执行排序。这在大多数情况下提供了正确的混合，但有时可能需要强制更改对象的渲染顺序。

要修改特定对象的渲染顺序，请更改Verge3D设置面板中的数字字段。索引越小，对象的渲染时间越早。![](https://www.soft8soft.com/docs/files/transparency-blender/rendering-order.jpg)

因此，如果后方有一个透明的连续对象，并且希望前面的其他透明对象能够正确渲染，请将一些负值设置为后方对象的渲染顺序。![](https://www.soft8soft.com/docs/files/transparency-common/rendering-order-example.jpg)

### 符合glTF标准的PBR材料的透明度

要为此类材质启用透明度，请将alpha蒙版信息添加到基色纹理的Alpha通道。然后将纹理的alpha通道与Verge3D PBR节点的**Alpha**输入连接。![](https://www.soft8soft.com/docs/files/transparency-blender/gltf-PBR-ztransparency.jpg)

使用**AlphaMode**滑块更改透明度类型：0将启用混合，1 - 遮罩。

### 周期材料的透明度

在Cycles中，可以通过使用**Transparent BSDF**和**Mix Shader**节点的组合来启用**透明度**。务必打开Verge3D设置面板上的**透明度**复选框。使用透明度类型选择器在混合和屏蔽模式之间切换。![](https://www.soft8soft.com/docs/files/transparency-blender/cycles-ztransparency.jpg)

“ **混合着色器”**节点中的因子可用于定义Alpha值。您还可以将此输入与包含其RGB或Alpha通道中的Alpha信息的纹理相连接。![](https://www.soft8soft.com/docs/files/transparency-blender/cycles-ztransparency-texture.jpg)

使用**Alpha Add Transparency**复选框启用添加模式。

### Eevee材料的透明度

与Cycles类似，可以通过使用**Transparent BSDF**和**Mix Shader**节点的组合来启用Eevee材质的**透明度**。“ **混合着色器”**节点中的因子可用于定义alpha值 - 您可以直接指定值或从其他节点（如**菲涅耳）**创建依赖关系，以获得更逼真的外观。![](https://www.soft8soft.com/docs/files/transparency-blender/eevee-ztransparency.jpg)

使用“ **混合模式”**下拉列表在透明度模式之间进行选择。

