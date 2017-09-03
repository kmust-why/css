# css(层叠样式表)
记录有关css的知识

# css页面引入方法： #

1. 外联式：通过link标签，链接到外部样式表到页面中。（最推荐使用的方法）
```html
<link rel="stylesheet" type="text/css" href="css/main.css">
```

2. 嵌入式：通过style标签，在网页上创建嵌入的样式表。(学习使用的方法，首页才使用该方法)
```html
<style type="text/css">
    div{ width:100px; height:100px; color:red }
    ......
</style>
```

3. 内联式：通过标签的style属性，在标签上直接写样式。（不推荐使用）


```html
<div style="width:100px; height:100px; color:red ">......</div>
```

# css文本设置 #

## 常用的应用文本的css样式 ##

- color 设置文字的颜色，如： color:red;

- font-size 设置文字的大小，如：font-size:12px;

- font-family 设置文字的字体，如：font-family:'微软雅黑';

- font-style 设置字体是否倾斜，如：font-style:'normal'; 设置不倾斜，font-style:'italic';设置文字倾斜

- font-weight 设置文字是否加粗，如：font-weight:bold; 设置加粗 font-weight:normal 设置不加粗

- font 同时设置文字的几个属性，写的顺序有兼容问题，建议按照如下顺序写： font：是否加粗 字号/行高 字体；如： font:normal 12px/36px '微软雅黑';

- line-height 设置文字的行高，如：line-height:24px;

- text-decoration 设置文字的下划线，如：text-decoration:none; 将文字下划线去掉

- text-indent 设置文字首行缩进，如：text-indent:24px; 设置文字首行缩进24px

- text-align 设置文字水平对齐方式，如text-align:center 设置文字水平居中

# css颜色表示法 #

## css颜色值主要有三种表示方法 ##

1. 颜色名表示，比如：red 红色，gold 金色

2. rgb表示，比如：rgb(255,0,0)表示红色

3. 16进制数值表示，比如：#ff0000 表示红色，这种可以简写成#f00

# css选择器 #
## 标签选择器（尽量少用，主要用到层级选择器中） ##
- `*{margin:0;padding:0}`表示匹配所有的标签

## id选择器（实际开发中不建议使用） ##

```html
#box{color:red} 

<div id="box">....</div>   <!-- 对应以上一条样式，其它元素不允许应用此样式 -->
```
## 类选择器（实际开发中使用最多） ##
## 层级选择器 ##
```html
.box span{color:red}
.box .red{color:pink}
.red{color:red}

<div class="box">
    <span>....</span>
    <a href="#" class="red">....</a>
</div>

<h3 class="red">....</h3>
```
## 组选择器 ##
- 多个选择器，如果有同样的样式设置，可以使用组选择器。
举例：
```html
.box1,.box2,.box3{width:100px;height:100px}
.box1{background:red}
.box2{background:pink}
.box2{background:gold}

<div class="box1">....</div>
<div class="box2">....</div>
<div class="box3">....</div>
```
## 伪类及伪元素选择器 ##
- 常用的伪类选择器有hover，表示鼠标悬浮在元素上时的状态，伪元素选择器有before和after,它们可以通过样式在元素中插入内容。
```html
.box1:hover{color:red}
.box2:before{content:'行首文字';}
.box3:after{content:'行尾文字';}

<div class="box1">....</div>
<div class="box2">....</div>
<div class="box3">....</div>
```
# 表格样式 #
# CSS盒子模型 #
## 盒子模型解释 ##
![](./images/hezi.png)
## 设置边框 ##
- 设置一边的边框，比如顶部边框，可以按如下设置：
```html
border-top-color:red;    /* 设置顶部边框颜色为红色 */  
border-top-width:10px;   /* 设置顶部边框粗细为10px */   
border-top-style:solid;  /* 设置顶部边框的线性为实线，常用的有：solid(实线)  
  dashed(虚线)  dotted(点线); */
```
- 上面三句可以简写成一句：
```html
border-top:10px solid red;
```
- 设置其它三个边的方法和上面一样，把上面的'top'换成'left'就是设置左边，换成'right'就是设置右边，换成'bottom'就是设置底边。

- 四个边如果设置一样，可以将四个边的设置合并成一句：
```html
border:10px solid red;
```
## 设置内间距padding ##

- 设置盒子四边的内间距，可设置如下：
```html
padding-top：20px;     /* 设置顶部内间距20px */ 
padding-left:30px;     /* 设置左边内间距30px */ 
padding-right:40px;    /* 设置右边内间距40px */ 
padding-bottom:50px;   /* 设置底部内间距50px */
```
- 上面的设置可以简写如下：
```html
padding：20px 40px 50px 30px; /* 四个值按照顺时针方向，分别设置的是 上 右 下 左  
四个方向的内边距值。 */
```
- padding后面还可以跟3个值，2个值和1个值，它们分别设置的项目如下：


```html
padding：20px 40px 50px; /* 设置顶部内边距为20px，左右内边距为40px，底部内边距为50px */ 
padding：20px 40px; /* 设置上下内边距为20px，左右内边距为40px*/ 
padding：20px; /* 设置四边内边距为20px */
```
## 设置外间距margin ##

- 外边距的设置方法和padding的设置方法相同，将上面设置项中的'padding'换成'margin'就是外边距设置方法。 

## 盒子模型的尺寸 ##
- 盒子的width和height设置的是盒子内容的宽和高，不是盒子本身的宽和高，盒子的真实尺寸计算公式如下：
```html
盒子宽度 = width + padding左右 + border左右
盒子高度 = height + padding上下 + border上下
```
## 外边距合并 ##

- 外边距合并指的是，当两个垂直外边距相遇时，它们将形成一个外边距。合并后的外边距的高度等于两个发生合并的外边距的高度中的较大者。解决方法如下：

1. 使用这种特性
2. 设置一边的外边距，一般设置margin-top
3. 将元素浮动或者定位

## margin-top 塌陷 ##

- 在两个盒子嵌套时候，内部的盒子设置的margin-top会加到外边的盒子上，导致内部的盒子margin-top设置失败，解决方法如下：
```html
1、外部盒子设置一个边框
2、外部盒子设置 overflow:hidden
3、使用伪元素类(使用最多的方法，类似于第一种方法)：

.clearfix:before{
    content: '';
    display:table;
}
```
# css元素溢出 #
- 当子元素的尺寸超过父元素的尺寸时，需要设置父元素显示溢出的子元素的方式，设置的方法是通过overflow属性来设置。

- overflow的设置项： 
1. visible 默认值。内容不会被修剪，会呈现在元素框之外。
2. hidden 内容会被修剪，并且其余内容是不可见的，此属性还有清除浮动、清除margin-top塌陷的功能。
3. scroll 内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。
4. auto 如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。
5. inherit 规定应该从父元素继承 overflow 属性的值。

# 块元素、内联元素、内联块元素 #
## 块元素（实际开发中使用较多） ## 
- 块元素，也可以称为行元素，布局中常用的标签如：div、p、ul、li、h1~h6、dl、dt、dd等等都是块元素，它在布局中的行为：

  - 支持全部的样式
  - 如果没有设置宽度，默认的宽度为父级宽度100%
  - 盒子占据一行、即使设置了宽度

## 内联元素 ##
- 内联元素，也可以称为行内元素，布局中常用的标签如：a、span、em、b、strong、i等等都是内联元素，它们在布局中的行为：

  - 支持部分样式（不支持宽、高、margin上下、padding上下）
  - 宽高由内容决定
  - 盒子并在一行
  - 代码换行，盒子之间会产生间距
  - 子元素是内联元素，父元素可以用text-align属性 设置子元素水平对齐方式，用line-height属性值设置垂直对齐方式
- 解决内联元素间隙的方法 
1. 去掉内联元素之间的换行
2. 将内联元素的父级设置font-size为0，内联元素自身再设置font-size(实际开发中使用该种方法)

## 内联块元素（集合了块元素和内联元素的优点） ##
- 内联块元素，也叫行内块元素，是新增的元素类型，现有元素没有归于此类别的，img和input元素的行为类似这种元素，但是也归类于内联元素，我们可以用display属性将块元素或者内联元素转化成这种元素。它们在布局中表现的行为：

  - 支持全部样式
  - 如果没有设置宽高，宽高由内容决定
  - 盒子并在一行
  - 代码换行，盒子会产生间距
  - 子元素是内联块元素，父元素可以用text-align属性设置子元素水平对齐方式，用line-height属性值设置子元素垂直对齐方式
这三种元素，可以通过display属性来相互转化，不过实际开发中，块元素用得比较多，所以我们经常把内联元素转化为块元素，少量转化为内联块，而要使用内联元素时，直接使用内联元素，而不用块元素转化了。

- display属性
- display属性是用来设置元素的类型及隐藏的，常用的属性有：
1. none 元素隐藏且不占位置
2. block 元素以块元素显示
3. inline 元素以内联元素显示
4. inline-block 元素以内联块元素显示

# 浮动 #
## 浮动特性 ##
1. 浮动元素有左浮动(float:left)和右浮动(float:right)两种

2. 浮动的元素会向左或向右浮动，碰到父元素边界、浮动元素、未浮动的元素才停下来

3. 相邻浮动的块元素可以并在一行，超出父级宽度就换行

4. 浮动让行内元素或块元素自动转化为行内块元素

5. 浮动元素后面没有浮动的元素会占据浮动元素的位置，没有浮动的元素内的文字会避开浮动的元素，形成文字饶图的效果

6. 父元素内整体浮动的元素无法撑开父元素（父元素没有给定高度），需要清除浮动

7. 浮动元素之间没有垂直margin的合并

## 清除浮动 ##

- 父级上增加属性overflow：hidden（不用定位的话的情况下使用）
- 在最后一个子元素的后面加一个空的div，给它样式属性 clear:both（不推荐使用）
- 使用成熟的清浮动样式类，clearfix（项目中经常使用的方法）（效果同第二种）

```html
.clearfix:after,.clearfix:before{ content: "";display: table;}
.clearfix:after{ clear:both;}
.clearfix{zoom:1;}（zoom是IE浏览器所特有的特性）
```
- 清除浮动的使用方法：

```html
.con2{... overflow:hidden}
或者
<div class="con2 clearfix">（推荐使用的方法）
```
# 定位 #

## 关于定位 ## 
- 我们可以使用css的position属性来设置元素的定位类型，postion的设置项如下：

- relative 生成相对定位元素，元素所占据的文档流的位置不变，元素本身相对文档流的位置进行偏移
- absolute 生成绝对定位元素，元素脱离文档流，不占据文档流的位置，可以理解为漂浮在文档流的上方，相对于上一个设置了相对或者绝对或者固定定位的父级元素来进行定位，如果找不到，则相对于body元素进行定位。
- fixed 生成固定定位元素，元素脱离文档流，不占据文档流的位置，可以理解为漂浮在文档流的上方，相对于浏览器窗口进行定位。
- static 默认值，没有定位，元素出现在正常的文档流中，相当于取消定位属性或者不设置定位属性
- inherit 从父元素继承 position 属性的值(比较少见)
## 定位元素特性 ## 
绝对定位和固定定位的块元素和行内元素会自动转化为行内块元素

## 定位元素层级 ## 
- 定位元素是浮动的正常的文档流之上的，可以用z-index属性来设置元素的层级

## 典型定位布局 ## 
1. 固定在顶部的菜单
2. 水平垂直居中的弹框
3. 固定的侧边的工具栏
4. 固定在底部的按钮

# background属性 #

## 属性解释 ## 
- background属性是css中应用比较多，且比较重要的一个属性，它是负责给盒子设置背景图片和背景颜色的，background是一个复合属性，它可以分解成如下几个设置项：

- background-color 设置背景颜色
- background-image 设置背景图片地址
- background-repeat 设置背景图片如何重复平铺
- background-position 设置背景图片的位置
- background-attachment 设置背景图片是固定还是随着页面滚动条滚动
- 实际应用中，我们可以用background属性将上面所有的设置项放在一起，而且也建议这么做，这样做性能更高，而且兼容性更好，比如：“background: #00FF00 url(bgimage.gif) no-repeat left center fixed”，这里面的“#00ff00”是设置background-color；“url(bgimage.gif)”是设置background-image；“no-repeat”是设置background-repeat；“left center”是设置background-position；“fixed”是设置background-attachment，各个设置项用空格隔开，有的设置项不写也是可以的，它会使用默认值。