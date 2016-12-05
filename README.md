# Bootstrap-study

在[慕课](http://www.imooc.com/video/3399)平台学习的bootastrap框架笔记
###lesson1 
mytest1.html对bootstrap框架各种常见组件的使用

###lesson2全局样式
在制作Web页面时，前端人员都习惯为网站设置一个全局样式（reset.css）。normalize.less并没有全局样式，建议到bootstrap.min.css里面查看。具体说明如下：

- 移除body的margin声明(margin:0)
- 设置body的背景色为白色(background-color:#fff)
- 为排版设置了基本的字体、字号和行高(
  font-family:"Helvetica Neue",Helvetica,Arial,sans-serif;
 	font-size:14px;
 	line-height:1.42857143;)
- 设置全局链接颜色，且当链接处于悬浮“:hover”状态时才会显示下划线样式(text-decoration:underline)

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
</table>
