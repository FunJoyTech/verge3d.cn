---
description: 待校订
---

# 矩阵变换（Matrix Transformations）

## 矩阵变换

Verge3D使用**矩阵**编码3D变换 - 平移（位置），旋转和缩放。Object3D的每个实例都有一个矩阵，用于存储该对象的位置，旋转和缩放。本页介绍如何更新对象的转换。

### 便利性和**matrixAutoUpdate**

有两种方法可以更新对象的转换：

1. 修改对象的**位置**，**四元数**和**缩放**属性，让Verge3D从这些属性中重新计算对象的矩阵： 默认情况下，**matrixAutoUpdate**属性设置为true，矩阵将自动重新计算。如果对象是静态的，或者您希望在重新计算时手动控制，则可以通过将属性设置为false来获得更好的性能： 在更改任何属性后，手动更新矩阵：`object.position.copy(start_position); object.quaternion.copy(quaternion);object.matrixAutoUpdate = false;object.updateMatrix();`
2. 直接修改对象的矩阵。该Matrix4类有修改矩阵的各种方法： 注意**matrixAutoUpdate** _必须_设置为**假**在这种情况下，你应该确保_不_调用**updateMatrix**。调用**updateMatrix**将破坏对矩阵所做的手动更改，从**位置**，**比例等**重新计算矩阵。`object.matrix.setRotationFromQuaternion(quaternion); object.matrix.setPosition(start_position); object.matrixAutoUpdate = false;`

### 对象和世界矩阵

对象的矩阵存储对象_相_对于对象父级的转换; 要在_世界_坐标中获取对象的变换，您必须访问对象的Object3D.matrixWorld。

当父对象或子对象的转换发生更改时，您可以通过调用updateMatrixWorld（）来请求更新子对象的matrixWorld。

### 旋转和四元数

Verge3D提供了两种表示3D旋转的方法：欧拉角和四元数，以及两者之间的转换方法。欧拉角受到称为“万向节锁定”的问题，其中某些配置可能失去一定程度的自由度（防止物体绕一个轴旋转）。因此，对象旋转_始终_存储在对象的四元数中。

该库的**早期**版本包含一个**useQuaternion**属性，当设置为false时，将导致从Euler角度计算对象的矩阵。这种做法已被弃用 - 相反，您应该使用setRotationFromEuler方法，该方法将更新四元数。

