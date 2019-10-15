# Camera

The puzzles from this category perform operations with the camera.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Camera.html#look_at)

**"look at"**

Smoothly animates the active camera so that it finally targets a specified object. The numeric parameter specifies the time period over which the animation is performed \(in seconds\).![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-lookat.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Camera.html#tween_camera)

**"tween camera"**

Smoothly animates the active camera so that its position finally coincides with the position of a specified object, and the camera targets another specified object. The numeric parameter specifies the time period for the animation \(in seconds\).

The optional **when finished do** slot may be used to detect the moment when the tweening is finished.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-tween-camera.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Camera.html#set_active_camera)

**"set active camera"**

Makes a specified camera active. This can be used to change camera control mode \("orbit" vs "flying" vs "no controls"\), field of view and other settings on the fly.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-set-active.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Camera.html#get_camera_direction)

**"get camera direction"**

Returns a list of X, Y and Z components of the active camera's world direction vector. If **from mouse/touch** is checked, this puzzle casts a ray from the camera to the cursor's screen position and returns the direction of that ray. If additionaly **inverted**is checked, then the cursor's screen position coordinates are negated.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-get-camera-direction.jpg)

In the following example, an object looks at the mouse cursor. This can be achived by mapping the position of an empty/dummy object to mouse cursor with some simple math.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-get-camera-direction-example2.jpg)

In order to setup such behavior in 3ds Max, make your object follow a dummy object by utilizing the **Rotation Controllers / LookAt Constraint**. In Blender, this corresponds to the **TrackTo** constraint.

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Camera.html#autorotate_camera)

**"autorotate camera"**

Smoothly animates the active **Orbit** camera by rotating it around the target.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-autorotate-camera.jpg)

In the following example, the camera starts to rotate after 3 seconds of user inactivity. When the user clicks a mouse button \(or touches the screen\), he or she regains the control over the camera until further 3 second period of inactivity.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-camera-autorotate-camera-example.jpg)

