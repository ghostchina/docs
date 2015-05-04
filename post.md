#post
文章或者页面的详细信息
###用法
`{{#post}}{{/post}}`或者`{{#foreach post}}{{/foreach}}`
###简介
在一个单独的文章模板例如post.hbs或者page.hbs中，你可以将它作为助手使用。  
在一个文章列表模板例如index.hbs或者tag.hbs中，请使用`{{#foreach post}}{{/foreach}}`来循环显示文章列表。  
在`{{#post}}{{/post}}`或者`{{#foreach post}}{{/foreach}}`标签里面，你可以获得文章的所有属性。
###属性列表
* id - 文章的ID
* title - 文章的标题([title](./title.md))
* excerpt - 文章的摘录([excerpt](./excerpt.md))
* content - 文章的内容([content](./content.md))
* url - 文章的web地址([url](./url.md))
* image - 文章的封面([image](./image.md))
* featured - 是否是推荐的文章，默认是false
* page - 是否是单独页，默认是false
* meta_title - 自定义的搜索引擎优化标题([meta_title](./meta_title.md))
* meta_description - 自定义的搜索引擎优化摘要([meta_description](./meta_description.md))
* published_at - 文章发表时的日期和时间([published_at](./published_at.md))
* created_at - 文章创建时的日期和时间([created_at](./created_at.md))
* author - 文章作者的详细信息(点击[author](./author.md)查看具体内容)
* tags - 文章的标签列表(点击[tags](./tags.md)查看具体内容)

###实用的文章助手函数
[{{title}}](./title.md), [{{content}}](./content.md), [{{url}}](./url.md), [{{author}}](./author.md), [{{date}}](./date.md), [{{excerpt}}](./excerpt.md), [{{image}}](./image.md), [{{post_class}}](./post_class.md), [{{tags}}](./tags.md)
###示例代码
```html
{{#post}}
<article class="{{post_class}}">
  <header class="post-header">
    <h1 class="post-title">{{title}}</h1>
    <section class="post-meta">
      <time class="post-date" datetime="{{date format='YYYY-MM-DD'}}">
        {{date format="DD MMMM YYYY"}}
      </time> 
      {{tags prefix=" on "}}
    </section>  
  </header>
  <section class="post-content">
    {{content}}
  </section>     
{{/post}}  
```
###推荐的文章
使用`{{#if featured}}{{/if}}`来判断当前文章是否被推荐了。  
推荐的文章会获得一个额外的CSS类名，所有可以使得推荐的文章显示得和其它文章不一样，但这并不意味着在文章列表中它们就会排在靠前的位置，也不会在列表页面中显示得和其它文章不一样。