
#  HTML 
##  标题


```HTML
<h1>1级标题</h1>
<h2>2级标题</h2>
<h3>3级标题</h3>
<h4>4级标题</h4>
<h5>5级标题</h5>
<h6>6级标题</h6>
```

示例：	

<h1>1级标题</h1>
<h2>2级标题</h2>
<h3>3级标题</h3>
<h4>4级标题</h4>
<h5>5级标题</h5>
<h6>6级标题</h6>

###  页面格式化标签

#### ( 1 ) 标题标签



```html
<hn align ="对齐方式"> 标题文本 </h>
```





##  font 标签

font标签设置文本样式

face ： 设置文字的字体，例如微软雅黑，黑体，宋体。

size  ：设置文字的大小，可取1~7之间的整数值

color： 设置文字的颜色

 

```html
<font>示例:</font>

<font>默认效果</font>

<font face="楷体">字体改为楷体</font>

<font size="5">五号字体</font>

<font color="red">红色字体效果</font>

<font face="宋体" size = "6" color = "blue">效果</font>
```



<font>示例  :</font>

效果

<font>默认效果</font>

<font face="楷体">字体改为楷体</font>

<font size="5">五号字体</font>

<font color="red">红色字体效果</font>

<font face="宋体" size = "6" color = "blue">效果</font>



##  文本格式化标签(推荐使用第二种标签)

```html
<b></b> 和<strong></strong>  文字以粗体方式显示
<u></u> 和<ins></ins>  		文字以加下划线方式显示
<i></i> 和<em></em>  		文字以斜体方式显示
<s></s> 和<del></del> 		文字以加删除线方式显示
```

|效果|第一种形式 |第二种形式(推荐) |
|-----|----|---|
|加粗|<b>加粗</b>       ```<b> 文字 </b>``` |<strong>加粗</strong> ```<strong> 文字 </strong>```|
|下划线|<u>下划线</u>   ```<u> 文字 </u>``` |<ins>下划线</ins> ```<ins> 文字 </ins>```|
|斜体|<i>斜体</i>       ```<i> 文字 </i>``` |<em>斜体</em> ```<em> 文字 </em>```|
|删除线|<s>删除线</s>   ```<s> 文字 </s>``` |<del>删除线</del> ```<del> 文字 </del>```|



##  图片标签

单标签:

```html
<img src=" " alt=" ">
```


| 属性   | 属性值 | 描述                                                       |
| ------ | :----- | :--------------------------------------------------------- |
| src    | URL    | 图像路径                                                   |
| alt    | 文本   | 图像不能显示时替换的文本                                   |
| title  | 文本   | 鼠标指针悬停时显示的内容                                   |
| width  | 像素值 | 设置图像的宽度                                             |
| height | 像素值 | 设置图像的高度                                             |
| border | 数字   | 设置图像边框的宽度                                         |
| vspace | 像素值 | 设置图像顶部和底部的空白(垂直边距)                         |
| hspace | 像素值 | 设置图像顶部和底部的空白(水平边距)                         |
|        | left   | 将图像对齐到右边                                      |
|        | right  | 将图像对齐到右边                                      |
| align  | top    | 将图像的顶端水与文本的第一行文字对齐，其他文字居图像下方   |
|        | middle | 将图像的水平中线与文本的第一行文字对齐，其他文字居图像下方 |
|        | bottom | 将图像的底部与文本的第一行文字对齐，其他文字居图像下方     |

```./ 表示当前文件夹```

```./ 文件夹名/```      




## 特殊字符标签
|特殊文字|描述|字符的代码|
|------------|:------|:--------------|
||空格符| ```&nbsp``` &nbsp; |
|<|小于号|```&lt;``` &lt;|
|>|大于号|```&gt;``` &gt;|
|&|和号|```&amp;``` &amp;|
|￥|人民币|```&yen;``` &yen;|
|&copy;|版权号|```&copy;``` &copy;|
|&reg;|注册商标|```&reg;``` &reg;|
|&deg;|度数符号|```&deg;``` &deg;|
|&plusmn;|正负号|```&plusmn;``` &plusmn;|
|&times;|乘号|```&times;``` &times;|
|&divide;|除号|```&divide;``` &divide;|
|&sup2;|平方2(上标2)|```&sup2;``` &sup2;|
|&sup3;|平方3(上标3)|```&sup3;``` &sup3;|

##  音视频标签



音频：

```html
<audio src = "./music.mp3" controls = "controls"></audio>
```



|属性|值|描述|
|-----|-----|-----|
|autoplay|autoplay|当页面载入完成后自动播放音频|
|loop|loop|音频结束时重新开始播放|
|preload|auto/meta/none|如果出现该属性，则音频在页面加载时进行加载，并预备播放；如果使用 “autoplay” 属性，浏览器会忽略 preload 属性 |



视频：

```html
<vedio src = "./music.mp3" controls = "controls"></vedio>
```

|属性|值|描述|
|-----|-----|-----|
|autoplay|autoplay|当页面载入完成后自动播放视频|
|loop|loop|视频结束时重新开始播放|
|preload|auto/meta/none|如果出现该属性，则视频在页面加载时进行加载，并预备播放；如果使用 “autoplay” 属性，浏览器会忽略 preload 属性 |
|poster|url|当视频缓冲不足时，该属性值链接一个图像，并将该图像按照一定的比例显示出来|



##  超链接标签



```html
<a href = "https://www.baidu.com"> 超链接 </a>
```



## 无序列表
```html
	<ul>
        <li>列表项1</li>
        <li>列表项2</li>
        <li>列表项3</li>
        <li>列表项4</li>
        <li>列表项5</li>
    </ul>
```

|type属性值|显示效果|
|------|----|
|disc(默认值)||
|circle||
|square||



##  有序列表

```html
    <ol>
        <li>西瓜</li>
        <li>芒果</li>
        <li>梨子</li>
    </ol>
```
|属性|属性值/属性值类型|描述|
|-------|-------|------|
||1 (默认)|项目符号显示为数字 1，2，3，...|
|type|a 或 A|项目符号显示为数字 a，b，c，d... 或 A，B，C，...|
||i 或 l|项目符号显示为数字 i , ii , iii ,...或 l , ll , lll ,...|
|start|数字|规定项目符号的起始值|
|value|数字|规定项目符号的数字|



##  定义列表

```html
  <dl>
        <dt>帮助中心</dt>
        <dd>账号管理</dd>  <!--dd会缩进--> 
        <dd>购物指南</dd>
        <dd>订单操作</dd>
    </dl>

```

##  td 标签的属性

|属性|描述|常用属性值或单位|
|------|-------|------------------------|
|width|设置单元格的宽度|像素|
|height|设置单元格的高度|像素|
|align|设置单元格内容的水平对齐方式|left、center、right|
|valign|设置单元格内容的垂直对齐方式|top、middle、bottom|
|bgcolor|设置单元格的背景颜色|预定义的颜色值、十六进制#RGB、rgb(r,g,b)|
|background|设置单元格的背景图像|url地址|
|colspan|设置单元格横跨的列数(用于合并水平方向的单元格)|正整数|
|rowspan|设置单元格竖跨的列数(用于合并竖直方向的单元格)|正整数|



## 表单

```html
创建表单

<form action="url 地址" method="提交方式" name="表单名称">
      <!--各种表单名称-->
</form>

action 属性用于指定接收并处理表单数据的服务器程序的url地址   无地址用 # 代替

action 的属性值可以是相对路径或绝对路径，还可以为接受数据的 E_mail 邮箱地址

<form action=mailto:htmlcss@163.com>
    
method 属性用于设置表单数据的提交方式 ， 其取值为 get 或 post
 
```



（1）表单控件

|表单控件|描述|
|------------|-----|
|```<input/>```|表单描述控件(可定义多种表单项)|
|```<textarea/></textarea>```|定义多行文本框|
|```<select></select>```|定义一个下拉列表(必须包含列表项)|

input控件

|属性|属性值|描述|
|---|----|------|
||text|单行文本输入框|
||password|密码输入框|
||radio|单选按钮|
||checkbox|复选框|
|type|button|普通按钮|
||submit|提交按钮|
||reset|重置按钮|
||image|图像形式的提交按钮|
||hidden|隐藏域|
||file|文件域|
|name|由用户自定义|控件的名称|
|value|由用户自定义|input控件中的默认文本值|
|size|正整数|input控件在页面中的显示宽度|
|readonly|readonly|改控件内容为只读(不能编辑修改)|
|disabled|disabled|第一次加载页面时禁用该控件(显示为灰色)|
|checked|checked|定义选择控件默认被选中的项|
|maxlength|正整数|控件允许输入的最多字符数|







# 使用CSS技术美化页面
```
web标准三大结构：结构 表现 行为

css 既可以嵌入在HTML文档中，也可以是一个单独的外部文件，如果是独立的文件，则必须以“.css”为后缀名。
```

##  css 基础选择器
###  (1)标签选择器

###  (2)类选择器
###  (3)id选择器
###  (4)通配符选择器

##  css 字体样式属性
### (1) font-size : 字号大小
|长度单位|说明|
|-------|-------|
|em|倍率，相当于当前对象内文本的字体尺寸|
|px|


(5) font : 综合设置字体样式
语法格式如下：
```html
选择器{font:font-style font-weight font-size/line-height font-family;}

使用font属性时，必须按照上面语法格式中的顺序书写，各个属性以空格隔开。line-height 指行高

例如：

```

## 文本外观属性
###  (1) color : 文本颜色
```
color 属性用于定义文本的颜色，其取值方式有如下3种。
(1) 预定义的颜色值，例如 red 、green 、 blue等
(2) 十六进制，例如 #FF0000 ##FF6600 #29D794等。实际工作中，十六进制是最常用的定义颜色的方式。 
(3) RGB代码，如红色可以表示为 rgb(255,0,0)或 rgb(100%,0%,0%)
```
###  (2) letter-spacing : 字间距

```
用于定义字间距，字间距就是字符与字符之间的空白。属性值为不同单位的数值。定义字间距可以使用负值，默认为 normal。
```

###  (3) word-spacing : 单词间距
```
用于定义英文单词之间的间距，对中文字符无效。与 letter-spacing 一样，其属性值可以为不同单位的数值，允许使用负值，默认为normal。 
```

###  (4) line-height : 行间距
```
用于设置行间距，行间距就是行与行之间的高度，即字符的垂直间距。一般称为行高。
常用属性值单位有三种：像素 px(工作中用的最多) 相对值 em  百分比 % 

垂直居中 line-height = height
```
###  (5) text-transform : 文本转换
```
none :不转换 (默认值)
capitailze :首字母大写
uppercase : 全部字符转换为大写
lowercase : 全部字符转换为小写
```

###  (6) text-decoration : 文本装饰
```
none :没有装饰 (正常文本默认值)
underline :下画线
overline : 上画线
line-through : 删除线
```

###  (7) text-align : 文本对齐方式
```
用于设置文本内容的水平对齐

left :右对齐(默认值)
right : 右对齐
center : 居中对齐

text-align 属性仅适用于块级元素，对行内元素无效

如需对图像设置水平对齐，可以为图像添加一个父标签(如<p>) 然后对父标签应用text-align属性。
```
###  (8) text-indent : 首行缩进
```
用于设置首行文本的缩进
```
##  css复合选择器
### (1)标签指定式选择器

```html
标签指定式选择器又称交集选择器，由两个选择器构成，其中第一个为标签选择器，第二个为class选择器或id选择器，两个选择器之间不能有空格

例子：

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style type="text/css">
        .d1 .p1 {
            color: red;
        }
    </style>
</head>

<body>
    <p>这是一个p标签 数媒2101 26 刘博</p>
    <div class="d1">
        <p class="p1">这个是div的儿子p标签</p>
    </div>
</body>

</html>
```





### (2)后代选择器
```html
后代选择器
```

### (3)并集选择器
```

```
###  hover伪类选择器
### Emmet 语法
