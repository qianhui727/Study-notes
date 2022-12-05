# html基础

### 表单标签

##### 表单域

```html
<form action="url地址" method="提交的方式" name="表单域的名称">
    各种表单元素控件
</form>
```

此处在html基础中不做研究，在前端的日后学习中将会深度学习

##### 表单控件（表单元素）

```html
<input type="属性值"/>
```

type属性值

1、hidden			定义隐藏的输入字段

2、text				定义单行输入字段，用于输入文本

3、password 	定义密码字段，字符将被掩盖

4、radio  			定义单选按钮

5、checkbox	  定义复选框

6、submit  		 定义提交按钮

7、reset 			定义重置按钮

8、button 		 定义可点击按钮

9、file   			  供文件上传

除了type外，input还有其他的属性

1.name				定义input名称

2.value				定义input值

3.checked			规定默认选中

4.maxlength		规定字符的最大长度

​		注：name和value给后台人员使用

​				单选和复选框要有向同的name值

​				checked主要用于单选和复选框

​				maxlength一般使用较少

​				name和value在每一个表单中都需要有

##### label标签

用于加强用户的体验

```html
<label for="sex">男</label>
<input type ="radio" name="sex" id="sex"/>
```

核心：label和for应当对于相同元素的id属性

##### select列表元素

用于定义下拉列表

```html
<select>
    <option>   </option>
    <option>   </option>
    <option>   </option>
</select>
```

1、select中至少含有一对option

2、option中定义select=”select“时，即表示默认选中项

##### 表单标签textarea

常用于留言板，评论，输入内容较多

```html
<textarea row="3" cols="20">
    文本内容，可写较多内容
</textarea>
```

可创建多行文本输入框

cols=”每行中的字符数“   	（实际开发是不使用，都用css改变大小）	

rows=”显示的行数“



### 结语

到此为止，html基础部分已经结束，接下来要学习css的内容，html基础中部分需要深入的内容在将来的前端学习将会得到深度学习，只有经常动手时间，才能发挥学习的最大效率。





