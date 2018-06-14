# FAQ

## General Questions

### Which Import Format/Exporter is best supported?

Verge3D is able to load various formats including glTF, OBJ, FBX, COLLADA, STL and PLY. Still, the preferred way to create 3D web content is to use glTF 2.0 format which is supported by both 3ds Max and Blender exporters

Also, standard application logic provided by the App and AppPuzzles classes supports loading glTF files only. To load other formats please refer to the corresponding loader classes.

### What are the limitations / restrictions of the Verge3D Trial? Can I do ... ?

Quick answer to that question would be to quote our License Agreement. The Verge3D EULA states: "The trial version of this software available for free download from the Soft8Soft website is intended for testing purposes only. Any use in production environments, for commercial or non-commercial purposes is prohibited.".

Basically, you can do whatever you want \(and for how long\) provided you don't create Apps for production use. For example, you can use it to create basic samples for practicing purposes, to develop your personal skills, or to create a mock-up presentation to the management at your office. You are not allowed to use it for Education \(please contact us to receive a special Educational license for reduced price\) or to create your own portfolio \(this qualifies as production use, feel free to purchage the Verge3D Personal license in that case\).

## Programming Questions

### You say Verge3D is based on Three.js. Is it compatible with Three.js API?

To create Verge3D we modified Three.js code base a lot and thus we decided to use "v3d" prefix for our APIs. However, we'll try to maintain source code compatibility with Three.js. Most of the Three.js-based applications/examples should work in Verge3D without any modifications.

### Why are there meta viewport tags in examples?

```text
<meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0">
```

These tags control viewport size and scale for mobile browsers \(where page content may be rendered at different size than visible viewport\).

[https://developer.mozilla.org/en/Mobile/Viewport\_meta\_tag](https://developer.mozilla.org/en/Mobile/Viewport_meta_tag)[http://developer.apple.com/library/safari/\#documentation/AppleApplications/Reference/SafariWebContent/UsingtheViewport/UsingtheViewport.html](http://developer.apple.com/library/safari/#documentation/AppleApplications/Reference/SafariWebContent/UsingtheViewport/UsingtheViewport.html)  


### How can scene scale be preserved on resize?

We want all objects, regardless of their distance from the camera, to appear the same size, even as the window is resized. The key equation to solving this is this formula for the visible height at a given distance:`visible_height = 2 * Math.tan( ( Math.PI / 180 ) * camera.fov / 2 ) * distance_from_camera;`If we increase the window height by a certain percentage, then what we want is the visible height at all distances to increase by the same percentage. This can not be done by changing the camera position. Instead you have to change the camera field-of-view. [Example](http://jsfiddle.net/Q4Jpu/).

### Why is part of my object invisible?

This could be because of face culling. Faces have an orientation that decides which side is which. And the culling removes the backside in normal circumstances. To see if this is your problem, change the material side to v3d.DoubleSide.`material.side = v3d.DoubleSide`

### Do you support Internet Explorer 11?

We have no intention to directly support IE 11 for several reasons:

* WebGL is only partially supported in IE 11, so there are some issues related to rendering, the WebGL API, etc... To deal with them you need to implement additional hacks/workarounds, which increase code complexity and codebase size.
* The lack of support for modern JS features used in the engine's code also requires some hacks/workarounds and slows down development.
* IE 11 is old and is no longer being actively developed in favor of the new Microsoft Edge browser. So it will most likely remain as is with its current drawbacks.
* The usage share of IE 11 is about [2-3 percent](https://www.w3schools.com/Browsers/browsers_explorer.asp) and is inevitably going down. So, we think that it isn't big enough to worth dealing with the drawbacks.

Thus we don't directly provide support for it speaking of the engine's core, but for those who still need to run their demos in IE 11 we have a partial solution.

You can use a compatibility script located inside the SDK at the path: ./build/ie\_compat.js. It applies some workarounds to prevent possible engine crashes and allows to run Verge3D applications in IE 11. Still it doesn't guarantee that your scenes will work flawlessly.

In order to use this solution just copy that script in your application's folder and include it in the main HTML file before other verge3d-related scripts, for example:

`<script src="ie_compat.js"></script>  
 ...   
<script src="v3d.js"></script>   
<script src="my_awesome_app.js"></script>`

