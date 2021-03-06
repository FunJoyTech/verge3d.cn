---
description: Project Structure  ——fastest已校订
---

# 项目结构

Pursuing a strong artist-friendly approach, Verge3D creates a complete set of files for a WebGL application. It is recommended not to edit most of the initialized project files, because some of them may be automatically regenerated upon certain user actions \(such as export, saving Puzzles etc\), while others may get overridden upon updating to new Verge3D versions.

Verge3D追求给予艺术家提供更加有效且友好的方式，为WebGL应用程序创建了一整套文件。建议不要编辑大多数初始化的项目文件，因为其中一些可能会在某些用户操作（例如导出，保存拼图等）时自动重新生成，而其他文件可能会在更新到新的Verge3D版本时被覆盖。

* 简单案例\(Simplest Case\)
* 高级案例\(Advanced Case\)

＃

### 简单案例\(Simplest Case\)

A default project initialized with the App Manager \(with default configuration parameters\) looks as follows.

使用App Manager初始化的默认项目（使用默认配置参数）如下所示。

![](https://www.soft8soft.com/docs/files/project-structure/project-structure-simple.jpg)

#### HTML，CSS和JavaScript文件\(HTML, CSS and JavaScript files\)

The application core consists of the **.html**, **.css** and **.js** files with the same name \("my\_awesome\_app"\), and the Verge3D runtime **v3d.js**. There is also a folder called **media** which contains small images \(fullscreen button icons and a set of favicons\).

应用程序的核心由相同名称的**.html**，**.css**和**.js文件**（“my\_awesome\_app”）以及Verge3D运行时文件**v3d.js**组成。还有一个名为**media**的文件夹，其中包含一些小图片（全屏按钮图标和一组图标）。

Although not recommended, you can edit the core **.html**, **.css** and **.js** files, although a better approach for adding your own CSS and JavaScript would be creating new files and linking them to the main **.html**. Be sure to cherry-pick your changes back after performing [clean updating](https://www.soft8soft.com/docs/manual/en/introduction/Updating.html).

虽然不推荐，但您可以编辑核心**.html**，**.css**和**.js**文件，尽管添加自己的CSS和JavaScript的更好方法是创建新文件并将它们链接到主**.html**。在执行[更新](https://www.soft8soft.com/docs/manual/en/introduction/Updating.html)后，请务必重新优化您的更改。

Please notice that if you attempt to launch a Verge3D application by simply clicking on the **.html** file, most likely it won't run due to the browser [security policy](https://en.wikipedia.org/wiki/Same-origin_policy) which forbids JavaScript from accessing files loaded not from the same domain. Please always use the App Manager, which includes a local web server, to run your apps.

请注意，如果您只是单击**.html**文件尝试启动Verge3D应用程序，则很可能由于浏览器[安全策略](https://en.wikipedia.org/wiki/Same-origin_policy)禁止JavaScript访问不是从同一域加载的文件而无法运行。请始终使用包含本地Web服务器的App Manager来运行您的应用程序。

#### glTF文件\(glTF files\)

When running, an application loads a 3D scene in **.gltf** format first, which in turn contains file paths for further loading of the binary part of a glTF scene **.bin** and external textures. The **.gltf** and **.bin** files are exported using user interface menu of your favorite 3D editor \(3ds Max or Blender\).

运行时，应用程序首先加载**.gltf**格式的3D场景，然后包含文件路径，以进一步加载glTF场景**.bin**和外部纹理的二进制部分。该**.gltf**和**.bin**文件使用您喜欢的3D编辑器（3ds Max或Blender）的用户界面菜单导出。

#### 工作场景文件\(Working scene files\)

Depending on the 3D editor you are using, there will be one **.max** or **.blend** file containing the default cube. This is where most work on your scenes is performed. Feel free to modify this file, rename or override it with some other file, but be certain to preserve the original name of the exported glTF file.

根据您使用的3D编辑器，将有一个包含默认立方体的**.max**或**.blend**文件。这是执行场景大部分工作的地方。您可以随意修改此文件，重命名或使用其他文件覆盖它，但一定要保留导出的glTF文件的原始名称。

You can add more **.max** or **.blend** files to the app folder, for using as library files or for multi-scene applications. If your app loads multiple glTF files, don't forget to perform export from the corresponding **.max** or **.blend** files.

您可以将更多**.max**或**.blend**文件添加到app文件夹，以用作库文件或用于多场景应用程序。如果您的应用加载了多个glTF文件，请不要忘记从相应的**.max**或**.blend**文件执行导出。

#### 资产\(Assets\)

Textures and sounds are typically loaded by an application as external files. Make sure that you use relative file paths in the 3D editor of your choice for all images, and that your images are stored inside your application folder, otherwise there may be issues with the publication of your app.

贴图和声音通常由应用程序作为外部文件加载。确保在所选图像的3D编辑器中使用相对文件路径，并将图像存储在应用程序文件夹中，否则应用程序发布时可能会出现问题。

#### 拼图\(Puzzles\)

When you click **Save** in the Puzzles editor, it will save your app puzzles in **visual\_logic.xml**. It will also generate JavaScript code from your puzzles and save it as **visual\_logic.js**. These files will keep being overridden every time you click the **Save**button, with the previous edition of the **visual\_logic.xml** copied to the **puzzles\_backup** folder, renamed with a time stamp. Therefore, you can always restore your puzzles from this backup by copying the **.xml** file to the root and renaming it back.

当您在拼图编辑器中单击“**保存“\(“Save“\)**时，拼图将保存在**visual\_logic.xml**中。它还将生成JavaScript代码并保存在**visual\_logic.js**中。每次单击“ **保存”**按钮时，这些文件都将被覆盖，并将之前版本的**visual\_logic.xml**复制到**puzzles\_backup**文件夹，并使用时间戳重命名。因此，您始终可以通过将**.xml**文件复制到根目录并将其重命名来从此备份中恢复您的拼图。

### 高级案例\(Advanced Case\)

Some Verge3D apps \(such as Soft8Soft's Industrial Robot demo\) may contain quite a number of additional files, which however, come from just 2 extra categories.

一些Verge3D应用程序（例如Soft8Soft官方案例中的工业机器人演示）可能包含大量其他文件，这些文件主要分为两类。

**压缩的glTF文件\(Compressed glTF files\)**

If you enable [asset compression](https://www.soft8soft.com/docs/manual/en/introduction/Asset-compression.html) for your app \(which is always a good thing\), the exporter will at first perform export as usual and then create a compressed version of glTF files. These files are automatically picked up by the application instead of the regular glTF file. There is no point in deleting the regular glTF files even if they are not used at the time, since they may be generated again in some future export operation.

如果您为应用启用了[资产压缩](https://www.soft8soft.com/docs/manual/en/introduction/Asset-compression.html)（asset compression这总是一件好事），导出器将首先执行导出，然后创建glTF文件的压缩版本。这些文件由应用程序自动选取，而不是常规的glTF文件。删除常规glTF文件没有意义，即使它们当时没有被使用，因为它们可能会在将来的某些导出操作中再次生成。

#### 第三方软件导出\(Third-party software exports\)

Composite applications may leverage HTML layouts designed in some third-party software \(such as Webflow or Google Web Designer\), in which a regular Verge3D application is embedded with an **iframe** element. In such cases, the HTML layout can be saved to the app folder without any change to be picked up by the App Manager. Complex HTML layouts may in turn include additional CSS/JavaScript files, fonts or images, which are also needed to be stored in the app folder with their original hierarchy preserved.

整合应用程序可以利用某些第三方软件（例如Webflow或Google Web Designer）设计的HTML布局，其中常规Verge3D应用程序嵌入了**iframe**元素。在这种情况下，HTML布局可以保存到app文件夹，而不需要由App Manager选择任何更改。复杂的HTML布局可能反过来包括其他CSS / JavaScript文件，字体或图像，这些文件也需要存储在app文件夹中，并保留其原始层次结构。

![](https://www.soft8soft.com/docs/files/project-structure/project-structure.jpg)

