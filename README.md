Table of Contents
=================

Introdution
===========
**TsCSS.css** is a CSS Lib for CSS3 transition feature in a unique thinking.
Using `javascript` is a recommended strategy to work with.

**TsCSS.css** 是一個CSS Lib，以一種獨特的方式來使用CSS3的transition特性。透過 `javascript` 搭配操作可以獲得最大效果。

Concept 1
=========
As we know , it is possible to put muti css selectors in DOM class attribute , like :

正如我們所知道的，在DOM元素的class屬性內，同時指派多個樣式選擇器是被允許的 , 如下 :
```html
<div class='bold light small'></div>
```

Concept 2
=========
CSS3 attribute `transition` provide a way which can a  designer do transition animation via four parameters:
- `properties` Numerical Variables in css(width , height , border , ...etc)
- `duration`  Time during transition (in seconds)
- `timing-function` transition timing function... ( Default "ease" )
- `delay` delay (in seconds)

CSS3的 `transition` 屬性，可讓設計者操作轉場動畫，該屬性具備四個參數 : 
- `properties` 允許的值為可量化的css屬性(width , height , border , ...etc)
- `duration`  轉場總時間
- `timing-function` 時間變化函數 ( Default "ease" )
- `delay` 延遲若干秒後才開使動作

Usually, we perform like below:

以往，我們可能以如下的方式使用這個特性：

```css
.myStyle{
  transition-property : width;
  transition-duration : 1;
  transition-timing-function : ease;
  transition-delay : 0;
  width : 50px;
  height:30px;
}

.myStyle:hover{
  width : 100px;
}
```
```html
  <div class="myStyle"></div>
```

Combination
===========
so us cut **transition attributes** parameters into difference **class selectors** :

我們將 **transition attributes**的參數分別以不同的 **樣式選擇器** 設置:

**CSS code**
```css
.Ts{
  transition-property:none;
  transition-duration:0.3s;
  transition-timing-function: linear;
}

.Ts_scale{
  transition-property : width,height;
}

```
接下來，我們看一下簡單的範例：

Now, Let's take a look ,example below:

```css
.myDemo{
  	  background-color:rgb(0,0,60);
		  font-size:13px;
		  color:#f33;
		  width:50px;
		  height:30px;
		  opacity:0.5;
		  cursor:pointer;
		  text-align:center;
		  font-weight:bold;
		}
.myDemo.ch_width{
  width:100px;
}
.myDemo.ch_height{
  height:60px;
}

```

**HTML code**
```html
<div class='myDemo Ts Ts_scale'></div>
```

**Javascript code**
```javascript
(function(document){
    var dir = 0;
    var myDemo = document.getElementsByClassName("myDemo")[0];
    var ch = function(type){
      var T=type;
    	return function(el){
    		var nowClass= el.className;
    		var RX = new RegExp(T);
    		if(RX.test(nowClass)){
    			el.className = el.className.replace(T,"");
    		}else{
    			el.className = el.className + " " + T;
    		}	
    		nowClass = null;RX = null;
    	}
    }
    var ch_width = ch("ch_width");
    var ch_height = ch("ch_height");
    
    myDemo.addEventListener("click",function(e){
    	if(dir > 1){dir = 0;}
    	switch(dir){
    		case 0:
    			ch_height(myDemo);
    		break;
    		default:
    			ch_width(myDemo);
    		break;
    	}		  	
      	dir ++;
    },false);  
})(documnt);
```
**See Demo**
[myDemo](http://codepen.io/anon/pen/eGfJA)<br>
License
=======
Copyright 2013 Vesic.D

Licensed under the Apache License, Version 2.0.



