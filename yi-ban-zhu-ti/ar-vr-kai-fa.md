---
description: AR/VR Development 待校订
---

# AR 和VR的开发

Verge3D允许创建基于Web的增强现实（AR）和虚拟现实（VR）体验，这些体验运行在开发中的浏览器技术之上，称为WebXR（Web上的eXtended Reality）。

### 配置

#### VR支持

我们建议在App Manager中的应用创建设置中启用**Legacy VR**选项，以支持更广泛的设备。![](https://www.soft8soft.com/docs/files/ar-vr-development/legacy-vr-app-creation-settings.jpg)

纸板设备应该可以在Android和iOS上的任何移动浏览器中开箱即用。

[Google Daydream](https://vr.google.com/daydream/)适用于Android手机上的稳定Chrome浏览器，并在chrome：// flags页面上启用了某些WebXR选项：![](https://www.soft8soft.com/docs/files/ar-vr-development/chrome-mobile-webxr-flags.jpg)

HTC Vive和Oculus设备可在稳定的Chrome和Firefox浏览器中使用。此外，Chrome浏览器需要在chrome：// flags页面上启用某些WebXR选项：![](https://www.soft8soft.com/docs/files/ar-vr-development/chrome-desktop-webxr-flags.jpg)

#### AR支持

目前WebXR规范正在快速发展，浏览器预览版本每天都在变化。鉴于此，我们决定禁用AR功能，直到规范稳定为止。

#### WebXR Origin Trial

您可以使用所谓的**原始试用令牌**在用户启动应用时自动激活**标记**，而不是在Chrome浏览器中启用WebXR标记。您可以在[此处](https://github.com/GoogleChrome/OriginTrials/blob/gh-pages/developer-guide.md)所述的网站域中请求使用这些令牌。`<meta http-equiv="origin-trial" content="Aop1aS3O0LG/MKmDbfhMRdlXGxB1ET...rJJScdLSaYLDCMJI5iOLQ0uwhBObX0=">`

App Manager中提供 的**标准**应用程序模板已包含Verge3D Network域**cdn.soft8soft.com**的原始试用令牌。

#### HTTPS

WebXR需要安全的上下文。Verge3D应用程序必须通过HTTPS / SSL或localhost URL提供。

### 创建VR应用程序

只需[2个谜题](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#init_vr_mode)就可以为任何Verge3D应用设置VR模式。![](https://www.soft8soft.com/docs/files/ar-vr-development/minimal-vr-puzzles.jpg)

通过使用为没有控制器（例如纸板）的VR设备自动提供的基于注视的标线指针来执行与3D对象的交互。![](https://www.soft8soft.com/docs/files/ar-vr-development/gaze-based-reticle-pointer.jpg)

对于具有控制器的 VR设备，通过从控制器铸造的虚拟光线执行交互（仅支持一条光线）。![](https://www.soft8soft.com/docs/files/ar-vr-development/google-daydream-vr-controller.jpg)

您可以[在悬停时](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#when_hovered)或[单击](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#when_clicked)谜题[时](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#when_hovered)使用标准来捕获用户事件。在**点击时**拼图在2秒的互动之后触发。

### 其他链接

* [WebXR设备API解释](https://github.com/immersive-web/webxr/blob/master/explainer.md)
* [WebXR样本](https://immersive-web.github.io/webxr-samples/)
* [WebXR设备API规范](https://immersive-web.github.io/webxr/)
* [Chrome浏览器开发跟踪器](https://bugs.chromium.org/p/chromium/issues/list?can=1&q=component%3ABlink%3EWebXR&sort=-modified&colspec=ID+Pri+M+Stars+ReleaseBlock+Component+Status+Owner+Summary+OS+Modified&x=m&y=releaseblock&cells=ids)

