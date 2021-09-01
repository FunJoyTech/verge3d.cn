# Verge3D应用MIME类型定义

## MIME type、Content type 列表

MIME type （现在称为“媒体类型(media type)”，但有时也是“内容类型(content type)”）是指示文件类型的字符串，与文件一起发送（例如，一个声音文件可能被标记为 audio/ogg ，一个图像文件可能是 image/png ）。它与传统Windows上的文件扩展名有相同目的。在使用 Windows的 IIS 服务器时，如果网页中所用到的文件后缀名在IIS中没有对应的 MIME 定义，则会在控制台输出404错误等导致页面不能正确加载，这是Verge3D应用部署到Windows服务器时常常会遇到的问题。因此，如果您使用IIS服务器部署Verge3D应用，请记得先为自己的网站做好MIME配置。



## Verge3D用到的MIME类型

下表是Verge3D用到的文件类型，请在IIS中进行配置添加。

| **后缀名** | **MimeType(Content-Type)** |
| ---------- | -------------------------- |
| .gltf      | model/gltf+json            |
| .glb       | model/gltf-binary          |
| .bin       | application/octet-stream   |
| .xz        | application/x-xz           |

MIME速查表（中文）：https://www.coderbusy.com/archives/597.html



## 配置参考流程：

![](https://cdn.funjoy.tech/web/blog/iis_mime_01.jpg)

![](https://cdn.funjoy.tech/web/blog/iis_mime_02.jpg)

![](https://cdn.funjoy.tech/web/blog/iis_mime_03.jpg)
