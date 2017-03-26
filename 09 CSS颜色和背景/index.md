颜色和背景
===


>**颜色**

分背景色background-color和前景色color

前景色一般可继承,背景色不继承

>**背景**

背景图片通过

```background-repeat```重复:

repeat(default),repeat-x,repeat-y,no-repeat,inherit

```background-position```定位:

[&lt;percentage&gt;|&lt;length&gt;|left|right|center]

default (0% 0%)

指定一个关键字,另一个默认```center```

```background-attachment```关联:

(default) scroll | fixed

fixed可以固定不随着内容上下滚动

一旦是fixed,背景图片会从视窗左上角平铺而不是单个元素左上角


```css
div{
    background-image: url(image.png);
    background-repeat: no-repeat;
    background-position: center;
    background-attachment: fixed;
}
```
