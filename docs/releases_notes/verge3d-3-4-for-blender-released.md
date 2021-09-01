# Verge3D 3.4 for Blender 发布

> 发布时间：2020年9月24日

作为面向艺术家与设计师的WebGL开发套件，Verge3D一直在可用性和易用性角度做出改进与升级。



Verge3D 3.4 版的新特性包括：页面滚动效果、多行文本和脚本拼图、支持OSL着色器、新的Blender集成、低延迟音频、引入拼图方式增加雾和射线投射效果、AR模式，以及许多其他特性和性能改进。详见下文。



## 滚动过渡效果

通过在拼图中跟踪用户的页面滚动变化量，可以根据滚动条的位置在3D场景中实现各种变换。您可用这种效果创建有趣的网站、登录页或产品演示等。例如，在此[官方案例](https://cdn.soft8soft.com/demo/applications/scroll_animation/scroll_animation.html)中，页面滚动量会影响动画、相机位置和颜色变化。



此特性基于**event(事件)拼图**的新选项——**scroll(滚动)**实现。同时，**get event property(获取项目属性)拼图**新增了**scrollX(水平滚动)**和**scrollY(垂直滚动)**属性。

![image](https://verge3d.funjoy.tech/web/image/1966/puzzle-event-scroll.jpg?access_token=98bfc239-6398-414a-9eda-17c5dd3a4c36)



有关详细说明，请参见以下教程：  
B站地址：https://www.bilibili.com/video/BV1pa4y1L79t/

<iframe src="//player.bilibili.com/player.html?aid=669966712&bvid=BV1pa4y1L79t&cid=243941579&page=1&high_quality=1&danmaku=0" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" width="800px" height="600px"> </iframe>




此案例**“Scroll Animation”**的源文件包含在Verge3D 3.4版的发行包中。



## 多行文本和脚本拼图

现在，**“Text(文本)”类别**中提供用于输入多行文本的拼图，它可与任何接受文本作为输入对象的拼图一起使用。

![image](https://verge3d.funjoy.tech/web/image/1967/puzzle-multi-line.jpg?access_token=725365d0-1514-4a4d-ab85-53fe24000cc2)

使用该拼图，您可以在应用中插入大量文本，如产品描述，或某些自定义的HTML / CSS标记。

多行拼图基于可嵌入的[Ace](https://ace.c9.io/)编辑器开发。Ace因用于Amazon的Cloud9的集成开发环境而被人熟知。它提供的特色功能包括语法突出显示、行编号、自动缩进，代码折叠和实时语法检查器等。

另外，“**Advanced(高级)”**类别中新增了可执行JavaScript脚本的拼图。您可将与**多行文本拼图**连用，直接在拼图编辑器中使用代码功能，无需手动编辑脚本文件。

![image](https://verge3d.funjoy.tech/web/image/1968/puzzle-exec-script.jpg?access_token=e46dfa6b-a462-4ef0-aa0e-7aad6f5fbd9e)

在此拼图中键入的JavaScript代码可以与场景的其他元素交互。 因此，您可以访问变量拼图，并从其内部触发规程拼图。

![image](https://verge3d.funjoy.tech/web/image/1969/exec-puzzle-vars-proc.jpg?access_token=d79c1272-29ea-4f13-893e-eaf2f7d3d3f4)

直接通过编辑JavaScript脚本来实现拼图交互的旧方法依然有效。关于此类用法的相信信息，请参阅[用户手册](https://www.soft8soft.com/docs/manual/en/introduction/Using-JavaScript.html)中的相关章节。



## OSL 着色器

现在，您可以使用开放着色语言（Open Shading Language）创建自定义的实时着色器。您可在Blender的“**Scene(场景)**”选项卡中启用此功能，请先切换到“**Cycles渲染器**”，然后勾选下方的复选框：



![image](https://verge3d.funjoy.tech/web/image/1970/blender-enabling-OSL.jpg?access_token=60a4af98-16d7-4c5c-b5c5-8b55bc58f354)



接下来，即可以在材质中使用“**Script(脚本)**”节点来调用自定义OSL文件。

![image](https://verge3d.funjoy.tech/web/image/1971/blender-osl-shader-example.jpg?access_token=4ef53025-1317-44b5-a5f4-0a136b65cc1b)



着色器本身可以使用OSL代码编写，也可以从某些[着色器库](https://github.com/ADN-DevTech/3dsMax-OSL-Shaders)中直接借用。 例如，3ds Max的检查着色器的代码如下：

```
shader Checker
[[ string help = "A simple Checkboard OSL sample shader",
   string category = "Textures"
]]
(
  point UVW   = vector(u,v,0) 
    [[ string help="The position to shade. Default to the standard UV space." ]],
  float Scale = 0.25, 
  color Color1 = color(1,1.0,0.2),   
  color Color2 = color(0.2,0.2,1.0),  

  output color Col = 0
)
{
    point p = UVW / Scale;
    int x = (int)mod(p[0],2.0);
    int y = (int)mod(p[1],2.0);
    int z = (int)mod(p[2],2.0);

    if( ((x%2) ^ (y%2)) == (z%2) ){
        Col = Color1;
    } else {
        Col = Color2;
    }
}
```

如果您对手动转换和调试OSL着色器感兴趣，可使用脚本`osl2glsl.py`运行转换器。 该转换器已在[Github](https://github.com/Soft8Soft/pyosl)上基于MIT许可开源。



## Blender集成

修复了与最近发布的Blender 2.9的节点材质相关的各种兼容性问题。此外，我们还为即将发布的Blender 2.91兼容做了一些准备工作。支持了Cycles节点**Wavelength(波长)**，它将波长值转换为RGB值，可用于获得光谱上的特定颜色。

![image](https://verge3d.funjoy.tech/web/image/1972/blender-wavelength-node.jpg?access_token=a0a010e7-5f5f-4238-9e95-be83cd1e7e4d)



“相机设置"中增加了From Cursor按钮，可用于通过3D光标设置相机目标。

![image](https://verge3d.funjoy.tech/web/image/1973/blender-camera-target-from-cursor.jpg?access_token=5d17540c-af29-43a5-862d-c4bdaf22e2e3)

最后，现在有可能在兼容gltf的材质中使用外部遮挡贴图（在AO必须始终打包到ORM纹理之前）。



## 网络音频

**load sound(加载声音)拼图**新增切换**sound(声音)**和**music(音乐)**。其中，切换到声音表示启用Web Audio后端，切换到音乐表示启用HTML5音频后端。

![image](https://verge3d.funjoy.tech/web/image/1974/sound-music-puzzle.jpg?access_token=dd9bf852-401d-4d5c-8ab8-a769d25f39a1)

Web Audio后端可播放低延迟和无间隙循环的音频。我们已经优化了发型包中所有案例的音频部分。

因为Web Audio需要消耗更多的内存和更高的处理性能，我们建议您仅将其用于短的音频片段。对于较长的音频片段，例如背景音乐，最好使用HTML5音频方式。

此外，**feature available(可用功能)**拼图新增**Web Audio API**选项，您可以在此检查浏览器是否支持此Web标准。 您也可以使用JavaScript API的方式`Detector.checkWebAudio()` 进行检查。

![image](https://verge3d.funjoy.tech/web/image/1975/feature-available-webaudio-api.jpg?access_token=5b7a1b41-427e-4485-ae8e-04aff5b05b19)

拼图编辑器的“**Sound/Video(**声音/视频)”类别已重命名为“**Audio/Video(**音频/视频)”。

现在可以在拼图编辑器的“**Init(**初始化)”选项卡中使用声音拼图，从而预先加载声音。



## AR 模式

目前，**enter AR mode(进入AR模式)**拼图支持类似于VR对应对象的各种定位模式：**looking around(环顾)**，**sitting or standing(坐/立)**，**room(室内)**，**walking(步行)**和**viewer locked(观察者锁定)**。

![image](https://verge3d.funjoy.tech/web/image/1976/enter-AR-puzzle.jpg?access_token=8e9372db-e458-4e5c-a272-c20f9f9a8156)

为与旧场景兼容，AR的最佳模式是**sitting(坐)**或**standing(立)**，**room(室内)**或**walking(步行)**，其中默认模式设置是**looking around(环顾)**（即当用户从场景原点观看）。



## 雾和射线投射拼图

新增**add fog(添加雾)**拼图，无需编码即可添加雾效。

![image](https://verge3d.funjoy.tech/web/image/1977/add-fog-puzzle.jpg?access_token=95d6c12d-88cd-440a-a1f9-35cec9812101)

您也可以指定雾的颜色和密度，将RGB或密度设置为零从而将其删除。

![image](https://verge3d.funjoy.tech/web/image/1978/fog-example.jpg?access_token=0a6747ac-fdc1-4bd1-bcbe-a7b4b8ba8a5b)

新增**ray cast(射线投射)**拼图，您可以在[参考页面](https://www.soft8soft.com/docs/manual/en/puzzles/Scenes.html#raycast)找到相关描述和使用示例。

![image](https://verge3d.funjoy.tech/web/image/1979/ray-cast-puzzle.jpg?access_token=9f9cddfe-6e76-4427-9993-bcabc05104c3)

## 连接器拼图

Connectors(连接器)拼图是一个新的便捷拼图，可用于组合具有返回值（例如声音）的拼图。

![image](https://verge3d.funjoy.tech/web/image/1980/puzzle-connector.png?access_token=e2fa9145-8c5a-483f-8bc8-cd87d99efdd8)

您无需再创建辅助变量，也能将这些拼图组合在一起。



## 安装程序签名

我们在Windows版安装程序中已使用扩展验证证书进行签名，因此不再显示“未知发布者”的警告。



## 其他改进

**replace texture(替换纹理)**拼图现在支持将视频纹理分配给与gltf兼容的材质。**replace texture(替换纹理)**和**get texture param(获取纹理参数)**拼图也可以正确地与视频纹理配合使用。

通过在WebGL纹理中使用RGB格式而非RGBA，减少了JPEG纹理的内存消耗。此外，**export to gltf(导出到gltf)**拼图现在可以直接导出JPEG纹理，而无需将其预转为PNG。

现在可以通过将JavaScript API属性设置 `OrbitControls.screenSpacePanning`为**false**来启用水平相机平移（用于实现类似Google Maps的悬停控制），例如：

```
app.controls.screenSpacePanning = false;
```

**set style(**设置样式)和**set attribute(**设置属性)拼图现在可以在IE 11中使用。**set style(**设置样式)拼图的插槽**@media**现在也可以在macOS和iOS的Safari浏览器中使用。

我们在**用户手册**中添加了[新的章节](https://www.soft8soft.com/docs/manual/en/introduction/Hardware-Related-Issues.html)，其中概述了创建场景时可能遇到的一些硬件限制。增加了对有关“Too many attributes”的错误的说明。



## 故障修复

- “活动摄像机”拼图现在可以正确启用/禁用渲染拼图（感谢用户报告[问题](https://www.soft8soft.com/topic/problem-when-switching-active-camera-with-antialias/)）。
- 现在可以在VR模式下正确切换基于图像的照明（感谢用户报告[问题](https://www.soft8soft.com/topic/vr-version-of-my-vehicle-fantasy-timer-and-ibl-lighting-issues/)）。
- 修复了**export to gltf(导出至gltf)**拼图时导致UV丢失的问题。
- 修复了未完成回调时相机补间的错误（感谢用户报告[问题](https://www.soft8soft.com/topic/bug-orbitcontrol-tween-not-calling-finishcb-if-the-camera-is-already-there/)）。
- 修复了形状键和分配材质的错误（感谢用户报告[问题](https://www.soft8soft.com/topic/assign-material-conflicts-with-morph-factor/)）
- 在**event(项目)**拼图中删除了重复的point事件选项。
- 修复了Blender当前不受支持的**BSDF Toon**着色器带来的引擎崩溃。
- JavaScript方法`Material.toJSON()`不再因基于节点的材质而出错。



## 立即升级

一如既往，在[Verge3D最新发行版下载](https://mp.weixin.qq.com/s/K-AWZ8smyOUt1pm0lgmpzQ)一文中获取最新预览版的百度盘分享链接吧！欢迎通过[论坛](https://www.soft8soft.com/forums/)、微信公众号、[QQ群](https://shang.qq.com/wpa/qunwpa?idkey=c31cf6597f3ed7ce68bd47aba6bba23049bf973ac6acc59b0a5a7d1bd933b3ea)、[电子邮件](mailto:verge3d@funjoy.tech)提出建议与意见！

