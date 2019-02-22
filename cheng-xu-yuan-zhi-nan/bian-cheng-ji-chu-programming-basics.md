---
description: 待校订
---

# 编程基础（Programming Basics）

## 编程基础

本节的目的是简要介绍Verge3D。我们将首先使用旋转立方体设置场景。页面底部提供了一个工作示例，以防您遇到困难并需要帮助。

### 在我们开始之前

在使用Verge3D之前，您需要在某处显示它。将以下HTML保存到计算机上的文件中，并在应用程序目录中保存Verge3D副本，然后在浏览器中打开它。`<!DOCTYPE html> <html> <head> <meta charset=utf-8> <title>My first Verge3D app</title> <style> body { margin: 0; } canvas { width: 100%; height: 100% } </style> </head> <body> <script src="v3d.js"></script> <script> // Our Javascript will go here. </script> </body> </html>`就这样。下面的所有代码都进入空的&lt;script&gt;标记。

### 创建场景

要实际能够使用Verge3D显示任何内容，我们需要三件事：场景，相机和渲染器，以便我们可以使用相机渲染场景。`var scene = new v3d.Scene(); var camera = new v3d.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000); var renderer = new v3d.WebGLRenderer(); renderer.setSize(window.innerWidth, window.innerHeight); document.body.appendChild(renderer.domElement);`我们花一点时间来解释这里发生了什么。我们现在已经设置了场景，我们的相机和渲染器。Verge3D中有几个不同的摄像头。现在，让我们使用**PerspectiveCamera**。第一个属性是**视野**。FOV是在任何给定时刻在显示器上看到的场景的范围。该值以度为单位。第二个是**宽高比**。你几乎总是想要使用元素的宽度除以高度，或者你会得到与在宽屏电视上播放旧电影时相同的结果 - 图像看起来很紧。接下来的两个属性是**近**剪裁平面和**远**剪裁平面。这意味着，远离相机的物体**远远**超过**近**或近的物体将不会被渲染。您现在不必担心这一点，但您可能希望在应用中使用其他值以获得更好的性能。接下来是渲染器。这就是魔术发生的地方。除了我们在这里使用的WebGLRenderer之外，Verge3D还附带了一些其他功能，通常用作旧浏览器用户的后备或者由于某些原因没有WebGL支持的用户。除了创建渲染器实例之外，我们还需要设置我们希望它渲染应用程序的大小。使用我们想要用我们的应用程序填充的区域的宽度和高度是个好主意 - 在这种情况下，浏览器窗口的宽度和高度。对于性能密集型应用程序，您还可以为**setSize提供**较小的值，例如**window.innerWidth / 2**和**window.innerHeight / 2**，这将使应用程序呈现为一半大小。如果您希望保持应用程序的大小但是以较低的分辨率渲染它，可以通过调用**setSize**并将其作为**updateStyle**（第三个参数）来调用。例如，假设您的&lt;canvas&gt;具有100％的宽度和高度，**setSize（window.innerWidth / 2，window.innerHeight / 2，false）**将以半分辨率呈现您的应用。最后但并非最不重要的是，我们将**渲染器**元素添加到HTML文档中。这是渲染器用于向我们显示场景的&lt;canvas&gt;元素。_“这一切都很好，但你承诺的那个立方体在哪里？”_ 我们现在加上吧。`var geometry = new v3d.BoxGeometry(1, 1, 1); var material = new v3d.MeshBasicMaterial({ color: 0x00ff00 }); var cube = new v3d.Mesh(geometry, material); scene.add(cube); camera.position.z = 5;`要创建一个立方体，我们需要一个**BoxGeometry**。这是一个包含多维数据集的所有点（**顶点**）和填充（**面**）的对象。我们将来会更多地探讨这个问题。除了几何外，我们还需要一种材料来为它着色。Verge3D有几种材料，但我们**暂时**坚持使用**MeshBasicMaterial**。所有材料都采用将应用于它们的属性对象。为了使事情变得非常简单，我们只提供**0x00ff00**的颜色属性，它是绿色的。这与CSS或Photoshop（**十六种颜色**）中的**颜色相同**。我们需要的第三件事是**Mesh**。网格是一个采用几何体的对象，并将一个材质应用于它，然后我们可以将其插入到场景中，并自由移动。默认情况下，当我们调用**scene.add（）时**，我们添加的东西将被添加到坐标**（0,0,0）中**。这会导致相机和立方体彼此在一起。为了避免这种情况，我们只需将相机移出一点。

### 渲染场景

如果您将上面的代码复制到我们之前创建的HTML文件中，您将无法看到任何内容。这是因为我们实际上还没有呈现任何东西。为此，我们需要所谓的**渲染或动画循环**。`function animate() { requestAnimationFrame(animate); renderer.render(scene, camera); } animate();`这将创建一个循环，使渲染器每秒绘制场景60次。如果您不熟悉在浏览器中编写游戏，您可能会说_“我们为什么不创建一个setInterval？”_ 问题是 - 我们可以，但**requestAnimationFrame**有许多优点。也许最重要的一点是当用户导航到另一个浏览器标签时它会暂停，因此不会浪费他们宝贵的处理能力和电池寿命。

### 动画多维数据集

如果您将上面的所有代码插入到我们开始之前创建的文件中，您应该会看到一个绿色框。让旋转它让它变得更有趣。在**animate**函数中的**renderer.render**调用上方添加以下内容：`cube.rotation.x += 0.1; cube.rotation.y += 0.1;`这将在每帧（每秒60次）运行，并为立方体提供一个很好的旋转动画。基本上，在应用程序运行时您想要移动或更改的任何内容都必须通过动画循环。你当然可以从那里调用其他函数，这样你就不会得到数百行的**动画**函数。

### 结果

恭喜！您现在已经完成了第一个Verge3D应用程序。这很简单，你必须从某个地方开始。完整代码如下。玩弄它以更好地理解它是如何工作的。`<html> <head> <title>My first Verge3D app</title> <style> body { margin: 0; } canvas { width: 100%; height: 100% } </style> </head> <body> <script src="v3d.js"></script> <script> var scene = new v3d.Scene(); var camera = new v3d.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000); var renderer = new v3d.WebGLRenderer(); renderer.setSize(window.innerWidth, window.innerHeight); document.body.appendChild(renderer.domElement); var geometry = new v3d.BoxGeometry(1, 1, 1); var material = new v3d.MeshBasicMaterial({ color: 0x00ff00 }); var cube = new v3d.Mesh(geometry, material); scene.add(cube); camera.position.z = 5; var animate = function() { requestAnimationFrame(animate); cube.rotation.x += 0.1; cube.rotation.y += 0.1; renderer.render(scene, camera); }; animate(); </script> </body> </html>`

