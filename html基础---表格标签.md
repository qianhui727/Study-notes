# html基础

### 结构标签

##### 表格的基本语法

```html
<table>
    <tr>    <!--定义行-->
    <td>单元格内的文字</td>
    </tr>
</table>
```

1. <tanle></table>是用户定义表格的标签
2. <tr></tr>用于定义行
3. <td></td>用于定义表格中的单元格

##### 表头单元格标签

```html
<tr>
    <th>姓名</th>
    <th>班级</th>
</tr>
```

一般不能位于表格第一行或者第一列，加粗居中显示

##### 表格属性   （放在table中间）

属性名			属性值							描述

align				left\center\right		表格相对元素对齐方式

border			"/"或" "						是否拥有边框，默认为" ",表示无边框

cellpadding	像素值						规定单元边沿与其内容间的黑白默认像素

cellspacing	 像素值						规定单元格之间的黑白

width			  像素值或百分比		 规定表格的宽度

##### 表格结构标签

```html
<table>
    <thead>
        <tr><th>内容</th></tr>
    </thead>
    <tbody>
        <tr><td>内容</td></tr>
    </tbody>
</table>
```

<thead>表格的头部区域

<tbody>表格的主体区域

##### 合并单元格  （放在<td>标签中）

三部曲：1、先确定跨行还是跨列合并

​				2、找到目标单元格，写上合并方式=合并的单元数量

​						例如：<td colspan="2"></td>

​				3、删除多余的单元格

跨行合并：rowspan="合并单元格数量"

跨列合并：colspan="合并单元格数量"

