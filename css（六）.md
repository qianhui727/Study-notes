## 19. 常见的布局技巧



#### 19.1 margin负值运用

当每一个盒子都有边框的时候，添加左浮动之后，左盒子的右边框和右盒子的左边框会进行重叠，形成看起来更粗的视觉效果。为了防止此效果，我们需要进行第一步

第一步：让每个盒子margin 往左侧移动 -1px 正好压住相邻盒子边框

我们想要鼠标移动到哪个盒子，哪个盒子的边框会变颜色，但是由于右盒子的左边框盖住了左盒子有边框，所以当鼠标移到左盒子的时候，左盒子的有边框无法显示，所以需要进行第二步

第二步：鼠标经过某个盒子的时候，提高当前盒子的层级即可（如果没有定位 ，则加相对定位来保留位置，如果有定位，则加z-index）

```css.
ul li:hover {
	如果盒子没有定位，则鼠标经过添加相对定位即可，因为相对定位会压住其他的标准流盒子
	position: relative;
	border: 1px solid blue;
} 
ul li:hover {
	如果i都有定位，则利用z-index提高层级
	z-index: 1;
	border: 1px solid blue;
}
```



#### 19.2 css三角强化

用于构造不等腰三角形

```css
width: 0;
height: 0;
border-color: transparent red transparent transparent;
border-style: solid;
border-width: 22px 8px 0 0;
```

```css
width: 0;
height: 0;
把上边框宽度调大
border-top: 100px solid transparent;
border-right: 50px solid skyblue;
左边和下边的边框宽度设置为0
border-bottom: 0 solid blue;
border-left: 0 solid green;
```



## 20.CSS 初始化

不同浏览器对有些标签的默认值是不同的，为了消除不同浏览器对HTML文本呈现的差异，照顾刘览器的兼容，我们需要对css初始化

简单理解：CSS初始化是指重设浏览器的样式。（也称为CSSvreset )

每个网页都必须首先进行CSS初始化。

这里我们以 京东CSS初始化代码为例。

Unicode编码字体：

把中文字体的名称用相应的Unicode编码来代替 ，这样就可以有效的避免浏览器解释CSS代码时候出现乱码的问题。

比如：

黑体 \9ED1\4F53

宋体 \15B8B\4F53 

微软雅黑 \5FAE\8F6F\96C5\9ED1

