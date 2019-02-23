---
description: FAQ ——fastest已校订
---

# 常见问题

以下是有关使用Verge3D的一些常见问题。

* 许可（Licensing）
* 一般问题（General Questions）
* 编程问题（Programming Questions）

＃

### 许可（Licensing）

#### 可以安装Verge3D的计算机数量？有多少用户可以使用单一许可证？

许可证是根据每个人（个人）或每个实体（团队，企业）分配的。安装数量不受限制。如果是“个人”选项，则只有一个人可以使用Verge3D。另一方面，对公司或组织内的用户数量没有限制。

#### Verge3D试用版有哪些限制/限制？我可以做些什么？

对该问题的快速回答是引用我们的许可协议。Verge3D EULA声明：“该软件的试用版可从Soft8Soft网站免费下载，仅供测试之用。禁止在生产环境中出于商业或非商业目的使用。” 。

基本上，如果您不为生产用途创建应用程序，则可以执行任何您想要的操作（以及持续时间）。例如，您可以使用它来创建用于练习目的的基本样本，发展您的个人技能，或为您的经理创建模拟演示文稿。您不得将其用于教育（请随时联系[我们](https://www.soft8soft.com/contact/)以降低价格申请特殊教育许可证）或创建您自己的投资组合（这有资格作为生产用途，因此请务必购买此类产品的Verge3D个人许可证案件）。

＃

### 一般问题（General Questions）

#### 当我在Chrome中打开它时，我的应用程序无法加载 - 但是当它从App Manager运行或在Firefox中打开时它可以正常运行...

由于浏览器供应商施加的安全策略，Web应用程序无法访问从其他域加载的数据，包括从本地文件系统（Firefox在此处例外）。因此，您应该使用App Manager（随本地服务器提供）进行开发，或者在Web服务器上发布Verge3D应用程序（或上传到Verge3D Network）以便能够运行它。

如果您需要桌面或移动应用程序，则可以使用第三方软件（例如[Electron](https://electronjs.org/)或[Cordova](https://cordova.apache.org/)）将Verge3D应用程序转换为这些平台。

#### 通过单击.html文件启动应用程序时无法加载应用程序。

请参阅上述问题的答案。

#### 我可以将场景导出到独立的全内置HTML文件吗？

不可以，Verge3D没有提供全面的HTML格式。如果您需要独立的可执行文件，可以尝试使用[Electron](https://electronjs.org/)进行转换。

#### 有计划支持Maxon Cinema 4D吗？可能是Autodesk Maya？

在论坛上查看[此问题](https://www.soft8soft.com/topic/verge3d-for-cinema4d-call-for-discussion/)的[答案](https://www.soft8soft.com/topic/verge3d-for-cinema4d-call-for-discussion/)。

#### Verge3D应用程序可以在Internet Explorer 11中运行吗？

是。在应用创建面板中启用IE 11兼容模块。

![](https://www.soft8soft.com/docs/files/faq/ie11-compat-module.jpg)

#### 如何将拼图复制到另一个项目中？

您可以使用[库](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#Library)功能。

#### 声音不在iOS上播放...

如何解决这个问题看[这里](https://www.soft8soft.com/docs/manual/en/introduction/Workflow.html#Audio_)。

#### Verge3D可以使用哪些3D格式？

Verge3D能够加载各种格式，包括glTF，OBJ，FBX，COLLADA，STL和PLY。尽管如此，创建3D Web内容的首选方法是使用3ds Max和Blender导出器支持的glTF 2.0格式。

此外，标准应用程序模板的脚本基于App类，该类仅支持加载glTF文件。要加载其他一些格式，请使用相应的[加载器](https://cdn.soft8soft.com/demo/examples/index.html?q=loader)。

＃

### 编程问题（Programming Questions）

#### 你说Verge3D基于Three.js。它与Three.js API兼容吗？

为了创建Verge3D，我们修改了Three.js代码库，因此我们决定在API中使用“v3d”前缀。但是，我们将尝试维护与Three.js的源代码兼容性。大多数基于Three.js的应用程序和[示例](https://cdn.soft8soft.com/demo/examples/index.html)都应该在Verge3D中运行而不做任何修改。

#### 为什么示例中有元视口标记？



```
<meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0">
```

这些标记控制移动浏览器的视口大小和比例（其中页面内容可以以与可见视口不同的大小呈现）。

[https://developer.mozilla.org/en/Mobile/Viewport\_meta\_tag](https://developer.mozilla.org/en/Mobile/Viewport_meta_tag)

#### 如何在调整大小时保留场景比例？

我们希望所有对象（无论与相机的距离如何）都显示相同的大小，即使窗口调整大小也是如此。解决这个问题的关键方程是给定距离处可见高度的公式： 如果我们将窗高增加一定百分比，那么我们想要的是所有距离的可见高度增加相同的百分比。这不能通过改变相机位置来完成。相反，您必须更改摄像机视野。 [例子](http://jsfiddle.net/Q4Jpu/)。

```
isible_height = 2 * Math.tan((Math.PI / 180) * camera.fov / 2) * distance_from_camera;
```

#### 为什么我的物体一部分不可见？

这可能是因为面被剔除了。面具有一个方向，决定哪一面是正面。在正常情况下，剔除会消除背面。要查看这是否是您的问题，请将材料面更改为v3d.DoubleSide。`material.side = v3d.DoubleSide`

#### 我的应用程序窗口在iOS设备上无休止地增长。怎么解决？

如果在iframe元素中嵌入Verge3D应用程序，则可能会遇到iOS设备上的特定问题，这会导致iframe的大小不断超出浏览器窗口的范围。这反过来可能导致WebGL崩溃。

要解决此问题，您可以使用以下代码段，该代码段会将iframe的大小调整为页面的正文，以防止所述iframe超出它。

```
<script>
if (/(iPad|iPhone|iPod)/g.test(navigator.userAgent)) {
    var iframe = document.getElementById('myIframe');
    function resize() {
        iframe.style.width = getComputedStyle(document.body).width;
        iframe.style.height = getComputedStyle(document.body).height;
        iframe.setAttribute('scrolling', 'no');
    }
    iframe.addEventListener('resize', function(e) {
        resize();
    });

    resize();
}
</script>
```

#### 键盘控件不适用于嵌入在iframe中的应用

当页面上的其他HTML得到关注时，就会发生这种情况。要解决此问题，请尝试以下代码： 其中**my\_iframe\_id**是iframe元素的ID。

```
document.getElementById("my_iframe_id").focus();
```

