---
description: FAQ ——fastest已校订
---

# 常见问题

Below are answered some common questions with regard to using Verge3D.

以下是有关使用Verge3D的一些常见问题。

* 许可（Licensing）
* 一般问题（General Questions）
* 编程问题（Programming Questions）

＃

### 许可（Licensing）

#### On how many computers can Verge3D be installed? How many users can use a single license?

The license is assigned on the per person \(Personal\) or per entity \(Team, Enterprise\) basis. The number of installations is not limited. In case of the Personal option, only one individual can use Verge3D. On the other hand, there is no limitation on the number of users within the company or organization.

#### 可以安装Verge3D的计算机数量？有多少用户可以使用单一许可证？

许可证是根据每个人（个人）或每个实体（团队，企业）分配的。安装数量不受限制。如果是“个人”选项，则只有一个人可以使用Verge3D。另一方面，对公司或组织内的用户数量没有限制。

#### What are the limitations / restrictions of the Verge3D Trial? Can I do ... ?

Quick answer to that question would be to quote our License Agreement. The Verge3D EULA states: "The trial version of this software available for free download from the Soft8Soft website is intended for testing purposes only. Any use in production environments, for commercial or non-commercial purposes is prohibited.".

Basically, you can do whatever you want \(and for how long\) provided you don't create apps for production use. For example, you can use it to create basic samples for practicing purposes, to develop your personal skills, or to create a mock-up presentation for your managers. You are not allowed to use it for education \(feel free to [reach us](https://www.soft8soft.com/contact/) to request a special Educational license at reduced price\) or to create your own portfolio \(this qualifies as production use, so be sure to purchase the Verge3D Personal license in such a case\).

#### Verge3D试用版有哪些限制/限制？我可以做些什么？

对该问题的快速回答是引用我们的许可协议。Verge3D EULA声明：“该软件的试用版可从Soft8Soft网站免费下载，仅供测试之用。禁止在生产环境中出于商业或非商业目的使用。” 。

基本上，如果您不为生产用途创建应用程序，则可以执行任何您想要的操作（以及持续时间）。例如，您可以使用它来创建用于练习目的的基本样本，发展您的个人技能，或为您的经理创建模拟演示文稿。您不得将其用于教育（请随时联系[我们](https://www.soft8soft.com/contact/)以降低价格申请特殊教育许可证）或创建您自己的投资组合（这有资格作为生产用途，因此请务必购买此类产品的Verge3D个人许可证案件）。

＃

### 一般问题（General Questions）

#### My app does not load when I open it in Chrome - yet it works when running from the App Manager or if opened in Firefox...

Due to security policy imposed by browser vendors, web applications cannot access data loaded from another domain, including from a local file system \(with Firefox being an exception here\). Therefore, you should use the App Manager \(which comes with a local server\) for development, or publish your Verge3D apps on a web server \(or upload to the Verge3D Network\) to be able to run it.

If you need a desktop or mobile application instead, you can convert your Verge3D apps to those platforms using third-party software \(such [Electron](https://electronjs.org/) or [Cordova](https://cordova.apache.org/)\).

#### 当我在Chrome中打开它时，我的应用程序无法加载 - 但是当它从App Manager运行或在Firefox中打开时它可以正常运行...

由于浏览器供应商施加的安全策略，Web应用程序无法访问从其他域加载的数据，包括从本地文件系统（Firefox在此处例外）。因此，您应该使用App Manager（随本地服务器提供）进行开发，或者在Web服务器上发布Verge3D应用程序（或上传到Verge3D Network）以便能够运行它。

如果您需要桌面或移动应用程序，则可以使用第三方软件（例如[Electron](https://electronjs.org/)或[Cordova](https://cordova.apache.org/)）将Verge3D应用程序转换为这些平台。

#### Cannot load app when I launch it by clicking on the .html file.

See the answer on the question above.

#### 通过单击.html文件启动应用程序时无法加载应用程序。

请参阅上述问题的答案。

#### Can I export my scene to a standalone all-in HTML file?

Nope, there is no all-in HTML format offered by Verge3D. If you need a standalone executable you can try to convert it with [Electron](https://electronjs.org/).

#### 我可以将场景导出到独立的全内置HTML文件吗？

不可以，Verge3D没有提供全面的HTML格式。如果您需要独立的可执行文件，可以尝试使用[Electron](https://electronjs.org/)进行转换。

#### Any plans to support Maxon Cinema 4D? May be Autodesk Maya?

See the [answer to this question](https://www.soft8soft.com/topic/verge3d-for-cinema4d-call-for-discussion/) on the forums.

#### 有计划支持Maxon Cinema 4D吗？可能是Autodesk Maya？

在论坛上查看[此问题](https://www.soft8soft.com/topic/verge3d-for-cinema4d-call-for-discussion/)的[答案](https://www.soft8soft.com/topic/verge3d-for-cinema4d-call-for-discussion/)。

#### Do Verge3D apps work in Internet Explorer 11?

Yes. Enable IE 11 compatibility module in the app creation panel.

#### Verge3D应用程序可以在Internet Explorer 11中运行吗？

是。在应用创建面板中启用IE 11兼容模块。

![](https://www.soft8soft.com/docs/files/faq/ie11-compat-module.jpg)

#### How can I copy Puzzles into another project?

You can use the [Library](https://www.soft8soft.com/docs/manual/en/puzzles/Library.html) feature for that.

#### 如何将拼图复制到另一个项目中？

您可以使用[库](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#Library)功能。

#### Sound is not played on iOS...

See how to fix that [here](https://www.soft8soft.com/docs/manual/en/introduction/Workflow.html#Audio_).

#### 声音不在iOS上播放...

如何解决这个问题看[这里](https://www.soft8soft.com/docs/manual/en/introduction/Workflow.html#Audio_)。

#### What 3D formats can be used with Verge3D?

Verge3D is able to load various formats including glTF, OBJ, FBX, COLLADA, STL and PLY. Still, the preferred way to create 3D web content is to use glTF 2.0 format which is supported by both 3ds Max and Blender exporters.

Also, the script of the Standard application template is based on the App class which supports loading glTF files only. For loading some other formats, use the corresponding [loaders](https://cdn.soft8soft.com/demo/examples/index.html?q=loader) instead.

#### Verge3D可以使用哪些3D格式？

Verge3D能够加载各种格式，包括glTF，OBJ，FBX，COLLADA，STL和PLY。尽管如此，创建3D Web内容的首选方法是使用3ds Max和Blender导出器支持的glTF 2.0格式。

此外，标准应用程序模板的脚本基于App类，该类仅支持加载glTF文件。要加载其他一些格式，请使用相应的[加载器](https://cdn.soft8soft.com/demo/examples/index.html?q=loader)。

＃

### 编程问题（Programming Questions）

#### You say Verge3D is based on Three.js. Is it compatible with Three.js API?

To create Verge3D we modified Three.js code base a lot and thus we decided to use "v3d" prefix for our APIs. However, we'll try to maintain source code compatibility with Three.js. Most of the Three.js-based applications and [examples](https://cdn.soft8soft.com/demo/examples/index.html) should work in Verge3D without any modifications.

#### 你说Verge3D基于Three.js。它与Three.js API兼容吗？

为了创建Verge3D，我们修改了Three.js代码库，因此我们决定在API中使用“v3d”前缀。但是，我们将尝试维护与Three.js的源代码兼容性。大多数基于Three.js的应用程序和[示例](https://cdn.soft8soft.com/demo/examples/index.html)都应该在Verge3D中运行而不做任何修改。

#### Why are there meta viewport tags in examples?

```
<meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0">
```

These tags control viewport size and scale for mobile browsers \(where page content may be rendered at different size than visible viewport\).

[https://developer.mozilla.org/en/Mobile/Viewport\_meta\_tag](https://developer.mozilla.org/en/Mobile/Viewport_meta_tag)

#### 为什么示例中有元视口标记？

```
<meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0">
```

这些标记控制移动浏览器的视口大小和比例（其中页面内容可以以与可见视口不同的大小呈现）。

[https://developer.mozilla.org/en/Mobile/Viewport\_meta\_tag](https://developer.mozilla.org/en/Mobile/Viewport_meta_tag)

#### How can scene scale be preserved on resize?

We want all objects, regardless of their distance from the camera, to appear the same size, even as the window is resized. The key equation to solving this is this formula for the visible height at a given distance:

```
isible_height = 2 * Math.tan((Math.PI / 180) * camera.fov / 2) * distance_from_camera;
```

If we increase the window height by a certain percentage, then what we want is the visible height at all distances to increase by the same percentage. This can not be done by changing the camera position. Instead you have to change the camera field-of-view. [Example](http://jsfiddle.net/Q4Jpu/).

#### 如何在调整大小时保留场景比例？

我们希望所有对象（无论与相机的距离如何）都显示相同的大小，即使窗口调整大小也是如此。解决这个问题的关键方程是给定距离处可见高度的公式： 

```
isible_height = 2 * Math.tan((Math.PI / 180) * camera.fov / 2) * distance_from_camera;
```

如果我们将窗高增加一定百分比，那么我们想要的是所有距离的可见高度增加相同的百分比。这不能通过改变相机位置来完成。相反，您必须更改摄像机视野。 [例子](http://jsfiddle.net/Q4Jpu/)。

#### Why is part of my object invisible?

This could be because of face culling. Faces have an orientation that decides which side is which. And the culling removes the backside in normal circumstances. To see if this is your problem, change the material side to v3d.DoubleSide.

```
material.side = v3d.DoubleSide
```

#### 为什么我的物体一部分不可见？

这可能是因为面被剔除了。面具有一个方向，决定哪一面是正面。在正常情况下，剔除会消除背面。要查看这是否是您的问题，请将材料面更改为v3d.DoubleSide。

```
material.side = v3d.DoubleSide
```

#### My app window grows endlessly on iOS devices. How to fix it?

If you embed a Verge3D application inside an iframe element, you may run into a specific issue on iOS devices, which causes iframes to constantly increase in size beyond the boundaries of the browser window. This in turn can lead to a WebGL crash.

To deal with this issue you can use the following snippet, which resizes the iframe to the page's body preventing the said iframe from extending beyond it.

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

#### Keyboard controls does not work for the app embedded in iframe

It happens when some other HTML on your page gets the focus. To fix this issue try the following code:

```
document.getElementById("my_iframe_id").focus();
```

Where **my\_iframe\_id** is the ID of your iframe element.

#### 键盘控件不适用于嵌入在iframe中的应用

当页面上的其他HTML得到关注时，就会发生这种情况。要解决此问题，请尝试以下代码： 

```
document.getElementById("my_iframe_id").focus();
```

其中**my\_iframe\_id**是iframe元素的ID。

