# 原生JS实现addClass,removeClass,toggleClass

标签（空格分隔）： 未分类

---

## [原生JS实现addClass,removeClass,toggleClass][1]

>jQuery操作class的方式非常强大，但是目前还有一些人不知道如何使用或者由于项目统一性的原因无法使用jquery.
在此写了一个利用原生js来实现对dom元素class的操作方法
1.addClass:为指定的dom元素添加样式
2.removeClass:删除指定dom元素的样式
3.toggleClass:如果存在(不存在)，就删除(添加)一个样式
4.hasClass:判断样式是否存在

```
<style type="text/css">  
    div.testClass{  
        background-color:gray;  
    }  
</style>  
  
<script type="text/javascript">  
function hasClass(obj, cls) {  
    return obj.className.match(new RegExp('(\\s|^)' + cls + '(\\s|$)'));  
}  
  
function addClass(obj, cls) {  
    if (!this.hasClass(obj, cls)) obj.className += " " + cls;  
}  
  
function removeClass(obj, cls) {  
    if (hasClass(obj, cls)) {  
        var reg = new RegExp('(\\s|^)' + cls + '(\\s|$)');  
        obj.className = obj.className.replace(reg, ' ');  
    }  
}  
  
function toggleClass(obj,cls){  
    if(hasClass(obj,cls)){  
        removeClass(obj, cls);  
    }else{  
        addClass(obj, cls);  
    }  
}  
  
function toggleClassTest(){  
    var obj = document. getElementById('test');  
    toggleClass(obj,"testClass");  
}  
</script>  
  
<body>  
    <div id = "test" style = "width:250px;height:100px;">  
        sssssssssssss  
    </div>  
    <input type = "button" value = "toggleClassTest" onclick = "toggleClassTest();" />  
</body>  
```


  [1]: http://blog.csdn.net/lowkeysk/article/details/8063816