#navigation
输出博客的导航内容
###用法
`{{navigation}}`
###简介
`{{navigation}}`是一个模板驱动的函数助手，它会输出一个由管理后台设置的导航信息生成的简单的菜单。Navigation是一个由多个URL和对应的标签组成的链接组合，默认只有一个‘Home’链接。如果导航信息中没有任何元素，那么这个助手将不会输出内容。  
你可以通过修改`content/themes/your-theme/partials`目录下的`navigation.hbs`来覆盖默认的导航HTML布局。下面有默认的模板的详细信息。  
###属性列表
* label - 链接的文字标签
* url - 链接的URL
* current - URL是否匹配当前页
* slug - slug化的标签，可用在dom节点的class类中

###默认模板
Ghost[默认的导航模板](https://github.com/TryGhost/Ghost/blob/0.5.9/core/server/helpers/tpl/navigation.hbs)如下所示，你可用通过修改主题文件夹下的`navigation.hbs`文件来修改默认的模板。

```html
<ul class="nav">
    {{#foreach navigation}}
    <li class="nav-{{slug}}{{#if current}} nav-current{{/if}}" role="presentation"><a href="{{url absolute="true"}}">{{label}}</a></li>
    {{/foreach}}
</ul>
```
###示例代码
`{{navigation}}`助手函数在没有导航内容的时候是不会输出任何内容的，因此不需要用`{{#if}}`来包裹它。然而你可以像Casper主题中那样来显示一个菜单用来打开主菜单：

```html
{{#if @blog.navigation}}
    <a class="menu-button" href="#"><span class="word">Menu</span></a>
{{/if}}
```
