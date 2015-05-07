#foreach
遍历临时变量({{each}}的扩展)
###用法
`{{#foreach data}}{{/foreach}}`
#####参数
`data` - 需要遍历的集合
#####属性
`columns` - 数字类型
###简介
`{{#foreach}}`是用来遍历文章列表的，当然它也可以用来遍历标签列表。这个助手函数将在它的开始和结束标签之间输出它正在遍历的集合的元素。
> `{{#foreach}}`助手函数不执行查询，而且只能遍历当前模版作用域内的可用数据。你可以点击[context table](http://themes.ghost.org/docs/structure#context-table)查看在模板中哪些数据是可用的。

虽然Handlebars内建了each助手函数，但是Ghost的foreach提供了更多的功能，所以推荐你最好使用`{{#foreach}}`。  

Handlebars里面的each提供两个私有的属性：用于数组的`@index`属性和用于对象的`@key`属性，这些在`foreach`上也能使用：

```html
{{#foreach posts}}
  <div class="post-{{@index}}">{{title}}</div>
{{/foreach}}
```
`{{#foreach}}`在此基础上添加了几个额外的数组和对象都能使用的私有属性`@first`、 `@last`、`@even`、`@odd`、`@rowStart`和`@rowEnd`。这样你就可以制作出更多更复杂的文章列表或者其它内容的样式。下面是一些例子：

`@first`和`@last`

下面这个例子检查了一个数组或者对象(例如posts)并判断是否是第一个元素：

```html
{{#foreach posts}}
    {{#if @first}}
        <div>First post</div>
    {{/if}}
{{/foreach}}
```
我们可以使用`if`来判断更多的属性，在下面这个例子中我们可以将第一篇和最后一篇文章与其它文章分开。

```html
{{#foreach posts}}
    {{#if @first}}
    <div>First post</div>
    {{else}}
        {{#if @last}}
            <div>Last post</div>
        {{else}}
            <div>All other posts</div>
        {{/if}}
    {{/if}}
{{/foreach}}
```
`@even`和`@odd`
下面的例子为div添加了even和odd的class类名，这在输出斑马条纹样式时很实用：

```html
{{#foreach posts}}
        <div class="{{#if @even}}even{{else}}odd{{/if}}">{{title}}</div>
{{/foreach}}
```
`@rowStart`和`@rowEnd`
下面的例子想你展示了如何传递一个column选项，这样一来你就可以为一行中的第一个和最后一个元素设置属性了，内容可以以格子布局得到展示。

```html
{{#foreach posts columns=3}}
    <li class="{{#if @rowStart}}first{{/if}}{{#if @rowEnd}}last{{/if}}">{{title}}</li>
{{/foreach}}
```
