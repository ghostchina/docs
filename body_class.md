#body_class
为页面输出动态的CSS类用来区分页面内容。
###用法
`{{body_class}}`
###简介
`{{body_class}}` - 在你的`default.hbs`或者其它模版文件的`<body>`标签处添加动态的CSS类，当你需要为不同的页面输出不同的样式时很实用。  
`{{body_class}}`会根据当前页面的内容输出不同的CSS类。例如在首页会输出`.home-template`类，在一个单独的文章页面会输出`.post-template`类。  
如果要查看详细的信息，请点击[contexts table](http://themes.ghost.org/v0.6.0/docs/structure#context-table)。

###示例代码
当文章在`/page/2`时，`default.hbs`中的如下片段

```html
<html>
    <head>...</head>
    <body class="{{body_class}}">
    ...
    {{{body}}}
    ...
    </body>
</html>
```
会输出为

```html
<html>
    <head>...</head>
    <body class="home-template paged">
    ...
    </body>
</html>
```

在一个静态的`/about/`页面中，`default.hbs`中的如下片段

```html
<html>
    <head>...</head>
    <body class="{{body_class}}">
    ...
    {{{body}}}
    ...
    </body>
</html>
```
会输出为

```html
<html>
    <head>...</head>
    <body class="page-template">
    ...
    </body>
</html>
```