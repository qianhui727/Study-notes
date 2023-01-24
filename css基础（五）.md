## 13 网络布局总结

通过盒子模型，清楚知道大部分html标签是一个盒子。

通过CSS浮动、定位可以让每个盒子排列成为网页。

一个完整的网页，是标准流、浮动、定位一起完成布局的，每个都有自己的专门用法。

1.标准流

可以让盒子上下排列或者左右排列，**垂直的块级盒子品示就用标准流布局**。

2.浮动

可以让多个块级元素一行品示或者左右对齐盒子，**多个块级盒子水平显示就用浮动布局**。

3.定位

定位最大的特点是有层叠的概念 ，就是可以上多个盒子前后叠压来展示。**如果元素自由在其个盒子內移动就用定位布局。**



## 14 .元素的显示与隐藏

网站广告，当我们点击关闭就不见了，但是我们重新刷新页面，会重新出现

**本质：让一个元素在页面中隐藏或者显示出来，隐藏不等于消失**

1）display			    显示隐藏

2）visibility 		 	显示隐藏

3）overflow			 溢出显示隐藏



#### 14.1 display 属性

display 属性用于设置一个元素应如何显示

1）display: none；			隐藏对象

2）display: block；			除了转换为块级元素之外，同时还有显示元素的意思

**display 隐藏元素后，不再占有原来的位置，后面的标准流会占用其位置**



#### 14.2 visibility 可见性

visibility 属性用于指定一个元素应可见还是隐藏。
1）visibility: visible;		 元素可视

2）visibility: hidden;		元素隐藏

**visibility 隐藏元素后，继续占有原来的位置，后面的标准流不会占用其位置**

**注意：**

如果隐藏元素想要原来位置，就用 visibility: hidden;

如果隐藏元素不想要原来位置，就用 display: none;



#### 14.3 overflow 溢出

overflow 属性指定了如果内容溢出一个元素的框（超过其指定高度及完度）时，会发生什么。

属性值								描述

visible							 不剪切内容也不添加滚动条

hidden							不显示超过对象尺寸的内容，超出的部分隐藏掉

scroll							   不管是否超出内容，总是显示滚动条

auto								 超出自动显示滚动条，不超出不显示滚动条

一般情况下 ，我们都不想让溢出的内容显示出来，因为溢出的部分会影响布局。

但是如果有定位的盒子，请慎用 overflow. hidden因为它会隐藏多余的部分。



## 15. CSS 高级技巧



#### 15.1 精灵图

**精灵圈（sprites）的使用**

第一步：先摆放小盒子

第二步：移动精灵图，是目标图片放在小盒子里

**核心：**

1）精灵技术主要针对于背景图片使用。就是把多个小背景图片整合到一张大图片中。

2）这个大图片也称为 sprites 精灵图 或者 雪碧图

3）移动背景图片位置，此时可以使用 background-position。

4）移动的距离就是这个日标图片的x和 y 坐标。注意网页中的坐标有所不同

5）因为一般情况下都是往上往左移动，所以数值是负值。

6）使用精灵图的时候需要精确测量 ，每个小背景图片的大小和位置。

**使用精灵图核心总结：**

1）精灵图主要针对于小的背景图片使用。

2）主要借助于背景位置来实现  background-position。

3）一般情况下精灵图都是负值。



#### 15.2 CSS三角

三网页中常见一些一角形，使用 CSS直接面出来就可以，不必做成图片或者字体图标

```css
div {
	width: 0;
	height: 0;
	border: 500px solid transparent;  500px为三角的大小
	border-left-color: red;  想要哪个三角，就给那一边添加颜色
}
```



## 16.CSS 用户界面样式



#### 16.1 鼠标样式 cursor

```css
li {
    cursor: pointer; 
}
```

设置或检索在对象上移动的鼠标指针采用那种系统预定义的光标形状。

属性值							描述

default						小白 默认

pointer							小手

move					 		  移动

text							  	文本

not-allowed			   	 禁止



#### 16.2 轮廓线 outline

给表单添加 outline: 0，或者 outline: none;样式之后，就可以去掉默认的蓝色边框。

```css
input {
    outline: none;
}
```



#### 16.3 防止拖拽文本域 resize

实际开发中 ，我们文本域石下角是不可以拖搜的。

```css
textarea {
    resize: none;
}
```

**文本域需要一行书写，不然会出现空格**



## 17. vertical-align 属性应用



#### 17.1 图片、表单和文字对齐

图片、表单都属于行内块元素，默认的 vertical-align 是基线对齐。

此时可以给图片、表单这些行内块元素的 vertical-align 属性设置为 middle 就可以让文字和图片垂直

居中对齐了。

**注意：给图片添加**

```css
vertical-align : baseline | top | middle | bottom;
				基线		  顶线    中线		底线
```



#### 17.2 解决图片底部默认空白缝隙问题

bug：图片底侧会有一个空白缝除，**原因是行内块元素会和文字的基线对齐。**

主要解决方法有两种：

1）给图片添加 vertical-align : baseline | top | middle | bottom; 等。（提倡使用的）

2）把图片转换为块级元素 display: block;



## 18. 溢出的文字省略号显示



#### 18.1 单行文本溢出显示省略号--必须满足三个条件

**三部曲：**

1）先强制一行内显示文本

white-space: nowrap;（默认 normal 自动换行)

2）超出的部分隐藏

overflow: hidden;

3）文字用省略号替代超出的部分

text-overflow : ellipsis;

```css
div {
	width: 150px;
	height: 80px;
	background-color: red;
	margin: 100px auto;
    
	white-space: nowrap;
	overflow: hidden;
	text-overflow: ellipsis;
}

<div>
	一处的文字省略号显示
</div>
```



#### 18.2 多行文本溢出显示省略号（仅作了解）

多行文本溢出显示省略号 ，有较大兼容性问题，适命于webkit浏览铅成移动端 移动端大部分是webkit内
核）

```css
overflow: hidden;
text-overflow: ellipsis;
display: -webkit-box;				弹性伸缩盒子模型显示
-webkit-1ine-clamp:2;				限制在一个块元素显示的文本的行数
-webkit-box-orient: vertical;		设置或检索伸缩盒对象的子元素的排列方式
```







