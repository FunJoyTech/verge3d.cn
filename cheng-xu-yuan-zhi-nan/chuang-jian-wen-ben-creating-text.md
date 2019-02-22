---
description: Creating Text 待校订
---

# 创建文本

有时您可能需要在Verge3D应用程序中使用文本 - 这里有几种方法可以执行此操作。

### 1. DOM + CSS

使用HTML通常是添加文本最简单，最快捷的方式。这是大多数Verge3D示例中用于描述性叠加的方法。

您可以向a添加内容`<div id="info">Description</div>`

并使用CSS标记绝对位于所有其他位置的z-index位置，尤其是在运行Verge3D全屏时。`#info { position: absolute; top: 10px; width: 100%; text-align: center; z-index: 100; display:block; }`

### 2.将文本绘制到画布并用作纹理

如果您希望在Verge3D场景中的平面上轻松绘制文本，请使用此方法。

### 3.在您喜欢的3D应用程序中创建模型并导出到Verge3D

如果您更喜欢使用3d应用程序并将模型导入Verge3D，请使用此方法

### 4.程序文本几何

如果您更喜欢纯粹在v3d.js中工作或创建过程和动态3D文本几何，则可以创建一个几何为v3d.TextGeometry实例的网格：

`new v3d.TextGeometry(text, parameters);`

但是，为了使其工作，TextGeometry将需要在其“font”参数上设置v3d.Font的实例。有关如何执行此操作的详细信息，每个接受参数的说明以及v3d.js分发本身附带的JSON字体列表，请参阅TextGeometry页面。

#### 例子

[WebGL /几何/文本](https://cdn.soft8soft.com/demo/examples/index.html#webgl_geometry_text)  
[WebGL / shadowmap](https://cdn.soft8soft.com/demo/examples/index.html#webgl_shadowmap)

如果Typeface已关闭，或者您想要使用不存在的字体，那么有一个带有blender的python脚本的教程，允许您将文本导出为Verge3D的JSON格式：[http](http://www.jaanga.com/2012/03/blender-to-threejs-create-3d-text-with.html)： [//www.jaanga.com/2012/03 /blender-to-threejs-create-3d-text-with.html](http://www.jaanga.com/2012/03/blender-to-threejs-create-3d-text-with.html)

### 5.位图字体

BMFonts（位图字体）允许将字形批处理为单个BufferGeometry。BMFont渲染支持自动换行，字母间距，字距调整，带标准导数的带符号距离场，多通道有符号距离场，多纹理字体等。请参阅[three-bmfont-text](https://github.com/Jam3/three-bmfont-text)。

库存字体在[A-Frame Fonts](https://github.com/etiennepinchon/aframe-fonts)等项目中可用 ，或者您可以从任何.TTF字体创建自己的字体，优化以仅包括项目所需的字符。

一些有用的工具：

* [msdf-bmfont-web ](http://msdf-bmfont.donmccurdy.com/)（基于网络）
* [msdf-bmfont-xml ](https://github.com/soimy/msdf-bmfont-xml)（命令行）
* [hiero ](https://github.com/libgdx/libgdx/wiki/Hiero)（桌面应用）

