---
description: Workflow 待校订
---

# 工作流程

下面是由Soft8Soft团队和Verge3D用户内部使用的一个典型的工作流程（案例包括[滑板车配置](https://cdn.soft8soft.com/demo/applications/scooter/index.html)演示，[茶壶加热器](https://cdn.soft8soft.com/demo/applications/teapot_heater_max/index.html)演示，[工业机器人](https://cdn.soft8soft.com/demo/applications/industrial_robot/index.html)演示，[电子商务网站](https://cdn.soft8soft.com/demo/applications/recliner_max/index.html)实体模型等）。

1. 建模和烘焙 （Modeling and Baking）
2. 选择材质系统（Choosing Material System）
3. 图片格式，分辨率和最佳实践（Image Formats, Resolution and Best Practices）
4. PBR贴图（PBR Textures）
5. 环境贴图（Environment Map）
6. HDR渲染（HDR Rendering）
7. 动画（Animation）
8. 项目（Project）
9. 拼图（Puzzles）
10. 布局和UI（Layout and UI）
11. 后期效果（Post-processing）
12. 声音（Audio）
13. 资产压缩（Asset Compression）
14. 发布（Publishing）



**3ds Max**和**Blender**版本的**Verge3D**都可以同样成功使用。

![](https://www.soft8soft.com/docs/files/workflow/teapot-heater.jpg)

＃

### 建模和烘焙 （Modeling and Baking）

在我们的团队中，使用以下建模流程。首先，创建高精度的模型。在下一阶段，通过简单地移除**suburf修改器**或**拓扑方式（retopology）**获得低面到中等面模型。模型建议不超过10万三角面片。

![](https://www.soft8soft.com/docs/files/workflow/teapot-modeling.jpg)

然后对低面模型进行展UV。最后，网格是三角形的 - 这并不是**Verge3D**的要求，而是适合用于**烘焙贴图**。此外，三角模型更适合加载到第三方编辑器，如**Substance Painter**。

根据需要，可以使用叠加的高模和低模来进行**烘焙法线**和**AO贴图**。

＃

### 选择材质系统（Choosing Material System）

我们建议3ds Max艺术家使用**standard/Scanline** 或 **physical/ART** （需要2017年或更高版本）材质。Blender艺术家应使用**Cycles**或**Eevee**（需要2.8版）材质。如果您的内容由于某种原因需要与[**glTF 2.0标准**](https://www.khronos.org/news/press/khronos-releases-gltf-2.0-specification)兼容（例如在Facebook上发布您的模型），您应该使用**Verge3D PBR着色器**（请参阅[3ds Max](https://www.soft8soft.com/docs/manual/en/introduction/Physical-material.html)，[Blender](https://www.soft8soft.com/docs/manual/en/introduction/Physical-material-Blender.html)的设置）。

您还可以查看以下视频，了解如何使用基于物理的材料：[3ds Max](https://www.youtube.com/watch?v=s_QjxCr8I6k)，[Blender](https://www.youtube.com/watch?v=wQ0KH4bA3Uw)。

＃

### 图像格式，分辨率和最佳实践（Image Formats, Resolution and Best Practices）

#### PNG或JPEG

为了获得最佳效率，我们建议您为纹理使用适用网络格式：具有最大压缩的**无损PNG**或**有损JPEG**（尽管Verge3D也支持GIF，BMP，TIFF）。根据经验，如果您不需要纹理中的Alpha通道，则首选使用JPEG而不是PNG。

#### 法线贴图

即使Alpha通道被浪费，法线贴图也应保存为PNG，因为以JPEG格式加载的法线贴图通常会产生可见的着色伪影。然而，PNG格式的图像在文件大小方面可能过于沉重，因此只有在需要时才使用法线贴图。

#### 解析度

除非你真的需要它们，否则不要使用太详细的纹理。大图像会对性能产生负面影响，耗尽手持设备上的视频内存（一直到崩溃）并显着延长负载。大多数纹理的分辨率应为1024像素或更低。

#### 小心NPOT

纹理的分辨率应遵循二次幂规则的功率（256,512,1024 px很好而1000 px很差）。无论如何，引擎在加载时重新调整所有非二次幂（NPOT）图像，因此请仔细检查纹理，以便在文件大小和加载时间方面实现最高效率。

#### 方面

纹理可以是正方形或矩形，例如1024x512像素。

#### 重复使用

始终尝试重复使用材质中的图像文件，以及着色器中的纹理贴图/节点，而不是复制。

#### 在RGBA中打包BW

如果您有多个黑白图像（AO，光照贴图，透明蒙版，颜色蒙版等），请考虑将它们打包在单个纹理的RGBA通道中。

#### 按需加载

如果您正在开发自定义程序或类似的应用程序，您可以考虑在启动时仅加载一组有限的纹理。可以使用[替换纹理](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#replace_texture)拼图在需求的基础上加载其他纹理并将其应用于模型。

```text
不要将大图作为图标重复使用 – 即使要用到更多图片，也应该预先缩放。
```

＃

### PBR纹理（PBR Textures）

**Verge3D**支持以下PBR材质模型：

* 物理材质/ART（3ds Max）
* Principled BSDF Cycles/Eevee 节点\(Blender\)
* glTF-兼容PBR \(3ds Max, Blender\)

但是，所有这三种情况都遵循在图像中打包PBR组件的相同惯例：

* AO打包在R通道中
* 粗糙度打包在G通道中
* 金属度包装在B通道中

可以使用任何合适的软件创建该组PBR纹理。在我们的团队中，我们使用Substance Painter为其创建了预设，以确保与Verge3D / glTF的兼容性。可以在以下部分中找到有关这些预设的说明和下载链接：[3ds Max](https://www.soft8soft.com/docs/manual/en/introduction/Physical-material.html)，[Blender](https://www.soft8soft.com/docs/manual/en/introduction/Physical-material-Blender.html)。

![](https://www.soft8soft.com/docs/files/workflow/substance_screenshot.jpg)

模型和烘焙的法线和AO贴图（如果有）可以通过OBJ格式加载到Substance Painter中。最终在该软件中生成3张贴图：颜色/透明度，AO/粗糙度/金属度和法线。使用 Substance Painter 的Verge3D预设导出纹理。

![](https://www.soft8soft.com/docs/files/workflow/pbr_texture_set_preview.jpg)

最后，通过使用本地PBR材质（3ds Max中的 physical / ART，Blender中的Principled BSDF Cycles / Eevee节点）或符合glTF的Verge3D PBR 材质 ，为相关模型设置PBR材质。

＃

### 环境贴图（Environment Map）

环境贴图是用于提供背景和材质反射的实时场景的关键组件。我们建议3ds Max和Blender艺术家使用HDR或JPEG格式的equirectangular图像（虽然也支持立方体贴图）。环境贴图的大小最好不超过2048x1024像素。

![](https://www.soft8soft.com/docs/files/workflow/hdr-environment.jpg)

除此之外，HDR纹理可用于模拟复杂的照明条件 - 例如，如果有太多的光源要由传统灯表示，或者它们是扩展的。

从v.2.10开始，3ds Max和Blender的默认立方体项目都包含名为environment.hdr的HDR纹理，您可以在应用中重复使用该纹理。

您还可以查看以下视频，了解如何为基于物理的管道设置HDR环境：[3ds Max](https://www.youtube.com/watch?v=s_QjxCr8I6k)，[Blender](https://www.youtube.com/watch?v=wQ0KH4bA3Uw)。

＃

### HDR渲染（HDR Rendering）

可以使用Verge3D导出设置窗口（3ds Max）中的相应复选框或“渲染”选项卡（Blender）下的Verge3D设置面板启用HDR（高动态范围）渲染流程。在此模式中，引擎使用半浮动纹理以获得更好的精度和强度范围，这对于正确渲染辉光后期处理效果（ [bloom post-process effect](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#bloom) ）非常重要。

![](https://www.soft8soft.com/docs/files/workflow/scooter-bloom.jpg)

＃

### 动画（Animation）

像往常一样为相关模型部件创建动画片段。可以使用蒙皮，整个对象，变形目标和材质动画来产生各种效果。

![](https://www.soft8soft.com/docs/files/workflow/animation.png)

您可能希望为动画对象提供易于读写的名称，以便可以在[Puzzles编辑器中](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#Animation_)轻松找到它们。

![](https://www.soft8soft.com/docs/files/workflow/advanced_animation_puzzle.jpg)

您还可以查看以下视频，了解如何创建动画：[3ds Max](https://www.youtube.com/watch?v=0dskMLdNpJ4)，[Blender](https://www.youtube.com/watch?v=doifPffYc_o)。

＃

### 项目（Animation）

在设置场景（在此期间您可以使用**Sneak Peek**按钮在浏览器中进行检查）之后，您可以使用**App Manager**创建一个持久的Verge3D项目。配置设置通常可以选择默认值。

![](https://www.soft8soft.com/docs/files/workflow/app-manager-create-new.jpg)

你可以简单地将自己**的.max**或**.blend**文件，覆盖默认立方体的**.max**或**.blend**文件，它位于您的应用程序文件夹中（verge3d / applications），请务必将所有相关的图像文件也移动到此文件夹。然后，重新打开**.max**或**.blend**文件，并以glTF格式执行导出，从而覆盖默认的**.glTF**文件。![](https://www.soft8soft.com/docs/files/workflow/default_application.png)

或者，您可以考虑首先创建一个Verge3D项目，然后使用位于应用程序文件夹中的默认**.max**或**.blend**文件开始工作，就像在初学者指南的[相关介绍](https://www.soft8soft.com/docs/manual/en/introduction/Beginner-Guide.html#App_Manager)中建议的那样。

您还可以查看以下视频，了解如何使用App Manager创建新的Verge3D项目：[3ds Max](https://www.youtube.com/watch?v=99swwn8kpCo)，[Blender](https://www.youtube.com/watch?v=ibPSGArAfJM)。

＃

### 拼图（Puzzles）

使用**拼图**创建交互式场景，用于在点击时触发动画，在悬停时显示轮廓，定位模型部件，逻辑检查等。

![](https://www.soft8soft.com/docs/files/workflow/puzzles-editor.jpg)

查看初学指南的[拼图部分](https://www.soft8soft.com/docs/manual/en/introduction/Beginner-Guide.html#Puzzles)中的教程，或直接进入[拼图参考](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html)以获取更多详细信息。

您还可以查看以下视频，了解如何使用拼图：[3ds Max](https://www.youtube.com/watch?v=Jsfqd9CIwqQ)，[Blender](https://www.youtube.com/watch?v=u-a_TJKQ8oQ)。

＃

### 布局和UI**（Layout and UI）**

在我们的无代码工作流程中，基于HTML的界面是使用外部Web设计软件构建的。任何能够导出HTML / CSS / JS文件的可视化编辑器都可以使用 - 例如，Google Web Designer（免费，跨平台）或Webflow（付费，基于云）。当然，您可以使用代码或使用其他一些工具手动构建HTML界面。

![](https://www.soft8soft.com/docs/files/workflow/webflow-project.jpg)

界面元素（菜单，按钮，信息框...）是作为嵌入Verge3D应用程序的单独网页的一部分创建的。有关更多详细信息和示例，请参阅[有关创建基于HTML的GUI](https://www.soft8soft.com/docs/manual/en/introduction/HTML-based-user-interfaces.html)的详细[指南](https://www.soft8soft.com/docs/manual/en/introduction/HTML-based-user-interfaces.html)。

＃

### 后期处理**（Post-processing）**

使用[后期效果拼图](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#Postprocessing)可以启用以下效果：辉光（在启用HDR时效果最佳），亮度对比度，灰度，景深和AO。这些效果的参数可以在运行时更改，也可以通过内部缓存以高性能设置动画。还有一个难题，可以从场景中删除所有后期效果。

![](https://www.soft8soft.com/docs/files/workflow/post-process-effects.jpg)

＃

### 音频**（Audio）**

可以使用[声音拼图](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#Sound)添加背景音乐和/或事件声音以由用户触发。您应该将**mp3**格式用于音频文件，因为它在所有Web浏览器中都受支持。

![](https://www.soft8soft.com/docs/files/workflow/sounds.jpg)

在iOS上播放声音有一个特殊限制：声音播放只能通过与网页的直接交互来启动。例如，以下设置可以在Apple的设备上随处可用：

![](https://www.soft8soft.com/docs/files/workflow/audio-example1.jpg)

但是，如果在某些事件上播放的声音不是由直接用户操作引起的，则在iOS上无效：

![](https://www.soft8soft.com/docs/files/workflow/audio-example2.jpg)

要解决此问题，您可以使用可以播放的**on event / touchstart**拼图，并在用户第一次点击屏幕时立即暂停场景中使用的所有声音：

![](https://www.soft8soft.com/docs/files/workflow/audio-example3.jpg)

以上设置可从Puzzle Library以**Sound iOS Workaround**的名称获得。

＃

### 资产压缩**（Asset compression）**

当应用程序完成时，您可以按照本手册相应[部分](https://www.soft8soft.com/docs/manual/en/introduction/Asset-compression.html)的说明优化其场景文件的加载。

您还可以查看以下视频，了解如何为您的应用启用资源压缩：[3ds Max](https://www.youtube.com/watch?v=2WHsmOohNy8)，[Blender](https://www.youtube.com/watch?v=eOY_yAJPRdw)。

＃

### 出版**（Publishing）**

您可以使用“初学指南”的“ [发布”](https://www.soft8soft.com/docs/manual/en/introduction/Beginner-Guide.html#Publishing)部分中提到的任一方法发布项目。

