# Verge3D 3.8 for Blender发行日志

> 发布时间：2021年9月23日

Verge3D for Blender 3.8正式版发布。此版本支持了iOS中原生增强现实功能，Eevee的原生环境光遮蔽，重新审视升级了3D用户界面的制作方式，光照探头中的平面反射，透明度中的alpha hashed模式，对Blender约束支持有更多改进与新增，改进和新增了拼图，另外还有大量的性能方面的优化。

## 通过USDZ格式在iOS原生浏览器中启用增强现实

目前，浏览器中的_WebXR_ 技术标准仅_适用于Android系统的Chrome浏览器_，_苹果公司_ 还在努力为移动端的 _Safari浏览器_ 做适配。但_苹果_ 有一套自己的方法，即使用Pixar通用场景描述格式(USD)实现网页中的增强现实，但这一方案相比起WebXR缺乏交互特性。

在本次更新中，我们设法在运行时中部署了一个导出器，可用 _拼图_ 中压缩输出 _.USDZ_ 格式。

![](https://www.soft8soft.com/wp-content/uploads/2021/07/puzzles-export-to-usdz.jpg)

因此，现在通过这种方法为iOS创建AR内容简单多了：首先导出到USDZ，然后替换“Enter AR”按钮的链接即可。

![](https://www.soft8soft.com/wp-content/uploads/2021/07/ar-ios-usdz.jpg)

为了达到最佳效果，我们建议使用与GLTF兼容的材质。我们已经更新了官方案例 _Augmented Reality_ ，现在其可在iOS上直接运行网页增强现实了。请使用iPhone或iPad上查看：[链接](https://cdn.soft8soft.com/demo/applications/augmented_reality/augmented_reality.html).

![](https://www.soft8soft.com/wp-content/uploads/2021/07/ar-ios-usdz-example.jpg)

此项苹果专属的技术，相比起WebXR而言还非常局限（目前在Safari中仍处在开发状态）。因此，使用此功能将不能部署动画、切换模型组件等功能，但您依然可以在运行时中执行替换材质、贴图或颜色等交互。

## 新的环境遮蔽(AO)

您现在可以使用Eevee的动态[环境遮蔽](https://docs.blender.org/manual/en/latest/render/cycles/world_settings.html#ambient-occlusion)，这是基于地面真实环境遮蔽(GTAO)技术。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/blender-ao-settings-outlined.png)

从现在起，支持 _Distance(距离)_ , _Factor(系数)_ 和 _Trace Precision(追踪精度)_ 设置了。我们推荐禁用其他两个参数的复选框，以保证一致性。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/scooter_ao.jpg)

此次对环境遮蔽的更改，在实际应用中性能表现要优于之前部署的通过SSAO拼图实现的方式——同时，此种方式可以直接在Blender中视图中预览。因此，我们决定从引擎中移除旧的SSAO效果，并让旧的SSAO拼图调用基于Eevee的新技术。

## 重新审视3D用户界面

在早期的Verge3D版本我们曾建议将按钮、面板、滑块或文本标签使用摄影机的3D子对象来实现。之后，我们引入了 _HTML拼图_ ，转而推荐 [基于Web的方法](https://www.soft8soft.com/docs/manual/en/introduction/HTML-based-user-interfaces.html) 构建UI/UX（例如使用Webflow等第三方工具）。现在到了重新审视3D用户界面的时候了，我们将为Verge3D带来3个改变游戏规则的功能特性。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/blender-3d-user-interfaces-settings2.png)

### 功能#1: 吸附边界

第一个功能特性可以将3D对象贴附到视窗边缘。新引进的设置 _Fit to Camera Edge(适应摄影机边缘)_ ，将在对象设置为摄影机的子对象后变得可见，从而精确地实现此功能。它提供了4个参数 – Horizontal(水平), Vertical(垂直), Fit Shape(适应形状), 和 Fit Offset(适应偏移)  – 无论屏幕分辨率或设备如何，您都可以使用它将面板或文本附加到预期的位置。

![](https://www.soft8soft.com/wp-content/uploads/2021/07/ring-demo-mobile.png)

### 功能#2: Visibility Breakpoints(可见性断点) 

第二个功能特性是 _Visibility Breakpoints(可见性断点)_ 。类似于 [CSS断点](https://en.wikipedia.org/wiki/Responsive_web_design) ，它们允许您为不同的屏幕分辨率或移动设备方向（横向/纵向）显示不同的对象集。同样，它也可以用来重新排列UI。

![](https://www.soft8soft.com/wp-content/uploads/2021/07/elearning-demo-improved.jpg)

### 功能#3: HiDPI合成

第三个对构建UI有帮助的功能特性是 _HiDPI Compositing(HiDPI合成)_ 。它允许您使用单独的高分辨率渲染通道来渲染对象（包括其子对象）。因此，您可以用它来显著提高应用在HiDPI屏幕上的质量，例如视网膜显示器和大多数移动设备。当渲染文本对象，或任何其他需要锋锐且精确的元素时，这可能尤其重要。

我们建议仅为使用简单着色器（例如 _自发光_ ）的对象或小对象使用此功能，以避免过高的性能消耗。

### 演示案例

我们改进了旧的演示案例应用 [E-learning](https://cdn.soft8soft.com/demo/player/player.html?load=../applications/e-learning/e-learning.gltf&logic=../applications/e-learning/visual_logic.js) 和 [Ring](https://cdn.soft8soft.com/demo/player/player.html?load=../applications/ring/ring.gltf&logic=../applications/ring/visual_logic.js) ，为UI对象使用了 _Fit to Camera Edge(适应摄影机边缘)_ 和 _HiDPI Compositing(HiDPI合成)_ 拼图。它们现在看起来更加清晰！

### 3D UI的逻辑

那么，为什么要使用3D用户界面，以及在什么情形下使用3D用户界面？毫无疑问，这种方法比使用HTML/CSS更适合3D艺术家，并且不需要外部工具。但它还有更多优点：由于UI元素是真正的3D对象，您可以为其使用着色器、灯光、动画、变形等——尽可大胆想象——使它们真正交互、无缝地集成到场景中。与基于HTML/CSS的方法相比，这可能会产生更吸引人和更有趣的效果。

## 光照探头升级

在3.7版中我们首次引入了 _light probes(光照探头)_ ，当时仅支持 _Reflection Cubemap(立方盒反射贴图)_ 这一种类型。从3.8版本起，Verge3D可以使用光照探头的 _Reflection Plane(反射平面)_ 类了，并支持Blender提供的所有设置。

![](https://www.soft8soft.com/wp-content/uploads/2021/08/blender-light-probes-reflection-plane.png)

得益于此，现在可以您可以应用中实现实时的镜面反射或地板反射了，同样也可以添加法线贴图。请查看最新的 [Load Unload(加载与卸载)](https://cdn.soft8soft.com/demo/applications/load_unload/load_unload.html) 演示案例。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/blender-load-unload-demo-with-normalmap.jpg)

为 _light probes(光照探头)_ 功能增加了新选项 - _Custom Influence(自定义影响)_ 。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/global-illumination-custom-influence.jpg)

通过此功能，您可以分辨出光照探头会影响到哪些对象，从而提升场景渲染的真实度（尤其是场景中使用了多个重叠的光探头时）。

![](https://www.soft8soft.com/wp-content/uploads/2021/06/example-light-probes-custom-influence.jpg)

我们使用此功能对官方案例 [Global Illumination(全局光照明)](https://cdn.soft8soft.com/demo/applications/global_illumination/global_illumination.html) 进行了升级和优化。在屏幕截图中，您可以看到厨房中的灯光不再影响天花板了。

## 透明度的Alpha Hashed模式

我们支持了透明度中的 _Alpha Hashed_ 模式。该特性可以去除三角形排序伪影，从而在场景渲染中实现与顺序无关的透明。这种类型的透明度只有在 _MSAA_ 已启用的情况下才可使用（MSAA是在抗锯齿选项设置为默认 _Auto(自动)_ 时的选项）。

![](https://www.soft8soft.com/wp-content/uploads/2021/06/blender-material-blend-mode-alpha-hashed.png)

## 对象约束

本次更新引入了一些新的实用的约束，并支持其他一些现有约束的设置。

新的约束有 Limit Distance(限制距离)，您可以使用Clamp Region(钳制范围) 的所有选项，Distance(j距离)，以及 Influence(影响) 参数；还有 Damped Track(阻尼跟踪)，支持其所有参数。

![](https://www.soft8soft.com/wp-content/uploads/2021/07/blender-constraints-limit-distance-damped-track.png)

Copy Transform(复制变换) 现在提供 Mix(混合) 的所有选项 及 Influence(影响) 的参数。Copy Rotation(复制旋转) 约束现在可用 Influence(影响) 参数和 Mix(混合) 参数的3个选项——Replace(替换), Before Original(初始前), 和 After Original(初始后) 。  

Copy Scale(复制缩放) 现在可以使用如下参数： Axis(轴向), Power(幂), Make Uniform(使一致), Offset(偏移), Additive(添加), 和 Influence(影响) 。

Verge3D现在支持了 _Copy Location(复制位置)_ 约束中的更多设置：_轴向_ ， _反转_ ， _偏移量_ ，以及 _影响_ 。感谢用户[建议](https://www.soft8soft.com/topic/copy-location-rotation-but-with-offset/)，抱歉迟迟没有回应。

![](https://www.soft8soft.com/wp-content/uploads/2021/07/blender-copy-location.png)

我们已经升级了 _Floor(基面)_ 约束-它现在可以用于倾斜的表面，这得益于对 _使用旋转_ 选项的支持。

![](https://www.soft8soft.com/wp-content/uploads/2021/08/blender-constraint-floor.png)

了解Verge3D中可用的Blender约束与选项详情请查看 [文档相关章节](https://www.soft8soft.com/docs/manual/en/blender/Object-Constraints.html) 。

## 更多Blender专属特性

现在Verge3D支持节点 _Object Info(对象信息)_ 了。通过它，您可以使用一个材质来绘制多个对象——例如，使用对象的顶点颜色来绘制它们。

![](https://www.soft8soft.com/wp-content/uploads/2021/07/blender-node-object-info.png)

![](https://www.soft8soft.com/wp-content/uploads/2021/07/blender-node-object-info-example.jpg)

为 _Object Properties(对象属性)_ 面板添加了一个新设置，名为 _Fix Ortho Zoom(固定正射变焦)_ 。您可以使用它来设置轨道摄影机与其子对象，开启后当用户缩放摄影机时其子对象不会移动。

![](https://www.soft8soft.com/wp-content/uploads/2021/08/blender-object-properties-fix-ortho-zoom.png)

为之前引入的 Clipping Planes(裁剪平面)  功能增加了一个新的参数 – Render Side(渲染面)，可用选项为Front(前面), Back(背面), 和 Double-sided(双面) 。可用于指定渲染复杂几何图形的切面与孔。

![](https://www.soft8soft.com/wp-content/uploads/2021/07/blender-clipping-planes-render-side.png)

## 新拼图

新增拼图 _is scene loaded(场景是否已加载)_ 。您可以使用它来检查特定场景是否已经在动态加载场景中加载。有关实际使用示例，请查看 _Load Unload(加载与卸载)_ 演示案例。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/puzzle-is-scene-loaded.jpg)

另一个新拼图 _check performance(检查性能)_ 可以用来检测用户计算机或设备的性能。在此情况中，它将使用开源库 [detect GPU](https://github.com/pmndrs/detect-gpu) 来快速运行一次benchmark，并对用户的GPU进行评级：good(良好) 或 poor(较差)。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/puzzle-check-performance-example.png)

因此，您可以使用此拼图在GPU性能较差的情况时加载简化版的场景，或者禁用一些较敏锐的图形特性（例如后期处理效果等）。另一方面，如果用户端GPU足够强大，您也可以设置参数来提升质量表现。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/webgl-report-performance-output.png)

我们在[WebGL性能检测](https://www.soft8soft.com/webglreport/) 页面中添加了此benchmark，您可以打开此页面快速检测GPU性能。

## 拼图升级

拼图 _save state(保存状态)_ 和 _undo state(撤消状态)_ 现在可以移除和创建对象。以前，它们只能改变对象的状态。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/puzzles-save-state-undo-state.png)

拼图get camera direction(获取摄影机方向) 现在可适用于在ortho(正交)摄像机。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/puzzle-get-camera-direction.png)

为 _HTML event_ 拼图添加 _load_ 选项。感谢用户[反馈](https://www.soft8soft.com/topic/feature-request-onload-function/)。

_comment(注释)_ 拼图的最大长度从50个字符增加到120个字符。

拼图 set transform(设置变换), set object direction(设置对象方向)，以及 change local transform(改变局部变换) 现在可以接受向量或列表(Vector or List) 的输入了。

![](https://www.soft8soft.com/wp-content/uploads/2021/06/puzzles-transform-vector-input.png)

拼图 set morph target(设定变形目标) 和 get morph target(获取变形目标) 现在可以使用 Text(文本) 输入了，之前进支持在下拉菜单中选择变形目标。这将有助于通过使用变量在应用中实现更加程序化的变形方法。

![](https://www.soft8soft.com/wp-content/uploads/2021/06/puzzles-morph-factor-flexible-input.png)

现在在 _add annotation(添加标注)_ 拼图中可以启用 _name(名称)_ 属性字段了，从而使标注名称与其标签不同（这在场景中有多个带有相同标签的标注时很有用）。

![](https://www.soft8soft.com/wp-content/uploads/2021/06/puzzle-add-annotation-name-input.png)

为 _limit constraint(约束)_ 和 _copy constraint(复制约束)_ 拼图分别增加了 _distance(距离)_ 和 _copy(复制)_ 选项。

![](https://www.soft8soft.com/wp-content/uploads/2021/08/puzzles-constraint.png)

_Puzzles Library(拼图库)_ 中新增一个条目：_Detect Pressed / Released(检测按下或释放)_ 。这一拼图组合可在实现与3D UI元素交互的设计情境中派上用场。一般情况下，它用于检测在选定的对象上的光标或触摸是否被按下或释放。

![](https://www.soft8soft.com/wp-content/uploads/2021/07/puzzles-library-detect-pressed-released.png)

此外，对拼图库中的其他一些条目进行了简化与注释，以使其更明了。

## API中的更改

基于Three.js(r130)库同步了Verge3D底层。代码库中的主要更改包括：

* 用于 _多渲染目标_ (MRT)的JS API；
* 在 _MeshPhysicalMaterial(物理网格材质)_ 中支持对真实感传输。
* 支持WebXR层，允许AR/VR场景之间的合成；
* 改进了多着色器材质的性能。

现在 _v3d.module.js_ 中的所有编程API都是基于类的。

我们在引擎代码中普遍添加了 _端到端_ 和 _单元测试_ 。从长远来看，它将能提高Verge3D的稳定性。

## 文档

新撰写了关于 [server side render(服务器端渲染)](https://www.soft8soft.com/docs/manual/en/programmers_guide/Server-Side-Rendering.html) 的文档。用户手册中还有其他各种更新。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/chinese-doc-1024x558.jpg)

在我们中国社区的帮助下，_用户手册_ 已全文翻译为 [中文](https://www.soft8soft.com/docs/manual/zh/index.html) 。同样，俄语版的手册也即将完成。

## 适用性提升与优化

我们创建了引擎运行时的一个变体，专门用于支持旧式浏览器，如 _Internet Explorer 11_ 或在非常早期的iPhone与iPad上运行的 _Safari_ 。当在应用创建界面勾选IE11支持选项时，应用将使用此运行时（ _v3d.legacy.js_ ）。请注意，此运行时变体非常笨重和迟缓。而默认的Verge3D运行时则更加紧凑，速度也快得多，并且适用于当今99%的浏览器。

> 请注意，微软官方已经停止了对Internet Explorer的支持。因此，我们也计划在将来在Verge3D中停止对IE的支持。

基于在WebGL着色器中使用了简化的sRGB转换技术，优化了Intel硬件上的引擎性能。

由于使用了加速结构， _Ray casting(光线投射)_ （用于 when clicked，when hovered 和 ray cast 拼图）现在在针对 _批处理几何对象_ （通过applying batch geometry 拼图获得）工作起来明显更快。

我们确保了Verge3D与即将到来的Windows11以及Windows10的ARM版本的兼容性。我们还确保了WebGL2.0系统可以在最近发布的iOS15上工作。

## 其他改进

通过 _performance profile(性能概况)_ 拼图（或通过P-P-P快捷键）输出的信息中包含了场景中使用到的 _light probes(光照探头)_ 信息。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/performance-profile-light-probes.png)

现在 _print performance(打印性能)_ 拼图（或P-P-P快速键）会输出于可能存在的潜在性能问题(红色警告信息)。例如，在下面的截图信息中表示，阴影图似乎太大(4K)，这可能会导致渲染变慢。

![](https://www.soft8soft.com/wp-content/uploads/2021/08/performance-info.png)

另一方面，我们优化了开启HDR渲染时的FXAA的质量。提高了 _HiDPI_ 渲染的稳定性。

## 错误修复

* 修复了退出AR模式时缺少背景的问题。感谢用户[反馈](https://www.soft8soft.com/topic/do-you-have-to-refresh-the-page-after-exiting-ar-mode/)。
* 修复了下载文件拼图中的性能下降问题。感谢用户[反馈](https://www.soft8soft.com/topic/save-function-slowed-on-recent-versions/)。
* 修了 _comment(注释)_ 拼图在某些情况下导致拼图编辑器奔溃的问题。感谢用户[反馈](https://www.soft8soft.com/topic/verge3d-3-8-pre3-available/page/2/#post-43657)。
* 修复了在iOS11-12旧版本系统的引擎崩溃问题。
* 修复了在最近发行的Safari 15浏览器中初始化WebXR失败的问题。感谢用户对[此问题](https://www.soft8soft.com/topic/ios-15-not-working-at-all/)的关注与呼吁。另一方面，Safari 15中部署了WebGL 2.0 —— 这意味着大量高级图形效果可以在此浏览器中使用了。

## 行动起来！

从 [下载](https://www.soft8soft.com/get-verge3d/) 页面获取最新版的Verge3D。欢迎在论坛发表您此次版本的使用心得，我们期待您的反馈！