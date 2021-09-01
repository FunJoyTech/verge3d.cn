# 在移动端调试Verge3D应用的简便方法

在设计开发面向移动端的Verge3D应用时，查看与调试应用是一个非常频繁的操作，面向PC端设计时，您可以直接在浏览器中调试应用，方便快捷。而在面向移动端开发时，您就需要跨屏幕协调开发过程了。

关于在移动端调试应用，Verge3D的用户手册里介绍了两种方式：使用本地IP地址+二维码，或端口转发的方式来进行调试。请参考文档：[在移动端浏览器中测试Verge3D应用](https://www.soft8soft.com/docs/manual/zh/introduction/Testing-Mobile-Browsers.html) 。

在本文中，我们将为大家介绍这2种手册中的方法，以及4种更轻松好用的替代方案。

## 本地（局域网）IP地址+二维码

开启External Server Interface后，Verge3D应用管理器可提供局域网可访问的IP地址，方便在局域网或可在移动设备上实时运行应用。最新版的Chrome或Edge浏览器的地址栏都可以直接将当前访问网址转换成二维码。通过扫码方式，可以更快捷地访问本地应用。

![](https://cdn.funjoy.tech/web/blog/mobile_debug/localaddress_qrcode.jpg)

但是这样的方法只能浏览应用，看不到控制台输出的日志。如果您需要通过控制台检查性能情况，以及可能出现的报错信息，那还需要以下方式来进行。

## 端口转发

这种方法仅适用于Android设备，需要开启设备的开发者模式后，使用USB连接电脑与设备。这样就可以方便的在Chrome浏览器中查看移动端调试的控制台日志了。

首先，在您的手机中打开“开发者选项”，开启“USB调试”，使用USB数据线连接电脑与手机后，选择“允许使用计算机调试”。

![](https://cdn.funjoy.tech/web/blog/mobile_debug/Android_developer_mode.jpg ':size=500')

接着，在Chrome浏览器地址栏中，输入 **chrome://inspect/** 访问页面，并参照文档配置端口转发 **8668** 到 **localhost:8668** ，然后在手机中使用 **localhost:8668** 即可访问应用管理器，点击对应的应用，并在Chrome页面中点击 inspect 按钮，即可打开调试窗口同步查看手机浏览器视窗，以及实时查看手机浏览器的控制台日志。

![](https://cdn.funjoy.tech/web/blog/mobile_debug/Chrome_inspect.jpg)

以上两种方法是我们在手册中推荐的移动应用调试方式。除此之外，我们再为您额外介绍几种易用使用的方法来助力移动端调试。

## 1. iOS系统调试

iOS也拥有类似Chrome端口转发的调试方法，但仅局限于使用macOS中的Safari浏览器进行操作。

首先，请在iPhone上打开Safari高级设置中的“网页检查器选项”，连接数据线后，请选择“信任此电脑”，如下图所示：

![](https://cdn.funjoy.tech/web/blog/mobile_debug/iOS_Develop.jpg)

然后，打开iPhone的Safari浏览器，使用**局域网IP地址**方式访问应用。您可以用iPhone的默认相机扫描二维码的方式来打开对应的页面地址。

紧接着，在macOS中打开Safari浏览器开发菜单中，找到设备，选择正在查看的页面，点击即可打开网页检查器，您可以在控制台中找到iPhone输出的控制台信息。

![](https://cdn.funjoy.tech/web/blog/mobile_debug/macOS_Safari.jpg)

如果您想要在查看性能信息，可以在拼图中插入 print performance info 拼图。

## 2. 在浏览器的设备模拟器中查看UI状态：

这是最常规的前端开发检查方式，以Chrome为例：打开应用页面后，点击键盘上的F12键，打开浏览器控制台，启用设备模拟，在这里您可以找到常见的设备类型，也可以增加新的设备。

![](https://cdn.funjoy.tech/web/blog/mobile_debug/chrome_console.jpg)

这种方式仅用于在设计制作页面时，快速预览和模拟移动端的UI显示情况，并不能完全反映设备上的实际情况，也无法输出对应的移动端设备性能信息。

## 3. 使用vConsole，为任何页面添加控制台

vConsole 是一个由微信前端团队研发的 Web 前端开发者面板，可用于展示 console 日志，方便开发、调试。vConsole会在页面中生成一个浮动的控制台，点击页面右下角的  **vConsole**  按钮，即可展开控制台查看页面输出的日志信息，如下图所示：

![](https://cdn.funjoy.tech/web/blog/mobile_debug/vConsole_mobile.jpg)

您只需使用文本编辑器打开需应用对应的html文件，并在</body>标签前嵌入下面这段代码，即可在页面中嵌入vConsole：

```
<script src="https://unpkg.com/vconsole/dist/vconsole.min.js"></script>
<script>
  // VConsole will be exported to `window.VConsole` by default.
  var vConsole = new window.VConsole();
</script>
```

![](https://cdn.funjoy.tech/web/blog/mobile_debug/vConsole_html.jpg)

当然，您也可以使用拼图来嵌入，请在init初始标签中，使用如下拼图来完成嵌入操作：

![](https://cdn.funjoy.tech/web/blog/mobile_debug/vConsole_puzzles.jpg)

其中，after ... second(s)拼图的时间，取决于您的网络加载该js文件的速度，如果开启后页面右下角没有显示出绿色的  **vConsole**  按钮，请刷新页面重试。

如果您的网络速度较慢，或者无法访问，您也可以在vConsole项目的Github页面下载该js文件到本地，以提高加载速度。

下载地址： https://github.com/Tencent/vConsole/releases/latest

下载压缩包后，请将 **dist** 目录中的 vconsole.min.js 文件复制到您的应用文件夹中，并替换拼图或html中的引用地址。

或者使用vConsole项目的国内CDN加速路线：

```
<script src="https://cdn.bootcdn.net/ajax/libs/vConsole/3.9.1/vconsole.min.js"></script>
<script>
  // VConsole will be exported to `window.VConsole` by default.
  var vConsole = new window.VConsole();
</script>
```

此加速服务由猫云提供，项目地址：https://www.bootcdn.cn/vConsole/


## 4. 使用weinre将移动端设备日志映射到电脑中

vConsole非常方便，但是它的日志只能在移动端查看。如果你想要提升效率，可以使用weinre服务在浏览器里直接查看移动端的页面日志。此项服务需要使用npm安装，如果你不了解，请先学习相关知识。

使用如下代码安装并启用weinre，其中，请替换 192.168.X.X 为您的电脑本地IP地址：

```
sudo npm -g install weinre
weinre --boundHost 192.168.X.X
```

安装完成后，将如下代码嵌入到您的应用html中，与第三个方法类似：

```
<script src="http://192.168.X.X:8080/target/target-script-min.js"></script>
```

![](https://cdn.funjoy.tech/web/blog/mobile_debug/weinre_install.jpg)

此时，如果您使用手机或者其他移动设备，通过本地IP地址访问此应用页面，将可以在weinre提供的调试客户端页面查看移动端设备访问时产生的日志：

![](https://cdn.funjoy.tech/web/blog/mobile_debug/weinre_use.jpg)

…… 

如果您没有macOS的电脑，方法3与方法4是一个简单的选择。或者当您并不想使用数据线连接手机，或在办公室请同事们一起测试时，可以这样建立远程调试，都可以轻松地查看页面日志。

当然，在移动端调试的方法还有很多，以上仅仅是我们在开发过程中经常用到的几种方式。如果您有更好的办法，欢迎留言给我们，或者在社区中（论坛、QQ群）与我们交流。
