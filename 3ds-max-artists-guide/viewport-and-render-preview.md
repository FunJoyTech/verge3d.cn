---
description: Viewport and Render Preview 待校订
---

# 视口和渲染预览

在本指南中，您可以了解如何配置3ds Max视口以匹配Verge3D外观，以及如何使用Scanline / ART渲染和ActiveShade功能获取参考图像。

* 视口设置
* 扫描线/ ART渲染
* ActiveShade模式

＃

### 视口设置

要在3ds Max中启用更好的视口预览，请在视口设置中从**标准**切换到**高质量**：![](https://www.soft8soft.com/docs/files/viewport-render-preview/viewport-settings.jpg)

在“ **材质”**子菜单中 单击“ **带有贴图的逼真材质”**（每次添加新材质时都需要执行此操作）：![](https://www.soft8soft.com/docs/files/viewport-render-preview/viewport-settings2.jpg)

在**默认着色**下的**视口背景**子菜单中 启用**环境背景**：![](https://www.soft8soft.com/docs/files/viewport-render-preview/viewport-settings3.jpg)

```text
The above-mentioned settings are pre-enabled for the default cube project.
```

但是，视口着色并不总是能够提供浏览器内渲染的准确近似值 - 例如，环境反射会忽略视口中的法线贴图等。

＃

### 扫描线/ ART渲染

如果使用标准材料，Verge3D渲染尽可能接近Scanline渲染，如果使用物理材质，则尽可能接近ART渲染。因此，您可以在3ds Max中预览场景而无需导出以便更快地进行调整。

要选择渲染器，请单击“ **渲染”**菜单中的“ **渲染设置...** ” （F10）：![](https://www.soft8soft.com/docs/files/viewport-render-preview/render-settings.jpg)

在窗口中使用“ **渲染器”**下拉列表在Scanline和ART之间切换：![](https://www.soft8soft.com/docs/files/viewport-render-preview/render-settings2.jpg)

要渲染场景，请单击“ **渲染”**（Shift + Q）：![](https://www.soft8soft.com/docs/files/viewport-render-preview/render-settings3.jpg)

随后您可以使用“ **渲染”**按钮重复渲染：![](https://www.soft8soft.com/docs/files/viewport-render-preview/render-settings4.jpg)

＃

### ActiveShade模式

为了加快迭代速度，您可以使用**ActiveShade**模式，每次修改场景时都会自动更新渲染（最适合ART渲染）。

您可以在“ **渲染设置...”**窗口中启用ActiveShade ：![](https://www.soft8soft.com/docs/files/viewport-render-preview/activeshade.jpg)

之后，您将能够将视口切换到ActiveShade模式：![](https://www.soft8soft.com/docs/files/viewport-render-preview/activeshade2.jpg)

通过这种方式，您可以近乎实时的速度更好地逼近浏览器中的内容。

