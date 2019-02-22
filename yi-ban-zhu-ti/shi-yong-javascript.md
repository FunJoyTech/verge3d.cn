---
description: Using JavaScript 待校订
---

# 使用JavaScript

## 在Verge3D应用程序中使用JavaScript

借助于Puzzles，您可以实现典型WebGL应用程序中的大多数功能，而无需编写任何代码。但是，可能存在一些特殊情况，您可能希望使用JavaScript - 例如，利用第三方编程库或实现一些无法通过Puzzles单独实现的非平凡功能。

您可以使用任何文本编辑器添加JavaScript代码，但如果您的编辑器支持语法高亮和行编号（例如Notepad ++或Atom），则工作更方便。

* 方法＃1（基础）
* 方法＃2（多功能）
* 方法＃3（Сompact）
* 方法＃4（硬核）

＃

### 方法＃1（基础）

假设您使用App Manager（使用默认配置选项）创建了应用程序，并将其命名为**my\_awesome\_app**。转到verge3d / applications文件夹，然后转到my\_awesome\_app文件夹，并使用您喜欢的文本编辑器打开JavaScript文件my\_awesome\_app.js。

搜索“runCode” - 文件中的这个位置应该如下所示：`function runCode(app) { // add your code here, e.g. console.log('Hello, World!'); }`

您可以在该声明中添加一些代码（在大括号之间），以便它转到：`function runCode(app) { // add your code here, e.g. console.log('Hello, World!'); console.log('Just added some JavaScript!'); }`

现在，如果您保存**.js**文件并运行您的应用程序，您将注意到......除非您打开浏览器控制台。后者通常可以使用F12键打开（Chrome，Firefox，Windows，Linux）。在Mac上，使用Chrome中的View&gt; Developer&gt; JavaScript Console菜单（Option-Cmd-J），或Safari中的Develop&gt; Show Error Console菜单（Option-Cmd-C）。![](https://www.soft8soft.com/docs/files/using-javascript/basics-console-log.jpg)

使用代码，您可以更改场景中的某些内容，例如，移动默认的Verge3D立方体（在3ds Max中命名为“Box001”，在Blender中命名为“Cube”）...`function runCode(app) { var obj = app.scene.getObjectByName('Cube'); obj.position.x = 2; }`

......或者凭空创造一种新材料：`function runCode(app) { var obj = app.scene.getObjectByName('Cube'); obj.material = new v3d.MeshPhongMaterial({ color: '#00BB00', emissive: '#550000' }); }`![](https://www.soft8soft.com/docs/files/using-javascript/basics-change-material.jpg)

查看[Verge3D代码示例](https://cdn.soft8soft.com/demo/examples/index.html)以获得灵感。单击“ **查看源”**按钮以打开示例的代码。![](https://www.soft8soft.com/docs/files/using-javascript/basics-code-examples.jpg)

＃

### 方法＃2（多功能）

在**runCode**函数中添加代码使其在应用程序加载时执行，一劳永逸。但是，如果您需要通过用户操作触发某些代码，该怎么办？例如，用户点击3D对象，该对象应该发生一些事情。

通过Puzzles的一些帮助，而不是纯代码，可以更轻松地实现这种情况。您可以使用Puzzles设置捕获用户事件，并仅使用代码执行特殊操作。这种方法可以为您节省大量时间。

打开应用程序**的.js**文件（例如，my\_awesome\_app.js位于verge3d /应用/ my\_awesome\_app用你喜欢的文本编辑器）。搜索“prepareExternalInterface”并在该声明中添加一个函数（在大括号之间），使它看起来像这样：`function prepareExternalInterface(app) { app.ExternalInterface.myJSFunction = function() { console.log('Running my JavaScript function!'); } }`

正如您所看到的，该函数已添加到**app.ExternalInterface**命名空间中 - 这对于Puzzles来说是非常重要的。如果需要，可以向此命名空间添加具有不同名称的更多函数。

您现在可以从谜题中触发名为“myJSFunction”的功能。为此，运行Puzzles编辑器并将拼图**调用JS函数**添加到工作区。默认情况下，它将触发名为“myJSFunction”的函数，因此如果您的函数名称不同，请确保在此谜题的文本字段中更改其名称。![](https://www.soft8soft.com/docs/files/using-javascript/external-interface-adding.jpg)

现在，如果你保存你的谜题并运行你的应用程序，谜题场景应该触发你添加的功能，并且消息应该出现在浏览器控制台中。![](https://www.soft8soft.com/docs/files/using-javascript/external-interface-running.jpg)

可以添加更多拼图，使您的功能仅在用户单击对象时运行。![](https://www.soft8soft.com/docs/files/using-javascript/external-interface-click.jpg)

如果您想将参数从谜题传递给JavaScript函数（例如，用户单击的对象的名称），您可以通过向其添加输入套接字来修改**调用JS函数**谜题。![](https://www.soft8soft.com/docs/files/using-javascript/external-interface-parameter.jpg)

还应修改代码以使函数接受参数作为其参数：`function prepareExternalInterface(app) { app.ExternalInterface.myJSFunction = function(myObject) { console.log(myObject); } }`

因此，将以编程方式生成的材质分配给所选对象的代码段可能如下所示：`function prepareExternalInterface(app) { app.ExternalInterface.myJSFunction = function(myObject) { var obj = app.scene.getObjectByName(myObject); obj.material = new v3d.MeshPhongMaterial({ color: '#00DD00', emissive: '#880000' }); } }`

＃

### 方法＃3（Сompact）

这种方法适合有经验的程序员，他们希望开始时只需要一个最小的工作代码片段。

创建新应用程序时，将“ **应用程序类型”**选择器切换为**“基于代码”**：![](https://www.soft8soft.com/docs/files/using-javascript/creating-code-based-app.jpg)

这将导致一个更简单的项目结构，没有Puzzles编辑器连接到您的应用程序，app **.js**文件将只包含几行代码：`'use strict'; window.addEventListener('load', function() { var app = new v3d.App('container', null, new v3d.SimplePreloader({ container: 'container' })); var url = 'my_awesome_app.gltf'; app.load(url, function() { app.enableControls(); runCode(); }); function runCode() { // add your code here, e.g. console.log('Hello, World!'); } });`

这种类型的应用程序非常简单，但它们仍然能够以**.gltf**格式加载场景（带预加载器），并为用户提供标准的摄像机控制。

您可以按照方法＃1中的描述在“runCode”函数中添加代码。当然，您可以完全彻底检修此应用程序模板 - 例如，您可以丢弃App类，使用其他一些文件格式加载场景或以某种特定方式设置控件。

＃

### 方法＃4（硬核）

你可以把**v3d.js**从文件verge3d /建立文件夹，将其链接到一个**html的**文件，并[开始编码](https://www.soft8soft.com/docs/manual/en/introduction/Programming-basics.html)！您是如何认为[代码示例](https://cdn.soft8soft.com/demo/examples/index.html)首先创建的？

