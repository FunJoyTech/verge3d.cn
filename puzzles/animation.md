# Animation

The puzzles from this category perform operations with animation clips.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#play_animation)

**"play animation"**

Plays an animation clip. Animation clip names correspond to objects to which animation is assigned in 3ds Max or Blender \(only one animation clip can be assigned per object\). Use the [animation selector](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#select_animation) puzzle to provide an animation clip for this puzzle.

Use the "from" and "to" fields to specify the frame range. Use the "speed" field to specify the playback speed. The "reversed" checkbox enables reversed playback. The drop-down can be used to change the animation mode - "auto" allows for using the animation mode specified in 3ds Max or Blender, while the other modes override the settings specified in 3ds Max or Blender.

Puzzles in the "when finished: do" slot are processed once the animation is finished \(this only is valid for the "once" animation mode\).![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-play.jpg)

This puzzle also works for a list of animation clips.

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#stop_animation)

**"stop animation"**

Stops playing back an animation clip. Also works for a list of animation clips.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-stop.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#pause_animation)

**"pause animation"**

Pauses an animation clip playback so that it can be resumed later starting from the frame it was paused on. Also works for a list of animation clips.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-pause.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#resume_animation)

**"resume animation"**

Resumes a previously paused animation clip. Also works for a list of animation clips.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-resume.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#set_animation_frame)

**"set animation frame"**

Sets an animation clip to a specified frame. Also works for a list of animation clips.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-set-animation-frame.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#is_animation_playing)

**"is animation playing"**

Checks if an animation clip \(or any of animations in a list\) is currently being played back.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-is-playing.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#get_animation)

**"get animation"**

Retrieves a specified object's animation clip. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle. The return value is always a list of animation clips \(even if there is only one of them\).![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-get-animation.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#animate_param)

**"animate param"**

Animates a numeric parameter \(or all parameters in a list or a [dictionary](https://www.soft8soft.com/docs/manual/en/puzzles/Dictionaries.html)\) in between **from** and **to**, during a period specified with **duration** \(in seconds\). The **easing** dropdown allows you to specify the animation mode \(see below\).

The **repeat** field specifies the number of repetitions after the first animation is complete. The **yoyo** checkbox enables backtrack movement \(works for **repeat** &gt; 1\).

Puzzles in the **on update do** slot are triggered every rendering frame while the parameter is animated. Puzzles in the **when finished do** slot are triggered once the animation is finished.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-animate-param.jpg)

This puzzle wraps the [Tween.js](https://github.com/tweenjs/tween.js/blob/master/docs/user_guide.md) library, exposing its all [31 easing modes](http://tweenjs.github.io/tween.js/examples/03_graphs.html) \(pictured\), duration, repeat and yoyo settings, and the update and complete callbacks.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-animate-param-easing-modes.jpg)

The in-between value may be retrieved with an [updated value](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#updated_value) puzzle usually placed inside the **on update do** slot.

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#updated_value)

**"updated value"**

Returns the in-between value produced by the [animate param](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#animate_param) puzzle. Depending on the type of the animated parameter, can be a number, a list or a [dictionary](https://www.soft8soft.com/docs/manual/en/puzzles/Dictionaries.html).![](https://www.soft8soft.com/docs/files/puzzles/puzzles-animation-updated-value.jpg)

This puzzle may be placed anywhere in a scenario, but naturally works in the **on update do** slot of the [animate param](https://www.soft8soft.com/docs/manual/en/puzzles/Animation.html#animate_param) puzzle where it is updated every frame.

