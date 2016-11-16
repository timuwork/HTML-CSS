## CSS 选择符

---
*教材page30*-*page32*


### 1、标签选择符：

    如p{color:#F00; font-size:36px;}；
    
    使用<p>直接作用</p>
### 2、类选择符：

   如 .red{color:#C00;};
   
   使用<p class="red">直接作用</p>
### 3、ID选择符：

    如 #two{color:#600; font-family:'汉仪行楷简';}；
    
    使用<p id="two">直接作用</p>
### 4、包含选择符：

    如 p strong{color:#F00;}；
    
    使用<p><strong>直接作用</strong></p>
### 5、通配选择符：

    如 *{color:#0C0; font-size:18px;};
    
    可以控制所有的html元素作用范围很广，但是效率较低
### 6、选择符分组：

     如p,h1,div{color:#F00;font-size:36px;}；
     
     对p,h1,div都有效
### 7、标签指定式选择符：

    如p#one{ color:#F00;font-size:36px;}；
    
    只对id为one的p标签有效
### 8、组合选择符：

    将所有选择符类型组合使用