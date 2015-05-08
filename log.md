# log

输出传入主题模板中的数据，用于调试。

### 用法：`{{log value}}`

|类型|参数|属性|
|----|----------|----------|
|[Output](helpers#output), Debugging, Handlebars|* value (any)|n/a|

### 简介

`{{log}}` 是 Handlebars 自带的一个助手函数，但是在 Ghost 0.4.2 版本之前此助手函数没有被赋予任何功能。

现在，Ghost 运行在 development 模式时，你可以使用 `{{log}}` 助手函数向服务器端的控制台窗口输出调试信息。具体来说，你可以让 handlebars 输出数据对象或者当前 handlebars 的上下文环境（context）的详细内容。

例如，输出 handlebars 当前可以访问的完整的上下文（ 'context' ）数据：

`{{log this}}`

或者只是在循环输出博文时输出博文的详细信息：

```handlebars
{{#foreach posts}}
   {{log post}}
{{/foreach}}
```