---
description: 待校订
---

# 如何更新事物（How to Update Things）

## 如何用代码更新事物

默认情况下，所有对象都会自动更新它们的矩阵（如果它们已添加到场景中）`var object = new v3d.Object3D(); scene.add(object);`或者如果它们是已添加到场景中的另一个对象的子节点：`var object1 = new v3d.Object3D(); var object2 = new v3d.Object3D(); object1.add(object2); scene.add(object1); //object1 and object2 will automatically update their matrices`

但是，如果您知道对象将是静态的，则可以禁用此选项并在需要时手动更新转换矩阵。`object.matrixAutoUpdate = false; object.updateMatrix();`

### 几何形状

#### BufferGeometry

BufferGeometries存储信息（如顶点位置，面指数，法线，色彩，UV的，并且任何自定义属性）在缓冲液 -即， [类型化数组](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Typed_arrays)。这使得它们通常比标准几何图形更快，但代价是更难以使用。

关于更新BufferGeometries，最重要的是要理解你无法调整缓冲区的大小（这非常昂贵，基本上相当于创建一个新的几何体）。但是，您可以更新缓冲区的内容。

这意味着如果您知道BufferGeometry的属性将增长（例如顶点数），则必须预先分配足够大的缓冲区以容纳可能创建的任何新顶点。当然，这也意味着BufferGeometry将有一个最大大小 - 没有办法创建一个可以无限期有效扩展的BufferGeometry。

我们将使用在渲染时扩展的行的示例。我们将在缓冲区中为500个顶点分配空间，但最初只使用BufferGeometry.drawRange绘制两个顶点。`var MAX_POINTS = 500; // geometry var geometry = new v3d.BufferGeometry(); // attributes var positions = new Float32Array(MAX_POINTS * 3); // 3 vertices per point geometry.addAttribute('position', new v3d.BufferAttribute(positions, 3)); // draw range var drawCount = 2; // draw the first 2 points, only geometry.setDrawRange(0, drawCount); // material var material = new v3d.LineBasicMaterial({ color: 0xff0000, linewidth: 2 }); // line var line = new v3d.Line(geometry, material); scene.add(line);`

接下来，我们将使用以下模式随机向线条添加点：`var positions = line.geometry.attributes.position.array; var x, y, z, index; x = y = z = index = 0; for (var i = 0, l = MAX_POINTS; i < l; i++) { positions[index ++] = x; positions[index ++] = y; positions[index ++] = z; x += (Math.random() - 0.5) * 30; y += (Math.random() - 0.5) * 30; z += (Math.random() - 0.5) * 30; }`

如果要更改第一次渲染后渲染_的点数_，请执行以下操作：`line.geometry.setDrawRange(0, newValue);`

如果要在第一次渲染后更改位置数据值，则需要设置needsUpdate标志，如下所示：`line.geometry.attributes.position.needsUpdate = true; // required after the first render`

如果在初始渲染后更改位置数据值，则可能需要调用\`.computeBoundingSphere（）\`以重新计算几何的边界球。`line.geometry.computeBoundingSphere();`

[这是一个小提琴，](http://jsfiddle.net/w67tzfhx/)显示一个动画线，你可以适应你的用例。

#### 例子：

[WebGL / custom / attributes ](https://cdn.soft8soft.com/demo/examples/index.html#webgl_custom_attributes)  
[WebGL / buffergeometry / custom / attributes / particles](https://cdn.soft8soft.com/demo/examples/index.html#webgl_buffergeometry_custom_attributes_particles)

#### 几何

以下标志控制各种几何属性的更新。仅为需要更新的属性设置标志，更新成本很高。缓冲区更改后，这些标志会自动重置为false。如果要继续更新缓冲区，则需要将它们设置为true。请注意，这仅适用于Geometry 而不适用于BufferGeometry。`var geometry = new v3d.Geometry(); geometry.verticesNeedUpdate = true; geometry.elementsNeedUpdate = true; geometry.morphTargetsNeedUpdate = true; geometry.uvsNeedUpdate = true; geometry.normalsNeedUpdate = true; geometry.colorsNeedUpdate = true; geometry.tangentsNeedUpdate = true;`

在[r66](https://github.com/mrdoob/three.js/releases/tag/r66)网格之前的版本中，还需要启用_动态_标志（以保持内部类型化数组）：`//removed after r66 geometry.dynamic = true;`

#### 例子：

[WebGL /几何/动态](https://cdn.soft8soft.com/demo/examples/index.html#webgl_geometry_dynamic)  


### 物料

所有制服值都可以自由更改（例如颜色，纹理，不透明度等），每帧都会将值发送到着色器。

此外，GLstate相关参数可以随时更改（depthTest，blend，polygonOffset等）。

平滑/平滑的阴影被烘焙成法线。您需要重置法线缓冲区（见上文）。

在运行时无法轻松更改以下属性（一旦材质至少呈现一次）：

* 制服的数量和类型
* 数字和灯的类型
* 存在与否
  * 质地
  * 多雾路段
  * 顶点颜色
  * 剥皮
  * 变形
  * 阴影贴图
  * 阿尔法测试

这些变化需要构建新的着色器程序。你需要设置`material.needsUpdate = true`

请记住，这可能会非常缓慢并导致帧率的急动（特别是在Windows上，因为着色器编译在DirectX中比OpenGL慢）。

为了获得更流畅的体验，您可以通过“虚拟”值（如零强度灯，白色纹理或零密度雾）在一定程度上模拟这些功能的变化。

您可以自由更改用于几何块的材质，但是无法更改对象如何划分为块（根据面材）。

#### 如果您需要在运行时使用不同的材料配置：

如果材料/块的数量很少，您可以事先预先划分物体（例如，人的头发/脸部/身体/上衣/裤子，前部/侧面/顶部/玻璃/轮胎/内部用于汽车）。

如果数量很大（例如，每个面可能有所不同），请考虑使用不同的解决方案，例如使用属性/纹理来驱动不同的每个面部外观。

#### 例子：

[WebGL /材料/汽车](https://cdn.soft8soft.com/demo/examples/index.html#webgl_materials_cars)  
[WebGL / webgl\_postprocessing / dof](https://cdn.soft8soft.com/demo/examples/index.html#webgl_postprocessing_dof)

### 纹理

如果更改了图像，画布，视频和数据纹理，则需要设置以下标志：`texture.needsUpdate = true;`

渲染目标会自动更新。

#### 例子：

[WebGL /材料/视频](https://cdn.soft8soft.com/demo/examples/index.html#webgl_materials_video)  
[WebGL / rtt](https://cdn.soft8soft.com/demo/examples/index.html#webgl_rtt)

### 相机

相机的位置和目标会自动更新。如果你需要改变

* FOV
* 方面
* 近
* 远

那么你需要重新计算投影矩阵：`camera.aspect = window.innerWidth / window.innerHeight; camera.updateProjectionMatrix();`

