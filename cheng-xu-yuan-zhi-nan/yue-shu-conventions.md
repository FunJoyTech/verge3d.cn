---
description: 待校订
---

# 约定（Conventions）

## 约定

### 汇总表

|  | Blender | 3ds Max | glTF | Verge3D |
| :--- | :--- | :--- | :--- | :--- |
| 坐标系 | X - 右，Y - 远，Z - 向上 | X - 右，Y - 向上，Z - 近（OpenGL） |  |  |
| UV | （0,0）左下角 | （0,0）左上角 | （0,0）左上角 图像/视频/画布和禁用翻转 |  |
| 法线贴图 | R \[0,255\] - X \[-1,1\]  G \[0,255\] - Y \[-1,1\]  B \[0,255\] - Z \[0,1\]  X - 右，Y - up，Z - 附近（OpenGL） | ？ | R \[0,255\] - X \[-1,1\]  G \[0,255\] - Y \[-1,1\]  B \[128,255\] - Z \[1 / 255,1\]  X - 右，Y - 向上，Z - 近（OpenGL） | ？ |
| 立方体地图 | \| 左-X \| 返回-Y \| 对+ X \|  \| 下来-Z \| Up + Z \| 前进+ Y \| | ？ | ？ | OpenGL： 0 GL\_TEXTURE\_CUBE\_MAP\_POSITIVE\_X  1 GL\_TEXTURE\_CUBE\_MAP\_NEGATIVE\_X  2 GL\_TEXTURE\_CUBE\_MAP\_OSEGTIVE\_Y  3 GL\_TEXTURE\_CUBE\_MAP\_NEGATIVE\_Y  4 GL\_TEXTURE\_CUBE\_MAP\_POSITIVE\_Z  5 GL\_TEXTURE\_CUBE\_MAP\_NEGATIVE\_Z  ...与+ X和-X交换 |
| Equirectangular Map | ？ | ？ | 通用2D纹理 | ？ |

