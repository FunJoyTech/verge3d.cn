---
description: Updating for New Versions 校订
---

# 更新版本

Verge3D正在积极开发，定期发布软件版本。还有预发布的更新频道，新版本更频繁地推出。我们建议您跟上开发周期并及时更新Verge3D分发和应用程序。

* 更新Verge3D安装
* 更新应用程序 - 方法＃1（自动）
* 更新应用程序 - 方法＃2（清洁）
* 更新后
* 已知问题和故障排除

＃

### 更新Verge3D安装

通过重命名来备份当前的Verge3D文件夹（例如，从“verge3d”到“verge3d\_old”）。

在具有相同名称的新文件夹（即“verge3d”）中下载并解压缩最新的Verge3D软件包。

![](https://www.soft8soft.com/docs/files/updating/files-backup.jpg)

通过对鲜文件夹使用相同的名称，可以避免在您选择的3D编辑器中重新配置路径。

### 更新应用程序

＃

**方法＃1（自动） - 使用更新功能**

只需将应用程序的整个文件夹复制到新Verge3D安装的**applications**文件夹即可。启动App Manager后，您的应用程序名称应显示在应用程序列表中（如果没有，则重新加载页面）。单击带有圆形箭头的更新按钮。![](https://www.soft8soft.com/docs/files/updating/app-manager-update-button.jpg)

在显示的窗口中，选择您要覆盖的模板文件。如果您不编辑文件，则可以安全地选择所有内容。如果您修改了文件，请务必先备份它们，这样您可以稍后再选择更改，然后再继续覆盖。

![](https://www.soft8soft.com/docs/files/updating/application-update-window.jpg)

在引擎盖下，此操作将通过**verge3d / build**文件夹中的文件覆盖引擎模块，即Verge3D运行时**v3d.js**和可选兼容模块**ie\_compat.js**（由**IE 11**启用复选框）和**webxr-polyfill.js**（由**Legacy**启用）应用创建面板中的**VR**复选框）。如果选择此操作，此操作还将通过**verge3d / manager / app / Standard**文件夹中的文件覆盖选定的HTML / CSS / JavaScript文件和图标文件夹**媒体**。

```text
The update feature can also be used to add the compatibility modules to your app any time after it was created, so that you can avoid creating the app from scratch. In order to add the compatibility modules, simply copy the files "ie_compat.js" and/or "webxr-polyfill.js" to the app folder and click the update button.
```

＃

**方法＃2（清洁） - 从头开始​​重新创建您的应用程序**

这是一种替代方法，可以更新您完全控制文件的位置。您可以使用它来删除过时的文件，或者由于某种原因，自动更新方法不适用。

要执行干净更新，请在App Manager中的“创建新应用程序”窗口中键入应用程序的名称，然后单击“创建应用程序”按钮。

![](https://www.soft8soft.com/docs/files/updating/app-manager-create-new.jpg)

将**.max**或**.blend**文件，所有纹理/声音和Puzzles场景文件**visual\_logic.xml**从旧的app文件夹复制到新创建的app文件夹（位于**verge3d / applications中**）。当你被问到时，请覆盖文件。如果您在应用中使用基于HTML的UI，请同时复制所有相关文件。

![](https://www.soft8soft.com/docs/files/updating/files-copy.jpg)

最后，您应该执行导出到glTF，以便导出的格式接收最新的更新。如果您在应用程序中使用Puzzles，则需要在Puzzles编辑器中重新保存场景，以便生成的代码与引擎的最新版本匹配。

如果您更改了应用程序的.html，.css或.js文件中的任何内容，请务必先备份它们，以便稍后可以选择更改。

＃

### 更新后

#### 还原拼图库

如果您在Puzzles库中添加新条目，则可以在更新后通过将文件**verge3d / puzzles / library.xml**复制到全新安装文件夹并覆盖旧文件来还原它。

#### 重新激活您的许可证

每次更新到新版本时都应输入许可证密钥，否则您的应用程序可能会在运行时呈现试用水印。

＃

### 已知问题和故障排除

在极少数情况下，Puzzles按钮可能会在App Manager中消失。请执行干净更新以解决此问题。

在极少数情况下，Puzzles编辑器可能无法在更新后加载。请重置您的浏览器设置以解决此问题。

如果更新某些功能后，请在[论坛](https://www.soft8soft.com/forum/bug-reports-and-feature-requests/)上报告，以便我们调查问题并发布更正版本。

