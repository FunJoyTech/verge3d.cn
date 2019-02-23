---
description: Animation System 待校订
---

# 动画系统

### 概观

在Verge3D动画系统中，您可以为模型的各种属性设置动画：蒙皮和装配模型的骨骼， 变形目标，不同材质属性（颜色，不透明度，布尔值），可见性和变换。动画属性可以淡入，淡出，交叉淡化和扭曲。可以独立地改变同一对象以及不同对象上的不同同时动画的权重和时间尺度。可以同步在相同和不同对象上的各种动画。  
  
为了在一个同类系统中实现所有这一切，Verge3D动画系统 [在2015年彻底改变了](https://github.com/mrdoob/three.js/issues/6881) （注意过时的信息！），它现在有一个类似于Unity /虚幻引擎4的架构。这个页面简要概述了系统的主要组件以及它们如何协同工作。

#### 动画片段

如果您已成功导入动画3D对象（如果它具有骨骼或变形目标或两者都无关紧要） - 例如，使用Blender导出器将其从Blender导出并使用GLTFLoader将其加载到Verge3D场景中，其中一个几何体加载网格的属性应该是一个名为“animations”的数组，其中包含此模型的AnimationClips（请参阅下面的可能加载器列表）。  
  
每个**AnimationClip**通常保存对象的某个活动的数据。例如，如果网格是一个角色，则可能有一个动作剪辑用于步行循环，第二个用于跳跃，第三个用于回避等等。

#### 关键帧轨道

在这样的**AnimationClip**内部，每个动画属性的数据存储在单独的KeyframeTrack中。假设一个角色对象有一个骨架，一个关键帧轨道可以存储下臂骨骼随时间的位置变化的数据，一个不同的轨道用于相同骨骼的旋转变化的数据，第三个是轨道位置，旋转或缩放另一个骨头，等等。应该清楚的是，AnimationClip可以由许多这样的轨道组成。  
  
假设模型具有变形目标（例如，一个变形目标显示友好的面部，另一个显示愤怒的面部），每个轨道保存有关影响的信息 在剪辑的执行期间某个变形目标的变化。

#### 动画混音器

存储的数据仅构成动画的基础 - 实际播放由AnimationMixer控制。你可以想象这不仅仅是一个动画播放器，而是一个模拟硬件，如真正的调音台控制台，它可以同时控制几个动画，混合和合并它们。

#### 动画动作

该**AnimationMixer**本身只有很少的（一般）属性和方法，因为它可以通过控制AnimationActions。通过配置 **AnimationAction，**您可以确定某个**AnimationClip**何时应在其中一个混音器上播放，暂停或停止，是否必须重复剪辑，是否应该使用淡入淡出或时间缩放，以及其他的东西，例如交叉淡化或同步。

#### 动画对象组

如果希望一组对象接收共享动画状态，则可以使用 AnimationObjectGroup。

#### 支持的格式和加载器

请注意，并非所有模型格式都包含动画（特别是OBJ），并且只有一些Verge3D加载器支持AnimationClip序列。有几个是做 支持这种动画类型：

* v3d.JSONLoader
* v3d.ObjectLoader
* v3d.BVHLoader
* v3d.ColladaLoader
* v3d.FBXLoader
* v3d.GLTFLoader
* v3d.MMDLoader
* v3d.SEA3DLoader

请注意，3ds max和Maya当前无法将多个动画（即不在同一时间轴上的动画）直接导出到单个文件。

### 例

`var mesh; // Create an AnimationMixer, and get the list of AnimationClip instances var mixer = new v3d.AnimationMixer(mesh); var clips = mesh.animations; // Update the mixer on each frame function update () { mixer.update(deltaSeconds); } // Play a specific animation var clip = v3d.AnimationClip.findByName(clips, 'dance'); var action = mixer.clipAction(clip); action.play(); // Play all animations clips.forEach(function(clip) { mixer.clipAction(clip).play(); });`

