## 盒模型
### margin 叠加

- 兄弟元素

![image](http://ogmu8h0g3.bkt.clouddn.com/illustrationCollapsingct_css_margin_collapsing_example_1.gif)

- 父子元素

![image](http://ogmu8h0g3.bkt.clouddn.com/illustrationCollapsingct_css_margin_collapsing_example_2.gif)

- 空元素

![image](http://ogmu8h0g3.bkt.clouddn.com/illustrationCollapsingct_css_margin_collapsing_example_3.gif)

- 以上三种混合

![image](http://ogmu8h0g3.bkt.clouddn.com/illustrationCollapsingct_css_margin_collapsing_example_4.gif)

### 解决方案
- 外层元素padding代替
- 外层元素 overflow:hidden;

- 内层元素透明边框 border:1px solid transparent;
- 内层元素绝对定位 postion:absolute:
- 内层元素 加float:left;或display:inline-block;
- 内层元素padding:1px;

案例代码: `margin.html / margin_1.html`

### 外边距叠加的意义

> 外边距的叠加只产生在普通流文档的上下外边距之间，这个看起来有点奇怪的规则，其实有其现实意义。设想，当我们上下排列一系列规则的块级元素（如段落P）时，那么块元素之间因为外边距叠加的存在，段落之间就不会产生双倍的距离。 

![image](http://ogmu8h0g3.bkt.clouddn.com/ct_css_margin_collapsing.gif)

[参考链接：](http://geekplux.com/2014/03/14/collapsing_margins.html)http://geekplux.com/2014/03/14/collapsing_margins.html

## 文档流 

[参考链接：](http://www.ituring.com.cn/article/198258)http://www.ituring.com.cn/article/198258

案例代码: ` normal_flow.html`

## 定位及浮动
### position

> Position的属性值共有四个static、relative、absolute、fixed。

position: relative并没有改变行内元素的Display属性，这个概念非常重要（注意与接下来的absolute的区别）。

应用了position: absolute的元素会脱离页面中的普通流并改变Display属性（重点）！

案例代码: ` position_absolute.html / position_fixed.html`

### float
float(display: inline-block)
会将元素的display属性变更为block
案例代码: ` float.html`

### 清除浮动的方法
1:
```css
        .clearfix {
            zoom: 1;
        }
        .clearfix:after {
            content: '';
            height: 0;
            visibility: hidden;
            display: block;
            clear: both;
        }
```
2:
```css
        .clear {
            clear: both;
        }
```
3:
```css
        .cf:before,
        .cf:after {
            content: " ";
            display: table;
        }
        .cf:after {
            clear: both;
        }
        .cf {
            *zoom: 1;
        }
```
4. 
`overflow:hidden`

推荐使用:
[http://nicolasgallagher.com/micro-clearfix-hack/](http://nicolasgallagher.com/micro-clearfix-hack/)

## 各种居中


### 水平居中
方法1（inline-* 元素）
`text-align: center`

案例代码: `heri-no-block.html`

方法2 （固定宽度高度）
`margin: 0 auto;`

案例代码: ` heri-block.html`

### 垂直居中


方法1（适用于不确定宽度高度）
```css
.parent {
  position: relative;
}
.child {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}
```

案例代码: `ver-block-unknow.html`

方法2（适用于固定宽度高度）
```css
.parent {
  position: relative;
}
.child {
  position: absolute;
  top: 50%;
  height: 100px;
  margin-top: -50px; /* account for padding and border if not using box-sizing: border-box; */
}
```

案例代码: `ver-block.html`

### 垂直和水平居中

方法1（适用于固定宽度和高度的元素）
```css
.parent {
  position: relative;
}
```
```css
.child {
  width: 300px;
  height: 100px;
  padding: 20px;

  position: absolute;
  top: 50%;
  left: 50%;

  margin: -70px 0 0 -170px;
}
```

案例代码: ` both-block-know.html`

方法2（适用于不确定宽度和高度）
```css
.parent {
  position: relative;
}
.child {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

案例代码: `both-block-unknow.html`

参考地址：[CSS居中定位(transform, margin)](https://css-tricks.com/centering-css-complete-guide/)
