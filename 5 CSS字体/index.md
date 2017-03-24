字体
===

>**字体系列**

Serif字体：宽度成比例，上下有短线

Sans-serif: 成比例，无短线

Monospace: 不成比例，用于老式打印

```{font-family: sans-serif;}```
指定字体时候，最好设置备用通用字体```{font-family: Arial, sans-serif;}```

字体名称中包含空格&等特殊字符在值上面需要引号

>**字体加粗**

font-weight

normal bold bolder lighter 100 200 ... 900 inherit

>**字体大小**

font-size

medium small 或者 长度单位 以及 百分比单位

>**风格和变形**

font-style

italic oblique normal inherit


>**字体变形**

font-variant

small-caps(小型的大写字母) normal inherit

>**行高与顺序**

font中font-size和font-family必须且顺序不变
如果需要行高```h2 {font: bold 200px/1.2 sans-serif}```

>**font-face规则**

```@font-face {font-family:"Monospace"; src: url(http://sss)}```