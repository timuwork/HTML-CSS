# 1201_gallery页面知识点

---

## 一、`javascript:;`


---
1. 如果想做一个链接点击后不做任何事情，或者响应点击而完成其他事情，可以设置其属性 `href = "#"`，但是，这样会有一个问题，就是当页面有滚动条时，点击后会返回到页面顶端，用户体验不好。
2. `href=”#”`包含了一个位置信息.默认的锚是#top,也就是网页的上端，当连续快速点击此链接时会导致浏览器巨慢甚至崩溃。
3. 因此我们通常使用`javascript:;`来代替空链接`href=”#”`，实现A标签的点击事件运行时，页面内容很多，有滚动条时，页面不会乱跳，用户体验更好。

## 二、CSS 属性选择器


---

例1.下面的例子是把包含标题（title）的所有元素变为蓝色：
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>我是标题</title>  
<style>
[title=a]
{
	border:5px solid green;
}
</style>
</head>

<body>
<h2>将适用:</h2>
<p title="a">Hi!</p>
<a title="a" href="javascript:;">正文正文啊啊啊啊111</a>
<hr>
<h2>将不适用:</h2>
<p title="b">Hi!</p>
<a class="b" href="javascript:;">正文正文啊啊啊啊111</a>
</body>
</html>
```
例2.表单样式
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>我是标题</title>  
<style>
input[type="text"]
{
	width:150px;
	display:block;
	margin-bottom:10px;
	background-color:yellow;
}
input[type="button"]
{
	width:120px;
	margin-left:35px;
	display:block;
}
</style>
</head>
<body>

<form name="input" action="demo-form.php" method="get">
    Firstname:<input type="text" name="fname" value="Peter" size="20">
    Lastname:<input type="text" name="lname" value="Griffin" size="20">
            <input type="button" value="Example Button">
</form>
</body>
</html>
```

## 三、瀑布流布局


---

> 瀑布流概念：又称瀑布流式布局，是比较流行的一种网站页面布局方式。视觉表现为参差不齐的多栏布局，最早采用此布局的是网站是Pinterest，后逐渐在国内流行。

 

> 瀑布流原理：页面容器内的多个高度不固定的div之间按照一定的间隔参差不齐的无序浮动，鼠标滚动时不断在容器内的尾部加载数据，且自动加载到空缺位置，不断循环。

 

         优点：


- 有效降低了界面复杂度，节省了空间：不再需要臃肿复杂的页面导航链接或者按钮了； 
- 在触屏设备上交互方式有更好的用户体验，通过向上滑动进行页面滚动和数据加载，对操作的精准程度要求远远低于点击按钮或者链接；
- 更高的参与度，使用户能更好的专注于浏览而不是操作；

         缺点：

- 无限滚动只适用与特定类型产品中的某一类型，如某类微博信息，购物网站的某类商品，而不适用与一般的门户网站，使用需斟酌；
- 需要打造额外的js库来保证页面数据的加载和排列，而这在一定意义上增加了在网页的性能和设备兼容等方面的问题；
                
                
### 最简单的瀑布流布局————来自百度经验
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>我是标题</title>  
</head>

<body><!--http://jingyan.baidu.com/article/0aa223758278b588cc0d6480.html-->
<div class="pubuliu" style="width:950px; height:600px;">
	<div class="no1" style="width:230px; height:600px; float:left;">
		<div style="width:230px; height:345px;">以淘宝旺铺装修自定义内容区为参考，用DIV来定义一个网页风格瀑布流1111111111</div>
		<div style="width:230px; height:245px; margin-top:10px;">以淘宝旺铺装修自定义内容区为参考，用DIV来定义一个网页风格瀑布流222222222222222</div>
	</div>
	<div class="no2" style="width:230px; height:600px; float:left;  margin-left:10px;">
		<div style="width:230px; height:245px;">以淘宝旺铺装修自定义内容区为参考，用DIV来定义一个网页风格瀑布流3333333333333333333</div>
		<div style="width:230px; height:345px; margin-top:10px;">以淘宝旺铺装修自定义内容区为参考，用DIV来定义一个网页风格瀑布流444444444444444444444</div>
	</div>
	<div class="no3" style="width:230px; height:600px; float:left;  margin-left:10px;">
		<div style="width:230px; height:345px;">以淘宝旺铺装修自定义内容区为参考，用DIV来定义一个网页风格瀑布流555555555555555555555</div>
		<div style="width:230px; height:245px; margin-top:10px;">以淘宝旺铺装修自定义内容区为参考，用DIV来定义一个网页风格瀑布流66666666666666666666</div>
	</div>
	<div class="no4" style="width:230px; height:600px; float:left;  margin-left:10px;">
		<div style="width:230px; height:245px;">以淘宝旺铺装修自定义内容区为参考，用DIV来定义一个网页风格瀑布流777777777777777</div>
		<div style="width:230px; height:345px; margin-top:10px;">以淘宝旺铺装修自定义内容区为参考，用DIV来定义一个网页风格瀑布流888888888888</div>
	</div>
	</div>
</body>
</html>
```



---


### 常见的瀑布流布局的几种实现方式



##### 1) 传统多列浮动。如下图所示:
![image](http://img.yixieshi.com/uploads/allimg/110915/01031462H-1.png?imageView2/2/w/600/h/452)
- 各列固定宽度，并且左浮动;
- 一列中的数据块为一组，列中的每个数据块依次排列即可;
- 更多数据加载时，需要分别插入到不同的列上;
    优点:

- 布局简单，应该说没啥特别的难点;
- 不用明确知道数据块高度，当数据块中有图片时，就不需要指定图片高度。

---


 　　缺点:
- 列数固定，扩展不易，当浏览器窗口大小变化时，只能固定的x列，如果要添加一列，很难调整数据块的排列;
- 滚动加载更多数据时，还要指定插入到第几列中，还是不方便。

　　
##### 2) CSS3 定义。W3C 中有讲述关于多列布局的文档 ，排列出来的样子:


![image](http://img.yixieshi.com/uploads/allimg/110915/0103144219-2.png?imageView2/2/w/600/h/452)

> column-count 为列数; 

>column-gap 为每列间隔距离; 

>column-rule 为间隔边线大小; 

>column-width 为每列宽度; 

>当只设置 column-width 时，浏览器窗口小于一列宽度时，列中内容自动隐藏; 

>当只设置 column-count 时，平均计算每列宽度，列内内容超出则隐藏; 

>都设了 column-count 和column-width，浏览器会根据 count 计算宽度和 width 比较，取大的那个值作为每列宽度，然后当窗口缩小时，width 的值为每列最小宽度。
 
       优点:
- 直接 CSS 定义，最方便了;
- 扩展方便，直接往容器里添加内容即可。


---


 　　缺点:
- 只有高级浏览器中才能使用;
- 还有一个缺点，他的数据块排列是从上到下排列到一定高度后，再把剩余元素依次添加到下一列，这个本质上就不一样了;
- 鉴于这两个主要缺点，注定了该方法只能局限于高端浏览器，而且，更适合于文字多栏排列。
 

##### 3) 绝对定位。

![image](http://img.yixieshi.com/uploads/allimg/110915/010314LV-3.png?imageView2/2/w/600/h/452)


可谓是最优的一种方案，方便添加数据内容，窗口变化，列数/数据块都会自动调整;


---


    缺点:
-  需要实现知道数据块高度，如果其中包含图片，需要知道图片高度;
-  JS 动态计算数据块位置，当窗口缩放频繁，可能会狂耗性能。



### 常见的瀑布流布局的网站
`https://guang.taobao.com`


`http://www.meilishuo.com`
### 视频学习网址
`http://www.imooc.com/learn/101`

## 四、CSS3基本兼容性问题
```html
-ms-transform:rotate(7deg);                //-ms代表ie内核识别码
-moz-transform:rotate(7deg);             //-moz代表火狐内核识别码
-webkit-transform:rotate(7deg);         //-webkit代表谷歌内核识别码
-o-transform:rotate(7deg);               //-o代表欧朋【opera】内核识别码
transform:rotate(7deg);                   //统一标识语句
```
使用css3属性时，大部分都要带这些识别前缀，早期点的浏览器才能识别