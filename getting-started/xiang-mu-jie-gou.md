---
description: 待校订
---

# 项目结构（Project Structure）

## 项目结构

Verge3D追求强大的艺术家友好型方法，为WebGL应用程序创建了一整套文件。建议不要编辑大多数初始化的项目文件，因为其中一些可能会在某些用户操作（例如导出，保存拼图等）时自动重新生成，而其他文件可能会在更新到新的Verge3D版本时被覆盖。

* 最简单的案例
* 高级案例

＃

### 最简单的案例

使用App Manager初始化的默认项目（使用默认配置参数）如下所示。

![](https://www.soft8soft.com/docs/files/project-structure/project-structure-simple.jpg)

#### HTML，CSS和JavaScript文件

该应用程序的核心由以下部分组成**的.html**，**的.css**和**.js文件**具有相同的名称（“my\_awesome\_app”），以及Verge3D运行时文件**v3d.js**。还有一个名为**media**的文件夹，其中包含小图像（全屏按钮图标和一组图标）。

虽然不推荐，但您可以编辑核心**.html**，**.css**和**.js**文件，尽管添加自己的CSS和JavaScript的更好方法是创建新文件并将它们链接到主**.html**。在执行[干净更新](https://www.soft8soft.com/docs/manual/en/introduction/Updating.html)后，请务必回复您的更改。

请注意，如果您只是单击**.html**文件尝试启动Verge3D应用程序，则很可能由于浏览器[安全策略](https://en.wikipedia.org/wiki/Same-origin_policy)禁止JavaScript访问不是从同一域加载的文件而无法运行。请始终使用包含本地Web服务器的App Manager来运行您的应用程序。

#### glTF文件

运行时，应用程序首先加载**.gltf**格式的3D场景，然后包含文件路径，以进一步加载glTF场景**.bin**和外部纹理的二进制部分。该**.gltf**和**的.bin**文件使用您喜欢的3D编辑器（3ds Max或搅拌机）的用户界面菜单出口。

#### 工作场景文件

根据您使用的3D编辑器，将有一个包含默认多维数据集的**.max**或**.blend**文件。这是执行场景大部分工作的地方。您可以随意修改此文件，使用其他文件重命名或覆盖它，但一定要保留导出的glTF文件的原始名称。

您可以将更多**.max**或**.blend**文件添加到app文件夹，以用作库文件或用于多场景应用程序。如果您的应用加载了多个glTF文件，请不要忘记从相应的**.max**或**.blend**文件执行导出。

#### 资产

纹理和声音通常由应用程序作为外部文件加载。确保在所选图像的3D编辑器中使用相对文件路径，并将图像存储在应用程序文件夹中，否则可能会出现应用程序发布问题。

#### 拼图

当您在Puzzles编辑器中单击**Save**时，它将在**visual\_logic.xml中**保存您的应用程序谜题。它还将从您的谜题中生成JavaScript代码并将其另存为**visual\_logic.js**。每次单击“ **保存”**按钮时，这些文件都将被覆盖，并将之前版本的**visual\_logic.xml**复制到**puzzles\_backup**文件夹，并使用时间戳重命名。因此，您始终可以通过将**.xml**文件复制到根目录并将其重命名来从此备份中恢复您的谜题。

＃

### 高级案例

一些Verge3D应用程序（例如Soft8Soft的工业机器人演示）可能包含大量其他文件，但这些文件仅来自2个额外类别。

#### 压缩的glTF文件

如果您为应用启用[资产压缩](https://www.soft8soft.com/docs/manual/en/introduction/Asset-compression.html)（这总是一件好事），导出器将首先执行导出，然后创建glTF文件的压缩版本。这些文件由应用程序自动选取，而不是常规的glTF文件。删除常规glTF文件没有意义，即使它们当时没有被使用，因为它们可能会在将来的某些导出操作中再次生成。

#### 第三方软件出口

复合应用程序可以利用在某些第三方软件（例如Webflow或Google Web Designer）中设计的HTML布局，其中常规Verge3D应用程序嵌入了**iframe**元素。在这种情况下，HTML布局可以保存到app文件夹，而不需要由App Manager选择任何更改。复杂的HTML布局可能反过来包括其他CSS / JavaScript文件，字体或图像，这些文件也需要存储在app文件夹中，并保留其原始层次结构。

![](https://www.soft8soft.com/docs/files/project-structure/project-structure.jpg)
