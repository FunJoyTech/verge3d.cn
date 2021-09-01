# Verge3D 3.7 for Blender发行日志

> 发布时间：2021年5月26日

期待已久的更新终于来了！当然不是故意拖延，这一次我们为Verge3D带来了大量的功能升级和性能优化。Verge3D 3.7 for Blender引入了全局光照技术，以大幅提高场景的真实感，引入了剪切平面来展示复杂对象的内部结构，集成了开发移动和桌面版应用的工具，实现了在运行时中的几何图形批处理和线框模式。此外，我们在本次更新中新增了3个官方案例演示。详细介绍见下文，友情提醒：调整下坐姿慢慢看，因为本次更新说明真的很长！

## 全局照明

现在您可以使用Eevee的光照探头来大幅提高场景的真实性与氛围效果。光照探头可以使用添加物体菜单添加（目前Verge3D仅支持[立方体(盒)反射](https://docs.blender.org/manual/en/latest/render/eevee/light_probes/reflection_cubemaps.html)）。

![](https://cdn.funjoy.tech/web/blog/blender-light-probe-add.jpg)

通过考虑光照探头与对象之间的位置，实现了对**球形**和**方框**两种视差类型的支持，显著提高了真实度。您也可以使用已支持的**自定义视差选项**来覆盖这些设置。

![](https://cdn.funjoy.tech/web/blog/blender-light-probe-settings.jpg)

加载时，场景中所有镜面和漫反射照明都会烘焙到每个光照探头，并应用于场景中所有对象。

在我们新的[室内设计案例](https://cdn.soft8soft.com/demo/applications/global_illumination/global_illumination.html)中来体验间接照明吧：试试看切换白天/黑夜，开关灯，添加装饰！

![](https://cdn.funjoy.tech/web/blog/global-illumination-demo.jpg)

此外，我们增加了一个新拼图：_updating light probes(更新光照探头_)到**Objects\|对象**类目中。如果场景被更新（例如，当一个新的对象被动态加载时），您可以用它来重新渲染立方体(盒)反射(Reflection Cubemap)。

![](https://cdn.funjoy.tech/web/blog/puzzle-update-light-probe.png)

请参考[文档](https://www.soft8soft.com/docs/manual/en/blender/Lighting-and-Rendering.html#light_probes)中关于此技术的所有可用设置的介绍。

## 剪切平面

现在您可以在Blender和3ds Max中使用*剪切平面*功能了，轻松实现交互式剪切模型，以显示其内部结构。请体验此的[案例演示](https://cdn.soft8soft.com/demo/applications/clipping_planes/clipping_planes.html)，了解其效果。

![](https://cdn.funjoy.tech/web/blog/clipping-planes-interactive-demo.png)

可以在Blender中添加一个剪切平面（或多个平面），使用**添加>Verge3D****>**********剪切平面**** 菜单。

![](https://cdn.funjoy.tech/web/blog/blender-clipping-plane-properties.png)

该对象的XY轴表示平面，Z轴表示横截面的法线。

剪切平面可用做某个可拖动物体的父级，或用以在交互场景中表现动画效果。可以对横截面设置**漫射BSDF**材质，您还可以为其设置颜色和alpha值。

最后，我可以在运行时中添加剪切平面，或应用于运行时加载的对象。

## 使用Verge3D创建Android和iOS应用

没错，您现在可以将Verge3D场景和拼图打包成为移动应用，并发布在Google Play和App Store商店里了！

![](https://cdn.funjoy.tech/web/blog/farmer-mobile.jpg)

为此，我们在应用管理器中集成了一个转换器工具，可生成基于[Cordova](https://en.wikipedia.org/wiki/Apache_Cordova)的移动应用模板。Cordova是一个功能强大的开源移动开发框架。

![](https://cdn.funjoy.tech/web/blog/app-manager-mobile-desktop-converter.png)

在这个模板的基础上，您可以使用标准过程轻松地构建可在应用商店发布的应用了。请查看我们的[综合指南](https://www.soft8soft.com/docs/manual/en/introduction/Creating-Mobile-Apps.html)了解详细过程。

为了方便移动开发，我们为HTML类目中的on event拼图增加了几个选项，包括：**deviceready（就绪）**, **pause（暂停）**, 和**resume（恢复），**您可以将其与**document**选择器一起使用。

![](https://cdn.funjoy.tech/web/blog/puzzle-on-event-deviceready-pause-resume.png)

这样您就可以检测到用户在手机或平板电脑上启动、隐藏或显示您的应用的时刻，并相应地修改应用行为。最重要的是，该选项可以暂停声音，~否则用户可能会杀了您~，以免在某些场合为用户带来不好的体验。

![](https://cdn.funjoy.tech/web/blog/puzzle-on-event-deviceready-pause-resume-examples.png)

我们已使用Cordova模板将Verge3D案例**农民的旅途**小游戏转化成了iOS应用，您现在就可以下载与体验了：[iOS应用商店](https://apps.apple.com/us/app/farmers-journey/id1565673160)。

## 使用Verge3D创建桌面版应用

除了移动应用之外，您现在可以使用上面提到的转换工具创建本地桌面应用。借助于[Electron](https://en.wikipedia.org/wiki/Electron_(software_framework))，这是一个更为简单的过程。

![](https://cdn.funjoy.tech/web/blog/teapot-heater-electron.png)

应用管理器将为您自动下载由Electron打包好的二进制文件（支持Windows，macOS，Linux系统，包含64-Bit/32-Bit/ARM架构），并将你的verge3D应用转换为桌面版可执行程序。请参阅[手册页面](https://www.soft8soft.com/docs/manual/en/introduction/Creating-Desktop-Apps.html)了解详细说明。

基于此种方法，您可以创建完全脱机运行的应用，而无需首先安装Verge3D或本地web服务器了。

## 线框模式

实现了启用线框渲染的拼图，在**Materials(材质)**类目中查看。

![](https://cdn.funjoy.tech/web/blog/wireframe-puzzle.png)

## 几何图形批处理

现在可以用拼图**batch geometry**可以来合并一组指定网格的几何图形，以提高渲染性能。

![](https://cdn.funjoy.tech/web/blog/puzzle-batch-geometry.jpg)

在引擎启动时，此拼图会收集具有类似属性的网格，例如所用材质、阴影设置、渲染顺序等，合并到一起再追加到场景中。对不能合并的的对象，则保持不变。

可以打开浏览器控制台(F12)来观察此批处理是否有帮助：

![](https://cdn.funjoy.tech/web/blog/geometry-batching-in-action.jpg)

在每一行中，您都可以看到创建的批处理对象的名称。例如，“Adding batch object: big\_table\_wood\_x6\_batch”行表示具有“big\_table\_wood”材质的6个网格被合并到一个新的批处理对象“big\_table\_wood\_x6\_batch”中。

请确保不要对计划移动、动画或更新的对象使用批处理，因为合并后这些操作将不再起作用。

## 连续碰撞检测

Verge3D的物理模块现在支持所谓的_连续碰撞检测_(CCD)技术。它显著改善了对快速移动物体的模拟，如炮弹、弹球/台球/保龄球等。

![](https://cdn.funjoy.tech/web/blog/puzzles-physics-ccd.jpg)

您可以使用拼图**apply body param(应用正文参数)**的选项**ccd motion threshold(ccd运动阈值****)**和**ccd swept sphere radius**(**ccd扫描球半径)**来快速设置CCD。这种技术通过在高速运动的小物体周围创建一个大球体来代替它进行模拟碰撞。

## 用拼图进行数据处理

[Data URI](https://www.soft8soft.com/docs/manual/en/puzzles/HTML.html#data_uri) 可以被用作拼图 **read JSON** 和 **read CSV**的输入节点了。因此，这些拼图现在可以直接与**open file****(打开文件)** 和 **drop file to(拖放文件到)**拼图连接。因此现在可以加载来自本地计算机的`.json`或`.csv`文件（之前只能从网络加载）。

![](https://cdn.funjoy.tech/web/blog/puzzles-html-download-file.jpg)

此外，拼图**download fil**e**(**下载文件)****现在可以使用列表、字典或文本作为输入了（之前此处只接受Data URI）。这意味着您现在不仅可以下载图像（比如屏幕截图），还可以下载任何类型的数据，例如：已保存的配置器设置、已保存的游戏进度等。

拼图**export to glttf(**导出到gltf**)**现在以URL编码的JSON格式返回数据，让您可以轻松地编辑导出的数据。例如，您可以向对象添加一些自定义数据后再将其导出。

## 应用管理器

创建新应用的模板中，新增了**Blank Scene(**空白场景**)**模板。使用此模板创建的应用中，将缺失灯光、摄影机、默认立方体模型等，但HDR环境光贴图包含在内。使用此模板，您可以无需打开三维软件即创建程序场景。

![](https://cdn.funjoy.tech/web/blog/app-manager-create-new-app-blank-scene-template.jpg)

应用管理器设置选项内新增了**隐藏官方案例**的选项，让您的应用管理器页面更加整洁清晰。

![](https://cdn.funjoy.tech/web/blog/app-manager-settings-hide-stock-applications.png)

最后，当应用管理器的网络目录中超过1000个文件时，也可以正常显示了。感谢[反馈](https://www.soft8soft.com/topic/network-directory-listing-is-incomplete)。

## 新的拼图

通过拼图**get style**(**获取样式****)**您可以检索HTML元素的CSS属性。这个拼图在配置器类应用中可能会很有用。例如，您可以使用以下设置从某些HTML元素的背景颜色中分配材质颜色：

![](https://cdn.funjoy.tech/web/blog/puzzle-set-style.jpg)

新增拼图**get playback time(获取播放时间)**和**set playback time(设置播放时间)**，可以用于声音（音乐类型）、视频或MIDI的控制。

![](https://cdn.funjoy.tech/web/blog/get-set-playback-time-puzzles.png)

修复了在使用MIDI格式时浏览器控制台报错的问题。

HTML类目中新增拼图：**remove html elem****(****删除html元素****)**。您可以通过它指定元素ID，来从.html页面中删除元素。

![](https://cdn.funjoy.tech/web/blog/puzzle-remove-html-elem.png)

## 拼图优化

现在可以在**when dragged over(当拖动)**拼图中指定鼠标按钮了（感谢[提议](https://www.soft8soft.com/topic/when-dragged-over-left-middle-or-right-mouse-button/)）。

![](https://cdn.funjoy.tech/web/blog/puzzle-when-dragged-over-mouse-buttons.png)

由于减少了全局变量，并按需插入部分代码块，现在使用拼图生成的JavaScript代码更加紧凑了。拼图编辑器中显示的FPS计数器也得到了改进。此外，我们修复了因为物理拼图引起的部分崩溃问题。

部分拼图的右键点击菜单里现在包含了创建相关拼图的快捷选项。例如，**when clicked(当点击时)**拼图的右键菜单中可以快捷创建**picked object(被选中对象)**拼图，**show(显示)**和**hide(隐藏)**拼图右键菜单中可以快捷创建彼此，**open file(打开文件)**拼图右键菜单中可以快捷创建**opened files(已打开的文件)**拼图，**load data(加载数据)**拼图右键菜单中可以快捷创建**loaded data(已加载的数据)**拼图等，诸如此类。

![](https://cdn.funjoy.tech/web/blog/puzzles-right-click-create-associated-puzzles.jpg)

AR内容有了新的特性，拖拽拼图现在可用于AR模式了，使用此功能时请确保开启**allow HTML(允许HTML)**复选框。

![](https://cdn.funjoy.tech/web/blog/enter-ar-mode-puzzle-allow-html-option.png)

拼图**feature available(可用功能)**增加了****do not track(**不跟踪)**选项。通过它，您可以检测用户是否将其浏览器设置为[不跟踪](https://en.wikipedia.org/wiki/Do_Not_Track)模式。

![](https://cdn.funjoy.tech/web/blog/puzzle-feature-available-do-not-track.png)

**export gltf（导出gltf）**拼图现在支持**export anims(输出动画)**，运行状态也更加稳定。

![](https://cdn.funjoy.tech/web/blog/puzzle-export-to-gltf-export-anims.png)

## 面光源与阴影

**面光源**现在可以投射阴影了（效果类似于点光源）。这为调试高级照明开启了新的可能性，我们在下面这个可爱的案例中做了[演示](https://cdn.soft8soft.com/demo/applications/tea_ceremony/tea_ceremony.html)，您可以在场景加载时选择**Spot****(聚光灯)**和**Area****(面光源)**灯光。

![](https://cdn.funjoy.tech/web/blog/tea-ceremony-demo.jpg)

## 其他改进

Blender的Verge3D插件面板添加了**Documentation(文档)**和**Report a Bug(上报错误)**按钮，以便于访问。

![](https://cdn.funjoy.tech/web/blog/blender-preferences-verge3d-addon-buttons.png)

阴影现在可以和屏幕空间反射/折射一起使用。

贴图范围节点提供所有插值类型，现在Verge3D中都被支持了。

![](https://cdn.funjoy.tech/web/blog/blender-map-range-node.jpg)

[常见问题](https://www.soft8soft.com/docs/manual/en/introduction/FAQ.html)中更新并补充了新的信息。

为Verge3D插件创建了一个新的[论坛分区](https://www.soft8soft.com/forum/plugins/)，您可以在这里搜索、讨论、发布及宣传您设计制作的插件。

更新了WordPress插件，适配了最新的5.7版。

修复了使用Box投影和**混合**参数设置为0时**Image Texture（图像纹理）**节点出现类似z-fighting的问题。感谢社区[反馈](https://www.soft8soft.com/topic/some-surfaces-come-up-black/)。

优化了在导出时的压缩效率，现在启用*LZMA压缩*导出时不会再冻结3D编辑器了。

优化了文档页面的加载速度，并修复了与搜索相关的一些问题。

最后，已兼容目前仍为beta版中的Blender 2.93。

## 错误修复

之前版本中，若某应用目录中包含名字结尾为`.js`,`.css`，或`.html`的文件夹时，会导致应用管理器崩溃，该错误已在此版本中修复。此外，如果您使用`npm`，此版本起，应用管理器将忽略`npm`的`node_modules`目录，这将有效提升系统性能。

修复了轮廓线的性能问题，此效果现在可以快速响应了。

修复了**load scene(加载场景)**拼图的一个小问题。

修复了轮廓效果应用了错误的Gamma效果的问题。

修复了形态键的**基型（Basis）**在部分情况下不能正常作用的bug。

修复了在WebGL1.0中无法使用超采样抗锯齿的问题。这一问题对苹果设备的影响尤为严重。感谢[反馈](https://www.soft8soft.com/topic/disable-rendering-anti-alias-puzzle-not-working-on-ipad/)。

恢复了draw line(画线)拼图。感谢[反馈](https://www.soft8soft.com/topic/something-wrong-with-draw-line-from-object-puzzle/)。

现在将压缩文件上载到Verge3D Network的功能，现在文件小了许多。

修复了复制规程拼图时出现的错误，感谢[反馈](https://www.soft8soft.com/topic/duplicate-procedures/)。

引擎内部的专用材质**MeshShadowMaterial(****网状阴影材质)**现在可以通过JavaScript API访问。

HTML拼图**bind element(绑定元素)**在摄影机朝相反的方向看时，可以正常工作了。感谢用户[反馈](https://www.soft8soft.com/topic/unbound-html-elements)。

拼图 **set light param(设置光参数)** 和 **get light param(获取光参数)** 现在与Blender保持一致，将_光强度_ 单位设置为瓦特。

修复了Internet Explorer 11中的一些问题。顺便说一下，微软已经停止对IE浏览器的支持，因此我们可能会在将来的某个版本中弃用IE。

_视频纹理_ 现在可以使用_Wrap modes(换行模式）_ 和_texture encoding(纹理编码)_ 设置了。感谢用户[反馈](https://www.soft8soft.com/topic/video-texture-loose-repeat)。

应用管理器现在可以正确处理名称以特殊符号开头的文件（例如 \& ？\# ）了。

## 收尾

在[下载](https://www.soft8soft.com/get-verge3d/)页面获取新版本的Verge3D！请告诉我们它是如何为您工作的，或者在[论坛](https://www.soft8soft.com/forums/)提出建议。我们很乐意听到您的反馈！

