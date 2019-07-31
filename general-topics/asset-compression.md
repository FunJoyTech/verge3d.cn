---
description: Asset Compression -fastest校订中
---

# 资产压缩

In Verge3D, scene files may be compressed using the highly effective LZMA2 compression algorithm, thus allowing to significantly reduce the size of the files. At the same time, LZMA2 offers fast decompression on the browser side. Typical compression rates observed for Verge3D scenes are: 20x for the **.gltf** files and 6x for the **.bin** files.

在Verge3D中，可以使用高效的LZMA2压缩算法压缩场景文件，从而允许显着减小文件的大小。同时，LZMA2在浏览器端提供快速解压缩。Verge3D场景的典型压缩率为：**.gltf**文件为20x，**.bin**文件为6x 。

* 压缩文件时（When Compress Files）
* 导出压缩文件（Exporting Compressed Files）
* 正在加载.xz文件（Loading .xz Files）
* 检查你的文件（Checking Your Files）
* 自定义应用程序或glTF查看器（Custom Apps or glTF Viewer）
* 档案库（Archivers）

＃

### 压缩文件时（When Compress Files）

Using asset compression is especially recommended in the following cases:

* .gltf/.bin or .glb scene files are relatively big so that the effect from compression is significant in terms of size reduction;
* you expect slow connections and every kilobyte counts;
* the standard server-side GZIP compression is not enabled or not satisfactory, or you don't even have any access to the server to setup GZIP for Verge3D scene files.

在以下情况下，特别建议使用资产压缩：

* .gltf / .bin或.glb场景文件相对较大，因此压缩效果在尺寸减小方面显着;
* 你期望缓慢的连接和每千字节计数;
* 标准服务器端GZIP压缩未启用或不满意，或者您甚至无法访问服务器以设置GZIP for Verge3D场景文件。

![Size comparison for a sample file: raw vs GZIP-compressed vs LZMA2-compressed](https://www.soft8soft.com/docs/files/scene_data_compression/compression_chart.png)

＃

### 导出压缩文件（Exporting Compressed Files）

Verge3D supports loading of scene files compressed in the **.xz** file format, which incorporates the LZMA2 compression algorithm. To enable creating **.xz** files automatically upon export, you can simply turn on the corresponding option in the export settings.

Verge3D支持加载以**.xz**文件格式压缩的场景文件，该文件格式包含LZMA2压缩算法。要在导出时自动创建**.xz**文件，只需在导出设置中打开相应的选项即可。

3ds Max：

![](https://www.soft8soft.com/docs/files/scene_data_compression/lzma-max.jpg)

Blender：

![](https://www.soft8soft.com/docs/files/scene_data_compression/lzma-blender.jpg)

＃

### 正在加载.xz文件（Loading .xz Files）

The compressed **.xz** files \(for example, my\_awesome\_app.gltf.xz and my\_awesome\_app.bin.xz\) should appear near the original ones. What is left is to enable loading them in your app. To do this, go to Puzzles and switch to the **init** tab:

压缩的**.xz**文件（例如，my\_awesome\_app.gltf.xz和my\_awesome\_app.bin.xz）应该出现在原始文件附近。剩下的就是在你的应用中加载它们。为此，请转到Puzzles并切换到**init**选项卡：

![](https://www.soft8soft.com/docs/files/scene_data_compression/puzzles-init.jpg)

Drag out the **configure application** puzzle from the **Initialization** category, if it is not already present in the workspace, and turn on the **compressed assets** checkbox on it:

从“ **初始化”**类别中 拖出**配置应用程序**谜题（如果它尚未存在于工作空间中），并打开其上的**压缩资源**复选框：

![](https://www.soft8soft.com/docs/files/scene_data_compression/puzzles-configure-app.jpg)

Finally, click the **Save** button. That's it!

最后，单击“ **保存”**按钮。而已！

＃

### 检查你的文件（Checking Your Files）

To ensure that your app now actually loads compressed assets, run your app \(either from App Manager or from a website where it is deployed\). Open the browser console and switch to the **Network** tab.

要确保您的应用程序现在实际加载压缩资产，请运行您的应用程序（从App Manager或部署它的网站）。打开浏览器控制台并切换到“ **网络”**选项卡。

![](https://www.soft8soft.com/docs/files/scene_data_compression/console-check.jpg)

Reload your app so that the console starts displaying files from the beginning. Find the scene files in the list - if everything is ok, they should end with **.xz**.

重新加载您的应用程序，以便控制台从头开始显示文件。在列表中查找场景文件 - 如果一切正常，则应以**.xz结尾**。

The browser console can usually be opened with the F12 key \(Chrome, Firefox on Windows, Linux\). On Mac use the View &gt; Developer &gt; JavaScript Console menu \(Option-Cmd-J\) in Chrome, or the Develop &gt; Show Error Console menu \(Option-Cmd-C\) in Safari.

通常可以使用F12键（Chrome，Windows，Linux上的Firefox）打开浏览器控制台。在Mac上，使用Chrome中的View&gt; Developer&gt; JavaScript Console菜单（Option-Cmd-J），或Safari中的Develop&gt; Show Error Console菜单（Option-Cmd-C）。

＃

### 自定义应用程序或glTF查看器（Custom Apps or glTF Viewer）

For **Custom** applications simply change

```
var url = 'my_awesome_app.gltf';
```

to:

```
var url = 'my_awesome_app.gltf.xz';
```

in the JavaScript code.

For Player-based applications that have a scene **.gltf** file specified in the URL as follows:

```
https://cdn.soft8soft.com/demo/player/player.html?load=../applications/ring/ring.gltf
```

you can simply replace it with the path to the compressed **.gltf.xz** file:

```
https://cdn.soft8soft.com/demo/player/player.html?load=../applications/ring/ring.gltf.xz
```

The same applies to **.glb** and **.glb.xz** files if they are used instead of **.gltf/.bin**.

对于**自定义**应用程序，只需 在JavaScript代码中 。

```
var url = 'my_awesome_app.gltf';
```

更改为：

```
var url = 'my_awesome_app.gltf.xz';
```

对于具有URL中指定的场景**.gltf**文件 的基于Player的应用程序， 

```
https://cdn.soft8soft.com/demo/player/player.html?load=../applications/ring/ring.gltf
```

您可以简单地将其替换为压缩的**.gltf.xz**文件的路径：

```
https://cdn.soft8soft.com/demo/player/player.html?load=../applications/ring/ring.gltf.xz
```

如果使用**.glb**和**.glb.xz**文件而不是**.gltf / .bin，**则 同样适用**.glb**和**.glb.xz**文件。

＃

### 档案库（Archivers）    

Alternatively, you can create **.xz** files using archive utilities as **7-Zip**, **XZ Utils** or others.

或者，您可以使用存档实用程序（如**7-Zip**，**XZ Utils**或其他）创建**.xz**文件 。

Verge3D implementation of an .xz decompressor puts some restrictions on compressed files due to optimization purposes, so not every .xz file can be loaded. .tar.xz files are also not supported. Considering this, it's recommended to use settings described below.

由于优化目的，.xz解压缩程序的Verge3D实现对压缩文件施加了一些限制，因此不能加载每个.xz文件。.tar.xz文件也不受支持。考虑到这一点，建议使用下面描述的设置。

#### 视窗（Windows）

1\) A popular file archiver [7-Zip](https://www.7-zip.org/download.html) can be used for creating .xz files.

To compress a file you can right click it, and then choose "7-Zip" -&gt; "Add to arcive..." - this opens the corresponding dialog window:

1）流行的文件存档器[7-Zip](https://www.7-zip.org/download.html) 可用于创建.xz文件。

要压缩文件，您可以右键单击它，然后选择“7-Zip” - &gt;“Add to arcive ...” - 这将打开相应的对话框窗口：

![](https://www.soft8soft.com/docs/files/scene_data_compression/7zip_add_to_archive.png)

The archivation settings should look like this:

* Archive format: xz
* Compression level: any \(Normal, Maximum and Ultra give best results\)
* Compression method: LZMA2 \(the only available option\)
* Dictionary size: up to 8 MB - the more the better \(more than 8MB is not supported by the engine\)

The rest of options can be left by default.

Also you can use a command line version of **7-Zip** instead:`7z.exe a -m0=LZMA2:d23 scene.gltf.xz scene.gltf 7z.exe a -m0=LZMA2:d23 scene.bin.xz scene.bin`

archivation设置应如下所示：

* 存档格式：xz
* 压缩级别：任何（正常，最大和超级给出最佳结果）
* 压缩方法：LZMA2（唯一可用的选项）
* 字典大小：最大8 MB - 越多越好（引擎不支持超过8 MB）

其余选项可以默认保留。

您也可以使用命令行版本的**7-Zip**：`7z.exe a -m0=LZMA2:d23 scene.gltf.xz scene.gltf 7z.exe a -m0=LZMA2:d23 scene.bin.xz scene.bin`

2\) Alternatively, you can use a special command line tool called **XZ Utils**. Its Windows binaries are available [here](https://tukaani.org/xz/) in the **Pre-built binaries** section.

The usage is simple:`xz.exe -k -f -6 scene.gltf xz.exe -k -f -6 scene.bin`

2）或者，您可以使用名为**XZ Utils**的特殊命令行工具 。它的Windows可执行文件都可以 [在这里](https://tukaani.org/xz/)的**预建的二进制文件**部分。

用法很简单：`xz.exe -k -f -6 scene.gltf xz.exe -k -f -6 scene.bin`

#### Linux

1\) A **7-Zip** command line port can be available out of the box or from official repositories as a package named **p7zip**.

The usage is similar to the one in Windows:`7z a -m0=LZMA2:d23 scene.gltf.xz scene.gltf 7z a -m0=LZMA2:d23 scene.bin.xz scene.bin`

1）**7-Zip**命令行端口可以是开箱即用的，也可以从官方存储库中获得，名为**p7zip**。

用法类似于Windows中的用法：`7z a -m0=LZMA2:d23 scene.gltf.xz scene.gltf 7z a -m0=LZMA2:d23 scene.bin.xz scene.bin`

2\) **XZ Utils** is also available out of the box or from official repositories in most Linux distros.

The usage is similar to the one in Windows:`xz -k -f -6 scene.gltf xz -k -f -6 scene.bin`

2）**XZ Utils**也可以在大多数Linux发行版中开箱即用或从官方存储库中获得。

用法类似于Windows中的用法：`xz -k -f -6 scene.gltf xz -k -f -6 scene.bin`

#### 苹果系统（macOS）

1\) A **7-Zip** command line port can be installed via **Homebrew** as a package named **p7zip**:`$ brew update $ brew install p7zip`

The usage is the same as in Linux.

1）**7-Zip**命令行端口可以通过 **Homebrew**作为名为**p7zip**的软件包**安装**：`$ brew update $ brew install p7zip`用法与Linux中的相同。

2\) **XZ Utils** binaries are available for macOS 10.5+ [here](https://tukaani.org/xz/) in the **Pre-built binaries** section. The usage is the same as in Linux.

2）**XZ utils的**二进制文件可用于MacOS 10.5+ [这里](https://tukaani.org/xz/)的**预建的二进制文件**部分。用法与Linux中的用法相同。

