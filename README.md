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
  <td rowspan="3">margin-top:10px;margin-bottom:10px;</td>
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
除此之外，Bootstrap还通过元素标签:&lt;small&gt;，&lt;strong&gt;给文本做突出样式处理。
####lesson2.4-粗体
在普通的元素中我们一般通过font-weight设置为bold关键词给文本加粗。在Bootstrap中，可以使用&lt;b&gt;和&lt;strong&gt;标签让文本直接加粗。
####lesson2.5-斜体
给元素设置样式font-style值为italic实现之外，在Bootstrap中还可以通过使用标签&lt;em&gt;或&lt;i&gt;来实现。
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
####lesson2.8-列表
```
ul,ol{
margin-top:0;margin-bottom:10px;
}
ul ul,ol ul,ul ol,ol ol {
  margin-bottom: 0;
}
```
- .list-unstyled的css是 
```
padding-left:0;list-style:none;
```
- .list-inline的css是
```
.list-inline {
padding-left: 0;
margin-left: -5px;
list-style: none;
}
.list-inline > li {
display: inline-block;
padding-right: 5px;
padding-left: 5px;
}
```
####定义列表
```
dl {
margin-top: 0;
margin-bottom: 20px;
}
dt,
dd {
line-height: 1.42857143;
}
dt {
font-weight: bold;
}
dd {
margin-left: 0;
}
```
####水平定义列表
```
@media (min-width:768px){
 	.dl-horizontal dt{
 		float:left;width:160px;overflow:hidden;clear:left;text-align:right;text-overflow:ellipsis;white-space:nowrap
 	}
 	.dl-horizontal dd{
 		margin-left:180px
 	}
  }
 .dl-horizontal dd:before,.dl-horizontal dd:after{
 display:table;content:" "
 }
```
也就是说，只有屏幕大于768px的时候，添加类名“.dl-horizontal”才具有水平定义列表效果。其实现主要方式：
1. 将dt设置了一个左浮动，并且设置了一个宽度为160px
2. 将dd设置一个margin-left的值为180px，达到水平的效果
3. 当标题宽度超过160px时，将会显示三个省略号
####代码风格
一般在个人博客上使用的较为频繁，用于显示代码的风格。在Bootstrap主要提供了三种代码风格：
1、使用```<code></code>```来显示单行内联代码
2、使用```<pre></pre>```来显示多行块代码
3、使用```<kbd></kbd>```来显示用户输入代码
预编译版本的Bootstrap将代码的样式单独提取出来：
1、LESS版本，请查阅code.less文件
2、Sass版本，请查阅_code.scss文件
```.pre-scrollable```可以控制代码块区域最大高度为340px，一旦超出这个高度，就会在Y轴出现滚动条。
#####滚动代码
.pre-scrollable {
max-height: 340px;
overflow-y: scroll;
}
####表格
Bootstrap为表格提供了1种基础样式和4种附加样式以及1个支持响应式的表格。table-style.html详细可点击查看
LESS版本，对应的文件是 tables.less
Sass版本，对应的文件是 _tables.scss
#####表格颜色
<table>
<tr>
<th>类名</th>
<th>描述</th>
<th>对应的颜色</th>
</tr>
<tr>
<td>.active</td>
<td>表示当前活动的信息</td>
<td>#f5f5f5</td>
</tr>
<tr>
<td>.success</td>
<td>表示成功或正确的行为</td>
<td>#dff0d8</td>
</tr>
<tr>
<td>.info</td>
<td>表示中立的信息或行为</td>
<td>#d9edf7</td>
</tr>
<tr>
<td>.warning</td>
<td>表示警告，需要特别注意</td>
<td>#fcf8e3</td>
</tr>
<tr>
<td>.danger</td>
<td>表示危险或可能是错误的行为</td>
<td>#f2dede</td>
</tr>
</table>
只需要在&lt;tr&gt;或者&lt;td&gt;中添加类名就行，不过需要注意的是<em>鼠标悬浮状态时需要在table上加上.table-hover类</em>
.table主要有三个作用：
1. 给表格设置了```width:100%,margin-bottom:20px```以及设置单元内距
2. 在thead底部设置了一个2px的浅灰实线并把元素的顶端与行中最低的元素的顶端对齐。```vertical-align:bottom;border-bottom:2px solid #ddd```
3. 每个单元格td顶部设置了一个1px的浅灰实线```border-top:1px solid #ddd```并把元素的顶端与行中最高元素的顶端对齐vertical-align:top;
#####斑马线表格
只需要在&lt;table class="table"&gt;的基础上增加类名“.table-striped”即可：即tbody隔行有一个浅灰色的背景色
```
.table-striped>tbody>tr:nth-child(odd){
 	background-color:#f9f9f9
 }
```
#####带边框的表格
只需要在基础表格&lt;table class="table"&gt;基础上添加一个“.table-bordered”
```
.table-bordered {
  border: 1px solid #ddd;/*整个表格设置边框*/
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd; /*每个单元格设置边框*/
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;/*表头底部边框*/
}
```
#####鼠标悬浮高亮的表格
提供了一个“.table-hover”类名来实现这种表格效果。即为.active的颜色hover
```
.table-hover>tbody>tr:hover{background-color:#f5f5f5}
```
#####紧凑型表格
Bootstrap中紧凑型的表格与基础表格差别不大，因为只是将单元格的内距padding由8px调至5px。
```
<div class="table-responsive">
<table class="table table-bordered">
   …
</table>
</div>
```

```
.table-responsive{min-height:.01%;overflow-x:auto}
 @media screen and (max-width:767px){
 	.table-responsive{
 		width:100%;margin-bottom:15px;overflow-y:hidden;-ms-overflow-style:-ms-autohiding-scrollbar;border:1px solid #ddd
 	}
  .table-responsive>.table>thead>tr>th,.table-responsive>.table>tbody>tr>th,.table-responsive>.table>tfoot>tr>th,.table-responsive>.table>thead>tr>td,.table-responsive>.table>tbody>tr>td,.table-responsive>.table>tfoot>tr>td{
 		white-space:nowrap
 	}
 }
```
最重要的是overflow-x:auto与white-space:nowrap两个属性控制横着的scroll
###lesson3-表单
####表单源码查询
- LESS版本：对应源文件 forms.less
- Sass版本：对应源文件 _forms.scss
对于基础表单，Bootstrap并未对其做太多的定制性效果设计，仅仅对表单内的fieldset、legend、label标签进行了定制。
