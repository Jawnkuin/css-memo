内边距&边框&外边距
===

>**外边距**

百分数与外边距
---
因为文档基于流的方式
,如果margin-top之类的垂直变量以父容器高度为基数,
会导致整体渲染死循环

外边距和行内元素
---

对于只包含文本的行,能改变行间距的只有

line-height,font-size和vertical-align

所以margin-top无用.

但是margin-left/right依然可用

>**边框**

默认边框颜色是元素的前景色,如果没有设置

边框颜色,它将和元素的```color```属性一样

边框和背景
---

元素的背景会延伸到边框边界之外,因为元素在背景之上

边框也会增加元素的整体宽度

没有样式的边框会默认宽度为0
```
<style>
div.bd{
    background:#669966;
    width:100px;
    height:100px;
    margin:1px;
}
div.bd#one{
    border: 3px dashed;
}
div.bd#two{
    border: 3px;
}
</style>
<div class="bd"></div>
<div class="bd" id="one"></div>
<div class="bd" id="two"></div>
```

<style>
div.bd{
    background:#669966;
    width:100px;
    height:100px;
    margin:1px;
}
div.bd#one{
    border: 3px dashed;
}
div.bd#two{
    border: 3px;
}
</style>
<div class="bd"></div>
<div class="bd" id="one"></div>
<div class="bd" id="two"></div>

边框和行内元素
---

非替换元素边框不影响行高,可能覆盖上一行,被下一行覆盖


>**内边距**

百分数值
---

内边距如果设置百分数值,其计算同样以父元素```width```为基数

内边距和行内元素
---

替换元素:padding-top/bottom 是行高的一部分
非替换元素:padding-top/bottom 会延伸背景不改变行高



