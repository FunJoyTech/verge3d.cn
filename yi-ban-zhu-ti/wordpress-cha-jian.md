---
description: 待校订
---

# Wordpress插件（Wordpress Plugin）

## Wordpress插件

从版本2.7开始，Verge3D附带了一个WordPress插件，这是目前最流行的内容管理系统（CMS）（超过6000万次安装）。

Verge3D WordPress插件提供以下功能：

* 应用程序托管和发布（嵌入）。
* 用于处理客户订单的标准电子商务系统，使用地点订单拼图提交。
* 完全可定制的电子商务系统，用于处理由发送数据拼图以JSON格式提交的订单。

这些功能可以相互独立工作。例如，您可能只想要嵌入，或者您可以处理从其他地方托管的Verge3D应用程序（例如Verge3D网络等）接收的订单。

### 安装

在安装此插件之前，请确保至少拥有WordPress 4.7。要在服务器上传应用程序，您需要拥有一个现代化的浏览器，例如Google Chrome，Firefox，Edge或Safari 11.1+。

请按照以下步骤安装Verge3D插件：

* 通过Wordpress管理界面从_verge3d / wordpress / verge3d.zip_上传插件存档。
* 在**插件**菜单中激活插件。**Verge3D**菜单应出现在管理面板中。

或者，在官方WordPress.org [存储库中](https://wordpress.org/plugins/verge3d/)找到Verge3D插件，并将其安装/激活为任何其他WP插件。

尝试上传部分应用或创建测试订单，以验证插件是否正常工作。

请注意，您的WordPress服务器配置可能具有严格的上传限制。如果您在上传应用程序时遇到麻烦，可能需要在_php.ini_文件中调整以下设置：`upload_max_filesize = 100M max_file_uploads = 100`

### 添加和管理应用程序

使用**Applications**管理菜单访问**Verge3D Applications**屏幕：![](https://www.soft8soft.com/docs/files/wordpress/app.png)

要上传您的应用，请单击应用程序标题下的**编辑**，单击**选择文件**，然后在**更新Verge3D应用程序**表单中选择一个应用程序文件夹：![](https://www.soft8soft.com/docs/files/wordpress/update_app.png)

在此表单上，您还可以配置应用程序的iframe（画布）大小，并使用全屏模式允许/拒绝。

要在WordPress页面/帖子中嵌入Verge3D应用程序，请使用以下短代码：`[verge3d id="YOUR_APP_ID"]`

其中_YOUR\_APP\_ID_是**Verge3D应用程序**屏幕上表格中显示的应用程序的ID 。

### 接收基本订单

要处理由Verge3D应用程序发送的常规订单（通过“下订单”拼图），请使用以下短代码向您的某些WordPress页面/帖子添加订单：`[verge3d_order]`

然后指定该页面/帖子的链接作为“下订单”拼图的“发送到”参数。每次执行此拼图时，您的应用都会将用户重定向到您的订单：![](https://www.soft8soft.com/docs/files/wordpress/order_form.png)

### 管理订单

使用**电子商务**管理菜单访问**电子商务订单**屏幕：![](https://www.soft8soft.com/docs/files/wordpress/orders.png)

此列表中的订单是在收到Verge3D应用程序的请求时自动创建的。您可以使用此屏幕查看和管理客户订单。

### 插件设置

使用**“设置”**管理菜单修改插件全局设置：![](https://www.soft8soft.com/docs/files/wordpress/settings.png)

**订单通知电子邮件**选项用于指定负责管理订单的人员的电子邮件地址。当客户下新订单时，您将在此电子邮件中收到有关此订单的通知。

**订购电子邮件“发件人”**选项用于指定负责与客户通信的个人/组织的名称/电子邮件。这可以是销售经理的电子邮件，一些常见的地址，如_sales@yourcompany.com，_或者只是一个无回复的地址，如_noreply@yourcompany.com_。

### 高级电子商务应用程序

在某些情况下，您可能希望扩展电子商务系统的功能。例如，如果您开发3D配置器或需要客户端的更多信息来正确处理订单，则需要向请求添加更多数据以及在服务器上处理此数据。对于这种情况，您需要使用“发送数据”谜题以JSON格式对数据进行编码，然后为您的电子商务系统创建自定义模板表单。

假设您要创建基本表自定义程序。这就是您的数据的样子：`{ "width": 120, "length": 150, "height": 100, "color": "Redwood", "title": "Custom Table", "price" 100, "user_name", "John Smith", "user_email", "john.smith@example.com", "user_phone", "+123456789" }`

您可以使用字典拼图构建此结构，然后使用“发送数据”拼图将其发送到服务器。之后，您需要为订单管理管理页面创建自定义模板，以及将发送给您的客户和销售人员的电子邮件。为此，请将以下源模板复制到**verge3d**子目录下的WP主题目录中：`WORDPRESS/wp-content/plugins/verge3d/templates/order_admin_form.php WORDPRESS/wp-content/plugins/verge3d/templates/order_email_body.php`

WORDPRESS是WordPress安装的根目录。根据为您的订单指定的结构编辑这些文件。

最后一部分是为“发送数据”拼图分配正确的URL。这个看起来像：`https://HOSTNAME/wp-json/verge3d/v1/place_order/`

其中HOSTNAME是WordPress服务器的主机名，例如_www.soft8soft.com_

### 电子商务协议规范

“下订单”拼图使用基本协议来处理订单。使用带有以下参数的HTTP POST请求从浏览器向服务器发送订单：

| POST参数 | 描述 |
| :--- | :--- |
| v3d\_title | 订单标题。该字段用于描述订单。由于该值对客户没用，因此仅供负责处理订单的人使用。 |
| v3d\_content | 订单内容。此文本字段包含完整的订单信息，并且对客户和销售经理都可见。 |
| v3d\_price | 订单总价。它可以是数字或字符串，例如99.99.99，“99.99美元”。 |
| v3d\_screenshot | 订购截图。此可选值必须是表示图像的数据URI。该值由**HTMLCanvasElement.toDataURL（）**方法生成。 |

更高级的基于JSON的协议使用以下一组默认参数：

| JSON字段 | 描述 |
| :--- | :--- |
| title | 订单标题。该字段用于描述订单。由于该值对客户没用，因此仅供负责处理订单的人使用。 |
| price | 订单总价。它可以是数字或字符串，例如99.99.99，“99.99美元”。 |
| user\_name | 客户的全名。 |
| USER\_EMAIL | 客户的电子邮件地址。 |
| USER\_PHONE | 客户的电话号码。 |
| USER\_COMMENT | 订单评论。 |
| screenshot | 订购截图。此可选值必须是表示图像的数据URI。该值由**HTMLCanvasElement.toDataURL（）**方法生成。 |

由于此协议是可扩展的，您可以添加所需的任何参数，例如其他配置选项，产品属性，送货地址，账单信息，税金，折扣等。

