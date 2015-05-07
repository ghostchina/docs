#image
输出文章的封面或者作者的头像
###用法
`{{image}}`
#####属性
`absolute` - 布尔值
###简介
`{{image}}`助手函数会根据你当前的作用域来显示文章的封面或者作者的头像。  
你可以使用absolute属性来强制使用图片的绝对路径`{{image absolute="true"}}`

文章页面的使用：

```html
{{#post}}
  {{image}} //Outputs post's image
  {{author.image}} //Outputs post author's image to author context
{{/post}}
```
作者页面的使用：

```html
{{#author}}
  {{image}} //Outputs this author's image
{{/author}}
```