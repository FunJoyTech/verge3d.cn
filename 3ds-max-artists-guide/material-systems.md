---
description: Material Systems ——fastest已校订
---

# 材质系统

Verge3D支持3ds Max中提供的以下类型的材质：

* 以ART渲染器为参考的物理材质\(Physical with ART as reference 要求3ds Max 2017或更高版本）
* 以扫描线渲染器为参考的标准材质\(Standard with Scanline as reference\)
* glTF兼容的物理材质（Physical glTF-compliant 要求3ds Max 2017或更高版本）

＃

### 物理材质\(Physical materials\)

物理材质可在3ds Max 2017或更高版本中使用。它们比标准材质更逼真，同时更易于使用。它们特别适用于表示金属和其他非平凡表面。Verge3D使用Autodesk ART渲染器作为参考，努力重现物理材质。

![](https://www.soft8soft.com/docs/files/material-system-max/physical-material-example.jpg)

![](https://www.soft8soft.com/docs/files/material-system-max/physical-material.jpg)

您可以使用“环境和效果”窗口设置环境纹理。

![](https://www.soft8soft.com/docs/files/material-system-max/environment.jpg)

大多数3ds Max的物理材质预设都可以与Verge3D一起使用。

![](https://www.soft8soft.com/docs/files/material-system-max/physical-material-presets.jpg)

可以使用**拼图\(Puzzles\)、Float**或**Point4**材质控制器的代码对材质参数进行动画处理或更改。

![](https://www.soft8soft.com/docs/files/material-system-max/texture-atlas-animated.jpg)

＃

### 标准材质\(Standard materials\)

这些是3ds Max中的默认材质，非常适合视口显示。Verge3D努力使用Autodesk Scanline渲染器作为参考来重现它们。

![](https://www.soft8soft.com/docs/files/material-system-max/standard-material-example.jpg)

标准材质具有足够的灵活性和功能，可用于创建各种设置。

![](https://www.soft8soft.com/docs/files/material-system-max/standard-material.jpg)

可以使用Puzzles或使用Float或Point3材质控制器的代码对材质参数进行动画处理或更改。

＃

### glTF兼容材质\(glTF-compliant materials\)

如果您的内容由于某种原因需要与[glTF 2.0标准](https://www.khronos.org/news/press/khronos-releases-gltf-2.0-specification)兼容（例如在Facebook上发布您的模型），您可以使用物理材质来实现此目的，如下所述。

根据glTF 2.0标准，材质信息以一组纹理编码：基色，遮挡 - 粗糙 - 金属分别包装在R，G和B通道中，并且是正常的。

![](https://www.soft8soft.com/docs/files/material-system-max/gltf-physical-material-example.jpg)

但是，您必须使用单独的位图来遮挡，粗糙和金属。Verge3D会在导出时自动将它们组合在一个纹理中。确保在材质设置面板中启用**glTF 2.0兼容**复选框。

![](https://www.soft8soft.com/docs/files/material-system-max/gltf-physical-material.jpg)

有关如何设置这些材质的更多信息， 请参阅本用户手册的[物理材质](https://www.soft8soft.com/docs/manual/en/introduction/Physical-material.html)部分。

