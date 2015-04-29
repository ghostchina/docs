#author
输出一篇文章的作者的详细信息

用法：`{{author}}` 或者 `{{#author}}{{/author}}`

###简介
author助手可以作为一个输出或者一个块级元素，它提供了各种获取文章作者信息的方式。

如果作为一个输出（例如：{{author}}），那么它将显示作者的名字和一个指向作者页面的链接。

```html
{{#post}}
    {{author}}       
{{/post}
```
如果作为一个块级元素去显示作者信息（例如：{{#author}}some information{{/author}}），那么腻久可以显示文章作者的各种信息。

```html
{{#post}}
    {{#author}}
        <h3>{{name}}</h3>
        <p>{{bio}}</p>
    {{/author}}
{{/post}
```
###属性列表

* id - 作者的ID
* name - 作者的名字
* bio - 作者的个人简介
* location - 作者所在地
* website - 作者的个人网站
* image - 作者的头像[image助手](http://themes.ghost.org/v0.6.0/docs/image)
* cover - 作者的封面
* url - 作者的个性网址[url助手](http://themes.ghost.org/v0.6.0/docs/url)
###示例代码
```html
{{#post}}
    {{#author}}
        <h3>Written by <a href="{{url}}">{{name}}</a></h3>
        <div>To contact {{name}}, send an email to {{email}} or visit {{website}}.</div>
    {{/author}}
    <div id="post-content">{{content}}</div>
{{/post}
```
```html
{{#foreach post}}
    <div id="author-header">
        Written by {{author}}. Here is a quick bio:   

        <p id="author-bio">
            {{author.bio}}
        </p>
    </div>

    <div id="post-content">
        {{content words="100"}}
    </div>
{{/foreach}}
```
