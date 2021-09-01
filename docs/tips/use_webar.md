# 网页增强现实使用流程

## 在Verge3D中启用WebAR



Verge3D为网络应用提供了基于浏览器的增强现实功能，但这个功能一直不是很好用，我们常常收到用户关于此功能的咨询。在这里，我们将演示如何在iPhone和Android手机上使用该功能。在Android系统手机上，此功能基于ARCore实现，在iOS系统中，您需要通过WebXR Viewer应用来访问应用网址。以下流程仅供参考，如果您发现我们的流程已经过时，欢迎评论或者联系我们反馈。

本文是使用说明，如果您想要查看开发说明，请查看用户手册：[AR/VR开发](https://www.soft8soft.com/docs/manual/zh/introduction/AR-VR-development.html#Creating_AR_Apps)。


## iOS流程

在iOS设备上启用该功能非常的简单，下载WebXR Viewer应用，访问应用网址，在浏览器中授予摄像头访问权限，即可体验该功能。

**注：**自Verge3D 3.8.0 pre2版本开始，您可以直接在iOS的Safari浏览器中访问Verge3D的AR内容了，这需要在指定应用的拼图中使用export to usdz将模型转化为usdz格式。详细说明见发行说明：[Verge3D 3.8 pre2预览版发布。](https://verge3d.funjoy.tech/blog/1/post/verge3d-3-8-pre2-134)

### 1. 下载XRViewer
应用商店地址： https://itunes.apple.com/us/app/webxr-viewer/id1295998056



### 2. 访问AR示例应用
访问官方案例Augmented Reality，测试WebXR Viewer是否可用。您可以通过WebXR Viewer的扫描二维码功能打开网址，在Chrome浏览器地址栏自带了二维码功能，点击即可生成当前访问URL对应的二维码。  
案例地址： https://cdn.funjoy.tech/verge3d/applications/augmented_reality/augmented_reality.html  



### 3. 授予权限

访问过程中，点击Enter AR即可启动增强现实进程，请授予WebXR Viewer摄像头访问权限。选择Always for this site选项，可为当前应用授予长期权限。  
完整过程录屏： https://www.bilibili.com/video/BV1cw411d79g

<iframe src="https://player.bilibili.com/player.html?aid=334044253&amp;bvid=BV1cw411d79g&amp;cid=366807422&amp;page=1&amp;high_quality=1&amp;danmaku=0" width="800px" height="600px" frameborder="no" scrolling="no" sandbox="allow-top-navigation allow-same-origin allow-forms allow-scripts allow-popups" allowfullscreen="allowfullscreen" style="box-sizing: border-box;"></iframe>





## Android平台流程
在Android系统中启用该功能需要依赖ARCore服务，而该服务又需要依赖Google Play Service服务。绝大多数国产手机的默认系统都删除了Google Play套件，底层所提供的Google服务框架往往也受到限制。因此这一过程会变得繁琐和容易失败。以下是我们在小米手机MIUI系统中的安装过程为例，演示这一过程。  
注意，安装AR服务框架以及在Play 商店中进行搜索，需要使用代理软件。本文中不涉及如何使用代理的内容。  



### 1. 安装谷歌服务框架
有很多工具都可以在国产系统中安装Google Play。根据我们的测试，推荐使用Go安装器，这是一款无需Root即可完整安装



### 2. 安装AR服务框架
在Play商店中，搜索“面向AR的Google Play服务”，选择安装该服务。注意不要使用“ARCore”作为关键词搜索，否则很可能会误导至第三方应用。



### 3. 安装Chrome浏览器
安装好谷务框架和AR服务框架后，您应该就可以在系统自带的浏览器中启用WebAR功能了，但很可能因为不同系统的浏览器对WebGL性能支持的不同设置，而导致无法正常启用。因此，我们推荐您安装Google官方浏览器Chrome。使用过程中，Chrome会提示申请使用摄像头权限，请点击允许。如果您遇到如下Chrome出现"请关闭来自其他所有气泡或叠加层，然后重试"的警告，请在手机设置中查找“显示在其他应用的上层”设置，将其中开启允许的应用关闭或停用其权限。  

![img](https://cdn.funjoy.tech/web/blog/chrome-alert.jpg ':size=500')
![img](https://cdn.funjoy.tech/web/blog/display_over_permission_page.jpg ':size=500')
![img](https://cdn.funjoy.tech/web/blog/display_over_permission_off.jpg ':size=500')


### 4. 访问AR示例应用

Chrome浏览器并没有提供扫描二维码的功能，因此您需要手动输入该地址，或者使用其他扫描工具复制URL到Chrome中打开。  
案例地址： https://cdn.funjoy.tech/verge3d/applications/augmented_reality/augmented_reality.html


### 5. 授予权限
访问过程中，点击Enter AR即可启动增强现实进程，在Chrome浏览器请求访问摄像头访问权限时，一定要点击允许。


在小米手机上的体验效果录屏如下：  
视频地址：https://www.bilibili.com/video/BV1yK4y1M79J  
<iframe src="//player.bilibili.com/player.html?aid=889081660&bvid=BV1yK4y1M79J&cid=366812367&page=1&amp;high_quality=1&amp;danmaku=0" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" width="800px" height="600px"> </iframe>

!> 注意：因为国产定制化系统对谷歌服务框架的限制各有不同，以上流程并不代表标准流程。您依然可能会遇到各种导致无法体验的问题，以及开启AR失败情况。
