# Bootstrap-study

在[慕课](http://www.imooc.com/video/3399)平台学习的bootastrap框架笔记
注：由于bootstrap版本不同，故有一些与慕课平台不一样的地方，我使用的是bootstrap-3.3.0，而慕课的是3.1.1
###lesson1.1
mytest1.html对bootstrap框架各种常见组件的使用

###lesson1.2-全局样式
在制作Web页面时，前端人员都习惯为网站设置一个全局样式（reset.css）。normalize.less并没有全局样式，建议到bootstrap.min.css里面查看。具体说明如下：

- 移除body的margin声明(margin:0)
- 设置body的背景色为白色(background-color:#fff)
- 为排版设置了基本的字体、字号和行高(
  font-family:"Helvetica Neue",Helvetica,Arial,sans-serif;
 	font-size:14px;
 	line-height:1.42857143;)
- 设置全局链接颜色，且当链接处于悬浮“:hover”状态时才会显示下划线样式(text-decoration:underline)

###lesson2.1-标题
####主标题
<table>
  <tr>
  <td>元素</td>
  <td>字体大小</td>
  <td>计算比例</td>
  <td>其他</td>
  </tr>
  <tr>
  <td>h1</td>
  <td>36px</td>
  <td>14px*2.60</td>
  <td rowspan="3">margin-top:20px;margin-bottom:10px;</td>
  </tr>
  <tr>
  <td>h2</td>
  <td>30px</td>
  <td>14px*2.15</td>
  </tr>
  <tr>
  <td>h3</td>
  <td>24px</td>
  <td>14px*1.70</td>
  </tr>
  <tr>
  <td>h4</td>
  <td>18px</td>
  <td>14*1.25</td>
  <td>margin-top:10px;margin-bottom:10px;</td>
  </tr>
  <tr>
  <td>h5</td>
  <td>14px</td>
  <td>14px*1</td>
  </tr>
  <tr>
  <td>h6</td>
  <td>12px</td>
  <td>14px*0.85</td>
  </tr>
</table>
对h1,h2,h3,h4,h5,h6,.h1,.h2,.h3,.h4,.h5,.h6设置了属性
```
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
 ```
 可以发现：1、重新设置了margin-top和margin-bottom的值，  h1~h3重置后的值都是20px；h4~h6重置后的值都是10px。
2、所有标题的行高都是1.1（也就是font-size的1.1倍）,而且文本颜色和字体都继承父元素的颜色和字体。
3、固定不同级别标题字体大小，h1=36px，h2=30px，h3=24px，h4=18px，h5=14px和h6=12px。
####副标题
使用了<small>标签来制作副标题。这个副标题具有其自己的一些独特样式：

1、行高都是1，而且font-weight设置了normal(400)变成了常规效果（不加粗），同时颜色被设置为灰色（#777）。
2、由于<small>内的文本字体在h1~h3内，其大小都设置为当前字号的65%；而在h4~h6内的字号都设置为当前字号的75%；

###lesson2.2-段落
在bootstrap.min.css的body中设置了文本的全局样式

```
font-family:"Helvetica Neue",Helvetica,Arial,sans-serif;
font-size:14px;
line-height:1.42857143;
color:#333;
```
另外在Bootstrap中，为了让段落p元素之间具有一定的间距，便于用户阅读文本，特意设置了p元素的margin值
```
margin: 0 0 10px;
```
在Bootstrap中，排版设置的默认值都存在variables.less文件中(Sass版本存在_variables.scss中)的两个变量：
LESS版本：
```
@font-size-base: 14px; @line-height-base: 1.428571429; // 20/14
```
SASS版本：
```
$font-size-base: 14px !default; $line-height-base: 1.428571429 !default; // 20/14
```

####lesson2.3-强调内容
如果想让一个段落p突出显示，可以通过添加类名“.lead”实现，其作用就是增大文本字号，加粗文本，而且对行高和margin也做相应的处理
.lead的css如下：
```
.lead {
margin-bottom: 20px;
font-size: 16px;
font-weight: 200;
line-height: 1.4;
}
@media (min-width: 768px) {/*大中型浏览器字体稍大*/
.lead {
font-size: 21px;
  }
}
```
除此之外，Bootstrap还通过元素标签:<small>、<strong>给文本做突出样式处理。
####lesson2.4-粗体
在普通的元素中我们一般通过font-weight设置为bold关键词给文本加粗。在Bootstrap中，可以使用<b>和<strong>标签让文本直接加粗。
####lesson2.5-斜体
给元素设置样式font-style值为italic实现之外，在Bootstrap中还可以通过使用标签<em>或<i>来实现。
####lesson2.6-text风格
主要有如下：具体可以查看text-style.html
- text-muted：提示，使用浅灰色（#999）
- text-primary：主要，使用蓝色（#428bca）
- text-success：成功，使用浅绿色(#3c763d)
- text-info：通知信息，使用浅蓝色（#31708f）
- text-warning：警告，使用黄色（#8a6d3b）
- text-danger：危险，使用褐色（#a94442）
####lesson2.7-text对齐
```
.text-left {
text-align: left;
}
.text-right {
text-align: right;
}
.text-center {
text-align: center;
}
.text-justify {
text-align: justify;
}
```
