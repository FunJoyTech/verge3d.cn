# Verge3D 3.8.1维护更新
> 发布日期： 2021年10月5日

Verge3D此次维护更新修复了若干在3.8版中已发现的问题，另带来了一些改进：

## 功能修复

通过实现绕过驱动错误，新引入的 _ambient occlusion(环境光遮蔽)_ 现在可以在Intel 600系列芯片组上运行了。感谢[反馈](https://www.soft8soft.com/topic/new-ao-turns-scene-objects-dark-on-integrated-graphics/)！

修复了以下专门针对3ds Max（可能还有Maya）的问题：在某些Win10系统上，_HDR贴图_ 被强制转换为低动态范围的PNG格式，这导致了照明中断。虽然导致这种行为的原因仍不清楚，但我们能够通过在Python导出器中明确指定此类文件的MIME类型来进行变通。感谢[用户反馈](https://www.soft8soft.com/topic/sorry-visual-bug-again/)以及对解决此错误的帮助!

移除了类似于 _404 Failed to load detect-gpu.umd.js.map_ 的控制台警告信息。此问题由用户通过企业支持渠道反馈。

修复了（在3ds Max中）使用米以外的单位时 _Area(区域)_ 灯光的工作强度不正确的错误。

Blender 3.0 Alpha版正在积极开发中，我们修复了与其兼容的各种缺陷。

## 新的功能
默认情况下，提供给 _set/get object transform_ 拼图的坐标是相对于对象的父对象（也称为 _父空间_ ）设置的。现在为这些拼图添加了 _世界空间_ 的选择。

![](https://www.soft8soft.com/wp-content/uploads/2021/10/puzzle-set-transform-world-space.png)

为物理拼图 _get body param_ 和 _apply body param_ 添加了一个新的可影响 _rotation_ 的下拉选项。

![](https://www.soft8soft.com/wp-content/uploads/2021/10/puzzles-physics-get-param-set-param-rotation.png)

最后，几天前发布的 _visibility breakpoints(可见性断点)_ 功能现在不仅适用于网格对象，也适用于摄影机。例如，当以横向或纵向模式查看场景时，可以切换摄影机（比如增加/减少FOV）。

## 下载更新
如果您受到上述问题的影响，或者希望利用引入的改进，请使用Verge3D 3.8.1升级您的Web3D交互应用。一如既往，请从[下载](https://www.soft8soft.com/get-verge3d/)页面获得最新版本。