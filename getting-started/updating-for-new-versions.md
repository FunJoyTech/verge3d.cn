---
description: Updating for New Versions  ——fastest已校订
---

# 更新版本

Verge3D is being actively developed with software releases occuring regularly. There is also the pre-release channel of updates with new versions coming out even more often. We recommend you to keep in pace with the development cycle and timely update your Verge3D distribution and applications.

Verge3D正在积极开发，定期发布软件版本。还有预发布的更新频道，新版本更频繁地推出。我们建议您跟上开发周期并及时更新Verge3D分发和应用程序。

* 更新Verge3D安装（Update Verge3D Installation）
* 更新应用程序 - 方法＃1（自动）（Update Applications - Method \#1 \(Automatic\)）
* 更新应用程序 - 方法＃2（纯净）（Update Applications - Method \#2 \(Clean\)）
* 更新后（After Update）
* 已知问题和故障排除（Known Issues and Troubleshooting）

＃

### 更新Verge3D安装（Update Verge3D Installation）

Backup your current Verge3D folder by renaming it \(from "verge3d" to "verge3d\_old", for example\).

通过重命名来备份当前的Verge3D文件夹（例如，将“verge3d”重命名为“verge3d\_old”）。

Download and unpack the latest Verge3D bundle in a fresh folder with the same name \(that is, "verge3d"\).

在具有相同名称的新文件夹（即“verge3d”）中下载并解压缩最新的Verge3D软件包。

![](https://www.soft8soft.com/docs/files/updating/files-backup.jpg)

By using the same name for the fresh folder you can avoid re-configuring paths in the 3D editor of your choice.

通过对新文件夹使用相同的名称，可以避免在您选择的3D软件中重新配置路径。

### 更新应用程序（Update Applications）

＃

**方法＃1（自动） - 使用更新功能（Method \#1 \(Automatic\) - use the update feature）**

Simply copy the entire folder with your application to the **applications** folder of the fresh Verge3D installation. After launching the App Manager, your app name should appear in the list of apps \(reload the page if not\). Click the update button with the round arrow on it.

只需将应用程序的整个文件夹复制到新Verge3D安装的**applications**文件夹即可。启动App Manager后，您的应用程序名称应显示在应用程序列表中（如果没有，则重新加载页面）。单击带有圆形箭头的更新按钮。

![](https://www.soft8soft.com/docs/files/updating/app-manager-update-button.jpg)

n the window shown up, select the template files you'd like to overwrite. You can safely select everything if you didn't edit the files. If you modified the files, be sure to backup them first so that you can cherry-pick the changes back later, and only after that proceed with overwriting.

在显示的窗口中，选择您要覆盖的模板文件。如果您不编辑文件，则可以安全地选择所有内容。如果您修改了文件，请务必先备份它们，这样您可以稍后再选择更改，然后再继续覆盖。

![](https://www.soft8soft.com/docs/files/updating/application-update-window.jpg)

Under the hood, this operation overwrites the engine modules by the files from **verge3d/build** folder, namely, Verge3D runtime **v3d.js** and optional compatibility modules **ie\_compat.js** \(enabled by **IE 11** checkbox\) and **webxr-polyfill.js** \(enabled by **Legacy VR** checkbox in the app creation panel\). If you choose so, this operation will also overwrite the selected HTML/CSS/JavaScript files and the icons folder **media** by the files from **verge3d/manager/app/Standard** folder.

此操作将通过**verge3d / build**文件夹中的文件覆盖引擎模块，即Verge3D运行时**v3d.js**和可选兼容模块**ie\_compat.js**（由**IE 11**启用复选框）和**webxr-polyfill.js**（由**Legacy**启用）应用创建面板中的**VR**复选框。如果选择此操作，此操作还将通过**verge3d / manager / app / Standard**文件夹中的文件覆盖选定的HTML / CSS / JavaScript文件和图标文件夹媒体。

```text
更新功能还可用于在创建应用程序后随时添加兼容性模块，以便您可以避免从头开始创建应用程序。
要添加兼容性模块，只需将文件“ie_compat.js”和/或“webxr-polyfill.js”复制到app文件夹，然后单击“更新”按钮。
```

＃

**方法＃2（纯净） - 从头开始​​重新创建您的应用程序（Method \#2 \(Clean\) - re-create your app from scratch）**

This is an alternative method of updating where you are in full control of your files. You can use it to get rid of obsolete files or if for some reason the automatic update method is not applicable.

这是一种替代方法，可以更新您完全控制文件的位置。您可以使用它来删除过时的文件，或者由于某种原因，自动更新方法不适用的时候来进行更新。

To perform clean updating, in the App Manager type the name of your app in the "Create new App" window and click "Create App" button.

要执行纯净更新，请在App Manager中的“创建新应用程序”窗口中键入应用程序的名称，然后单击“创建应用程序”按钮。

![](https://www.soft8soft.com/docs/files/updating/app-manager-create-new.jpg)

Copy **.max** or **.blend** files, all the textures/sounds and the Puzzles scenario file **visual\_logic.xml** from your old app folder to the newly created app folder \(located within **verge3d/applications**\). Overwrite files when you're asked so. If you were using HTML-based UI in your app, copy all relevant files as well.

将**.max**或**.blend**文件，所有纹理/声音和Puzzles场景文件**visual\_logic.xml**从旧的app文件夹复制到新创建的app文件夹（位于**verge3d / applications中**）。出现弹窗时，请点击覆盖文件。如果您在应用中使用基于HTML的UI，请同时复制所有相关文件。

![](https://www.soft8soft.com/docs/files/updating/files-copy.jpg)

Finally, you should perform exporting to glTF so that the exported format receives the latest updates. If you were using Puzzles in your app, you'll need to re-save your scenario in the Puzzles editor so that the generated code matches the newest version of the engine.

最后，您应该执行导出到glTF，以便导出的格式接收最新的更新。如果您在应用程序中使用**拼图（Puzzles）**，则需要在**拼图编辑器（Puzzles）**中重新保存场景，以便生成的代码与引擎的最新版本匹配。

If you changed anything in your application's .html, .css or .js files, be sure to backup them first so that you can cherry-pick the changes back later.

如果您更改了应用程序的.html，.css或.js文件中的任何内容，请务必先备份它们，以便稍后可以选择更改。

＃

### 更新后（After Update）

#### 还原拼图库（Restore Puzzles library）

If you were adding new entries in the Puzzles library, you can restore it after updating by copying the file **verge3d/puzzles/library.xml** to the fresh installation folder and overriding the old file.

如果您在Puzzles库中添加新条目，则可以在更新后通过将文件**verge3d / puzzles / library.xml**复制到全新安装文件夹并覆盖旧文件来还原它。

#### 重新激活您的许可证（Re-activate your license）

You should enter the license key each time you update to a new version, otherwise your apps may render the trial watermark when running.

每次更新到新版本时都应输入许可证密钥，否则您的应用程序可能会在运行时呈现试用水印。

＃

### 已知问题和故障排除（Known Issues and Troubleshooting）

On rare occasions the Puzzles button can disappear for your app in the App Manager. Please perform clean updating to fix this.

在极少数情况下，拼图按钮可能会在App Manager中消失。请执行干净更新以解决此问题。

On rare occasions the Puzzles editor may fail to load after updating. Please reset your browser settings to fix this.

在极少数情况下，拼图编辑器可能无法在更新后加载。请重置您的浏览器设置以解决此问题。

If after updating some feature got broken, please report this on the [forums](https://www.soft8soft.com/forum/bug-reports-and-feature-requests/) so that we can investigate the problem and issue a correcting release.

如果更新后某些功能有问题，请在[论坛](https://www.soft8soft.com/forum/bug-reports-and-feature-requests/)上报告，以便我们调查问题并发布更正版本。

