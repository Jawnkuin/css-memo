基本视觉格式化
===

>**包含块**

由最近的块级祖先框、表单元或行内块祖先框的内容边界构成

>**块级元素**

水平格式化
---

width影响的是内容区宽度，而不是整个可见的元素框,```行内非替换元素忽略这个属性```

```HTML
<div style="width:300px;height:200px">
<p style="width:200px;border:1px solid">Lorem</p>
<p style="width:200px;padding:10px;border:1px solid">Lorem</p>
<p style="width:200px;padding:10px;margin:20px;border:1px solid">Lorem</p>
</div>
```
<div style="width:300px;height:200px">
<p style="width:200px;border:1px solid">Lorem</p>
<p style="width:200px;padding:10px;border:1px solid">Lorem</p>
<p style="width:200px;padding:10px;margin:20px;border:1px solid">Lorem</p>
</div>

水平七个属性
---

margin-left/right,border-left/right,padding-left/right以及width

7个值之和为包含块的宽度，通常也是父元素的width值

只有margin-left/right和width可以设置为```auto```,其中width非负,其余必须设置为特定值或者默认0

margin-left\margin-right\width中仅有某一个为```auto```，而其它为特定值，

那么设为```auto```的属性会确定所需长度，使得元素框宽度等于父元素的width

设置好margin-left/right可以获得自动宽度，如果相等就是居中

如果三个属性都设置为确定值那么margin-right自动设置为auto(根据语言从左向右还是从右向左)
```HTML
<div style="width:400px;height:200px;background:#669966">
<p style="width:100px;margin-left:100px;margin-right:100px;border:1px solid">Lorem</p>
<p style="width:100px;margin-left:100px;margin-right:auto;border:1px solid">Lorem</p>
<p style="width:auto;margin-left:100px;margin-right:100px;border:1px solid">Lorem</p>
<p style="width:auto;margin-left:auto;margin-right:auto;border:1px solid">Lorem</p>
<p style="width:100px;margin-left:auto;margin-right:auto;border:1px solid">Lorem</p>
<p style="width:auto;margin-left:auto;margin-right:100px;border:1px solid">Lorem</p>
</div>
```

<div style="width:400px;height:300px;background:#669966">
<p style="width:100px;margin-left:100px;margin-right:100px;border:1px solid">Lorem</p>
<p style="width:100px;margin-left:100px;margin-right:auto;border:1px solid">Lorem</p>
<p style="width:auto;margin-left:100px;margin-right:100px;border:1px solid">Lorem</p>
<p style="width:auto;margin-left:auto;margin-right:auto;border:1px solid">Lorem</p>
<p style="width:100px;margin-left:auto;margin-right:auto;border:1px solid">Lorem</p>
<p style="width:auto;margin-left:auto;margin-right:100px;border:1px solid">Lorem</p>
</div>

负外边距
---
同样遵守七个属性值和为父组件的width值
```HTML
<div style="width:400px;height:100px;background:#669966">
<p style="width:auto;margin-left:-20px;margin-right:-20px;border:1px solid">Lorem</p>
<p style="width:100px;margin-left:auto;margin-right:-20px;border:1px solid">Lorem</p>
</div>

```

<div style="width:400px;height:100px;background:#669966">
<p style="width:auto;margin-left:-20px;margin-right:-20px;border:1px solid">Lorem</p>
<p style="width:100px;margin-left:auto;margin-right:-20px;border:1px solid">Lorem</p>
</div>



>**替换元素**

替换块元素
---

块级元素所有规则依然适用于替换块元素，除当```width="auto"```的时候，宽度为内容固有宽度。

如果设定宽度不等于固有宽度，元素```height```会成比例变化，除非同时设定```height```。

反过来```height="auto"```同样的道理

>**垂直格式化**

高度由其内容决定，还会受到内容宽度的影响，段落越窄高度越高以便容纳所有内联内容,如果高度不够可能会增加一个滚动条
```HTML
<div style="width:400px;height:150px;background:#669966">
<p style="height:4em;margin-left:20px;margin-right:20px;border:1px solid">Lorem</p>
<p style="margin-left:150px;margin-right:150px;height:1em;border:1px solid">Lorem ipsum dolor sit amet</p>
</div>
```

<div style="width:400px;height:150px;background:#669966">
<p style="height:4em;margin-left:20px;margin-right:20px;border:1px solid">Lorem</p>
<p style="margin-left:150px;margin-right:150px;height:1em;border:1px solid">Lorem ipsum dolor sit amet</p>
</div>

>**垂直属性**

margin-top/bottom,padding-top/bottom,border-top/bottom,height

```垂直的margin-top和margin-bottom对行内非替换元素无作用。```

七个属性和值为包含块内容高度，通常是父元素的height属性

margin-top/bottom和height可设为```auto```，其余设置为特定值或者默认```0```。

正常流中，快元素的margin-top或者margin-bottom设置为auto，会自动计算为0，就没有垂直上居中的效果

```HTML
<div style="width:400px;height:50px;background:#669966">
<p style="margin-top:auto;margin-bottom:auto;margin-left:20px;margin-right:20px;border:1px solid">Lorem</p>
</div>
```
<div style="width:400px;height:50px;background:#669966">
<p style="margin-top:auto;margin-bottom:auto;margin-left:20px;margin-right:20px;border:1px solid">Lorem</p>
</div>

百分数值
---
The percentage is calculated with respect to the ```width``` of the generated box's containing block.

Note that this is true for 'margin-top' and 'margin-bottom' as well.

But percentage value for ```height``` is still calculated with respect to the containing block ```height```

```HTML
<div style="width:400px;height:50px;background:#669966;position:absolute">
<p style="margin-top:25%;height:100%;margin-left:20px;margin-right:20px;border:1px solid">Lorem</p>
</div>
```
<div style="width:400px;height:50px;background:#669966;position:absolute">
<p style="margin-top:10%;height:100%;margin-left:20px;margin-right:20px;border:1px solid">Lorem</p>
</div>

</br>
</br>
</br>
</br>
</br>


auto高度
--- 
如果正常流元素设置height:auto，显示时其高度将恰好足以包含其内联内容(包括文本)的行盒。

高度为auto时，会在段落上设置一个边框，并认为没有内边距

如果只有块级子元素，高度为最高的子元素上外边距到最低下外边距的距离```width=H(margautoin_top_max-margin_bottom_min)```

<div style="width:400px;height:auto;background:#669966">
<p style="margin-top:2em;margin-bottom:2em;margin-left:20px;margin-right:20px;border:1px solid">Lorem</p>
</div>


合并垂直外边距
---
垂直相邻元素合并

*horizontal margins never collapse

上下```li```之间的距离是```2em```而不是```1em+2em```
```
<style>
.collapse {width:400px;height:auto;background:#669966}
.collapse li{margin-top: 1em; margin-bottom: 2em;border:1px solid;width:200px;}
</style>
<div class="collapse">
<ul>
<li>
Lorem ipsum
</li>
<li>
Lorem ipsum
</li>
<li>
Lorem ipsum
</li>
</ul>
</div>
```

<style>
.collapse {width:400px;height:auto;background:#669966}
.collapse li{margin-top: 1em; margin-bottom: 2em;border:1px solid;width:200px;}
.collapse p{margin-top: 1em; margin-bottom: 2em;border:1px solid;width:200px;}
</style>
<div class="collapse">
<li>
Lorem ipsum
</li>
<p>Lorem ipsum</p>
<li>
Lorem ipsum
</li>
<li>
Lorem ipsum
</li>
</div>


垂直负外边距
---

两个都为负值取绝对值最大值,一个正一个负从正值减去负值

负值会影响同一父元素下面的兄弟元素，比如向外侧移动
```
<style>
.collapse2 {width:400px;height:auto;background:#669966}
.collapse2 li{margin-top: 0; margin-bottom: -0.1em;border:1px solid;width:200px;}
.collapse2 p{margin-top: -0.5em; margin-bottom: 0;border:1px solid;width:200px;}
</style>
<div class="collapse2">
<li>
Lorem
</li>
<p>ipsum</p>
</div>
```

<style>
.collapse2 {width:400px;height:auto;background:#669966}
.collapse2 li{margin-top: 0; margin-bottom: -0.1em;border:1px solid;width:200px;}
.collapse2 p{margin-top: -0.5em; margin-bottom: 0;border:1px solid;width:200px;}
</style>
<div class="collapse2">
<li>
Lorem
</li>
<p>ipsum</p>
</div>

>**列表项**

列表标志取决于list-style-position值，标志在内部即是一个块级元素，在外则是内容左边界一定距离

>**行内元素**

行布局
---

匿名文本:所有未包含在行内元素中的字符串。```<p> I'm <em>so</em> happy!</p>```中，``` I'm,happy!```是匿名文本(包含空格)

em:在font-size中定义,用来包裹字

内容区:非替换元素是em串在一起的框 替换元素是元素的固有高度再加上margin border padding

行间距:line-height - font-size 

行内框: 非替换元素==line-height 替换元素==内容区高度

行框:包含行内框的最高点和最低点


- 内容区类似一个块级元素的内容框
- 行内元素背景应用于内容区以及所有的内边距
- 行内元素的边框保卫内容区以及所有内边距和边框
- 非替换元素padding border margin不影响行框高度
- 替换元素margin和border会影响行内框高度

*行内非替换元素 padding border margin 不影响高度，width不影响宽度*

>**行内格式化**

line-height 对block元素高度没有直接影响，但是会简介影响内部的inline元素

