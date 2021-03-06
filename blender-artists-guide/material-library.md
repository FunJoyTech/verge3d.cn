---
description: Using Material Library 待校订
---

# 使用材质库

## 使用材质库（Verge3D for Blender）

有关推荐工作流程的说明，请参见下文。

* 安装
* 向项目添加材质
* 建立环境
* UV映射
* 配置您的材质
* 图像分辨率
* 将纹理重定位到App文件夹

＃

### 安装

材质库在Soft8Soft商店中以主题包的形式提供，例如：

* [Essential Material Pack](https://www.soft8soft.com/product/verge3d-blender-essential-material-pack/)（基于Eevee，还包括与Blender 2.79兼容的传统GLSL材质）
* 珠宝材质包（基于Eevee，正在开发中）
* 汽车材质包（基于Eevee，正在开发中）

只需将带有库包的存档解压缩到计算机上的任何文件夹即可。给存档充气后，您将看到一个或两个文件夹（如果这是Essential Material Pack）：

* 2\_79
* 2\_80

该**2\_80**文件夹包含Blender 2.80兼容基于伊布的材质。在此文件夹中有**混合**文件（每个材质一个文件）。材质中使用的纹理位于**material\_maps**文件夹中。文件夹**环境**包含3种可用于环境的HDR图像变体（每种变体有3种分辨率：1k，2k和4k）。

该**2\_79**文件夹（只在必要的材质包中提供）包含基于Blender内部GLSL材质遗留库（这是修订库的前5名提供的唯一变量）。

＃

### 向项目添加材质

要在项目中使用库材质，请调用“ **文件/追加”**对话框。

![](https://www.soft8soft.com/docs/files/mat-library-blender/append-material.jpg)

然后导航到库文件夹，并在**混合**文件上单击一次，并添加要添加的材质。

![](https://www.soft8soft.com/docs/files/mat-library-blender/append-material2.jpg)

在**Material**文件夹上单击一次...

![](https://www.soft8soft.com/docs/files/mat-library-blender/append-material3.jpg)

...选择材质，然后单击“ **从库中追加”**按钮。

![](https://www.soft8soft.com/docs/files/mat-library-blender/append-material4.jpg)

添加材质后，您应该能够将其分配给模型。选择模型，转到“ 材质**”**选项卡，单击材质名称附近的小按钮（或“ **新建”**按钮附近没有指定材质），然后从列表中选择附加材质。

![](https://www.soft8soft.com/docs/files/mat-library-blender/assign-material.jpg)

＃

### 建立环境

基于Eevee的材质需要设置环境，否则材质将看起来黑暗且不反光。环境已经在Verge3D的默认多维数据集项目中设置，您可以将其用作自己的应用程序的基础。或者，您可以从头开始配置环境，如本[视频教程中](https://www.youtube.com/watch?v=wQ0KH4bA3Uw&t=11m34s)所示。为此，您可以在材质包的**环境**文件夹中使用HDR纹理。

＃

### UV映射

库中的大多数材质都需要模型进行UV映射。考虑展开您的模型以获得最佳效果。

＃

### 配置您的材质

大多数着色器通过调整提供输入集，您可以创建适合您需求的独特材质。

![](https://www.soft8soft.com/docs/files/mat-library-blender/material-settings.jpg)

除此之外，还有一些特殊的输入可以方便地连接烘焙的普通和AO地图。

＃

### 图像分辨率

某些材质可能使用高分辨率纹理（高达8k），这可能会影响加载速度和性能。如果您的应用程序不需要这样详细程度，请考虑重新缩放图像。

＃

### 将纹理重定位到App文件夹

为了您的应用程序的完整性（如果您将项目源转移到第三方，这很重要），您可以将附加材质使用的纹理保存在app文件夹中，如下所述。

在Blender中 打开**图像编辑器**（或**UV编辑器**）。从下拉菜单中选择一个纹理，并检查其文件路径。

![](https://www.soft8soft.com/docs/files/mat-library-blender/texture-file-paths.jpg)

如果看起来纹理是从材质库文件夹引用的，请使用菜单**Image / Save As**将其重新保存到应用程序文件夹中。

![](https://www.soft8soft.com/docs/files/mat-library-blender/texture-file-paths2.jpg)

搜索其他材质库纹理并重复此操作，直到重新定位所有纹理。

您可以通过将文件夹移动到文件系统中的其他位置来检查应用程序的完整性。打开**混合**文件并调用**文件/外部数据/报告丢失文件**。

![](https://www.soft8soft.com/docs/files/mat-library-blender/texture-file-paths3.jpg)

如果缺少**混合**文件中使用的任何纹理，则底部将显示黄色飞溅警告。

![](https://www.soft8soft.com/docs/files/mat-library-blender/texture-file-paths4.jpg)

