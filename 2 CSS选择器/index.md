选择器
======
元素选择器 类选择器 ID选择器 区分大小写

>**选择器分组和声明分组**

```h2, p {color: gray;}```
```
h2{
        color:gray;
        background: white;
}
```

>**通配选择器**

```*```任何元素

>**类选择器**

.warning.help匹配```<p class="warning help"></p>```和```<p class="warning help urgent"></p>```

但是不匹配```<p class="warning"></p>```

>**ID选择器**

ID最好保持唯一性，虽然不检查 不能多选(x #id1#id2)

>**属性选择器**

可多选 [attr1][attr2] 和类规则同
```[class]```包含该属性

```=```完整属性匹配  
```~=```包含属性  

```
span[class~=baren]{color:red;}
<span class="ca baren">balalalala</span>
<span class="baren">balalalala</span>
```

```|=```特定属性选择器具 en匹配 en-   
```
span[lang|=en]{color:red;}
<span lang="en-us">balalalala</span>
<span lang="en-au">balalalala</span>
```
>**后代选择器**  
所有后代
ul li 
td.main a:link
blockquote b, p b {}

>**子元素选择器**  
直系后代
ul>li 
td.main>a:link

>**兄弟选择器**

h1 + p
无视 ```<h1></h1> 文本 <p></p>```之间的文本


>**伪类选择器**

链接伪类 
用于a锚元素
a:visited a:link(含有href属性的)

动态伪类
:focus
:hover
:active

静态伪类
:first-child

p：first-child 表示选择第一个p元素，不是选择p的第一个子元素

>**伪元素选择器**

首字母
p:first-letter p里面的首字母而不是p本身

首行
p:first-line

之前插入并设置样式
p:before
之后插入并设置样式
p:after
