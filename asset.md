#asset
在你的主题中安全地使用资源文件

###用法
`{{asset "asset-path"}}`
###简介
使用`{{asset}}`可以免去资源文件管理的麻烦。首先，它能够保证相对路径始终是正确的而不用考虑Ghost是如何安装的。即使Ghost是安装在子目录中，在不使用绝对路径的情况下资源的路径仍然是正确的。  

其次，资源文件是可以缓存的。所有的资源文件在请求时都有一个`?v=######`的查询字符串，当Ghost重启的时候这个字符串才会改变。  

另外，对于主题开发者来说，`{{asset}}`提供了稳定的资源文件接入和管理，开发者不必担心以后为它们开发的主题做后续适应工作。  

最后，因为它规定了主题需要一个`assets`目录，所以Ghost知道去主题目录的哪个文件夹去查找资源文件，这样使以后做动态更新简单了许多。
###示例代码
如果需要在主题中使用`{{asset}}`输出一个资源文件，只需要提供它在`assets`目录中的位置。

css代码:

```html
<link rel="stylesheet" type="text/css" href="{{asset "css/style.css"}}" />
```
js代码：

```html
<script type="text/javascript" src="{{asset "js/index.js"}}"></script>
```
主题的图片：

```html
<img src="{{asset "images/my-image.jpg"}}" />
```
**注意：**在使用handlebars写主题时不用在单引号和双引号之间切换，因为handlebars的内容会被优先解析。

###Favicons
Favicons的使用和其它的资源文件的获取稍微有些不一样，因为浏览器总是会去请求这个文件，而Ghost则是为了更好地响应请求。  

默认情况下`{{asset "favicon.ico"}}`和浏览器的请求一样，都是返回`shared`目录下的favicon，这意味着不管博客使用的是什么主题甚至主题目录是否存在。  

如果你希望使用自定义的favicon，你可以将`favicon.ico`文件放在主题的`assets`目录中，并在页面中使用

```html
{{asset "/favicon.ico"}}
```
这里面的斜杠就是告诉Ghost不使用默认的favicon而是使用`assets`目录中的favicon。