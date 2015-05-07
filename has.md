#has
用来判断一篇文章是否有制定的属性
###用法
`{{#has tag="value", author="value"}}`
#####属性
* `tag` 逗号分开的列表
* `author` 逗号分开的列表

###简介
`{{#has}}`允许主题开发者判断当前的内容来制作更多的不同的布局。  
和其它的助手函数一样，`{{#has}}`也支持`{{else}}`块或者使用`^`来代替`#`。这意味着`{{#has}}`和`{{else}}`的配合与`{{^has}}`和`{{else}}`的配合达到的效果正好相反。
###示例代码
目前的情况下，`{{#has}}`只允许你判断一篇文章的作者和标签：  
判断一篇文章是否包括一个指定的作者：

```html
{{#post}}
    {{#has author="Joe Bloggs"}}
        ...do something if the author is Joe Bloggs...
    {{/has}}
{{/post}}
```
判断一篇文章是否包括一个指点的标签：

```html
{{#post}}
    {{#has tag="photo"}}
        ...do something if this post has a tag of photo...
    {{else}}
        ...do something if this posts doesn't have a tag of photo...
    {{/has}}
{{/post}}
```
你可以通过传入一个逗号分割的标签列表(等同于OR或查询)来判断文章是否包含其中任何一个标签：

```html
{{#has tag="photo, video, audio"}}
    ...do something if this post has a tag of photo or video or audio...
{{else}}
    ...do something with other posts...
{{/has}}
```
你可以通过嵌套来实现AND且查询：

```html
{{#has tag="photo"}}
    ...do something if this post has a tag of photo..
    {{#has tag="panorama"}}
       ...if the post has both the photo and panorama tags
    {{/has}}
{{else}}
    ...do something with other posts...
{{/has}}
```
你还可以在`{{else}}`标签里面嵌套使用`{{＃has}}`来做更多的判断，看起来有点像switch判断语句：

```html
{{#has tag="photo"}}
    ...post has the photo tag...
{{else}}
    {{#has tag="video"}}
        ...post has the video tag...
    {{else}}
        {{#has tag="audio"}}
            ...post has the audio tag...
        {{else}}
            ...post has none of the mentioned tags...
        {{/has}}
    {{/has}}
{{/has}}
```
如果你喜欢做否定判断，比如判断一篇文章是否不包含某个特定的标签，这也是可以实现的，你只需要将`#`替换成`^`：

```html
{{^has tag="photo"}}
    ...do something if this post does **not** have a tag of photo...
{{else}}
    ...do something if this posts does have a tag of photo...
{{/has}}
```