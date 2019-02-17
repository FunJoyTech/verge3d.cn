# 入门指南（重点）

## 入门指南

  
Verge3D is a versatile piece of software which you can utilize differently depending on you personal preferences. This guide describes just one of possible ways of how you can build your workflow, so take it as a friendly recommendation. The only prerequisite is that you should have some experience with 3D editing software such as Autodesk 3ds Max or Blender.

Verge3D是一款多功能软件，您可以根据个人喜好不同地使用它。本指南仅介绍了如何构建工作流程的可能方法之一，因此请将其作为友好推荐。

### 安装

The installation procedure is throughly described in the corresponding sections for each supported 3D suite separately \([3ds Max](https://www.soft8soft.com/docs/manual/introduction/Installation-3ds-Max.html), [Blender](https://www.soft8soft.com/docs/manual/introduction/Installation-Blender.html)\).

### 应用管理

Although you can start working on graphics first and create a Verge3D project later, we encourage you to leverage the Verge3D App Manager from the beginning. By doing so you ensure that your files are properly organized and stored within the same folder which is important for publishing. You will also have a working web application which you can run/reload in the browser independently from your 3D scenes.

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-main.png)

The App Manager as a web-based tool which opens up in the browser when you select the "App Manager" option in the "Verge3D" menu \(3dsMax\) or click the corresponding button \(Blender\). The default system browser will be running - you can change it in your OS settings. Any modern browser will work yet we recommend the latest version of Google Chrome for best results.

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-max.png)

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-blender.png)

You can create a new project using the form on the right. Just enter a project name \(My Awesome App will also work\) and click "Create App". You can safely leave other creation options as is.

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-create.png)

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-created.png)

As a result, a folder named after your app will be created inside the "applications" folder of your Verge3D installation. You can look in this folder but this is not really necessary since you can open app files from the App Manager.

![](https://www.soft8soft.com/docs/files/beginner_guide/app-folder.png)

After you created a project, return to the main screen of the App Manager - your project should be listed there. Now you can proceed with your app in several directions: simply running it, authoring the graphics, creating interactive scenarios and eventually, publishing.

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-app-buttons.png)

### 运行你的应用

You can run your app any time by clicking the Verge3D icons, either the blue or the green one. The blue icon launches an app in its final form, with its Puzzles scenario and the programming code \(if present\). On the contrary, the green icon only opens the exported scene.

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-app-buttons-run.png)

A freshly created app loads and shows just a single cube. If instead it shows something like "This site can’t be reached" this means that you accidentally closed your 3D editor and the development server along with it. In this case you should launch 3ds Max or Blender again.

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-app-running.png)

Although very rare, another warning can be shown: "Your graphics card does not seem to support WebGL." This can happen if you're using an outdated or unsupported browser such as Internet Explorer, or your video card and/or drivers are blacklisted by the browser. Try installing Google Chrome/updating your OS/drivers or just find another computer.For now you can do no more than simply look around with the left mouse button pressed and zoom in and out with the mouse wheel. With Puzzles you'll be able to add various scenarios so that your 3D scene becomes a truly interactive web application.

### 图形设计

Clicking on the 3ds Max or Blender icon opens up the main .max or .blend file of your application respectively. You can have more 3D editor files in a single project, but this one is considered "main" since the 3D scene which it produces upon exporting, will be loaded into your app first.  


![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-app-buttons-max.png)

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-app-buttons-blender.png)

The 3D editor files can be also opened as usual via the "File &gt; Open" dialog or simply by double-clicking on them in the application folder.**It is important to understand that an application loads only exported scenes and not the source 3D editor files.**So every time you change something in your source file you should export it in order to see the changes in your app. Exporting can be performed from the Verge3D menu of the main menu bar \(in 3ds Max\) or from the File &gt; Export menu \(in Blender\). You might want to assign a shortcut for this operation since you may perform it quite often.

![](https://www.soft8soft.com/docs/files/beginner_guide/export-max.png)

![](https://www.soft8soft.com/docs/files/beginner_guide/export-blender.png)

You can export your scene file right to the root of the application folder, in glTF format.![](https://www.soft8soft.com/docs/files/beginner_guide/export-name-blender.png)

Instead of exporting, you can "preview" your models and scenes in the web browser with the "Sneak Peek" menu option \(3dsMax\) or button \(Blender\). This will perform an export to a temporary folder and immediately show your scene in a new browser tab. Use this for quick tests when creating new projects is not feasible.

![](https://www.soft8soft.com/docs/files/beginner_guide/sneak-peek-max.png)

![](https://www.soft8soft.com/docs/files/beginner_guide/sneak-peek-blender.png)

Authoring graphics for Verge3D is no different from a typical game development workflow. Obviously one does not simply walk into Mordor utilize ray-tracing techniques or million poly assets. Still you can achieve very plausible results with real-time materials, both standard and physically-based, and low- to mid-poly models.

![](https://www.soft8soft.com/docs/files/beginner_guide/graphics-blender-mat.png)

What helps a lot is that the changes can be displayed in the editor's viewport right as you do something. Coupled with the immediate availability of your favorite modeling tools, the viewport preview feature significantly accelerates the graphics pipeline compared to "external" game engines such as Unreal or Unity. Speaking of which, you don't need advanced artificial intelligence or multiplayer in your product configurator, do you?

![](https://www.soft8soft.com/docs/files/beginner_guide/graphics-blender.png)

The viewport preview feature is already available in the default 3ds Max/Blender projects which are created by the App Manager. See below for the information on how to enable if you didn't use the App Manager to create your asset files.To enable the viewport preview in 3ds Max, switch from "Standard" to "High Quality" in the viewport settings, select "Realistic Materials with Maps" from the Materials submenu and set "Environment Background" in the "Viewport Background" submenu under "Default Shading".

![](https://www.soft8soft.com/docs/files/beginner_guide/viewport-settings-max1.png)

![](https://www.soft8soft.com/docs/files/beginner_guide/viewport-settings-max2.png)

![](https://www.soft8soft.com/docs/files/beginner_guide/viewport-settings-max3.png)

To enable the viewport preview in Blender, select "Material" in the "Viewport Shading" menu. Also select "GLSL" on the "Shading" panel and enable "World Background" on the "Display" panel - both these panels can be found in the "Properties" window \(which is, in turn, revealed with the "N" shortcut\). Optionally, you also can enable "Backface Culling" to hide all surfaces invisible in Verge3D render.

![](https://www.soft8soft.com/docs/files/beginner_guide/viewport-settings-blender1.png)

![](https://www.soft8soft.com/docs/files/beginner_guide/viewport-settings-blender2.png)

For the sake of familiarizing yourself with the basics, just add some teapots/Suzannes to your scene, export to glTF and run your app by clicking the blue Verge3D logo icon in the App Manager.For quicker updates, you can keep your application running in a browser tab. Hit "F5" on your keyboard every time you re-export your scene so that it reloads \(works for an active browser tab only\). Use the Alt+Tab \(Command+Tab on Mac\) shortcut to instantly switch between your 3D editor and the browser.

### Puzzles编辑器

Until now we used Verge3D as a fancy web exporter, which "just" generates live 3D views running in the browser. But you can do much, much more! With Puzzles, the powerful yet entertaining scripting environment which comes with Verge3D, you no longer have to be a programmer to do... programming.![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-app-buttons-puzzles.png)Click the "Puzzles" button near your app name in the App Manager. This will run your app with the Puzzles editor on top of it. Then you simply click the toolbox on the left and drag puzzles to the workspace. Connecting puzzles together creates a scenario, which will be applied to your scene on startup.

![](https://www.soft8soft.com/docs/files/beginner_guide/puzzles-toolbox.png)

To do something meaningful for the beginning, drag the "when clicked" puzzle from the "Events" category, and the "Select an object" puzzle from the "Selectors".

![](https://www.soft8soft.com/docs/files/beginner_guide/puzzles-toolbox2.png)

Connecting them together means that you app will be waiting until the user clicks on the object that you chose in the dropdown menu, and will do... nothing until you add something in the "do" slot.

![](https://www.soft8soft.com/docs/files/beginner_guide/puzzles-example.png)

For the sake of this example, drag the "hide" puzzle from the "Objects" and insert it to that slot, connected with another object selector puzzle.

![](https://www.soft8soft.com/docs/files/beginner_guide/puzzles-example2.png)

Now, when the user clicks the object of your choice, it will hide the object you specified in the second selector puzzle. Click "Run" to "compile" your program and check if it works by clicking on the cube.

![](https://www.soft8soft.com/docs/files/beginner_guide/puzzles-run.png)

Now you a have a simple scenario - let's check how it works outside the Puzzles. Click the "Save" button and return to the App Manager's main screen.

![](https://www.soft8soft.com/docs/files/beginner_guide/puzzles-save.png)

Switch to the App Manager tab and run your app as usual and see that your scenario actually works. Congratulations, you have become a programmer!

### 超越 Puzzles

Puzzles offer many functions out of the box, but what if your application needs something special? For example, your app can be a part of a e-commerce website \(or e-learning system\) and so has to communicate with the rest of the website environment. For such a case Verge3D offers the so called "External Interface" which allows Puzzles to communicate with the JavaScript programming code in both directions.Basically you can call a properly registered JavaScript function from Puzzles and vice versa, the programming code can trigger your "JSCallback" puzzle \(located in "Events"\).

![](https://www.soft8soft.com/docs/files/beginner_guide/puzzles-code-example.png)

New functions can be registered by adding them to the application **.js** file inside **prepareExternalInterface\(\)** that is already present there:`// Register "myJSFunction" to be called by Puzzles function prepareExternalInterface(app) { app.ExternalInterface.myJSFunction = function(arg) { alert(arg); // prints the passed parameter in a modal window } }`On the other hand, if you need to trigger your puzzles, you can simply call the method with the same name from inside **runCode\(\)** function that is also already present in the **.js** file:`// Trigger the "myJSCallback" puzzle with an argument function runCode() { app.ExternalInterface.myJSCallback('Hello, Puzzles!'); }`

### 发布

You've created a web application and probably you'd like the billions of Internet users to come and check it out. If you own a website, this won't be a problem - simply upload the entire folder with your application to your server \(for example, via FTP or SSH\). Once deployed, you can provide a link to the app's HTML file somewhere on your website or embed it in a web page with an iframe.`<iframe width="1024" height="640" allowfullscreen src="https://www.example.com/my_awesome_app/my_awesome_app.html"></iframe>`But what if you haven't had the chance to become a web master? Actually, there is a button for that in the App Manager \(one with the "Earth" icon\). Clicking that button will upload your app to the Verge3D Network, a cloud-based storage and CDN hosted on Amazon servers.

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-app-buttons-network.png)

After uploading is completed, it will provide you with a direct web link which you are free to share by whatever means \(in a blog post, social media, comments, email, you name it\). It will also generate HTML code for embedding your app in third-party websites just like you do it with YouTube videos.

![](https://www.soft8soft.com/docs/files/beginner_guide/network-uploaded.png)

### 更新

Verge3D is currently in active development with regular releases happening from time to time. We recommend you to keep in pace with the development cycle and timely update your Verge3D distribution and applications.

![](https://www.soft8soft.com/docs/files/beginner_guide/updating-download.png)

The most "clean" method to make an update is to backup your current Verge3D folder by renaming it \(from "verge3d" to "verge3d\_old", for example\) and to unpack the latest bundle in a fresh folder with the same name \(that is, "verge3d"\).

![](https://www.soft8soft.com/docs/files/beginner_guide/updating-backup.png)

As inconvenient as it may seem, prefer initializing your apps with the "Create App" button, instead of copying app folders from your old Verge3D folder. This way your apps will receive the latest improvements derived from the updated app templates. If you simply copy your apps, they'll still work but keep using older templates.

![](https://www.soft8soft.com/docs/files/beginner_guide/app-manager-create.png)

After initializing, copy .max or .blend files, all the textures and the Puzzles scenario file \(called "visual\_logic.xml"\) from your old app folder \(located within "verge3d/applications"\) to the newly created app folder. Override files if you're asked so.

![](https://www.soft8soft.com/docs/files/beginner_guide/updating-copy.png)

Finally, you should perform exporting to glTF so that the exported format receives the latest updates. If you're using Puzzles, be sure to re-save your scenarios so that they match the newest version of code.

### 授权码

After acquiring a license, you'll be sent the license information in an email \(the key below is a random example\).

![](https://www.soft8soft.com/docs/files/beginner_guide/license-info.png)

The license key will activate your Verge3D instance and will remove the trial warning from all your apps.

![](https://www.soft8soft.com/docs/files/beginner_guide/license-activation.png)

You should enter the license key each time you update to a new version.

![](https://www.soft8soft.com/docs/files/beginner_guide/license-activated.png)

### 技术支持

This is just a brief overview of Verge3D workflow with many topics possibly left undiscussed. We invite you join the [Verge3D community forums](https://www.soft8soft.com/forums/) where we'll be happy to answer all your questions.

