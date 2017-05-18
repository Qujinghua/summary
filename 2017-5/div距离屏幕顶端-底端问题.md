# div距离屏幕顶端/底端问题

标签（空格分隔）： JS

---
- 文档窗口高度
```
$(window).height();//是文档窗口高度
```

---

- 标签距离顶部高度
```
$("div").offset().top//是标签距离顶部高度
```

---

- 滚动条高度
```
$(document).scrollTop();//是滚动条高度
```

---

- 标签高度
```
$("div").height();//是标签高度
```

---

- 标签距离底部高度
```
$(window).height()-$("div").height()-[$("div").offset().top-$(document).scrollTop()]
```




