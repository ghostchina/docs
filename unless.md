#unless
反向条件助手函数，`{{#unless}}`助手函数是Handlebars内建的。
###用法
`{{#unless featured}}{{/unless}}`
#####参数
`featured` 判断条件，任意类型
###简介
`{{#unless}}`正好和`{{#if}}`功能相反，如果你只关心`{{#if}}`里面的`{{else}}`部分，那么`{{#unless}}`将非常适合你使用。  
它和`{{if}}`的用法一样，并且支持`{{else}}`和`^`否定功能。  
`{{#unless}}`和`{{#if}}`使用的条件判断表达式是一样的。
###示例代码
简单的unless示例，当`featured`为假时输出unless标签中间的内容。

```html
{{#unless featured}}
  ...do something...
{{/unless}}
```
如果你愿意的话，你也可以在unless中使用else，不过这个时候使用`{{#if}}`可能会方便阅读。

```html
// This is identical to if, but with the blocks reversed
{{#unless featured}}
  ...do thing 1...
{{else}}
  ...do thing 2...
{{/unless}}
```
所有的块级助手都是支持否定的，但是这个时候你真的应该使用if助手了。

```html
// The negation symbol means that this is identical to using if
{{^unless featured}}
  ...do thing 1...
{{else}}
  ...do thing 2...
{{/unless}}
```