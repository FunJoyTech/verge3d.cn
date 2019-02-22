---
description: 待校订
---

# 在移动浏览器上进行（Testing on Mobile Browsers）

## 在移动浏览器上测试Verge3D应用程序

从App Manager启动Verge3D应用程序时，它使用**localhost**地址在本地开发服务器上运行。此地址只能在本地计算机上使用。为了测试您的应用在移动设备的浏览器上的工作方式，您可以使用以下过程之一。

* 方法＃1：本地IP地址
* 方法＃2：本地IP地址+ QR码
* 方法＃3：端口转发

＃

### 方法＃1：本地IP地址

使用任何文本编辑器 打开Python脚本verge3d / manager / server.py。找到以**ADDRESS**开头的行- 文件中的这个位置应该如下所示：`ADDRESS = 'localhost' #ADDRESS = '0.0.0.0'`

从第二行（取消注释）中删除哈希符号＃，制作它`ADDRESS = 'localhost' ADDRESS = '0.0.0.0'`

保存文件并重新启动3ds Max或Blender。

现在，您可以在本地Wi-Fi或以太网网络中使用IP地址，而不是**localhost**。您可以从操作系统首选项中找到您的计算机IP地址：[Windows 10](https://www.groovypost.com/howto/find-windows-10-device-ip-address/)，[Windows 7](https://www.groovypost.com/howto/microsoft/windows-7/find-your-local-ip-address-windows-7-cmd/)，[Mac](https://www.wikihow.com/Find-Your-IP-Address-on-a-Mac)，[Linux](https://www.linuxtrainingacademy.com/determine-public-ip-address-command-line-curl/)。通过导航到网络地址，在移动设备的Web浏览器上启动App Manager，例如：

```text
http://192.168.0.2:8668/
```

最后，像往常一样在移动设备上运行应用程序 - 通过在应用管理器中点击蓝色图标。

＃

### 方法＃2：本地IP地址+ QR码

这是方法＃1的变体。您可以使用网络地址通过App Manager 在计算机上启动应用程序，而不是在移动设备的浏览器上运行App Manager和应用程序。

```text
http://192.168.0.2:8668/
```

可以使用QR码在移动设备上方便地打开应用程序的链接。您需要在计算机的浏览器中安装QR代码扩展，例如，[QR Code Generator for Chrome](https://chrome.google.com/webstore/detail/the-qr-code-generator/gcmhlmapohffdglflokbgknlknnmogbb?hl=en)或[QRify for Safari](https://safari-extensions.apple.com/details/?id=de.retiolum.safari.qrify-RSADU6MKX9)。![](https://www.soft8soft.com/docs/files/testing-mobile-browsers/qr-code-extention-chrome.jpg)

可以使用移动设备的相机扫描获得的QR码，从而在移动浏览器上打开链接。您需要先在移动设备上安装QR扫描仪应用程序，例如，[Android的QR码阅读器](https://play.google.com/store/apps/details?id=tw.mobileapp.qrcode.banner&hl=en)或[iPhone的QR阅读器](https://itunes.apple.com/au/app/qr-reader-for-iphone/id368494609?mt=8)。

＃

### 方法＃3：端口转发

此方法适用于Android设备。使用USB线和Chrome DevTools，您可以直接从移动设备的浏览器启动App Manager，导航到localhost：8668。

与方法1-2不同，此方法适用于启动AR / VR应用程序，因为localhost不需要移动浏览器和工作站之间的安全连接。此外，您还可以看到移动浏览器控制台的输出。

在Android设备上，转到**设置&gt;开发人员选项**并启用**USB调试**。

```text
By default, the developer options in Android devices are hidden. You can unlock them by locating the Build number in your Settings menu and tapping it multiple times.
```

![](https://www.soft8soft.com/docs/files/testing-mobile-browsers/android-developer-options.jpg)

使用USB线连接Android设备。在计算机上的Chrome浏览器中，导航到chrome：// inspect。![](https://www.soft8soft.com/docs/files/testing-mobile-browsers/chrome-inspect.jpg)

这应该会在您的Android设备上显示一个对话框弹出窗口 - 如果没有，请重新加载chrome：//检查或重新插入USB连接线。在弹出窗口中，点击OK即可进行USB调试。![](https://www.soft8soft.com/docs/files/testing-mobile-browsers/android-usb-debugging.jpg)

您现在应该在chrome：// inspect页面上看到您的Android设备。此外，如果您在移动设备上打开Chrome，则应在此处列出。![](https://www.soft8soft.com/docs/files/testing-mobile-browsers/chrome-inspect2.jpg)

单击chrome：// inspect页面上的**Port forwarding**按钮。在显示的窗口中：在**Port**字段中，键入8668，在**IP地址和端口**字段中，键入localhost：8668。单击“ **启用端口转发”**并使用**“完成”**按钮关闭窗口。![](https://www.soft8soft.com/docs/files/testing-mobile-browsers/chrome-port-forwarding.jpg)

该铬：//检查页面应该显示设备附近的端口转发的绿色指示灯。![](https://www.soft8soft.com/docs/files/testing-mobile-browsers/chrome-port-forwarding2.jpg)

因此，您应该可以通过导航到localhost：8668直接从移动设备的浏览器启动App Manager 。此外，您可以通过单击chrome：// inspect页面上的**inspect**链接来**查看**移动浏览器控制台的输出。

