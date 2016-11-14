## 存在的问题

1. 有些同学没有按照设计稿的要求编码。在实际项目开发中，设计稿还原非常重要，应该尽量按照设计稿上标注的尺寸及内容进行编码。

2. 1/4 圆，可以使用负的`margin`外边距，或`position`中的`left/right/top/bottom` 进行设置，值应该为圆的半径。有些同学设置的值小于或大于半径，就显得有点别扭了。

3. style外联样式表路径设置有问题，不清楚绝对路径和相对路径。```<link rel="stylesheet" href="../3/style.css">```
路径尽量使用相对路径，使用绝对路径如果你的文件夹或盘符发生更改，就会失效，就像如上代码一样，在我的电脑中打开就没有样式显示了。修改后如下：```<link rel="stylesheet" href="style.css">```或```<link rel="stylesheet" href="./style.css">```
> `..`代表上一级目录，`.`代表当前目录。

4. DIV层次关系为 灰色矩形DIV内应该包裹 两个圆，有些同学将这三个并列排布，位置无法相对的来设置了，会发生变形。

```html
<div class="main"></div>
<div class="yuane"></div>
<div class="yuanr"></div>
```
修改后如下
```html
<div class="main">
    <div class="yuane"></div>
    <div class="yuanr"></div>
</div>
```
5. 有些同学碰到了圆显示在矩形外，无法被隐藏，这里可以在外层矩形上设置`overflow:hidden`将圆形的部分隐藏掉。
 
6. 圆怎么放到左上角和右上角，在外层矩形框设置`position:relative`，圆可以用`position:absolute`来进行定位。

7.外层矩形的居中问题。可以参看此处：[各种居中的方法](https://css-tricks.com/centering-css-complete-guide/)。

8.CSS命名应尽量使用英文，避免使用拼音或无意义单词。

作业源代码请看目录中的 `task1.html`