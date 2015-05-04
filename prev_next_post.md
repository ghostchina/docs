#prev_post & next_post
获得当前文章的上一篇或者下一篇文章
###用法
`{{#prev_post}}{{title}}{{/prev_post}}` - `{{#next_post}}{{title}}{{/next_post}}`
###简介
在一篇文章的作用域内，你可以使用prev_post或者next_post助手函数来获得时间顺序上的上一篇或者下一篇文章。  
在`{{#prev_post}}{{/prev_post}}`和`{{#next_post}}{{/next_post}}`标签里面，post助手函数里面的助手函数都是可以使用的，但是这些是通过API来获取的而不是通过原始的文章。

```html
{{#post}}
  <h2>{{title}}</h2>
  <div class="{{post_class}}">
    {{content}}
  </div>

  {{#prev_post}}
    <a href="{{url}}">{{title}}</a>
  {{/prev_post}}

  {{#next_post}}
    <a href="{{url}}">{{title}}</a>
  {{/next_post}}
{{/post}}
```
和其它块级助手函数一样，`next_post`和`prev_post`支持`else`标签，或者使用`^`来代替`#`来实现否定。这意味着`{{#next_post}}`与`{{else}}`的组合和`{{^next_post}}`与`{{else}}`的组合在功能上正好相反，这在没有上一篇或者没有下一篇文章时非常实用。

```html
{{#next_post}}
  <p><a href="{{url}}">{{title}}</a></p>
{{else}}
  <p>No more posts!</p>
{{/next_post}}
```
**注意：**这2个助手函数不能相互嵌套使用，因为它们都执行了一个查询，而我们现在无法支持相互嵌套查询。  
你可以在一个页面中执行多次查询，所以你可以同时使用`{{#next_post}}`和`{#prev_post}}`，或者多次调用这2个助手函数。