# Verge3D无法打包桌面版应用解决方案

Verge3D应用管理器中可以将您做好的3D网页应用打包成不依赖网络环境和本地服务器的应用程序（即可执行文件，例如Windows系统中的.exe文件，或macOS系统中的.app文件）。具体使用方法请参考文档 “使用Electron创建(Verge3D)桌面应用程序”。


此项功能在第一次执行时，需要联网从Github获取Electron模版文件。如果您的网络环境不畅，可能导致此项操作失败。作为替代方案，您可以手动下载如下Electron模板文件，复制粘贴到Verge3D安装目录 `../verge3d_DCC/manager/dist/` 中，即可使用对应平台的打包功能。


不同版本对应路径：

Blender版：`../verge3d_blender/manager/dist/`

3ds Max版 `../verge3d_max/manager/dist/`

Maya版 `../verge3d_maya/manager/dist/`

旗舰版 `../verge3d_ultimate/manager/dist/`



## Windows (64-bit)
64位Windows版，适用于Windows 7之后的系统。

模板文件： _electron-v12.0.5-win32-x64.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-win32-x64.zip


## macOS (64-bit)
系统版本高于macOS 10.10 (Yosemite)的Intel芯片Mac电脑。

模板文件： _electron-v12.0.5-darwin-x64.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-darwin-x64.zip



## macOS App Store (64-bit)
针对Mac应用商店的缩小版本。运行于系统版本高于macOS 10.10 (Yosemite)的Intel芯片Mac电脑。

模板文件： _electron-v12.0.5-mas-x64.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-mas-x64.zip


## Linux (64-bit)
64位Linux，例如Ubuntu, Fedora, OpenSuse 或 ARCH。

模板文件： _electron-v12.0.5-linux-x64.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-linux-x64.zip


## Windows (ARM)
在带有64位ARM处理器的设备上运行的Windows10。

模板文件： _electron-v12.0.5-win32-arm64.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-win32-arm64.zip


## macOS (ARM)
系统版本高于macOS 11（Big Sur）的苹果芯片（M1芯片）Mac电脑。

模板文件： _electron-v12.0.5-darwin-arm64.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-darwin-arm64.zip


## macOS App Store (ARM)
针对Mac应用商店的缩小版本。系统版本高于macOS 11（Big Sur）的苹果芯片（M1芯片）Mac电脑。

模板文件： _electron-v12.0.5-mas-arm64.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-mas-arm64.zip


## Linux (ARM)
64位ARM设备上的Linux。

模板文件： _electron-v12.0.5-linux-arm64.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-linux-arm64.zip


## Windows (32-bit)
32位Windows版，适用于Windows 7之后的系统。

模板文件： _electron-v12.0.5-win32-ia32.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-win32-ia32.zip


## Linux (32-bit)
Linux ，32bit版本

模板文件： _electron-v12.0.5-linux-ia32.zip_

下载地址： https://cdn.funjoy.tech/electron_binary/electron-v12.0.5-linux-ia32.zip

----

批量下载以上模板文件请到百度网盘提取：

链接: https://pan.baidu.com/s/1spnA8pOLsMom_8xc2Yh7zA
提取码: `elec`


!> 请注意，即使您已经将如下模板文件放在了对应的目录下，也需要电脑连接到网络才可以使用打包。如果出现500错误，请检查您当前的网络环境是否可以访问互联网。
