#@blog
全局数据

`@blog`能在主题的任何位置使用，该属性可以让你获取到[全局数据](http://themes.ghost.org/v0.6.0/docs/handlebars#global-data)：

* `{{@blog.url}}` - 在`config.js`中指定的url  
* `{{@blog.title}}` - 在后台设置页面中设置的博客名称  
* `{{@blog.description}}` - 在后台设置页面中设置的博客简介  
* `{{@blog.logo}}` - 在后台设置页面中设置的博客logo标志  
* `{{@blog.cover}}` - 在后台设置页面中设置的博客封面  
* `{{@blog.navigation}}` - 在后台设置/导航菜单页面中设置的导航信息

###示例代码
```html
<nav class="main-nav overlay clearfix">
    {{#if @blog.logo}}
        <a class="blog-logo" href="{{@blog.url}}"><img src="{{@blog.logo}}" alt="Blog Logo" /></a>
    {{/if}}
    <a class="subscribe-button icon-feed" href="{{@blog.url}}/rss/">Subscribe</a>
 </nav>
```
> 点击[navigation](./navigation.md)查看如何在主题中使用导航