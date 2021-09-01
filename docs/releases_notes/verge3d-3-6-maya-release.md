# Verge3D 3.6.0 for Maya版发行日志 

> 发布时间：2021年2月11日

用于Maya和[旗舰版](https://www.soft8soft.com/product/verge3d-ultimate-web-interactive-suite/)的Verge3D 3.6已经发布。有赖于此次更新支持了更多的新的着色器节点及其属性设置，电动车配置器案例已经在Maya中重制，再加上新发布的Maya材质库，Maya版本性能有了更多新的突破。此次更新显著强化了在上一个版本中引入的插件系统，增加了用于创建动态对象的拼图，并部署了一个兼容MIDI的声音合成器（附带演示案例）。您还将可用到以下列出的更多功能和改进。

## Scooter Demo - 电动车演示案例

随着对Verge3D for Maya进一步的开发，终于可以在Maya中重现之前只在Blender和3ds Max发行版中才有的[Scooter案例](https://cdn.soft8soft.com/demo/applications/scooter_maya/index.html)。这个强大的配置器应用展示了实现交互性和真实性的各种方法，您可以从中学习并在您的应用程序中重新使用。

![](https://cdn.funjoy.tech/web/blog/scooter-maya.jpg)

## 材质

材质库中包含了31个开箱即用的高质量着色器，包括金属、塑料、油漆和织物等。这些材质全都可以自定义定制，允许连接自定义纹理和法线贴图，并提供了一套现成的HDR格式环境贴图。

![](https://cdn.funjoy.tech/web/blog/maya-lib-1024x522.jpg)

请在产品页面上查看这些材质的实时[预览。](https://www.soft8soft.com/product/verge3d-maya-essential-material-pack/)请在《用户手册》中阅读如何高效使用材质库的[详细说明。](https://www.soft8soft.com/docs/manual/en/maya/Material-Library.html)

## 折射

当**StandardSurface节点**的参**Thin Walled(薄壁)**选项被关闭时启用的_折_射透明度在Verge3D支持了。

![](https://cdn.funjoy.tech/web/blog/maya-standard-surface-settings-thin-walled.jpg)

它可用来渲染冰、玻璃和类似的物体。参见文档中的[详细说明。](https://www.soft8soft.com/docs/manual/en/maya/Transparency.html#standard_surface_materials)

![](https://cdn.funjoy.tech/web/blog/maya-thin-walled-vs-refraction.jpg)

## Area Light - 面光

现在可在Verge3D中使用**Area(面光)**。

![](https://cdn.funjoy.tech/web/blog/maya-area-light.jpg)

## Sheen - 光泽

Verge3D现在支持标准表面节点的**Sheen(光泽)** 了。

![](https://cdn.funjoy.tech/web/blog/maya-sheen-settings.jpg)

它可以用来渲染写实的纤维表面，如衣服等。

![](https://cdn.funjoy.tech/web/blog/sheen_no_sheen.jpg)

## 节点

Verge3D现在支持Maya的**Vector Product(向量积)**节点了。

![](https://cdn.funjoy.tech/web/blog/maya-vector-product-node.jpg)

我们支持了**Sampler Info(采样器信息)**节点中的**Normal Camera(法线相机)**输入，因此您现在可以使用该节点的法线贴图了。您可以用此特性来创建复杂的照明效果，请参考Maya版本材质库中的展示。

![](https://cdn.funjoy.tech/web/blog/maya-sampler-info-node.jpg)

支持了 StandardSurface 和 aiStandardSurface 节点的**Transmission(透射)**输入。Transmission(透射)与不透明度不同，不影响镜面反射。

![](https://cdn.funjoy.tech/web/blog/maya-standard_surface-transmission.jpg)

## 3D文本

Verge3D现在支持通过Maya的**T面板**创建的三维文本对象。

![](https://cdn.funjoy.tech/web/blog/maya-text-add.jpg)

![](https://cdn.funjoy.tech/web/blog/maya-text-add-settings-1.jpg)

您可以选择系统字体，例如_Arial, Times Roman,Calibri_等来定义文本外观。这些文本对象在导出至Verge3D场景后，可通过拼图动态更新文本内容。

![](https://cdn.funjoy.tech/web/blog/puzzle-update-text.jpg)

此项功能归功于**OpenType.js**，如果需要启用此功能，请在应用创建时勾选**Font Converter(字体转换器)**选项。您也可以之后手动从**build**文件夹拷贝该文件到应用目录。

![](https://cdn.funjoy.tech/web/blog/create-app-font-converter.jpg)

作为替代，启用此功能后，您仍然可以使用**Bake Text(烘焙文本)**选项。如果您的应用页面中需要高度精确的文本模型，请依然使用此功能。但烘焙后的文本不能再通过拼图动态改变。

![](https://cdn.funjoy.tech/web/blog/static-text-export-settings-maya.jpg)

请阅读[手册相关页面](https://www.soft8soft.com/docs/manual/en/introduction/Text-Rendering.html)，了解Verge3D创建文本的所有可用方法。

## Verge3D插件

此次更新为自3.5版本引入的Verge3D插件系统做了进一步的改进。

##### 简化语法

首先，简化了定义新拼图的语法，使其更具声明性。因此，现在定义拼图所需的JavaScript减少了。请参阅 [对应章节](https://www.soft8soft.com/docs/manual/en/puzzles/Plugins.html) 了解更多信息。

示例插件**E-commerce(电子商务)**已经更新了新的语法，以供参考。之前的JavaScript方法依然使用。

##### 新示例

我们创建了一个示例插件，作为如何创建典型拼图块的演示：[ExamplePlugin.zip](https://www.soft8soft.com/docs/files/puzzles/ExamplePlugin.zip) （该链接也可以从插件的手册页面找到）。您可以将其解压到 puzzles/plugins 文件夹中，然后在工具箱中查看 "Example Plugin "的拼图类目。

##### 调试

插件开发的容错性更高了——插件中的任何错误都将被拦截，以防止整个编辑器崩溃。

![](https://cdn.funjoy.tech/web/blog/plugin-error.jpg)

浏览器控制台会输出更有可读性的错误信息，以帮助您调试插件。请在此[页面](https://www.soft8soft.com/docs/manual/en/puzzles/Plugins.html#plugin_errors)阅读典型错误和变通方法的完整列表。

##### 工具

在拼图上单击右键，会看到**Print Puzzle XML Tree(打印拼图XML树)**选项。它会将拼图的布局代码输出到浏览器控制台，以便您查看并将其作为自己的插件部分使用。

![](https://cdn.funjoy.tech/web/blog/print-puzzle-xml-tree.jpg)

![](https://cdn.funjoy.tech/web/blog/print-puzzle-xml-tree-console.jpg)

现在`Plug.provide()`方法现在可用于重用函数，从而产生更高效的代码。请参阅 [对应章节](https://www.soft8soft.com/docs/manual/en/puzzles/Plugins.html#block_file_code_mitigating_code_bloat) 的更多信息。

优化了从插件拼图生成的代码。因此，只有在插件被使用时，其代码才会插入到最终的**.js**文件中。

## 拼图

新的拼图_creating objects(创建对象)_实现了无中生有。您可以创建：

* 网格（box-立方体、circle-圆、cone-圆锥、cylinder-柱、sphere-球、plane-平面、teapot-茶壶、torus-环体）；
* perspective(透视)或orthographic(正交摄影机)，并设置视野；
* ambient(环境光), directional(方向光), hemispherical(半球光), point(点光), area(面光), 或spot lights(聚光灯)；
* empty objects(空对象)。

![](https://cdn.funjoy.tech/web/blog/puzzle-create-object.jpg)

默认情况下，对网格应用符合GLTF的白色PBR材质（粗糙度设置为1，金属度设置为0）。使用 **set color(设置颜色)** 和 **set(设置值)** 拼图来调整该材质。创建的对象可以以glTF格式导出，以便在Verge3D之外查看或重新导入。

除了上面提到的文本改进之外，新的拼图**create text object(创建文本对象)**可在运行时中添加**Text(文本)**对象。

![](https://cdn.funjoy.tech/web/blog/puzzle-create-text-object.jpg)

这个拼图支持从本地文件夹或远程服务器加载的**ttf**和**woff**格式字体（不支持**woff2**）。

在拼图**load scene(加载场景)**和**append scene(附加场景)**的插槽增加了**on error do(遇错误则执行...)**选项。此外，这些拼图现在加载场景的速度更快。

![](https://cdn.funjoy.tech/web/blog/puzzles-load-append-scene-on-error.jpg)

应社区[请求](https://www.soft8soft.com/topic/2d-user-controls-in-ar-ar-dom-overlay/)，在**on enter AR mode(进入AR模式)**拼图上增加了**allow HTML**选项。

![](https://cdn.funjoy.tech/web/blog/puzzle-enter-AR-mode-allow-HTML.png)

当打开时，canvas容器的所有内容都覆盖在AR内容之上。还请确保在的**Init(初始化)/configure applilcation(配置应用)**拼图中启用**transparent background(透明背景)**选项。

## 声音合成器

在声音拼图中嵌入了兼容MIDI的声音[合成器](https://github.com/g200kg/webaudio-tinysynth)。您可以使用这个拼图创建虚拟的[乐器](https://en.wikipedia.org/wiki/Rhythm_game)，为动态UI生成实时的声音，并为应用创作出各种可交互音效，包括[VR模式](https://www.youtube.com/watch?v=h1ccLiIR5Ek)。

![](https://cdn.funjoy.tech/web/blog/puzzle-synth-set-instrument-play-note-1024x331.jpg)

您也可以使用MIDI文件作为配乐，其加载速度比MP3快得多。

![](https://cdn.funjoy.tech/web/blog/puzzle-sound-midi-1024x298.jpg)

一起来演奏俄罗斯三弦琴吧！

## 其他针对Maya的改进

**Alpha mode**设置为**Auto(自动)**时，现在可以在各种情况下正确工作。此外，**Alpha**节点中的**Ramp**输出现在可以正常工作了。

如果**Ramp**节点的**Ruv Coord**没有任何输入时可以正常工作。此外，**Ramp**节点现在支持更多的斜率类型和插值模式。

分**纹Layered Texture(分层纹理)**节点现在可以在其输入按按通道单独连接的情况下工作。

深色模板“Dark Standard”现在与Blender和3ds Max版本类似，带有自己的场景。深色背景中的金色立方体。

修复了在Maya.env中没有换行符号的情况下发生的一个安装故障（感谢[反馈](https://www.soft8soft.com/topic/verge3d-plugin-not-installing-for-maya-2020-4/) ）。

我们还修复了从缩放的灯光投射阴影的问题（感谢[反馈](https://www.soft8soft.com/topic/directional-shadow-problem-in-maya/)）。

修复了一系列与不同对象之间共享材质有关的错误。修复了最近发现的一个关于UV的问题。

## 更多优化

Verge3D核心已与**Three.JS r124**版本同步，改进了现有功能，引入了新的特性。其中包括：使用了更现代的JavaScript语法(ES6)，支持添加动画，VR，VSM阴影，性能优化和稳定性提升。

![](https://cdn.funjoy.tech/web/blog/threejs-logo.png)

另外，删除了一些遗留代码，engine.js文件现在更紧凑了。

新增了一篇关于如何使用Electron创建桌面Verge3D应用的[参考文档](https://www.soft8soft.com/docs/manual/en/programmers_guide/Creating-Desktop-Apps.html)。

![](https://cdn.funjoy.tech/web/blog/electronjs-logo.svg)

其他文档页面也有许多改进（拼图、Verge3D插件等）。

Verge3D现在可在iOS上支持WebGL2.0了。请通过以下方式启用这种还处在开发中的技术：[Safari flags](https://discussions.apple.com/thread/8655829#:~:text=Click%20on%20WebGL%202.0%20to%20enable%20it.)。

![](https://cdn.funjoy.tech/web/blog/IOS_logo.svg)

## 错误修复

修复了同时为平滑着色对象和平直着色对象同时指定材质的错误。同时，为共用材质但使用不同UV或顶点颜色集合的对象指定材质现在正常了。

修复了**undo(撤销，Ctrl-Z)操作**导致拼图消失的严重[错误](https://www.soft8soft.com/topic/warning-excedeed-ctrl-z-deletes-variables-in-puzzle/)。

提升了**multi-line/exec script(多行文本/执行脚本)**拼图现在Safari浏览器中的视觉效果。拼图的整体反应速度也得到了提高。

修复了**screen-space(屏幕空间反射/折射)**拼图产生的颜色伽马值错误的问题。

之前版本中，不同数量变形目标对象在场景中投射阴影不正确的问题，已得到解决。

修复了使用**load scene(加载场景)**或**append scene(附加场景)**时，如果改变被加载或替换的场景对象材质导致应用崩溃的问题。

修复了当使用由**disable rendering(禁用渲染)**拼图时摄影机偏移的问题（感谢[反馈](https://www.soft8soft.com/topic/film-offset-lens-shift-support-for-ssaoonpause/)）。

拼图**detect collision(检测碰撞)**拼图现在可以用于其他拼图插槽了（感谢[反馈](https://www.soft8soft.com/topic/physics-demo-cloned-balls-collisions/)）。

修复了在Verge3D插件中使用特殊符号的bug（感谢[反馈](https://www.soft8soft.com/topic/custom-puzzles-less-than-symbol-must-be-escaped-in-template-literal/)）。插件拼图现在可用于在**Init(初始化)**类目了（谢谢[反馈](https://www.soft8soft.com/topic/v3d3-6pre3custom-puzzles-disappeared-in-init-tab/)）。修复了插件命名的各种问题。

修复了保存包含非拉丁字符的拼图的错误。

有赖于64位Python为web服务器提供的支持，我们修复了在保存上百个拼图时的内存溢出问题。这一定程度上改善了应用管理器的性能。

我们修复了Verge3D WordPress插件中的WooCommerce集成问题，该问题是由**WC\_ADD\_TO\_CART\_PARAMS**结构在某些情况下不存在（感谢所有[反馈](https://www.soft8soft.com/topic/woocommerce-communication-not-working/)）。

## 立即更新

一如既往，从[下载页面](https://www.soft8soft.com/get-verge3d/)获取最新版安装包吧。Verge3D旗舰版用户请从网站仪表板下载此更新。同时欢迎您在[社区论坛](https://www.soft8soft.com/forums/)中提建议与反馈。