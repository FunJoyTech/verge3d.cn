---
description: Physical Material 待校订
---

# 物理材质

## 物理材质（符合glTF标准的PBR）

如果您的内容由于某种原因需要与[glTF 2.0标准](https://www.khronos.org/news/press/khronos-releases-gltf-2.0-specification)兼容（例如在Facebook上发布您的模型），您可以使用物理材料来实现此目的，如下所述。![](https://www.soft8soft.com/docs/files/physical-material/phmat_00.png)

### 配置

添加**物理材质**着色器节点，如下所示：转到“ **材质/贴图浏览器”，**然后从“ **常规**材质”列表中选择“ **物理材质** ” 。![](https://www.soft8soft.com/docs/files/physical-material/phmat_02.png)

然后，您可以将纹理节点连接到**物理材质**，如下所述。请注意，所有纹理都是可选的，可以安全地省略任何纹理。![](https://www.soft8soft.com/docs/files/physical-material/phmat_01.png)

* 将**Ambient Occlusion**纹理连接到**Base Weight Map**输入。为了在3ds Max视口和Verge3D之间获得更好的一致性，您还可以将**Ambient Occlusion**纹理连接到**Refl Color Map**输入，但这不是必需的。
* 将**基色**纹理连接到**基色图**输入。
* 将**粗糙度**纹理连接到**粗糙度贴图**输入。
* 将**Metallic**纹理连接到**Metalness Map**输入。
* 将**Normal**纹理连接到**法线贴图**节点，然后将其连接到**物理材质**的**凹凸贴图**输入。您还应将**物理材质**的“ **特殊地图”**面板中的“ **凹凸贴图量”**值设置为1.0。
* 将**发射**纹理连接到**发射颜色图**。您还应在“ **物理材质”**首选项的“ **基本参数”**面板中将排放因子设置为1.0 。
* 在**透明度**地图将从阿尔法通道采取**基色**质感。

![](https://www.soft8soft.com/docs/files/physical-material/phmat_03.png)

### 色彩空间和Gamma校正

为了正确渲染，应该考虑图像的颜色空间。所有图像，除了**基本色**和**排放**纹理，必须在线性颜色空间呈现。要执行此操作，请在“ **打开图像”**对话框中**打开图像**时，在“ **Gamma首选项”中**选择“ 使用1.0值**覆盖Gamma** ”（如下所示）。![](https://www.soft8soft.com/docs/files/physical-material/phmat_04.png)

相反，在**基色**和**排放**纹理必须sRGB色彩空间（与伽玛2.2）被打开。要实现此目的，只需将“ **自动”**保留在“ **打开图像”**对话框的伽玛首选项中即可。![](https://www.soft8soft.com/docs/files/physical-material/phmat_05.png)

### 透明纹理

如果存在，引擎将自动使用**Base Color**纹理中的**Alpha**通道作为透明度贴图。为了使透明度3ds Max的视口可见，连接**阿尔法**的通道**基本颜色**质地的**透明彩色地图**输入。![](https://www.soft8soft.com/docs/files/physical-material/phmat_06.png)

同样在纹理的**“首选项”**中，在“ **位图参数”**面板中，您应将**Mono Chanel输出**设置为**Alpha**，将**RGB通道输出设置**为**Alpha为灰色**。![](https://www.soft8soft.com/docs/files/physical-material/phmat_07.png)

### 从Substance Painter导出纹理

为了便于从Substance Painter导出纹理并确保Verge3D引擎中的最大功能，我们建议使用[Verge3D导出预设](https://www.soft8soft.com/docs/files/physical-material/Verge3D_for_3ds_Max.spexp)。![](https://www.soft8soft.com/docs/files/physical-material/phmat_09.png)

将此预设文件放在通常位于**My Documents \ Allegorithmic \ Substance Painter \ shelf \**文件夹中的**export-presets**文件夹中（如果没有则创建）。![](https://www.soft8soft.com/docs/files/physical-material/phmat_08.png)

从Substance Painter导出纹理时，在导出对话框窗口中**为3ds Max**选择**Verge3d，**以便所有生成的纹理与Verge3D基于的glTF 2.0标准兼容。

