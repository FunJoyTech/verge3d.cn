# AnimationAction

## AnimationAction

AnimationActions调度存储在AnimationClips中的动画的表现。  
注意：大多数AnimationAction的方法都可以链接。  
有关Verge3D动画系统的不同元素的概述，请参阅本手册“后续步骤”部分中的“动画系统”一文。

### 构造函数

#### AnimationAction\(mixer : AnimationMixer, clip : AnimationClip, localRoot : Object3D\)

mixer - the **AnimationMixer** that is controlled by this action.  
clip - the **AnimationClip** that holds the animation data for this action.  
localRoot - the root object on which this action is performed.  
  
注意：不应直接调用此构造函数，而应使用AnimationMixer.clipAction实例化AnimationAction，因为此方法提供了缓存以获得更好的性能。

### 属性

#### \#.clampWhenFinished : Boolean

If **clampWhenFinished** is set to true the animation will automatically be paused on its last frame.  
  
如果**clampWhenFinished**设置为false，则在操作的最后一个循环结束时，enabled将自动切换为false，因此该操作不会产生进一步的影响。  
  
默认值为false。  
  
Note: **clampWhenFinished** has no impact if the action is interrupted \(it has only an effect if its last loop has really finished\).

#### \#.enabled : Boolean

Setting **enabled** to **false** disables this action, so that it has no impact. Default is **true**.  
  
When the action is re-enabled, the animation continues from its current time \(setting **enabled** to **false** doesn't reset the action\).  
  
Note: Setting **enabled** to **true** doesn’t automatically restart the animation. Setting **enabled** to **true** will only restart the animation immediately if the following condition is fulfilled: paused is **false**, this action has not been deactivated in the meantime \(by executing a stop or reset command\), and neither weight nor timeScale is 0.

#### \#.loop : Number

The looping mode \(can be changed with setLoop\). Default is v3d.LoopRepeat \(with an infinite number of repetitions\)  
  
Must be one of these constants:  
  
v3d.LoopOnce - playing the clip once,  
v3d.LoopRepeat - playing the clip with the choosen number of **repetitions**, each time jumping from the end of the clip directly to its beginning,  
v3d.LoopPingPong - playing the clip with the choosen number of **repetitions**, alternately playing forward and backward.

#### \#.paused : Boolean

Setting **paused** to **true** pauses the execution of the action by setting the effective time scale to 0. Default is **false**.  
  


#### \#.repetitions : Number

The number of repetitions of the performed AnimationClip over the course of this action. Can be set via setLoop. Default is **Infinity**.  
  
Setting this number has no effect, if the loop mode is set to v3d.LoopOnce.

#### \#.time : Number

The local time of this action \(in seconds, starting with 0\).  
  
The value gets clamped or wrapped to 0...clip.duration \(according to the loop state\). It can be scaled relativly to the global mixer time by changing timeScale \(using setEffectiveTimeScale or setDuration\).  


#### \#.timeScale : Number

Scaling factor for the time. A value of 0 causes the animation to pause. Negative values cause the animation to play backwards. Default is 1.  
  
Properties/methods concerning **timeScale** \(respectively **time**\) are: getEffectiveTimeScale, halt, paused, setDuration,setEffectiveTimeScale, stopWarping, syncWith, warp.

#### \#.timeStart : Number

The local start time for this action \(in seconds\). Use with AnimationClip.duration to set the playback range.  
  


#### \#.weight : Number

The degree of influence of this action \(in the interval \[0, 1\]\). Values between 0 \(no impact\) and 1 \(full impact\) can be used to blend between several actions. Default is 1.   
  
Properties/methods concerning **weight** are: crossFadeFrom, crossFadeTo, enabled, fadeIn, fadeOut, getEffectiveWeight,setEffectiveWeight, stopFading.

#### \#.zeroSlopeAtEnd : Boolean

Enables smooth interpolation without separate clips for start, loop and end. Default is **true**.

#### \#.zeroSlopeAtStart : Boolean

Enables smooth interpolation without separate clips for start, loop and end. Default is **true**.

### 方法

#### \#.crossFadeFrom \(fadeOutAction : AnimationAction, durationInSeconds : Number, warpBoolean : Boolean\) : AnimationAction

Causes this action to fade in, fading out another action simultaneously, within the passed time interval. This method can be chained.  
  
If warpBoolean is true, additional warping \(gradually changes of the time scales\) will be applied.  
  
Note: Like with **fadeIn**/**fadeOut**, the fading starts/ends with a weight of 1.

#### \#.crossFadeTo \(fadeInAction : AnimationAction, durationInSeconds : Number, warpBoolean : Boolean\) : AnimationAction

Causes this action to fade out, fading in another action simultaneously, within the passed time interval. This method can be chained.  
  
If warpBoolean is true, additional warping \(gradually changes of the time scales\) will be applied.  
  
Note: Like with **fadeIn**/**fadeOut**, the fading starts/ends with a weight of 1.

#### \#.fadeIn \(durationInSeconds : Number\) : AnimationAction

Increases the weight of this action gradually from 0 to 1, within the passed time interval. This method can be chained.

#### \#.fadeOut \(durationInSeconds : Number\) : AnimationAction

Decreases the weight of this action gradually from 1 to 0, within the passed time interval. This method can be chained.

#### \#.getEffectiveTimeScale \(\) : Number

Returns the effective time scale \(considering the current states of warping and paused\).

#### \#.getEffectiveWeight \(\) : number

Returns the effective weight \(considering the current states of fading and enabled\).

#### \#.getClip \(\) : AnimationClip

Returns the clip which holds the animation data for this action.

#### \#.getMixer \(\) : AnimationMixer

Returns the mixer which is responsible for playing this action.

#### \#.getRoot \(\) : Object3D

Returns the root object on which this action is performed.

#### \#.halt \(durationInSeconds : Number\) : AnimationAction

Decelerates this animation's speed to 0 by decreasing timeScale gradually \(starting from its current value\), within the passed time interval. This method can be chained.

#### \#.isRunning \(\) : Boolean

Returns true if the action’s time is currently running.  
  
In addition to being activated in the mixer \(see isScheduled\) the following conditions must be fulfilled: paused is equal to false, enabled is equal to true, timeScale is different from 0, and there is no scheduling for a delayed start \(startAt\).  
  
Note: **isRunning** being true doesn’t necessarily mean that the animation can actually be seen. This is only the case, if weight is additionally set to a non-zero value.

#### \#.isScheduled \(\) : Boolean

Returns true, if this action is activated in the mixer.  
  
Note: This doesn’t necessarily mean that the animation is actually running \(compare the additional conditions for isRunning\).

#### \#.play \(\) : AnimationAction

Tells the mixer to activate the action. This method can be chained.  
  
Note: Activating this action doesn’t necessarily mean that the animation starts immediately: If the action had already finished before \(by reaching the end of its last loop\), or if a time for a delayed start has been set \(via startAt\), a reset must be executed first. Some other settings \(paused=true, enabled=false, weight=0, timeScale=0\) can prevent the animation from playing, too.

#### \#.reset \(\) : AnimationAction

Resets the action. This method can be chained.  
  
This method sets paused to false, enabled to true, time to 0, interrupts any scheduled fading and warping, and removes the internal loop count and scheduling for delayed starting.  
  
Note: .**reset** is always called by stop, but .**reset** doesn’t call .**stop** itself. This means: If you want both, resetting and stopping, don’t call .**reset**; call .**stop** instead.

#### \#.setDuration \(durationInSeconds : Number\) : AnimationAction

Sets the duration for a single loop of this action \(by adjusting timeScale and stopping any scheduled warping\). This method can be chained.

#### \#.setEffectiveTimeScale \(timeScale : Number\) : AnimationAction

Sets the timeScale and stops any scheduled warping. This method can be chained.  
  
If paused is false, the effective time scale \(an internal property\) will also be set to this value; otherwise the effective time scale \(directly affecting the animation at this moment\) will be set to 0.  
  
Note: .**paused** will not be switched to **true** automatically, if .**timeScale** is set to 0 by this method.

#### \#.setEffectiveWeight \(weight : Number\) : AnimationAction

Sets the weight and stops any scheduled fading. This method can be chained.  
  
If enabled is true, the effective weight \(an internal property\) will also be set to this value; otherwise the effective weight \(directly affecting the animation at this moment\) will be set to 0.  
  
Note: .**enabled** will not be switched to **false** automatically, if .**weight** is set to 0 by this method.

#### \#.setLoop \(loopMode : Number, repetitions : Number\) : AnimationAction

Sets the loop mode and the number of repetitions. This method can be chained.

#### \#.startAt \(startTimeInSeconds : Number\) : AnimationAction

Defines the time for a delayed start \(usually passed as AnimationMixer.time + deltaTimeInSeconds\). This method can be chained.  
  
Note: The animation will only start at the given time, if .**startAt** is chained with play, or if the action has already been activated in the mixer \(by a previous call of .**play**, without stopping or resetting it in the meantime\).

#### \#.stop \(\) : AnimationAction

Tells the mixer to deactivate this action. This method can be chained.  
  
The action will be immediately stopped and completely reset.  
  
Note: You can stop all active actions on the same mixer in one go via mixer.stopAllAction.

#### \#.stopFading \(\) : AnimationAction

Stops any scheduled fading which is applied to this action. This method can be chained.

#### \#.stopWarping \(\) : AnimationAction

Stops any scheduled warping which is applied to this action. This method can be chained.

#### \#.syncWith \(otherAction : AnimationAction\) : AnimationAction

Synchronizes this action with the passed other action. This method can be chained.  
  
Synchronizing is done by setting this action’s time and timeScale values to the corresponding values of the other action \(stopping any scheduled warping\).  
  
Note: Future changes of the other action's **time** and **timeScale** will not be detected.

#### \#.warp \(startTimeScale : Number, endTimeScale : Number, durationInSeconds : Number\) : AnimationAction

Changes the playback speed, within the passed time interval, by modifying timeScale gradually from **startTimeScale** to **endTimeScale**. This method can be chained.

### 事件

There are two events indicating when a single loop of the action respectively the entire action has finished. You can react to them with:`mixer.addEventListener('loop', function(e) { …}); // properties of e: type, action and loopDelta mixer.addEventListener('finished', function(e) { …}); // properties of e: type, action and direction`

### 资源

有关如何获取此模块源代码的详细信息，请参阅[此页面](http://www.soft8soft.com/docs/manual/en/introduction/How-to-obtain-Verge3D-sources.html)。

