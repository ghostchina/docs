#date
使用moment.js格式化时间
###用法
`{{date dateToFormat format="formatString"}}`
#####参数
`dateToFormat` 需要格式化的数据，时间类型，默认是`published_at`
#####属性
* `format` 格式化字符串，默认是“MMM Do, YYYY”
* `timeage` 布尔值

###简介
`{{date}}`是一个用来格式化时间的助手函数，你可以像下面这样传入一个时间和一个格式化字符串来显示时间：
```html
// outputs something like 'July 11, 2014'
{{date published_at format="MMMM DD, YYYY"}}
```
或者传入一个时间以及timeage标识：
```html
// outputs something like '5 mins ago'
{{date published_at timeago="true"}}
```
如果没有传入格式化字符串，`{{date}}`将默认格式化为“MMM Do, YYYY”格式。
如果在post元素里面使用但没有传入显示的时间，`{{date}}`将默认显示`published_at`的时间。
如果在post元素外使用但又没有传入显示的时间，`{{date}}`将默认显示当前时间。
`date`使用的是[momentjs](http://momentjs.com/)来格式化时间的，你可以点击他们的[文档](http://momentjs.com/docs/#/parsing/string-format/)来查看能够使用的各种不同的格式化字符串。