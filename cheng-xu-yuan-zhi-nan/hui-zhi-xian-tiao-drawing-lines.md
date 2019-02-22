---
description: Drawing Lines 待校订
---

# 绘制线条

假设您要绘制直线或圆，而不是线框网格。首先，我们需要设置渲染器，场景和相机（请参阅创建场景页面）。

这是我们将使用的代码：`var renderer = new v3d.WebGLRenderer(); renderer.setSize(window.innerWidth, window.innerHeight); document.body.appendChild(renderer.domElement); var camera = new v3d.PerspectiveCamera(45, window.innerWidth / window.innerHeight, 1, 500); camera.position.set(0, 0, 100); camera.lookAt(0, 0, 0); var scene = new v3d.Scene();`

接下来我们要做的是定义一种材料。对于行，我们必须使用LineBasicMaterial或LineDashedMaterial。`//create a blue LineBasicMaterial var material = new v3d.LineBasicMaterial({ color: 0x0000ff });`

在材质之后，我们需要一个带有一些顶点的Geometry或BufferGeometry（建议使用BufferGeometry，因为它更高效，但为了简单起见，我们将在这里使用Geometry）：`var geometry = new v3d.Geometry(); geometry.vertices.push(new v3d.Vector3(-10, 0, 0)); geometry.vertices.push(new v3d.Vector3(0, 10, 0)); geometry.vertices.push(new v3d.Vector3(10, 0, 0));`

请注意，在每对连续的顶点之间绘制线条，但不在第一个和最后一个顶点之间绘制线条（线条未关闭）。

现在我们有两条线和一条材料的点，我们可以将它们组合在一起形成一条线。`var line = new v3d.Line(geometry, material);`

剩下的就是将它添加到场景中并调用渲染。`scene.add(line); renderer.render(scene, camera);`

你现在应该看到一个向上的箭头，由两条蓝线组成。

