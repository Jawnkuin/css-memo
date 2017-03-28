浮动和定位
===

>**浮动**

浮动图像会让其他文本包裹
```
<div style="width:100px">
Lorem ipsum dolor
<img
    src='a.png'
    style="float:left"
/>
sit amet Lorem ipsum dolor sit amet
</div>
```
<div style="width:100px">
Lorem ipsum dolor
<img
    src='a.png'
    style="float:left;"
/>
sit amet Lorem ipsum dolor sit amet
</div>

浮动元素会从正常的文档流中删除,

浮动元素的包含块是其最近的块级祖先元素

浮动元素会生成一个块级框,无论这个元素本身是什么

浮动规则
---

浮动元素的左(右)外边界不能超出其包含块的左(右)内边界(padding)

同一方向浮动的元素不会重叠

不同方向的浮动元素也不会重叠

浮动元素的顶端不能比其父元素的内顶端更高,如果
在两个合并外边距之间,不会上浮到顶端

浮动元素顶端不能比之前所有的浮动元素或者块级元素高

浮动元素顶端不能比之前元素的行框高

左浮动元素左边有其他浮动元素,如果宽度不够会换行,还不够会超出包含块边界
(右浮动元素同理)

在以上所有条件下,浮动元素尽量放置得高一些,左浮动元素尽量左,右浮动元素尽量右

浮动元素外边距不合并

```
<div style="width:150px;height:150px;border:1px solid">
<div style="border:#669966 1px solid;width:50px;height:50px;float:left">
1
</div>
<div style="border:#669966 1px solid;width:110px;height:50px;float:left">
2
</div>
<div style="border:#669966 1px solid;width:20px;height:50px;float:right">
3
</div>
</div>
```
2和3都不能比1高, 3不能比2高

<div style="width:150px;height:150px;border:1px solid">
<div style="border:#669966 1px solid;width:50px;height:50px;float:left">
1
</div>
<div style="border:#669966 1px solid;width:110px;height:50px;float:left">
2
</div>
<div style="border:#669966 1px solid;width:20px;height:50px;float:right">
3
</div>
</div>

浮动元素的包含块高度未设定情况下:

包含块不浮动:```height=0```

包含块浮动:高度包含子浮动元素

负外边距可以使浮动元素出包含块内容区

>**浮动元素,内容和重叠**
