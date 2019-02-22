---
description: 待校订
---

# 物理材质（Physical Material）

## 物理材料（符合glTF标准的PBR）

如果您的内容由于某种原因需要与[glTF 2.0标准](https://www.khronos.org/news/press/khronos-releases-gltf-2.0-specification)兼容（例如在Facebook上发布您的模型），您可以使用物理材料来实现此目的，如下所述。

### 配置

Blender中的物理材料由名为**Verge3D PBR**的基于Cycles的节点组**提供**。![](https://www.soft8soft.com/docs/files/physical-material-blender/phmat_00.png)

您可以将完整的PBR材料或**Verge3D PBR**节点组添加到项目中，如下所示：选择**File&gt; Append，**然后转到**/applications/materials/pbr\_material.blend**文件。![](https://www.soft8soft.com/docs/files/physical-material-blender/phmat_01.png)

然后从**Material**类别中选择**Verge3D PBR**材料，或者从**NodeTree**类别中选择**Verge3D PBR**节点组。![](https://www.soft8soft.com/docs/files/physical-material-blender/phmat_02.png)

您可以将纹理节点连接到**Verge3D PBR**节点，如下所述。请注意，所有纹理都是可选的，可以安全地省略任何纹理。![](https://www.soft8soft.com/docs/files/physical-material-blender/phmat_03.png)

* 将**BaseColor**纹理连接到**Verge3D PBR**节点的**BaseColor**输入。纹理的**颜色空间**必须设置为“ **颜色”**。
* 将**OcclusionRoughnessMetallic**纹理连接到**Verge3D PBR**节点的**MetallicRoughness**和**Occlusion**输入。为了优化加载和渲染PBR着色器，您应该将遮挡，粗糙度和金属纹理分别打包到单个纹理的R，G和B通道中。当您仅包装粗糙度和金属纹理并保持遮挡时，也可以使用变体。此纹理的“ **颜色空间”**设置必须设置为“ **非颜色”**。
* 将**NormalMap**纹理连接到**Verge3D PBR**节点的**Normal**输入。纹理的**颜色空间**必须设置**为非颜色**。
* 将**自发光**纹理连接到**Verge3D PBR**节点的**自发光**输入。纹理的**颜色空间**必须设置为“ **颜色”**。
* 将**BaseColor**纹理的**Alpha**输出连接到**Verge3D PBR**节点的**Alpha**输入。要为材质启用透明度，必须在**BaseColor**纹理的Alpha通道中打包透明度图- 将其连接到**Alpha**输入。使用**AlphaMode**滑块更改材质的透明度类型：0 - Blend，1 - Mask。
* 您还可以在**Verge3D PBR**材质中使用一个顶点颜色图层。为此，只需将**Attribute**节点的**Color**输出（在**Input**类别中找到）连接到**Verge3D PBR**节点的**COLOR\_0**输入，并将**Use COLOR\_0**设置为1.确保指定了顶点颜色层的名称**Attribute**节点的**Name**字段。

要在Blender视口中查看**Verge3D PBR**着色器的预览，您可以将**3D视图**的显示方法设置为**渲染，**或者仅使用同一面板上的**Sneak Peak**按钮在Verge3D中预览场景。

### 使用没有纹理的PBR着色器

如果您想使用纯色而不是纹理，可以使用**BaseColorFactor**输入而不是**BaseColor**。相应地，为了设置**粗糙度**，**金属**和**自发光**，使用具有相同名称而不是颜色输入的**Verge3d PBR**节点的值输入。但是，如果没有纹理，则无法设置**遮挡**和**透明度**。![](https://www.soft8soft.com/docs/files/physical-material-blender/phmat_04.png)

### 从Substance Painter导出纹理

为了便于从Substance Painter导出纹理并确保Verge3D引擎中的最大功能，我们建议使用[Verge3D导出预设](https://www.soft8soft.com/docs/files/physical-material-blender/Verge3D_for_Blender.spexp)。![](https://www.soft8soft.com/docs/files/physical-material/phmat_09.png)

将此预设文件放在通常位于**My Documents \ Allegorithmic \ Substance Painter \ shelf \**文件夹中的**export-presets**文件夹中（如果没有则创建）。![](https://www.soft8soft.com/docs/files/physical-material-blender/phmat_08.png)

从Substance Painter导出纹理时，在导出对话框窗口中选择**Verge3d for Blender**，以便所有生成的纹理都与Verge3D基于的glTF 2.0标准兼容。

