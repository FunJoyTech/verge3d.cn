# Initialization（初始化）

此拼图位于**init**选项卡下，并在初始化Verge3D应用程序之前进行预读和解释。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-init.jpg)

### **"configure application" - 应用配置**

允许设置应用程序初始化参数，包括一些WebGL上下文创建参数。

* "compressed assets（资产压缩）" —— 使应用程序加载**.xz**格式的压缩场景而不是常规**.gltf**文件（有关详细信息，请参阅[资产压缩](../general-topics/asset-compression.md)）;
* "default fullscreen button（默认全屏按钮）" —— 启用在屏幕右上角的默认全屏按钮；
* "transparent background（背景透明）" —— 使背景透明，以便透过WebGL画布显示网页的底层部分;
* "enable screenshots（启用屏幕截图）" —— 可从WebGL画布中正确捕获屏幕截图（将WebGL上下文的**preserveDrawingBuffer**属性设置为**true**）;
* "fade annotations（淡化注释）" —— 当注释被场景对象阻挡时，注释会消隐。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-init-configure-app.jpg)

### **"setup preloader" + "percentage" - 设置预加载 + 百分比**

删除默认预加载器并公开事件回调以允许预加载器读取处理进度。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-init-setup-preloader.jpg)

在以下示例中，自定义的预加载器由具有id“**preloader**”的HTML容器元素（例如一个&lt;div&gt;）表示。在它内部，还有一个ID为“**loading progress（加载进度）**”的元素（例如一个&lt;span&gt;），其中加载百分比与**%**是使用Percentage拼图打印的。除此之外，第三个元素的宽度（例如一个&lt;div&gt;）以图形方式动态更改表示加载进度。

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-init-setup-preloader-example.jpg)

