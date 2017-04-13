# CSRF、停止事件冒泡、阻止事件默认行为

标签（空格分隔）： JS

---

#CSRF
[浅谈CSRF攻击方式][1]

- 下图简单阐述了CSRF攻击的思想：
![此处输入图片的描述][2]
>从上图可以看出，要完成一次CSRF攻击，受害者必须依次完成两个步骤：
　　1.登录受信任网站A，并在本地生成Cookie。
　　2.在不登出A的情况下，访问危险网站B。

##[JavaScript 事件模型 事件处理机制][3]
#停止事件冒泡
>停止事件冒泡是指，停止冒泡型事件的进一步传递（取消事件传递,不只是停止IE和DOM标准共有的冒泡型事件，我们还可以停止支持DOM标准浏览器的捕捉型事件，用topPropagation()方法）。例如上图中的冒泡型事件传递中，在body处理停止事件传递后，位于上层的document的事件监听器就不再收到通知，不再被处理。

- 在IE下,通过设置event对象的cancelBubble为true即可。
```
 function someHandle() {
   window.event.cancelBubble = true;
 }
```
- DOM标准通过调用event对象的stopPropagation()方法即可。
```
function someHandle(event) {
   event.stopPropagation();
}
```
- 因此，跨浏览器的停止事件传递的方法是:
```
function someHandle(event) {
   event = event || window.event;
   if(event.stopPropagation){
     event.stopPropagation();
   }else {
     event.cancelBubble = true;
   }
 }
```
#阻止事件的默认行为
>停止事件的默认行为是指，通常浏览器在事件传递并处理完后会执行与该事件关联的默认动作（如果存在这样的动作）。例如，如果表单中input type 属性是 “submit”，点击后在事件传播完浏览器就自动提交表单。又例如，input 元素的 keydown 事件发生并处理后，浏览器默认会将用户键入的字符自动追加到 input 元素的值中。

- 在IE下,通过设置event对象的returnValue为false即可。

```
 function someHandle() {
   window.event.returnValue = false;
 }
```
 
- DOM标准通过调用event对象的preventDefault()方法即可。
```
 function someHandle(event) {
   event.preventDefault();
 }
```
- 因此，跨浏览器的取消事件传递后的默认处理方法是：
```
 function someHandle(event) {
   event = event || window.event;
   if(event.preventDefault){
     event.preventDefault();
   }else{
     event.returnValue = false;
   }
 }
```


  [1]: http://www.cnblogs.com/hyddd/archive/2009/04/09/1432744.html
  [2]: http://pic002.cnblogs.com/img/hyddd/200904/2009040916453171.jpg
  [3]: http://blog.csdn.net/chenmoquan/article/details/10162477