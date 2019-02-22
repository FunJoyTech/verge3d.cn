---
description: Facebook 3D Posts 待校定
---

# 在Facebook发布3D主题



## Facebook 3D帖子（Facebook 3D Posts）

As of February 2018, Facebook offers the support for 3D posts via the glTF file format. Verge3D users may export content from 3ds Max or Blender and publish it live in their Facebook feeds.

截至2018年2月，Facebook通过glTF文件格式提供对3D帖子的支持。Verge3D用户可以从3ds Max或Blender导出内容并在其Facebook Feed中实时发布。

Creating a 3D post on Facebook is straightforward: at first, you perform export in .glb format \(.glb is the binary version of the glTF\), and then drag and drop this file to your Facebook post composer. Below is the detailed breakdown.

在Facebook上创建3D帖子很简单：首先，您以.glb格式执行导出（.glb是glTF的二进制版本），然后将此文件拖放到您的Facebook帖子编辑器中。以下是详细分类。

### 从3ds Max导出GLB（Export GLB from 3ds Max）

To perform export in **3ds Max**, go to the Verge3D menu and select "Export Facebook GLB...".

要在**3ds Max中**执行导出，请转到Verge3D菜单并选择“导出Facebook GLB ...”。

![](https://www.soft8soft.com/docs/files/facebook-3d-posts/export-glb-max1.jpg)

In the appeared file dialog, choose the export path and click **Save**.

在出现的文件对话框中，选择导出路径，然后单击“ **保存”**。

![](https://www.soft8soft.com/docs/files/facebook-3d-posts/export-glb-max2.jpg)

### 从Blender导出GLB（Export GLB from Blender）

To perform export in **Blender**, go to "File &gt; Export" and select the "Facebook GLB \(.glb\)" option. The generic GLB-export option "Verge3D glTF Binary \(.glb\)" will also work but will produce slightly less optimized files.

要在**Blender中**执行导出，请转到“文件&gt;导出”，然后选择“Facebook GLB（.glb）”选项。通用GLB导出选项“Verge3D glTF二进制（.glb）”也可以工作，但会产生略微不太优化的文件。

![](https://www.soft8soft.com/docs/files/facebook-3d-posts/export-glb-blender.png)

### 在Facebook撰写3D帖子（Compose 3D Post in Facebook）

Now you can just drag and drop the GLB file to your Facebook post.

现在，您只需将GLB文件拖放到Facebook帖子即可。

![](https://www.soft8soft.com/docs/files/facebook-3d-posts/post-fb.png)

In the Facebook post composer you can also choose the background to your liking.

在Facebook post composer中，您还可以根据自己的喜好选择背景。

![](https://www.soft8soft.com/docs/files/facebook-3d-posts/3d-post-example.png)

Check it out how it looks on Facebook: [link](https://www.facebook.com/soft8soft/posts/2003080113280076). The source file for this model can be found in your Verge3D installation inside the "applications" folder \(see below in "Starter files"\).

看看它在Facebook上的样子：[链接](https://www.facebook.com/soft8soft/posts/2003080113280076)。可以在“applications”文件夹中的Verge3D安装中找到此模型的源文件（请参阅下面的“Starter files”）。

### 入门文件（Starter Files）

We provide a sample Verge3D project that has been configured with the necessary export settings, for both 3ds Max and Blender. The starter project contains exactly the same environment map that is used by Facebook for maximum consistency.

我们提供了一个示例Verge3D项目，该项目已针对3​​ds Max和Blender配置了必要的导出设置。入门项目包含与Facebook使用的完全一致的环境贴图。

![](https://www.soft8soft.com/docs/files/facebook-3d-posts/facebook-ready-asset-file-blender.jpg)

It can be found inside the Verge3D [distribution](https://www.soft8soft.com/get-verge3d/), located "applications/fb\_max" \(3ds Max\) or "applications/fb" \(Blender\).

它可以在Verge3D [发行版中](https://www.soft8soft.com/get-verge3d/)找到，位于“applications / fb\_max”（3ds Max）或“applications / fb”（Blender）。

### 技术要求（Technical Requirements）

* Facebook requires your GLB to be under 3Mb in total, the smaller the better.
* glTF-compliant PBR materials \([3ds Max](https://www.soft8soft.com/docs/manual/en/introduction/Physical-material.html), [Blender](https://www.soft8soft.com/docs/manual/en/introduction/Physical-material-Blender.html)\) are only supported - consider converting your materials if it is not the case.
* PNG or JPEG files must be used for textures, and must be power-of-2 in each dimension \(256x512 is ok, for example\).
* Textures can be up to 4k, although Facebook developers recommend keeping them under 2k.



* Facebook要求你的GLB总量低于3Mb，越小越好。
* 仅支持 符合glTF标准的PBR材料（[3ds Max](https://www.soft8soft.com/docs/manual/en/introduction/Physical-material.html)，[Blender](https://www.soft8soft.com/docs/manual/en/introduction/Physical-material-Blender.html)） - 如果不是这种情况，请考虑转换材料。
* PNG或JPEG文件必须用于纹理，并且每个维度必须为2的幂（例如256x512就可以）。
* 纹理可以达到4k，尽管Facebook开发者建议将它们保持在2k以下。

### 优化提示（Optimization Tips）

Here are some recommendations on how to keep your GLB file below 3 Mb yet to have decent graphics.

* Prefer JPEG textures over PNG when you don't need transparency.
* Consider finding an optimal compression ratio for the JPEG files.
* Clean your asset files from any unused data. This includes auxiliary objects, animation and shape keys \(which are not currently supported by Facebook anyway\), unused vertex colors, UVs, etc.



这里有一些关于如何保持你的GLB文件低于3 Mb尚未拥有体面图形的建议。

* 当您不需要透明度时，首选PNG纹理。
* 考虑为JPEG文件找到最佳压缩比。
* 从任何未使用的数据中清除资产文件。这包括辅助对象，动画和形状键（无论目前还不支持Facebook），未使用的顶点颜色，UV等。

