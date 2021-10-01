# Verge3D 3.8 pre5预览版

Verge3D 3.8正式版发布在即。此次第五个预览版本带来了Blender Eevee的动态环境遮蔽效果、支持法线映射的平面光照探头、升级版的保存状态和撤消状态拼图，以及支持了Maya渐变节点的 _Mirror(镜子)_ 和 _Wrap(包裹)_ 模式。详细介绍如下：

## Blender专属特性

您现在可以使用Eevee的动态[环境遮蔽](https://docs.blender.org/manual/en/latest/render/cycles/world_settings.html#ambient-occlusion)，这是基于地面真实环境遮蔽(GTAO)技术。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/blender-ao-settings.png)

实践证明，它比以前由SSAO拼图提供的效果要快得多，也更逼真。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/blender-ambient-occlusion-3.8pre5.jpg)

我们在 _reflection plane light probes(反射平面光照探头)_ 中支持了法线映射。此外，反射平面现在性能更好了，尤其是在移动设备上。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/blender-load-unload-demo-with-normalmap.jpg)

对[Load Unload](https://cdn.soft8soft.com/demo/applications/load_unload/load_unload.html)演示案例做了包含此功能的更新。

## 3ds Max专属特性

您现在可以通过添加 _V3DReflectionPlane_ 对象使用 _Planar light probes(平面光照探头)_ 。该对象可以在 创建面板 ->帮助对象 ->Verge3D 子类别中找到。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/max-light-probe-reflection-plane-create.jpg)

得益于此，现在可以您可以应用中实现实时的镜面反射或地板反射了。反射也会应用法线映射。请查看最新的[Load Unload(加载与卸载)](https://cdn.soft8soft.com/demo/applications/load_unload_max/load_unload.html)演示案例。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/max-load-unload-demo.jpg)

我们添加了一个名为 _Fix Ortho Zoom_ 的设置，您可以使用它来设置轨道摄影机与其子对象，开启后当用户缩放摄影机时其子对象不会移动。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/max-verge3d-settings-fix-ortho-zoom.png)

## Maya专属特性

您现在可以方便地使用唯一资产来同时导出Verge3D/GLTF和USDZ格式。此功能依赖于 _USDPreviewSurface_ 材质，当导出到Verge3D时，它将变成一个与GLTF兼容的PBR材质。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/pbr-usd-surface-example.jpg)

因此，您可以从同一个场景中制作同时支持基于WebXR和基于苹果USDZ的增强现实应用！请注意，此节点只在Maya 2022有。

您现在可以通过添加 _Reflection Plane(反射面)_ 对象使用 _Planar light probes(平面光照探头)_ 。得益于此，现在可以您可以应用中实现实时的镜面反射或地板反射了。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/maya-light-probe-reflection-plane-create.jpg)

我们添加了一个名为 _Fix Ortho Zoom_ 的设置，您可以使用它来设置轨道摄影机与其子对象，开启后当用户缩放摄影机时其子对象不会移动。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/maya-verge3d-settings-fix-ortho-zoom.png)

为 _Ramp(渐变)_ 节点支持了 _Mirror(镜子)_ 和 _Wrap(包裹)_ 的模式。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/maya-ramp-node-settings-mirror-wrap.png)

修复了一个与 _NURBS_ 表面相关的导出问题。

## 拼图

新增拼图 _is scene loaded(场景是否已加载)_ 。您可以使用它来检查特定场景是否已经在动态加载场景中加载。有关实际使用示例，请查看 _Load Unload(加载与卸载)_ 演示案例。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/puzzle-is-scene-loaded.jpg)

拼图 _save state(保存状态)_ 和 _undo state(撤消状态)_ 现在可以移除和创建对象。以前，它们只能改变对象的状态。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/puzzles-save-state-undo-state.png)

拼图 _get camera direction(获取摄影机方向)_ 现在可适用于在 _ortho(正交)_ 摄像机。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/puzzle-get-camera-direction.png)

_HTML event_ 拼图添加 _load_ 选项。感谢用户[反馈](https://www.soft8soft.com/topic/feature-request-onload-function/)。

## 其他改进

现在，通过 _performance profile(性能概况)_ 拼图（或通过P-P-P快捷键）输出的信息中包含了场景中使用到的 _light probes(光照探头)_ 信息。

![](https://www.soft8soft.com/wp-content/uploads/2021/09/performance-profile-light-probes.png)

修复了退出AR模式时缺少背景的问题。感谢用户[反馈](https://www.soft8soft.com/topic/do-you-have-to-refresh-the-page-after-exiting-ar-mode/)！

我们确保了Verge3D与即将到来的Windows11以及Windows10的ARM版本的兼容性。我们还确保了WebGL2.0系统可以在即将到来的iOS15上工作。

新撰写了关于[server side render(服务器端渲染)](https://www.soft8soft.com/docs/manual/en/programmers_guide/Server-Side-Rendering.html)的文档。用户手册中还有其他各种更新。

我们在引擎代码中普遍添加了 _端到端_ 和 _单元测试_ 。从长远来看，它将能提高Verge3D的稳定性。

一如既往，从[下载页面](https://www.soft8soft.com/get-verge3d/)获取最新版安装包！欢迎提出反馈与建议！