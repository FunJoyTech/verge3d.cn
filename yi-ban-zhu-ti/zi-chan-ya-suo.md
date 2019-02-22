---
description: 待校订
---

# 资产压缩（Asset Compression）

## 资产压缩

在Verge3D中，可以使用高效的LZMA2压缩算法压缩场景文件，从而允许显着减小文件的大小。同时，LZMA2在浏览器端提供快速解压缩。Verge3D场景的典型压缩率为：**.gltf**文件为20x，**.bin**文件为6x 。

* 压缩文件时
* 导出压缩文件
* 正在加载.xz文件
* 检查你的文件
* 自定义应用程序或glTF查看器
* 档案库

＃

### 压缩文件时

在以下情况下，特别建议使用资产压缩：

* .gltf / .bin或.glb场景文件相对较大，因此压缩效果在尺寸减小方面显着;
* 你期望缓慢的连接和每千字节计数;
* 标准服务器端GZIP压缩未启用或不满意，或者您甚至无法访问服务器以设置GZIP for Verge3D场景文件。

![](https://www.soft8soft.com/docs/files/scene_data_compression/compression_chart.png)样本文件的大小比较：raw vs GZIP-compressed vs LZMA2-compressed

＃

### 导出压缩文件

Verge3D支持加载以**.xz**文件格式压缩的场景文件，该文件格式包含LZMA2压缩算法。要在导出时自动创建**.xz**文件，只需在导出设置中打开相应的选项即可。

3ds Max：![](https://www.soft8soft.com/docs/files/scene_data_compression/lzma-max.jpg)

搅拌机：![](https://www.soft8soft.com/docs/files/scene_data_compression/lzma-blender.jpg)

＃

### 正在加载.xz文件

压缩的**.xz**文件（例如，my\_awesome\_app.gltf.xz和my\_awesome\_app.bin.xz）应该出现在原始文件附近。剩下的就是在你的应用中加载它们。为此，请转到Puzzles并切换到**init**选项卡：![](https://www.soft8soft.com/docs/files/scene_data_compression/puzzles-init.jpg)

从“ **初始化”**类别中 拖出**配置应用程序**谜题（如果它尚未存在于工作空间中），并打开其上的**压缩资源**复选框：![](https://www.soft8soft.com/docs/files/scene_data_compression/puzzles-configure-app.jpg)

最后，单击“ **保存”**按钮。而已！

＃

### 检查你的文件

要确保您的应用程序现在实际加载压缩资产，请运行您的应用程序（从App Manager或部署它的网站）。打开浏览器控制台并切换到“ **网络”**选项卡。![](https://www.soft8soft.com/docs/files/scene_data_compression/console-check.jpg)

重新加载您的应用程序，以便控制台从头开始显示文件。在列表中查找场景文件 - 如果一切正常，则应以**.xz结尾**。

通常可以使用F12键（Chrome，Windows，Linux上的Firefox）打开浏览器控制台。在Mac上，使用Chrome中的View&gt; Developer&gt; JavaScript Console菜单（Option-Cmd-J），或Safari中的Develop&gt; Show Error Console菜单（Option-Cmd-C）。

＃

### 自定义应用程序或glTF查看器

对于**自定义**应用程序，只需 在JavaScript代码中更改 为： 。`var url = 'my_awesome_app.gltf';var url = 'my_awesome_app.gltf.xz';`

对于具有URL中指定的场景**.gltf**文件 的基于Player的应用程序， 您可以简单地将其替换为压缩的**.gltf.xz**文件的路径：`https://cdn.soft8soft.com/demo/player/player.html?load=../applications/ring/ring.gltfhttps://cdn.soft8soft.com/demo/player/player.html?load=../applications/ring/ring.gltf.xz`

如果使用**.glb**和**.glb.xz**文件而不是**.gltf / .bin，**则 同样适用**.glb**和**.glb.xz**文件。

＃

### 档案库

或者，您可以使用存档实用程序（如**7-Zip**，**XZ Utils**或其他）创建**.xz**文件 。

由于优化目的，.xz解压缩程序的Verge3D实现对压缩文件施加了一些限制，因此不能加载每个.xz文件。.tar.xz文件也不受支持。考虑到这一点，建议使用下面描述的设置。

#### 视窗

1）流行的文件存档器[7-Zip](https://www.7-zip.org/download.html) 可用于创建.xz文件。

要压缩文件，您可以右键单击它，然后选择“7-Zip” - &gt;“Add to arcive ...” - 这将打开相应的对话框窗口：![](https://www.soft8soft.com/docs/files/scene_data_compression/7zip_add_to_archive.png)

archivation设置应如下所示：

* 存档格式：xz
* 压缩级别：任何（正常，最大和超级给出最佳结果）
* 压缩方法：LZMA2（唯一可用的选项）
* 字典大小：最大8 MB - 越多越好（引擎不支持超过8 MB）

其余选项可以默认保留。

您也可以使用命令行版本的**7-Zip**：`7z.exe a -m0=LZMA2:d23 scene.gltf.xz scene.gltf 7z.exe a -m0=LZMA2:d23 scene.bin.xz scene.bin`

2）或者，您可以使用名为**XZ Utils**的特殊命令行工具 。它的Windows可执行文件都可以 [在这里](https://tukaani.org/xz/)的**预建的二进制文件**部分。

用法很简单：`xz.exe -k -f -6 scene.gltf xz.exe -k -f -6 scene.bin`

#### Linux的

1）**7-Zip**命令行端口可以是开箱即用的，也可以从官方存储库中获得，名为**p7zip**。

用法类似于Windows中的用法：`7z a -m0=LZMA2:d23 scene.gltf.xz scene.gltf 7z a -m0=LZMA2:d23 scene.bin.xz scene.bin`

2）**XZ Utils**也可以在大多数Linux发行版中开箱即用或从官方存储库中获得。

用法类似于Windows中的用法：`xz -k -f -6 scene.gltf xz -k -f -6 scene.bin`

#### 苹果系统

1）**7-Zip**命令行端口可以通过 **Homebrew**作为名为**p7zip**的软件包**安装**：`$ brew update $ brew install p7zip`用法与Linux中的相同。

2）**XZ utils的**二进制文件可用于MacOS 10.5+ [这里](https://tukaani.org/xz/)的**预建的二进制文件**部分。用法与Linux中的用法相同。

