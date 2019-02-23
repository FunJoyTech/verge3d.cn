---
description: HTML-Based User Interfaces 待校订
---

# 基于HTML的用户界面

## 为3D Web应用程序构建基于HTML的用户界面

了解如何利用标准Web技术创建丰富的移动友好型用户界面和网站集成。

* 介绍
* 在哪里添加HTML和CSS
* 快速概览：茶壶加热器
* 教程
* 案例＃1：Google Web Designer
* 案例＃2：Webflow
* 案例＃3：文本编辑器
* 连接一切：HTML拼图

＃

### 介绍

模板Verge3D应用程序提供单页宽屏布局，带有全屏按钮和预加载器。诸如按钮之类的交互式元素可以实现为固定到相机的3D对象 - 这同样适用于文本框。

然而，更灵活和有效的方法是利用已建立的Web标准来创建用户界面。使用HTML和CSS，您可以为您的应用构建任何布局，使其响应和SEO友好。由于现代Web浏览器的专用光栅化引擎，UI和特别是使用HTML和CSS创建的文本看起来通常比3D对应物更清晰。此方法还允许您轻松地将2D媒体（如图像，视频和Web链接）与WebGL内容混合，并为您的应用设置样式以匹配将部署它的网站的设计。

有很多网页设计工具，从纯文本编辑器到完全成熟的网站建设者。后者可以生成完整的HTML / CSS / JavaScript即用型网页，从而使您可以永远不会触摸任何代码。

＃

### 在哪里添加HTML和CSS

假设您使用App Manager（使用默认配置选项）创建了应用程序，并将其命名为**my\_awesome\_app**。如果您查看verge3d / applications / my\_awesome\_app文件夹，您会发现my\_awesome\_app.html和my\_awesome\_app.css文件似乎很自然地开始编辑 - 但它们看起来只是如此！

实际上，您可能永远不想编辑这些文件，因为它们是由App Manager自动生成的，并且可能会因[更新](https://www.soft8soft.com/docs/manual/en/introduction/Updating.html)而被覆盖。将自己的HTML / CSS添加到Verge3D应用程序的更健壮的方法是创建一个新的 **.html**文件，其中嵌入了Verge3D app **.html**，matryoshka-style。

＃

### 快速概览：茶壶加热器

查看以下示例（Verge3D [Teapot Heater](https://cdn.soft8soft.com/demo/applications/teapot_heater_max/index.html)演示）：所有界面均使用第三方Web设计软件构建并保存为index.html（此名称不是必需的）。除了界面HTML元素之外，index.html文件还包含一个**iframe**元素，通过该元素嵌入了Verge3D项目teapot\_heater.html。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/layered-html.jpg)

在Verge3D App Manager中，这样的复合项目有两个启动图标，您可以使用它们独立运行纯Verge3D项目或组装的应用程序：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/teapot-heater-app-manager.jpg)

最后，2D和3D部分在逻辑上与[HTML谜题](https://www.soft8soft.com/docs/manual/en/introduction/Puzzles.html#HTML)互连，以处理用户事件。

＃

### 教程

在下面的教程中，我们将展示如何使用基于HTML的UI创建一个简单的应用程序。此应用程序将只有2个按钮用于隐藏和显示默认多维数据集。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/tutorial-final-app.jpg)

让我们从使用App Manager 创建名为**my\_awesome\_app**的新项目开始。下面我们将向您展示如何使用3种替代工具创建用户界面**.html**文件：Google Web Designer，Webflow和文本编辑器。一旦用户界面准备就绪，我们就可以使用Puzzles操作 HTML按钮。

＃

### 案例＃1：Google Web Designer

[Google Web Designer](https://www.google.com/webdesigner/)是一款免费的跨平台工具，可用于创建HTML元素并以可视方式为其分配样式。

启动此程序后，选择“ **创建新文件** ...”![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-create-new.jpg)

...然后选择**HTML**左侧面板上，并填写所有字段：**姓名**（如“my\_awesome\_app\_gwd”），**位置**（使用任何路径，最好出你的应用程序文件夹中，以避免与已发布的版本混乱）和**标题**，以及单击**确定**。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-create-new2.jpg)

让我们首先添加**iframe**元素，以嵌入我们的Verge3D应用程序的主要启动文件my\_awesome\_app.html。在Google Web Designer中，可以通过从“ **组件”**选项卡下的列表中拖出**IFrame**组件来完成此操作。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-add-iframe.jpg)

将**IFrame**组件放置在页面上后，切换到“ **属性”**选项卡，通过为左侧和顶部位置指定零，并为宽度和高度指定100％，使**iframe**元素占据整个页面。此外，在**Source**字段中将路径放到Verge3D app主文件 - “my\_awesome\_app.html”（假设我们将在app文件夹的根目录中发布我们的UI文件）。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-add-iframe2.jpg)

在这个阶段，我们可以生成我们的UI **.html**文件，并使用Verge3D应用程序进行尝试。单击右上角的“ **发布”**按钮，然后选择“ **本地”**。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-publish.jpg)

在发布对话框中，选择app文件夹的路径**my\_awesome\_app**作为**Location**。将“ **名称”**字段保留为空，以便将文件保存在应用程序文件夹的根目录中。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-publish2.jpg)

新的**.html**文件立即开始在App Manager中显示为一个额外的蓝色图标。您可以运行它来检查它是否实际加载了Verge3D应用程序。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/my-awesome-app-manager.jpg)

现在让我们添加这两个按钮。在最左侧的面板上单击**元素工具**，然后选择**Div元素**并开始在页面上绘制一个矩形。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-add-buttons.jpg)

在“ **属性”**选项卡中，使用颜色选择器用颜色填充按钮，指定其位置和尺寸，最重要的是，设置此元素的**ID**，我们将在拼图中引用它。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-add-buttons2.jpg)

要为按钮添加标题（“隐藏”或“显示”），请双击它以使其以红色标出轮廓。单击**文本工具**，然后单击按钮并在文本区域中键入文本。使用字体设置来设置大小，颜色和其他属性。您可以使用“ **选择”工具**（带箭头的第一个按钮）移动按钮上的文本字段。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-add-buttons3.jpg)

因此，在“ **大纲视图”**面板中，您应该看到**iframe**元素，分配了唯一ID的2个**div**元素以及嵌套在这些**div中的**两个文本元素。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-add-buttons4.jpg)

作为画龙点睛之笔，在CSS属性窗口中，当鼠标光标悬停在这些按钮上时，我们可以将鼠标光标变为“点击”形式：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/gwd-add-buttons5.jpg)

发布index.html文件并从App Manager运行已组装的应用程序后，您应该看到如下内容：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/tutorial-final-app.jpg)

有关使用Google Web Designer工具和组件的详细信息，请参阅其[文档](https://support.google.com/webdesigner)。

＃

### 案例＃2：Webflow

[Webflow](https://webflow.com/)是一个基于云的工具，也可用于为Verge3D应用程序创建HTML / CSS用户界面。必要的**嵌入**组件和**导出代码**功能仅适用于从“精简版”级别开始的付费帐户。

在仪表板中单击“ **新建项目”**按钮，然后从模板中选择“ **空白站点** ”：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-new-project.jpg)

填写项目名称，然后单击“ **创建项目”**：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-new-project2.jpg)

现在让我们添加一个**iframe**元素来嵌入我们的Verge3D应用程序的主要启动文件my\_awesome\_app.html。在Webflow中，这可以通过以下方式实现。在左侧面板上，单击“ **添加元素”**，然后单击或拖出“ **嵌入”**组件：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-iframe.jpg)

将以下行复制并粘贴到编辑器窗口：`<iframe width="100%" height="100%" frameborder="0" src="my_awesome_app.html"></iframe>`![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-iframe2.jpg)

这里我们假设Webflow生成的index.html将放在app文件夹的根目录中。单击“ **保存并关闭”**。

将**嵌入**组件放置在页面上后，切换到“ **样式”**选项卡，并使**iframe**元素占据整个页面，方法是为其位置指定“ **固定”**，为宽度和高度指定“ 100％”。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-iframe3.jpg)

在这个阶段，我们可以生成我们的UI **.html**文件，并使用Verge3D应用程序进行尝试。单击顶部栏上的“ **导出代码”**按钮...![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-export-code.jpg)

...然后单击**准备ZIP**并最终**下载ZIP**：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-export-code2.jpg)

将存档保存到硬盘驱动器上的任何位置，然后解压缩到应用程序文件夹**my\_awesome\_app**的根目录。新的**.html**文件立即开始在App Manager中显示为一个额外的蓝色图标。您可以运行它来检查它是否实际加载了Verge3D应用程序。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/my-awesome-app-manager.jpg)

现在让我们添加这两个按钮。在最左侧的面板上单击**添加元素**，然后单击或拖出**Div Block**组件。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-buttons.jpg)

在“ **样式”**选项卡中，使用颜色选择器用颜色填充按钮，指定其位置和尺寸。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-buttons2.jpg)

为了设置我们将用于在拼图中引用它的元素的**ID**，请转到**元素设置**选项卡，然后在**ID**字段中键入“hide\_button”或“show\_button” 。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-buttons3.jpg)

要为按钮添加标题（“隐藏”或“显示”），请拖出按钮上的**文本块**组件，然后在文本区域中键入文本。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-buttons4.jpg)

使用“ **样式”**选项卡下的**“ 排版**设置” 设置大小，颜色和其他属性。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-buttons5.jpg)

因此，在“ **导航器”**选项卡中，您应该看到**iframe**元素，2个**div**元素（显示它们的样式名称）和嵌套在这些**div中的**两个文本元素。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-buttons6.jpg)

作为画龙点睛，在“ **样式”**选项卡中，当鼠标光标悬停在这些按钮上时，我们可以将鼠标光标变为“点击”形式：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/webflow-add-buttons7.jpg)

导出项目并从App Manager运行组装的应用程序后，您应该看到如下内容：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/tutorial-final-app.jpg)

有关使用Webflow工具和组件的更多信息，请参阅其[教程](https://university.webflow.com/courses/webflow-101-crash-course)。

＃

### 案例＃3：文本编辑器

许多网页设计师仍然认为纯文本编辑器是构建网页的最强大和最灵活的工具。即使您不想深入编写代码，本指南也可以帮助您了解更多艺术家友好工具生成的网页内部结构。

您可以使用任何文本编辑器来编辑HTML / CSS代码，但如果您的编辑器支持语法高亮和行编号（如Notepad ++或Atom），则工作更方便。

我们可以从中开始的基本HTML文档可以如下所示。您可以将这些内容复制到新的文本文档，并将其另存为index.html在**verge3d / applications / my\_awesome\_app**文件夹中。同样，文件的名称不是强制性的，为了保持一致性，我们只在任何地方使用它。`<!DOCTYPE html> <html> <head> <title>Index of My Awesome App</title> <meta charset="utf-8"> <meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0"> <meta name="description" content="Put some description here - remember about SEO!"> </head> <body> </body> </html>`

新的**.html**文件立即开始在App Manager中显示为一个额外的蓝色图标，在启动时会生成一个白色的空白页面。![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/my-awesome-app-manager.jpg)

现在我们可以在文档的**主体中**添加一个**iframe**元素来嵌入我们的Verge3D应用程序的主要启动文件my\_awesome\_app.html：`<body> <iframe id="my_iframe" src="my_awesome_app.html"></iframe> </body>`

如果您现在从App Manager运行已组装的应用程序，它将在左上角显示默认多维数据集应用程序的小嵌入。我们可以通过嵌入一些CSS来使它成为宽屏和无边框：`<style> #my_iframe { position: absolute; top: 0px; left: 0px; width: 100%; height: 100%; border: 0; } </style>`

现在让我们通过向主体添加2个**div**元素来创建2个按钮，提供唯一的**id**属性，以便在CSS和Puzzles中进行引用：`<div id="hide_button">Hide</div> <div id="show_button">Show</div>`

您不会在应用程序中注意到它们，直到您使用一些CSS对它们进行绝对定位和样式设置：`#hide_button, #show_button { position: absolute; width: 100px; height: 30px; background-color: DodgerBlue; color: white; text-align: center; line-height: 30px; cursor: pointer; } #hide_button { left: 10px; } #show_button { left: 120px; }`

就是这样 - 现在你的应用程序中有两个HTML按钮！以下是index.html的完整列表：`<!DOCTYPE html> <html> <head> <title>Index of My Awesome App</title> <meta charset="utf-8"> <meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0"> <meta name="description" content="Put some description here - remember about SEO!"> <style> #my_iframe { position: absolute; top: 0px; left: 0px; width: 100%; height: 100%; border: 0; } #hide_button, #show_button { position: absolute; width: 100px; height: 30px; background-color: DodgerBlue; color: white; text-align: center; line-height: 30px; cursor: pointer; } #hide_button { left: 10px; } #show_button { left: 120px; } </style> </head> <body> <iframe id="my_iframe" src="my_awesome_app.html"></iframe> <div id="hide_button">Hide</div> <div id="show_button">Show</div> </body> </html>`

从App Manager运行组装的应用程序时，您应该看到如下内容：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/tutorial-final-app.jpg)访问[w3schools.com，](https://www.w3schools.com/)获取有关HTML和CSS的更多教程，参考资料和示例。

＃

### 连接一切：HTML拼图

现在剩下的就是使我们的按钮可操作，以便通过点击它们，用户可以隐藏和显示立方体。这可以通过利用与元素ID结合使用的HTML 事件谜题轻松实现：![](https://www.soft8soft.com/docs/files/HTML-based-user-interfaces/html-puzzles.jpg)

由于可点击的HTML元素位于嵌入了Verge3D应用程序的父**.html**文件中，因此我们应该检查**父母文档**复选框以使它们起作用。

而已！保存您的拼图并检查按钮是否适用于多维数据集。

在此[论坛主题中](https://www.soft8soft.com/topic/creating-html-based-gui-with-google-web-designer-webflow-or-text-editor/)留下您的反馈或问题（如果有的话）。

