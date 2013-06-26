Intro
=====
**TsCSS.css** is a CSS Lib for CSS3 transition feature in a unique thinking.
Using `javascript` is a recommended strategy to work with.

**TsCSS.css** 是一個CSS Lib，以一種獨特的方式來使用CSS3的transition特性。透過 `javascript` 搭配操作可以獲得最大效果。

Concept
=======
As we know , it is possible to put muti css selectors in DOM class attribute , like :

正如我們所知道的，在DOM元素的class屬性內，同時指派多個樣式選擇器是被允許的 , 如下 :
```html
<div class='bold light small'></div>
```
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

License
=======
Copyright 2013 Vesic.D

Licensed under the Apache License, Version 2.0.

ToDo
=====
Demo pages:
- `Slide-down menu`
- `FadeIn/fadeOut effect`
- `Tasteful options`

