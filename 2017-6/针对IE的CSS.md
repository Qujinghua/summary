# 针对IE的CSS

标签（空格分隔）： 小知识

---

针对IE9的CSS只需在相应CSS代码加入只有IE9识别的 \9\0。具体代码如下：
```
.div{ background-color:#0f0\9\0;/* ie9 */ 
```
其他浏览器写法：
```
background-color:#f00;/*all*/ 
background-color:#0ff\0;/* ie 8/9 */ 
background-color:#0f0\9\0;/* ie9 */ 
*background-color:#00f;/*ie7*/ 
_background-color:#ff0;/*ie6*/ 
background-color//:#090;/*非IE*/ 
background-color:#900\9;/*所有ie*/ 
```





