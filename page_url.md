# page_url

输出一系列页面列表中的某个页面的链接（URL），例如输出页面导航中的“后一页”。

### 用法：`{{page_url 2}}`

|类型|参数|属性|
|----|----------|----------|
|[Output](/docs/helpers#output), [Ghost](/docs/helpers#ghost)|page number (number)|n/a|

### 简介

此助手函数用在分页模板中，由 [`{{pagination}}` helper](doc:pagination) 调用并输出后一页、前一页或某个指定页面的 URL。向此助手函数传递的变量需要包含期望输出的页码。

### 实例

> 下面列出了 Handlebars 模板和实际输出的 HTML 代码

Handlebars 模板来自 [pagination.hbs](https://github.com/TryGhost/Ghost/blob/0.5.3/core/server/helpers/tpl/pagination.hbs) 文件，HTML 代码展示了当前在第2页时的页面导航状态。

```handlebars
<nav class="pagination" role="navigation">
    {{#if prev}}
        <a class="newer-posts" href="{{page_url prev}}">&larr; Newer Posts</a>
    {{/if}}
    <span class="page-number">Page {{page}} of {{pages}}</span>
    {{#if next}}
        <a class="older-posts" href="{{page_url next}}">Older Posts &rarr;</a>
    {{/if}}
</nav>
```

```html
<nav class="pagination" role="navigation">
    <a class="newer-posts" href="/">&larr; Newer Posts</a>
    <span class="page-number">Page 2 of 3</span>
    <a class="older-posts" href="/page/3/">Older Posts &rarr;</a>
</nav>
```