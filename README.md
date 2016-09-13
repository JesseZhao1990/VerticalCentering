## css垂直居中的几个方法的总结
在实际的开发中，垂直居中一个元素一直以来都不是那么好搞定。今天总结7种常用的方法

### 1. 针对单行文本可以用line-height
当height的值和line-height的值相等时。文本就居中了（仅仅适用于单行文本）
	 
**html**
``` 
<div id="parent">
	<div id="child">
		Line-Height Method For Vertical Centering With CSS
	</div>
</div>
```  
**css**
```
#parent{
	height: 200px;     
	border:1px solid #000;   //不是必须，仅仅是为了演示
}
#child{
	line-height: 200px;
}
```

### 2. 设置display为table的方法
把父元素的display设置为table。子元素的display设置为table-cell
	 
**html**
``` 
<div id="parent">
	<div id="child">
		table Method For Vertical Centering With CSS
	</div>
</div>
```  
**css**
```
#parent {
		display: table;
		border:1px solid #000;
		height: 500px;
	}
#child {
	display: table-cell;
	vertical-align: middle;
}
```  
### 3. 绝对定位和负边距
利用绝对定位先向下移动父元素高度的50%。再利用负边距往上移动自身高度的50%
	 
**html**
``` 
<div id="parent">
	<div id="child">
		Vertical Centering With CSS
	</div>
</div>
```  
**css**
```
#parent {
	position: relative;
	height: 500px;
	border:1px solid #000;
}
#child {
	position: absolute;
	top: 50%;
	height: 30%;
	margin-top: -15%;
}
```  
### 4. 绝对定位和拉伸元素
子元素利用绝对定位同时设置top和bottom充满父元素。然后再设置height
	 
**html**
``` 
<div id="parent">
	<div id="child">
		Vertical Centering With CSS
	</div>
</div>
```  
**css**
```
#parent {position: relative;}

#child {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    width: 50%;
    height: 30%;
    margin: auto;
}
```      
### 5. 设置相等的上边内边距
设置相等的上边内边距
	 
**html**
``` 
<div id="parent">
	<div id="child">
		Vertical Centering With CSS
	</div>
</div>
```  
**css**
```
#parent {
    padding: 5% 0;
}

#child {
    padding: 10% 0;
}
```      
### 6. 浮动的方法
让floater浮动。占据父元素的一半高，然后清除浮动。然后让floater的下边距为负的子元素的高度的一半
	 
**html**
``` 
<div id="parent">
    <div id="floater"></div>
    <div id="child">Vertical Centering With CSS</div>
</div>
```  
**css**
```
#parent {height: 250px;}

#floater {
    float: left;
    height: 50%;
    width: 100%;
    margin-bottom: -50px;
}

#child {
    clear: both;
    height: 100px;
}
```    
### 7. flex box
利用弹性盒[详情](http://www.w3cplus.com/css3/a-guide-to-flexbox.html)
	 
**html**
``` 
<div id="parent">
    <div id="child">Vertical Centering With CSS</div>
</div>
```  
**css**
```
#parent {height: 250px;}
#child {
   
}
```    

