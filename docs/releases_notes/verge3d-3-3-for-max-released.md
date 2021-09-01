# Verge3D 3.3 for 3ds Max发布

> 发布时间：2020年7月28日

作为面向艺术家与设计师的WebGL开发套件，Verge3D一直在可用性和易用性角度做出改进与升级。

Verge3D 3.3版显著加快了应用的加载速度及整体性能，另外为Max版本引入OSL着色器、噪波贴图和无光/投影材质，以及使用拼图将Verge3D场景导出为glTF格式的方式，并实现了动态画布纹理。此版本还增加了一些新的拼图，支持了Woocommerce的全局产品属性。阅读下文，了解更多新增特性与性能改进。

## OSL 着色器

从本版本开始，Verge3D支持开放式着色语言(OSL)贴图。这些OSL着色器在3ds Max从2019版开始得到支持，并可实时在视口中准确显示，目前支持以下贴图：大多数的**Math Color、Math Float和Math Vector**贴图，纹理和UV查找功能（例如**Bitmap Lookup**，**UVW Channel**，**UVW Transform和UVW Matcap**），以及多个过程和颜色校正贴图（例如**Checker, 4-point Gradient, Simple Gradient，Noise, Normal**等）。

![max osl example](https://cdn.funjoy.tech/web/blog/max-osl-example.jpg)

上图渲染是使用了Simple Tiles贴图的效果。

![max osl](https://cdn.funjoy.tech/web/blog/max-osl.jpg)

## 噪波贴图和无光/投影材质

Verge3D现在支持**Noise(噪波)**贴图。

![max noise map](https://cdn.funjoy.tech/web/blog/max-noise-map.jpg)

Matte/Shadow(无光/投影)材质在Verge3D中已实现。

![max material matte shadow2](https://cdn.funjoy.tech/web/blog/max-material-matte-shadow2.jpg)

## 加载速度

基于用户的关注，此版本我们将优化的重心放在优化加载效率方向。着色器编译通常是加载过程中的瓶颈，经过新版本对此执行的一系列优化，场景的加载速度有了显著地提升（部分场景达可3倍）。

![loading time optimization2](https://cdn.funjoy.tech/web/blog/loading-time-optimization2-1024x576.jpg)

这些优化措施包括：

- 引入了并行着色器编译，（在着色器逐个编译之前）若存在[KHR_parallel_shader_compile](https://www.khronos.org/registry/webgl/extensions/KHR_parallel_shader_compile/) WebGL扩展，编译将更高效；
- 优化了代表环境光的着色器；
- 优化了与实时阴影有关的着色器；
- 优化了材质着色器；
- 重组了加载流程，整个加载过程更为平滑和快速；

其中一些优化嗨提高了Verge3D的渲染性能，尤其是在低端硬件或移动设备上。

## 从应用中导出

现在可以以glTF格式导出对象、对象组或整个场景到.gltf或.glb（二进制）两种格式。

![puzzle export gltf](https://cdn.funjoy.tech/web/blog/puzzle-export-gltf.jpg)

此拼图可用于保存应用中的配置好的物体。

为了获得最佳效果，以及创建可由第三方glTF查看器（如Microsoft Windows 10的默认glTF查看器）打开的标准glTF文件（不带Soft8Soft/Verge3D扩展名），我们建议您使用[与glTF兼容的材质](https://www.soft8soft.com/docs/manual/en/introduction/FAQ.html#gltf_materials)。

## 摄影机补间轨迹

您现在可以在**tween camera(摄影机补间)**拼图中选择球形轨迹了。球形轨迹意味着摄影机将围绕中心轴，以插值距离作为半径，旋转到新位置。

![tween camera trajectory](https://cdn.funjoy.tech/web/blog/tween-camera-trajectory.jpg)

当新的视点位于模型后面时，此功能尤其有用。对于轨道摄影机，球面轨迹更为自然，可以防止摄影机在移动途中与模型发生交叉现象。

另外，**tween camera(摄影机补间)**拼图现在可以使用附近物体的坐标，坐标可以用列表或向量方式提供给拼图。

## 动态画布纹理

HTML画布现在可以作为材质纹理使用了。可以使用新引入的HTML拼图**create canvas elem**来创建`<canvas>`元素，并如之前一样为材质指定纹理，即使用**replace texture(替换纹理)**拼图。

![canvas puzzle](https://cdn.funjoy.tech/web/blog/canvas-puzzle.jpg)

一旦创建好，画布即可通过JavaScript进行绘制。您可以在以应用名开头的js文件（*your_app_name.js*）的`runCode()` 功能更新画布。为此，请在此处使用拼图中指定的ID来检索画布纹理：

```
var canvasTex = v3d.puzzles.canvasTextures['my_canvas'];
```

之后，您可以按如下方式访问HTML画布元素：

```
var canvas = canvasTex.image;
```

您可以使用可用于在HTML画布上绘制的[标准方法](https://www.w3schools.com/graphics/canvas_reference.asp)。例如，如下代码即在白色背景上画了一个蓝色的笑脸:

```
var ctx = canvas.getContext("2d");

ctx.fillStyle = 'white';
ctx.strokeStyle = 'blue';

ctx.fillRect(0, 0, canvas.width, canvas.height);

ctx.beginPath();
ctx.arc(75, 75, 50, 0, Math.PI * 2, true); // Outer circle
ctx.moveTo(110, 75);
ctx.arc(75, 75, 35, 0, Math.PI, false);  // Mouth (clockwise)
ctx.moveTo(65, 65);
ctx.arc(60, 65, 5, 0, Math.PI * 2, true);  // Left eye
ctx.moveTo(95, 65);
ctx.arc(90, 65, 5, 0, Math.PI * 2, true);  // Right eye
ctx.stroke(); 
```

最后，如果您希望更新在3D渲染中立即可见，则应该将画布纹理标记为动态：

```
canvasTex.needsUpdate = true;
```

## 新拼图

将拼图库中的**Misc(杂项)**类重命名为了**Advanced(高级)**，并在此类中新增**wait promise**和**promise value**拼图**。**

可以使用这些拼图取回来自[JavaScript promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) 中检索的数据，这些数据由**generate normal map(生成法线贴图)**和**export glTF(导出glTF)**拼图返回。

![puzzle wait promise](https://cdn.funjoy.tech/web/blog/puzzle-wait-promise.jpg)

部署了新的**Material(材质)**拼图：**get color(获取颜色)**和**get value(获取值)**先前可用的**set color(设置颜色)**和**set value(设置值)**拼图在一起。

![puzzle get color](https://cdn.funjoy.tech/web/blog/puzzle-get-color.jpg)

拼图**get object transform(获取对象位移)**现在可以使用列表同时检索三个坐标系信息。

![puzzle get object transform](https://cdn.funjoy.tech/web/blog/puzzle-get-object-transform.jpg)

这个选项可以用于直接为矢量拼图提供输出。

![puzzle get object transform use with vector](https://cdn.funjoy.tech/web/blog/puzzle-get-object-transform-use-with-vector.jpg)

## JavaScript 应用程序接口

现在在JavaScript方法 `Geometry.fromBufferGeometry()` 中可以正常使用顶点色了。

新版提供了之前仅在企业版中提供的Verge3D运行时(run-time)变体**v3d.module.js**。这一方式修复了运行示例代码时遇到的大部分问题。

如果需要在JavaScript代码中[导入](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)声明，，可以使用此运行时。这个模块也简化了您在自己的编程项目中嵌入Verge3D代码的过程。



## 更多特性

在Verge3D WordPress插件中支持了WooCommerce的全局产品属性。  
为3.2版本中引入的高级代码合并功能做了进一步的改进、加速和稳定性优化。  
为引擎着色器代码做了一些代码清理和重构。  
在稳定中做了各种小的改进，包括修复失效链接、缺失的媒体文件等。


## 故障修复

修复了应用管理器中与应用更新功能相关的一些错误，同时提高了更新的稳定性。

修复了退出应用时的内存泄漏的问题。

修复了论坛中上报使用JavaScript为对象指定自定义材质时的[崩溃问题](https://www.soft8soft.com/topic/cannot-read-property-dispose-of-null/)。

修复了论坛中上报的create environment(创建环境)拼图出现的翻转[问题](https://www.soft8soft.com/topic/create-environment-puzzle-issuewrong-direction-of-the-background-texture/)。



## 立即升级

一如既往，在[Verge3D最新发行版下载](https://mp.weixin.qq.com/s/K-AWZ8smyOUt1pm0lgmpzQ)一文中获取最新预览版的百度盘分享链接吧！欢迎通过[论坛](https://www.soft8soft.com/forums/)、微信公众号、[QQ群](https://shang.qq.com/wpa/qunwpa?idkey=c31cf6597f3ed7ce68bd47aba6bba23049bf973ac6acc59b0a5a7d1bd933b3ea)、[电子邮件](mailto:verge3d@funjoy.tech)提出建议与意见！


