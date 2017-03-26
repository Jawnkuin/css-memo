CSS与文档
========
元素
---
>**替换元素与非替换元素**   

**替换元素**元素内容会被替换 eg:   

        <img src=""/>
   
**非替换元素**使用原有元素内容 eg:  

        <div>balabala</div>  
>**块级元素和行内元素**

**块级元素**前后分隔符eg:  
    
        <div>  <p>        
**行内元素**前后无分隔符eg:

        <strong><em>
inline or block can be changed by   

        display:inline|block;

CSS与HTML
---
>**link**  

media 属性 用于不同媒体

Specify the target medium from a style sheet with the @media or @import at-rules.
```css
@import url("fancyfonts.css") screen;
@media print {
  /* style sheet for print goes here */
}
```

>**候选样式**   

        <link rel="stylesheet" type="text/css" href="sheet1.css" title="Theme1"/>
        <link rel="alternate stylesheet" type="text/css" href="sheet2.css" title="Theme2"/>

>**@import指令**

        @import "sheet1.css"
        @import url(sheet1.css)   
        与link效果相似但是可以在style容器中```<style></style>```使用
 
>**css注释**

```/* */```
但不能嵌套
```/*  /*  */ */```

>**内联样式**

HTML元素中style属性

