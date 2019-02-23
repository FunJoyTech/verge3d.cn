---
description: Puzzles ——fastest校订中···
---

# 拼图工具

Verge3D的Puzzles编辑器是开发任何复杂的智能Web应用程序的强大工具。通过Puzzles，您可以轻松地将行为场景添加到3D内容中，使其具有交互性并响应用户操作。这个神奇的工具既可用于快速原型制作，也可用于生产。对于3D艺术家来说，这个宝贵的工具克服了Web开发的技术障碍，从而可以将他们的创造力应用于交互式3D Web领域。

    未描述功能Logic Loops Text Numbers Lists Dicts 

* 初始化\(Initialization\)
* 事件\(Events\)
* 选择器\(Selectors\)
* 对象\(Objects\)
* 材质\(Materials\)
* 动画\(Animation\)
* 相机\(Camera\)
* 场景\(Scenes\)
* 杂项\(Misc\)
* 时间\(Time\)
* HTML\(HTML\)
* AR / VR\(AR/VR\)
* 声音\(Sound\)
* 约束\(Constraints\) 
* 后期处理\(Post-processing\)
* 变量\(Variables\)
* 程序\(Procedures\)
* 调试\(Debug\)
* 图书馆\(Library\)

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-editor.jpg)

[初学指南](https://www.soft8soft.com/docs/manual/en/introduction/Beginner-Guide.html) 中介绍了Puzzles编辑器的基本操作。

＃

### 初始化\(Initialization\)

这些拼图位于**init**选项卡下，并在初始化Verge3D应用程序之前进行解释。

＃

**“配置应用程序”\("configure application"\)**

允许设置应用程序初始化参数，包括一些WebGL上下文创建参数。

* “压缩资产”\("compressed assets"\)- 使应用程序加载**.xz**格式的压缩场景而不是常规**.gltf**文件（有关详细信息，请参阅资产压缩部分）
* “默认全屏按钮” \("default fullscreen button"\)- 使默认全屏按钮显示在右上角
* “透明背景”\("transparent background"\) - 使背景透明，以便通过WebGL画布显示网页的底层部分
* “启用屏幕截图”\("enable screenshots"\) - 将WebGL上下文的**preserveDrawingBuffer**属性设置为true，从而可以从WebGL画布正确捕获屏幕截图
* “淡化注释” \("fade annotations"\)- 当注释被场景对象阻挡时，注释会消失

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-init-configure-app.jpg)

＃

**“设置预加载器”+“百分比”\("setup preloader" + "percentage"\)**

删除默认预加载器并公开事件回调以允许处理预加载器进度事件。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-init-setup-preloader.jpg)

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-init-setup-preloader-example.jpg)

＃

### 事件\(Events\)

此类别的拼图处理用户生成的事件：鼠标点击/触摸，悬停和拖动。

＃

**“点击时”\(**"**when clicked"\)**

等待用户点击指定的3D对象（或在列表或组里的任何物体，或在启用“all objects”拼图时场景里的所有物体） – 然后在“do”插槽中运行拼图，或者如果用户点击其他内容则在“miss：do”插槽中运行拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-when-clicked.jpg)

＃

**“选择的物体”\("picked object"\)**

返回用户单击的对象。与“点击时”\("when clicked"\)拼图一起使用。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-picked-object.jpg)

＃

**“悬停时”\(“when hovered”\)**

等待用户将鼠标悬停在指定的3D对象上（或在列表或组里的任何物体，或在启用“all objects”拼图时场景里的所有物体） – 然后在“over / out：do”插槽中运行拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-when-hovered.jpg)

＃

**“悬停的物体”\("hovered object"\)**

返回用户悬停的对象。与“悬停时” \(“when hovered”\)拼图一起使用。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-hovered-object.jpg)

＃

**“移动时”\(**"when moved"**\)**

跟跟踪指定对象 （或在列表或组里的任何物体，或在启用“all objects”拼图时场景里的所有物体） 的任何移动（位置，旋转和缩放）。如果对象开始移动，则在“start：do”插槽中运行拼图，在“while moving：do”插槽中继续运行拼图，直到对象停止移动，然后在“stop：do”插槽中运行拼图。“delta”参数表示触发此拼图所需的位置，旋转或比例的任何坐标（x，y或z）的绝对变化。“period”参数表示在再次检查移动之前拼图等待的渲染帧数。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-when-moved.jpg)

＃

**“被拖动时”\("when dragged"\)**

等待用户使用鼠标拖动指定的3D对象 （或在列表或组里的任何物体，或在启用“all objects”拼图时场景里的所有物体） – 然后生成移动数据，以便在“拖动”\(”drag move”\)，“拖动旋转”\(”drag rotate”\)和“拖曳比例”\(”drag scale”\)拼图中使用。还可以捕获开始和结束拖动的事件。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-when-dragged-over.jpg)

＃

**“拖动”\(”drag move”\)**

根据“被拖动时”\("when dragged"\)拼图生成的拖动移动数据，移动指定的3D对象（或在列表或组里的任何物体，或在启用“所有物体”\(“all objects”拼图时场景里的所有物体） 。使用下拉菜单限制移动到特定轴或平面，或根本不限制。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-drag-move.jpg)

＃

**“拖动旋转”\(“drag rotate”\)**

根据”when dragged over”拼图生成的拖动移动数据旋转指定的3D对象（或指定列表或组中的所有对象，或者如果使用所有对象拼图，则为场景上的所有对象）。使用下拉菜单将旋转限制为特定轴。 “space” 下拉允许在”local” 和”parent” 坐标空间之间切换。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-drag-rotate.jpg)

＃

**“拖曳比例”\("drag scale"\)**

根据”when dragged over”拼图生成的拖动移动数据缩放指定的3D对象（或指定列表或组中的所有对象，或者如果使用所有对象拼图，则为场景上的所有对象）。使用下拉菜单限制缩放到特定轴。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-drag-scale.jpg)

＃

### 选择（Selectors）

此类别的拼图用于选择3D对象，组，动画片段和材料以适应其他拼图。

＃

**“选择对象”\(“select object”\)**

下拉列表包含场景中所有对象的按字母顺序排列的列表。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-selector-object.jpg)

＃

**“所有对象”\(“all objects”\)** 

表示场景中的所有对象，以便可以批量应用操作。不可迭代。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-selector-all-objects.jpg)

＃

**“选择组”**

下拉列表包含场景中显示的所有对象组的按字母顺序排列的列表。操作可以批量应用于一组对象。不可迭代。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-selector-group.jpg)

＃

**“选择动画”**

下拉列表包含场景中显示的所有动画片段的按字母顺序排列的列表。根据在3ds Max或Blender中应用动画的对象命名动画剪辑。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-selector-animation.jpg)

＃

**“选择材料”**

下拉列表包含场景中存在的所有材质的按字母顺序排列的列表。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-selector-material.jpg)

＃

### 对象

此类别的拼图使用对象执行各种操作。

＃

**“节目”**

使最初或以前隐藏的指定对象可见。也适用于对象列表，组（或组列表）或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-show.jpg)

＃

**“隐藏”**

使指定的对象不可见。也适用于对象列表，组（或组列表）或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-hide.jpg)

＃

**“是可见的”**

检查对象（或列表中的任何对象）当前是否可见。如果是这样，则返回true，否则返回false。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-is-visible.jpg)

＃

**“克隆”**

制作对象副本，为新对象生成唯一名称并立即将其添加到场景中。输出新对象。不适用于列表，组或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-clone.jpg)

＃

**“对齐对象”**

通过复制其变换数据将对象移动到另一个对象的位置。还复制旋转和缩放。不适用于列表，组或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-snap.jpg)

＃

**“集变换”**

根据指定的变换数据移动，旋转或缩放对象。“偏移”复选框允许相对于原始位置/旋转/比例移动/旋转/缩放对象。任何轴输入都可以留空。也适用于对象列表，组（或组列表）或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-set-transform.jpg)

＃

**“变换”**

检索对象的位置，旋转或缩放数据。不适用于列表，组或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-get-transform.jpg)

＃

**“改变局部转型”**

根据其本地空间中的指定变换数据移动，旋转或缩放对象。任何轴输入都可以留空。也适用于对象列表，组（或组列表）或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-change-local-transform.jpg)

＃

**“添加注释”**

将2D标记添加到用户可以展开的对象，方法是单击该标记以查看对象描述。也适用于对象列表，组（或组列表）或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-add-annotation.jpg)

＃

**“删除注释”**

从对象中删除以前添加的注释。也适用于对象列表，组（或组列表）或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-remove-annotation.jpg)

＃

**“更新文本对象”**

根据指定的文本内容为文本对象生成新网格。也适用于对象列表，组（或组列表）或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-update-text.jpg)

＃

**“父”**

在对象之间创建父关系，以便第一个对象跟随第二个对象的位置/旋转/缩放。不适用于列表，组或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-parent.jpg)

＃

**“距离”**

输出两个指定对象之间的距离。不适用于列表，组或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-distance.jpg)

＃

**“大纲”**

对指定对象应用或删除轮廓效果。要解锁此拼图，请在3ds Max或Blender中启用轮廓效果。也适用于对象列表，组（或组列表）或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-outline.jpg)

＃

### 物料

＃

**“分配材料”**

将材质指定给对象，完全替换旧材质。也适用于对象列表，组（或组列表）或所有对象拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-materials-assign-material.jpg)

＃

**“替换纹理”**

使用从提供的URI加载的纹理替换为指定材质找到的纹理。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-materials-replace-texture.jpg)

＃

**“设置颜色”**

设置为指定材料找到的颜色参数的R，G和B分量。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-materials-set-color.jpg)

**对于3ds Max用户：**您可以在材质（标准或物理）中添加**控制器**，其名称将显示在下拉菜单中。此外，还可以访问标准或物理材料节点的漫反射（或“基础”）颜色输入。对于**符合glTF标准的PBR**材料，**基本颜色**和**发射**输入只能通过此拼图访问。

**对于Blender用户：**您可以在基于节点的材料（GLSL Internal，Cycles，Eevee）中添加**RGB**节点，它们的名称将显示在下拉菜单中。此外，还可以访问材料，扩展材料，BSDF Principled，BSDF Diffuse和BSDF Glossy节点的漫反射（或“基础”）颜色输入。对于**符合glTF标准的PBR材料**，**BaseColor**和**Emissive**输入只能通过此拼图访问。

此拼图还可用于修改环境着色器。在下拉列表中，环境着色器的名称以“Verge3D\_Environment”开头。

有关Verge3D用户可用材料的更多信息，请参阅本手册的材料系统概述章节：[3ds Max](https://www.soft8soft.com/docs/manual/en/introduction/Material-System-Max.html)，[Blender](https://www.soft8soft.com/docs/manual/en/introduction/Material-System-Blender.html)。

＃

**“设定值”**

设置为指定材料找到的值参数。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-materials-set-value.jpg)

**对于3ds Max用户：**您可以在材质（标准或物理）中添加**控制器**，其名称将显示在下拉菜单中。在**符合glTF标准的PBR**材料的情况下，可以通过以下难题访问以下输入：金属度，粗糙度，凹凸比例，发射强度和环境图强度。

**对于Blender用户：**您可以在基于节点的材料（GLSL Internal，Cycles，Eevee）中添加**Value**节点，它们的名称将显示在下拉菜单中。在**符合glTF标准的PBR**材料的情况下，可以通过以下难题访问以下输入：金属度（PBR节点中的MetallicFactor），粗糙度（PBR节点中的RoughnessFactor），bumpScale（PBR节点中的NormalScale），emissiveIntesity（PBR节点中的EmissiveFactor）和envMapIntensity （未在PBR节点中显示）。

此拼图还可用于修改环境着色器。在下拉列表中，环境着色器的名称以“Verge3D\_Environment”开头。

有关Verge3D用户可用材料的更多信息，请参阅本手册的材料系统概述章节：[3ds Max](https://www.soft8soft.com/docs/manual/en/introduction/Material-System-Max.html)，[Blender](https://www.soft8soft.com/docs/manual/en/introduction/Material-System-Blender.html)。

＃

**“得到材料”**

检索分配给对象的材质的名称。如果为同一对象分配了多个材质，则返回第一个。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-get-material.jpg)

＃

### 动画

此类别的拼图使用动画片段执行操作。

＃

**“播放动画”**

播放动画片段。动画剪辑名称对应于在3ds Max或Blender中为其指定动画的对象（每个对象只能分配一个动画片段）。使用动画选择器拼图为此拼图提供动画剪辑。

使用“from”和“to”字段指定帧范围。使用“速度”字段指定播放速度。“反转”复选框启用反向播放。下拉菜单可用于更改动画模式 - “auto”允许使用3ds Max或Blender中指定的动画模式，而其他模式则覆盖3ds Max或Blender中指定的设置。

动画结束后处理“完成时：完成”插槽中的拼图（这仅对“一次”动画模式有效）。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-play.jpg)

此拼图也适用于动画片段列表。

＃

**“停止动画”**

停止播放动画片段。也适用于动画片段列表。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-stop.jpg)

＃

**“暂停动画”**

暂停动画片段播放，以便稍后从暂停的帧开始恢复。也适用于动画片段列表。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-pause.jpg)

＃

**“恢复动画”**

恢复以前暂停的动画片段。也适用于动画片段列表。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-resume.jpg)

＃

**“设置动画帧”**

将动画片段设置为指定的帧。也适用于动画片段列表。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-set-animation-frame.jpg)

＃

**“是动画片”**

检查当前是否正在播放动画片段（或列表中的任何动画）。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-is-playing.jpg)

＃

**“搞动画”**

检索指定对象的动画片段。也适用于对象列表，组（或组列表）或所有对象拼图。返回值始终是动画片段列表（即使只有一个动画片段）。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-get-animation.jpg)

＃

### 相机

此类别的拼图使用相机执行操作。

＃

**“看着”**

平滑地为活动相机设置动画，使其最终以指定对象为目标。numeric参数指定执行动画的时间段（以秒为单位）。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-lookat.jpg)

＃

**“补间相机”**

平滑地为活动相机设置动画，使其位置最终更改为指定对象的位置，并且相机将指向另一个指定对象。numeric参数指定执行动画的时间段（以秒为单位）。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-tween-camera.jpg)

＃

**“设置有源相机”**

使指定的相机处于活动状态。这可用于更改摄像机控制模式（“轨道”与“飞行”与“无控制”），视野和其他设置。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-set-active.jpg)

＃

### 场景

此类别的拼图通过场景执行加载/卸载操作。

＃

**“加载场景”+“百分比”**

触发此拼图时，将卸载当前场景并从指定的.gltf文件加载新场景。加载完成后，触发“加载时”插槽中的拼图。还可以启用“on progress do”插槽。放置在此插槽中的拼图在装载期间不断触发，并可利用“百分比”拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-load-scene.jpg)

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-load-scene-example.jpg)

＃

**“追加场景”+“百分比”**

触发此拼图时，将从指定的.gltf文件加载新场景并将其附加到当前场景。加载完成后，触发“加载时”插槽中的拼图。还可以启用“on progress do”插槽。放置在此插槽中的拼图在装载期间不断触发，并可利用“百分比”拼图。默认情况下，“追加场景”拼图不会从新场景加载相机和灯光。可以在拼图选项中更改此行为。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-append-scene.jpg)

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-append-scene-example.jpg)

＃

**“卸载场景”**

从应用程序卸载指定的场景或其部分。使用空文本值以卸载所有场景。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-unload-scene.jpg)

＃

### 杂项

杂项拼图在高层次上执行各种操作。

＃

**“打开网页”**

触发此拼图时，将根据下拉选项在新的或相同的浏览器选项卡中打开指定的URL。当从Puzzles编辑器触发时，它会在离开选项卡之前要求用户确认。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-open-web-page.jpg)

＃

**“社交分享链接”**

生成用于在流行社交媒体中共享应用程序的链接。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-social-share-link.jpg)

＃

**“替换场景”**

这个拼图已被弃用。请改用加载场景。

触发此拼图时，将卸载当前场景并从指定的**.gltf**文件加载新场景。加载完成后，触发“加载时”插槽中的拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-replace-scene.jpg)

＃

**“调用JS函数”**

执行应用程序的JavaScript代码中指定的函数。可选择传递要用作函数参数的参数。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-call-js-function.jpg)

为了将函数添加到JavaScript代码，打开应用程序**的.js**文件（例如，my\_awesome\_app.js位于verge3d /应用/ my\_awesome\_app）用任何文本编辑器。搜索“prepareExternalInterface”并在该声明中添加您的函数（在大括号之间），使它看起来像这样：`function prepareExternalInterface(app) { app.ExternalInterface.myJSFunction = function(numericArg, textArg) { alert('Got some params from Puzzles: ' + numericArg + ' and ' + textArg); } }`

＃

**“当从JS调用时”**

允许从应用程序的JavaScript代码触发Puzzles。（可选）检索从JavaScript代码传递的参数，并将它们保存为变量以供“do”插槽中的拼图使用。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-when-called-from-js.jpg)

为了从JavaScript代码触发这个难题，打开应用程序**的.js**文件（例如，my\_awesome\_app.js位于verge3d /应用/ my\_awesome\_app）用任何文本编辑器。搜索“runCode”并在该声明中添加一个函数调用（在大括号之间），这样它看起来像这样：`function runCode(app) { app.ExternalInterface.myJSCallback('Hello, Puzzles!', 80); }`

＃

**“加载数据”**

尝试从指定位置加载数据。无论尝试是否成功，都会解释“曾经准备就绪”插槽中的难题。可以通过加载的数据拼图访问检索到的数据。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-load-data.jpg)

＃

**“发送数据”**

尝试使用异步[POST HTTP](https://en.wikipedia.org/wiki/POST_%28HTTP%29)请求将指定数据发送到远程位置。无论尝试是否成功，都会解释“曾经准备就绪”插槽中的难题。如果有任何响应数据，可以通过加载的数据拼图访问它。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-send-data.jpg)

＃

**“加载数据”**

返回由加载数据检索的数据或发送数据拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-loaded-data.jpg)

＃

**“读JSON”**

将文本解释为[JavaScript Object Notation](https://en.wikipedia.org/wiki/JSON#Example)数据。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-read-JSON.jpg)

＃

**“读取CSV”**

将文本解释为[逗号分隔值](https://en.wikipedia.org/wiki/Comma-separated_values#Example)。返回表行列表，每行表示为值列表。可以使用下拉列表选择分隔符以对应CSV文件的导出设置。“从行”值表示从顶部开始将跳过多少行。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-read-CSV.jpg)

表行和值由它们的数字索引从0开始访问。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-csv-example.jpg)

＃

**“拯救国家”**

保存指定对象的状态和/或由其名称指定的变量值。克隆对象并将其存储在内存中。检索变量的值并将其存储在每个指定变量名的内存中。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-save-state.jpg)

如果多次调用此拼图，则按顺序保存状态，以便可以使用撤消状态拼图返回任何先前的状态。

＃

**“撤消状态”**

恢复使用保存状态拼图保存的对象和/或变量的状态。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-undo-state.jpg)

如果多次调用此拼图，则从保存的序列（如果有）恢复状态，这使得可以从堆栈返回任何先前保存的状态。

＃

**“所有变量名称”**

返回一个列表，其中包含Puzzles中使用的所有变量的名称。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-all-variable-names.jpg)

＃

**“按名称变量值”**

返回由其名称指定的变量的值。此拼图与标准变量值拼图的工作方式类似，但不需要从预定义的下拉菜单中选择变量。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-variable-value-by-name.jpg)

＃

**“下订单”**

使用“标题”，“内容”和“总价格”字段以及可选的屏幕截图组成隐藏的订单表单，并根据Wordpress插件部分中说明的规范将此表单提交到指定的URL。默认情况下，订单表单将提交给[演示订购页面](https://www.soft8soft.com/order-form-demo)。

Verge3D附带一个免费的Wordpress插件，可以处理这个拼图提交的请求。收到这样的请求后，这个Wordpress插件呈现一个页面，其中包含扩展形式，并附有联系和注释字段，嵌入式屏幕截图和验证码。最终填写的表单由客户提交，并在Wordpress管理界面中创建新订单。客户和销售经理都通过电子邮件通知订单。

有关设置信息，请参阅本手册的Wordpress插件部分。

请务必在配置应用程序拼图中启用屏幕截图，否则屏幕截图可能会以黑色呈现。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-place-order.jpg)

＃

**“功能可用”**

检查用户浏览器中是否提供从下拉列表中选择的功能。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-misc-feature-available.jpg)

＃

### 时间

这些拼图产生基于时间的事件。

＃

**“后”**

等待指定的时间，然后触发放置在“do”插槽内的拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-after.jpg)

＃

**“每”**

等待指定的时间，然后触发放置在“do”插槽内的拼图。然后重复。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-every.jpg)

＃

**“每一帧”**

触发每个渲染帧放置在“do”插槽内的拼图（通常以每秒60帧的速率）。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-every-frame.jpg)

＃

**“过去”**

输出从前一个渲染帧传递的时间量（以秒为单位）。可以与“每帧”拼图一起使用来实现与帧无关的动画。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-time-elapsed.jpg)

＃

### HTML

这些拼图操纵HTML DOM元素。

＃

**“添加HTML元素”**

创建具有指定[类型](https://www.w3schools.com/tags/default.asp)和标识符（对应于“id”属性）的HTML元素，并将其附加到文档正文。还将其样式属性“position”设置为“absolute”。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-add-html-elem.jpg)

＃

**“获取属性”**

从具有指定标识的HTML元素中 获取[属性](https://www.w3schools.com/tags/ref_attributes.asp)。如果HTML元素位于外部HTML文档（使用**iframe**嵌入Verge3D应用程序的**.html**文件）中，则应启用“在父文档中”复选框。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-get-attr.jpg)

＃

**“设置属性”**

为具有指定标识的HTML元素 设置[属性](https://www.w3schools.com/tags/ref_attributes.asp)。如果HTML元素位于外部HTML文档（使用**iframe**嵌入Verge3D应用程序的**.html**文件）中，则应启用“在父文档中”复选框。也适用于元素ID列表。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-set-attr.jpg)

＃

**“设定风格”**

为具有指定标识的HTML元素 设置[CSS属性](https://www.w3schools.com/cssref/default.asp)。如果HTML元素位于外部HTML文档（使用**iframe**嵌入Verge3D应用程序的**.html**文件）中，则应启用“在父文档中”复选框。也适用于元素ID列表。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-set-style.jpg)

＃

**“设置CSS规则”**

为指定的CSS规则（在应用程序的**.css**文件中找到） 设置[CSS属性](https://www.w3schools.com/cssref/default.asp)。如果样式表属于外部HTML文档（使用**iframe**嵌入Verge3D应用程序的**.html**文件），则应启用“在父文档中”复选框。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-set-css-rule.jpg)

＃

**“事件”**

为具有指定标识的HTML元素 注册[事件侦听](https://www.w3schools.com/jsref/dom_obj_event.asp)器。如果HTML元素位于外部HTML文档（使用**iframe**嵌入Verge3D应用程序的**.html**文件）中，则应启用“在父文档中”复选框。一旦发生事件，触发放置在“do”槽中的拼图。也适用于元素ID列表。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-on-event.jpg)

＃

**“获取事件属性”**

输出由“事件”拼图生成的事件的[属性](https://www.w3schools.com/jsref/obj_events.asp)值。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-get-event-property.jpg)

＃

**“文献”**

表示[DOM文档对象](https://www.w3schools.com/jsref/dom_obj_document.asp) - HTML文档的根节点。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-document.jpg)

＃

**“身体”**

表示[DOM正文对象](https://www.w3schools.com/jsref/dom_obj_body.asp) - HTML文档的&lt;body&gt;元素。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-body.jpg)

＃

**“画线”**

通过动态更新的线将指定的3D对象与指定的HTML元素连接起来。如果HTML元素位于外部HTML文档（使用**iframe**嵌入Verge3D应用程序的**.html**文件）中，则应启用“在父文档中”复选框。您还可以设置线条的宽度，颜色和偏移量。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-draw-line.jpg)

＃

**“删除线”**

从指定对象中删除以前创建的行。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-remove-line.jpg)

＃

**“绑定元素”**

使指定的HTML元素跟随屏幕空间中指定3D对象的中心。如果HTML元素位于外部HTML文档（使用**iframe**嵌入Verge3D应用程序的**.html**文件）中，则应启用“在父文档中”复选框。一个更加可自定义的“添加注释”拼图的变体。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-bind-element.jpg)

＃

**“初始化全屏”**

使指定的HTML元素表现为全屏模式按钮 - 首次单击它会触发进入全屏模式，第二次单击会退出全屏模式。进入或退出全屏模式时会触发放置在“on enter do”和“on do do”插槽中的拼图。如果浏览器不支持全屏（例如iOS Safari），则会触发放置在“if unavailable do”中的拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-init-fullscreen.jpg)

＃

**“截图”**

获取视口的屏幕截图并以[数据URI](https://en.wikipedia.org/wiki/Data_URI_scheme#Examples_of_use)格式输出。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-html-take-screenshot.jpg)

＃

### AR / VR

这些拼图用于实现基于Web的增强现实（AR）和虚拟现实（VR）体验，这些体验运行在开发中的浏览器技术之上，称为[WebXR](https://github.com/immersive-web/webxr/blob/master/explainer.md)（Web上的eXtended Reality）。

这些拼图被认为是实验性的，因为WebXR正在快速发展，浏览器预览版本每天都在变化。目前AR拼图被禁用，直到规格稳定。为了使用VR拼图，我们建议在创建[新项目](https://www.soft8soft.com/docs/manual/en/introduction/Workflow.html#Project)时打开**Legacy VR**复选框。

＃

**“初始VR模式”**

初始化虚拟现实系统。如果成功，将触发“if available do”中的拼图。否则，如果浏览器不支持VR或VR硬件未找到，则触发“if unavailable do”插槽中的拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-ar-vr-init-vr-mode.jpg)

有关支持的VR设备和最佳实践的更多信息，请参阅“ [用户手册”](https://www.soft8soft.com/docs/manual/en/introduction/AR-VR-development.html)。

＃

**“进入VR模式”**

进入虚拟现实模式。进入或退出VR模式时会触发放置在“on enter do”和“on do do”插槽中的拼图。如果无法建立VR会话，则会触发放置在“if unavailable do”中的拼图。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-ar-vr-enter-vr-mode.jpg)

＃

### 声音

这些拼图用于加载和播放HTML5声音。

＃

**“加载声音”**

创建[HTML5音频](https://www.w3schools.com/html/html5_audio.asp)元素并使用指定的URL加载声音文件。此拼图还将创建的音频元素添加到内存缓存中，以便具有相同URL的此拼图的任何后续使用不会再次加载相同的声音文件。建议使用**.mp3**格式，因为大多数Web浏览器都支持。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-sound-load-sound.jpg)

＃

**“播放声音”**

开始播放音频。如果启用，循环复选框将重复声音播放。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-sound-play-sound.jpg)

＃

**“暂停声音”**

暂停音频播放。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-sound-pause-sound.jpg)

＃

**“倒带声”**

设置音频元素以从头开始播放声音。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-sound-rewind-sound.jpg)

＃

**“设定音量”**

设定音量。输入音量被钳制到0.0-1.0范围。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-sound-set-volume.jpg)

＃

**“正在玩”**

检查当前是否正在播放声音。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-sound-is-playing.jpg)

＃

### 约束

这些拼图用于约束物体运动。如果对象不是另一个对象的父级，则约束将在世界空间中起作用。否则它们将在父对象的空间中工作 - 您可以在3ds Max或Blender中选择父对象以显示坐标轴。

＃

**“极限变换”**

设置约束以限制沿选定轴的对象位置，旋转或缩放。指定的id应该是唯一的，否则将替换具有相同的现有约束。“min”和“max”槽指定允许移动之间的范围。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-constraints-limit-transform.jpg)

＃

**“复制变换”**

设置约束以从另一个对象复制对象位置，旋转或缩放。指定的id应该是唯一的，否则将替换具有相同的现有约束。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-constraints-copy-transform.jpg)

＃

**“操作”**

使用分配给指定对象的指定id删除，静音或取消静音约束。分配给此对象的其他约束（如果有）将保持不变。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-constraints-operations.jpg)

＃

### 后期处理

这些拼图用于设置各种后处理效果。

＃

**“盛开”**

启用绽放效果。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-postprocessing-bloom.jpg)

＃

**“亮度/对比度”**

允许调整渲染的亮度和对比度。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-postprocessing-brightness-contrast.jpg)

＃

**“景深”**

启用景深（DOF）效果。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-postprocessing-dof.jpg)

＃

**“灰度”**

启用灰度效果。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-postprocessing-grayscale.jpg)

＃

**“环境光遮蔽”**

启用屏幕空间环境光遮挡（SSAO）效果。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-postprocessing-ssao.jpg)

＃

**“删除后处理效果”**

删除所有后处理效果。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-postprocessing-remove-postprocessing.jpg)

＃

### 变量

变量是可以更改（变化）的命名值。变量可以通过几种不同的方式创建：

* 您可以通过单击**Create variable ...**按钮**创建变量，**然后为其选择任何名称。名称，无论它出现在程序中的哪个位置，都可以随时通过变量的下拉菜单进行更改。
* 过程可以定义输入，这些输入创建只能在过程中使用的变量。这些传统上称为参数或参数。
* 每个“count with”和“for each”拼图都使用变量并定义其值。这些值只能在拼图中使用。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-variables-create.jpg)

变量的典型用例是当您有一个可以处于多个状态的对象时。例如，门可以打开或关闭，如果您想要正确地设置它，您需要知道它现在的状态。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-variables-example.jpg)

＃

**“组”**

这个拼图为变量赋值。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-variables-set.jpg)

＃

**“得到”**

此拼图提供存储在变量中的值，而不更改它。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-variables-get.jpg)

＃

**“更改”**

将存储在变量中的值增加指定的数字。如果初始值不是数字，或者未设置，则认为它是零，并且递增。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-variables-change.jpg)

＃

### 程序

过程（又称函数）是执行特定任务的一组命名的拼图。通过在程序中组织您的拼图，您可以使您的场景更紧凑和可维护。

通过从工具箱中拖出过程定义拼图，可以创建一个新过程：

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-create.jpg)

可以重新命名新创建的程序拼图并填充其他拼图以执行某项任务：

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-create2.jpg)

要能够触发（调用）过程，请从工具箱中拖出相应的拼图：

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-trigger.jpg)

可以从Puzzles场景的多个位置触发多次过程。这可以允许重复使用拼图而不是直接复制类似的拼图数次。例如，只要用户单击对象本身或HTML按钮（因此保护重复控件），就可以启动动画。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-trigger2.jpg)

过程可能具有其他输入参数（也称为参数）。要在程序中添加输入，请单击齿轮图标并从左侧的工具箱中拖出参数拼图，将其粘贴在输入拼图中：

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-inputs.jpg)

为了能够在过程中使用输入参数，请拖出在“变量”中自动创建的相应“get”变量拼图：

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-inputs2.jpg)

此变量可用作实际数据（如对象名称）的替代，以执行某些任务。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-inputs3.jpg)

使用输入触发过程时，为每个触发器拼图提供数据。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-trigger-with-inputs.jpg)

您可以使用右键单击菜单从触发器拼图跳转到相应的过程定义拼图：

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-jump.jpg)

＃

**“返回程序”**

过程可以将计算值输出到其调用者（也称为返回值）。要创建这样的过程，请从工具箱中拖出带有返回槽的过程拼图的变体。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-return.jpg)

＃

**“如果回归”**

在解释所有内部拼图之前，过程可以在某些条件下返回值。在这种情况下，程序会过早停止运行。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-procedures-if-return.jpg)

＃

### 调试

＃

**“打印到控制台”**

将任何类型的数据打印到浏览器控制台。后者通常可以使用F12键打开（Chrome，Firefox，Windows，Linux）。在Mac上，使用Chrome中的View&gt; Developer&gt; JavaScript Console菜单（Option-Cmd-J），或Safari中的Develop&gt; Show Error Console菜单（Option-Cmd-C）。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-debug-print-console.jpg)

＃

**“打印性能信息”**

在1秒内记录性能配置文件并将其打印到浏览器控制台。后者通常可以使用F12键打开（Chrome，Firefox，Windows，Linux）。在Mac上，使用Chrome中的View&gt; Developer&gt; JavaScript Console菜单（Option-Cmd-J），或Safari中的Develop&gt; Show Error Console菜单（Option-Cmd-C）。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-debug-print-performance-info.jpg)

＃

### 图书馆

库是一组持久存储，用于在多个项目中重复使用的拼图组。您可以通过右键单击拼图组并选择“ **将N拼图保存到库** ”选项，**将拼图组添加到库中**。在模态窗口中键入组的名称，因为它将出现在库的条目列表中（通过重新加载Puzzle编辑器来刷新它）。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-library-save.jpg)

通过将其拖出到工作区，可以从库中检索已保存的拼图组。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-library-retrieve.jpg)

单击**删除此项**按钮可以从库中**删除**条目（通过重新加载Puzzle编辑器刷新条目列表）。

