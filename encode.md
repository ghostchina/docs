#encode

###用法
`{{encode value}}`
#####参数
`value` 字符串类型
###简介
`{{encode}}`是一个将能将字符串编码后在URL中使用的助手函数。最明显的一个例子就是在`post.hbs`中用来输出一个twitter的分享的链接：

```html
<a class="icon-twitter" href="http://twitter.com/share?text={{encode title}}&url={{url absolute="true"}}"
    onclick="window.open(this.href, 'twitter-share', 'width=550,height=235');return false;">
    <span class="hidden">Twitter</span>
</a>
```
如果在文章的标题处不使用`{{encode}}`助手函数，那么标题中的空格和其它的标点符号将不能被很好的处理。