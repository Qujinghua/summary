# 前端开发

标签（空格分隔）： HTML&CSS

---


[前端开发面试题集锦][1]
##对Web标准的理解
1、标签闭合
2、标签小写
3、不乱嵌套
4、使用外链css和js脚本
5、结构行为表现的分离
6、文件下载与页面速度更快
7、内容能被更多的用户所访问
8、内容能被更广泛的设备所访问
9、更少的代码和组件
10、容易维护、改版方便
11、提高网站易用性；

----------

##浏览器内核差异

[不同浏览器内核差异及渲染][2]

1、Tridend内核，如果不知道Tridend，那么你一定知道微软的IE吧，没错，它就是IE的核心引擎，从IE诞生到现在一直使用的就是Tridend内核，国内的80%以上的浏览器用的都是它，只是在IE上面再次做了包装和本地化而已，如果搜搜、搜狗、360、遨游、世界之窗；其中搜狗浏览器可以使用双引擎，该引擎只在windows平台下使用。
2、Gecko内核，这个是火狐firefox御用内核，新版的火狐对其进行了内核升级，据说可以将速度提升2-5倍。
3、Webkit内核，大家知道有苹果的和google的浏览器使用的是该内核，它的优点是快速解析javascript，也是这些浏览器打广告时经常用到的口号，国产的双引擎浏览器搜狗高速浏览器就是采用了该内核。

##兼容性

[常见浏览器兼容性问题与解决方案][3]

##hack

CSS hack 由于不同厂商的浏览器，比如 IE、safari、Mozilla Firefox、Chrome 等，或者是同一厂商的浏览器的不同版本，如 IE6/7。对 CSS 的解析认识完全不一样，因此会导致生成的页面效果不一样，得不到我们所需要的页面效果。这个时候我们就需要针对不同的浏览器去写不同的 CSS，让它能够同时兼容不同的浏览器。能在不同的浏览器中也能得到我们想要的页面效果。

CSS hack 的目的是使 CSS 代码兼容不同的浏览器，利用 CSS hack 为不同版本的浏览器定制编写不同的 CSS 效果。

CSS hack 有三种表现形式：CSS 类内部 Hack、选择器 Hack、HTML 条件注释 Hack。

- CSS 类内部 Hack（属性前缀法）

例如 IE6 能识别下划线 _ 和星号 *，IE7 能识别星号 *，但不能识别下划线 _，IE6~IE10 都认识\9，但 firefox 前述三个都不能认识。

- 选择器 Hack（选择器前缀法）

例如 IE6 能识别 *html .class{}，IE7 能识别 *+html .class{} 或者 *:first-child + html .class{}。

- HTML 条件注释 Hack（IE 条件注释法)

针对所有 IE：<!–[if IE]><!–代码–><![endif]–>，针对 IE6 及以下版本：<!–[if lt IE 7]><!–代码–><![endif]–>等等，这类 Hack 不仅对 CSS 生效，对写在判断语句里面的所有代码都会生效。

在标准模式中

– 减号是 IE6 专有的 hack；
\9 IE6/IE7/IE8/IE9/IE10 都生效；
\0 IE8/IE9/IE10 都生效，是 IE8/9/10 的 hack；
\9\0 只对 IE9/IE10 生效，是 IE9/10 的 hack；
IE7可以辨别 * 和 !important。

##盒子模型

- W3C的标准Box Model（标准 W3C 盒子模型）
><外盒尺寸计算（元素空间尺寸）>
Element 空间宽度 = content width + padding + border + margin
Element 空间高度 = content height + padding + border + margin
<内盒尺寸计算（元素大小）>
Element Width = content width + padding + border（width 为内容宽度）
Element Height = content height + padding + border（height 为内容高度)

- IE传统下Box Model（IE 盒子模型）

><外盒尺寸计算（元素空间尺寸）（占据的空间）>
Element 空间宽度 = content width + margin (width 包含了元素内容宽度、边框宽度、内距宽度)
Element 空间高度 = content height + margin (height 包含了元素内容宽度、边框宽度、内距宽度)
<内盒尺寸计算（元素大小）（盒子的实际大小）>
Element Width = content width(width 包含了元素内容宽度、边框宽度、内距宽度)
Element Height = content height(height 包含了元素内容宽度、边框宽度、内距宽度)

##选择器优先级

[HTML中使用CSS][4]

>内联式 > 内嵌式 > 外部样式；
在多个样式中，后出现的样式的优先级高于先出现的样式；
在样式中，选择器的优先级：id 样式 > class 样式 > 标记样式。


  [1]: https://github.com/markyun/My-blog/tree/master/Front-end-Developer-Questions/Questions-and-Answers
  [2]: http://www.cnblogs.com/dong93/p/4668527.html
  [3]: http://blog.csdn.net/chuyuqing/article/details/37561313/
  [4]: http://www.bizhongbio.com/html-use-css.html