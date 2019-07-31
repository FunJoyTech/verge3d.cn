# LOD

## LOD

LOD，即Level of Detail，意为细节级别——根据与相机的距离显示具有更多或更少几何体的网格。

每个级别都与一个对象相关联，并且根据指定的距离时在其间切换渲染。通常需要创建三个网格物体，一个用于远处（低细节），一个用于中等范围（中等细节），一个用于近距离（高细节）。

### 范例

[webgl / lod](https://cdn.soft8soft.com/demo/examples/index.html#webgl_lod)\`\`

```text
var lod = new v3d.LOD();

//Create spheres with 3 levels of detail and create new LOD levels for them
for(var i = 0; i < 3; i++) {

  var geometry = new v3d.IcosahedronBufferGeometry(10, 3 - i)

  var mesh = new v3d.Mesh(geometry, material);

  lod.addLevel(mesh, i * 75);

}

scene.add(lod);
```

请注意，因为LOD需要切换不同的细节级别，你必须在渲染循环中update\(camera\)。参见本示例中的源代码以了解细节：[WebGL / LOD](https://cdn.soft8soft.com/demo/examples/index.html#webgl_lod)

### 构造函数

#### LOD\(\)

创建一个新的LOD。

### 属性

有关常见属性，请参阅基础Object3D类。

#### \#.levels : array

一组分级对象  
每一级别都有一个包含两个属性的对象：  
object - 本级别所需要显示的Object3D。  
distance - 切换显示细节级别的距离。

### Methods

有关常用方法，请参阅基础Object3D类。

#### \#.addLevel \(object : Object3D, distance : Float\) : null

object - 本级别所需要显示的Object3D。  
distance - 切换显示细节级别的距离。  
  
添加将以特定距离和更大距离显示的网格。通常距离越远，网格上的细节越低。

#### \#.clone \(\) : LOD

返回此LOD对象及其关联的距离特定对象的克隆。

#### \#.getObjectForDistance \(distance : Float\) : Object3D

获取大于距离的第一个Object3D（网格）的引用。

#### \#.raycast \(raycaster : Raycaster, intersects : Array\) : Array

在一个铸造的雷和这个LOD之间获得交叉点。 Raycaster.intersectObject将调用此方法。

#### \#.toJSON \(meta\) : null

使用此LOD对象的详细信息创建JSON结构。

#### \#.update \(camera : Camera\) : null

根据与摄像机的距离设置每个级别对象的可见性。这需要在渲染循环中调用，以便动态更新细节级别。

### 资源

有关如何获取此模块源代码的详细信息，请参阅此[页面](https://www.soft8soft.com/docs/manual/en/introduction/How-to-obtain-Verge3D-sources.html)。

