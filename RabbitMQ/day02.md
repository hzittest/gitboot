# day02_jquery选择器

## 一、选择器

``` java
public class hell{
    
}
```





``` html
<html>
    <head>
        <title>hehe</title>
    </head>
    <body>
        <img sr="xxx" />
    </body>
</html>
```



``` javascript
function xx(){
    alert("xx");
}
```







### 1.作用

用来获取页面中的标签内容。jquery提供了很多选择器。都是同一个目的。

应该使用最方便最快的速度完成元素查找即可。



> $("h3").css("background","#09F");

获取并设置网页中所有<h3>元素的背景

“h3”为选择器语法，必须放在$()中

(“h3”)返回jQuery对象

.css()是为jQuery对象设置样式的方法



### 2.分类

jQuery选择器功能强大，种类也很多，分类如下：

- 类CSS选择器
  - 基本选择器
  - 层次选择器
  - 属性选择器
- 过滤选择器
  - 基本过滤选择器
  - 可见性过滤选择器



### 3.基本选择器

基本选择器包括标签选择器、类选择器、ID选择器、并集选择器、交集选择器和全局选择器

| 名称       | 语法构成 | 描述                     | 示例                                    |
| ---------- | -------- | ------------------------ | --------------------------------------- |
| 标签选择器 | element  | 根据给定的标签名匹配元素 | $("h2" )选取所有h2元素                  |
| 类选择器   | .class   | 根据给定的class匹配元素  | $("  .title")选取所有class为title的元素 |
| ID选择器   | #id      | 根据给定的id匹配元素     | $("  #title")选取id为title的元素        |

| 名称       | 语法构成                          | 描述                                   | 示例                                                     |
| ---------- | --------------------------------- | -------------------------------------- | -------------------------------------------------------- |
| 并集选择器 | selector1,selector2,...,selectorN | 将每一个选择器匹配的元素合并后一起返回 | $("div,p,.title" )选取所有div、p和拥有class为title的元素 |
| 交集选择器 | element.class或element#id         | 匹配指定class或id的某元素或元素集合    | $("h2.title")选取所有拥有class为title的h2元素            |
| 全局选择器 | *                                 | 匹配所有元素                           | $("*" )选取所有元素                                      |



### 4.层次选择器

层次选择器通过DOM元素之间的层次关系来获取元素

| 名称           | 语法构成             | 描述                                           | 示例                                             |
| -------------- | -------------------- | ---------------------------------------------- | ------------------------------------------------ |
| 后代选择器     | ancestor  descendant | 选取ancestor元素里的所有descendant（后代）元素 | $("#menu  span" )选取#menu下的<span>元素         |
| 子选择器       | parent>child         | 选取parent元素下的child（子）元素              | $("  #menu>span" )选取#menu的子元素<span>        |
| 相邻元素选择器 | prev+next            | 选取紧邻prev元素之后的next元素                 | $("  h2+dl " )选取紧邻<h2>元素之后的同辈元素<dl> |
| 同辈元素选择器 | prev~siblings        | 选取prev元素之后的所有siblings元素             | $("  h2~dl " )选取<h2>元素之后所有的同辈元素<dl> |

### 5.属性选择器

> <img  src="" title=""/>  title和src就是img的属性

属性选择器通过HTML元素的属性来选择元素

| 语法构成            | 描述                                 | 示例                                            |
| ------------------- | ------------------------------------ | ----------------------------------------------- |
| [attribute]         | 选取包含给定属性的元素               | $("  [href]" )选取含有href属性的元素            |
| [attribute=value]   | 选取等于给定属性是某个特定值的元素   | $("  [href ='#']" )选取href属性值为“#”的元素    |
| [attribute !=value] | 选取不等于给定属性是某个特定值的元素 | $("  [href !='#']" )选取href属性值不为“#”的元素 |

| 语法构成                            | 描述                                 | 示例                                                         |
| ----------------------------------- | ------------------------------------ | ------------------------------------------------------------ |
| [attribute^=value]                  | 选取给定属性是以某些特定值开始的元素 | $("  [href^='en']" )选取href属性值以en开头的元素             |
| [attribute$=value]                  | 选取给定属性是以某些特定值结尾的元素 | $("  [href$='.jpg']" )选取href属性值以.jpg结尾的元素         |
| [attribute*=value]                  | 选取给定属性是以包含某些值的元素     | $("  [href* ='txt']" )选取href属性值中含有txt的元素          |
| [selector]  [selector2] [selectorN] | 选取满足多个条件的复合属性的元素     | $("li[id][title=新闻要点]" )选取含有id属性和title属性为新闻要点的<li>元素 |

### 6.过滤选择器

过滤选择器通过特定的过滤规则来筛选元素

语法特点是使用“:”，如使用$(“li:first”)来选取第一个li元素

主要分类如下：

- 基本过滤选择器
- 可见性过滤选择器
- 表单对象过滤选择器
- 容过滤选择器、子元素过滤选择器……



#### 6.1 基本过滤选择器

| 语法构成 | 描述                                     | 示例                                                |
| -------- | ---------------------------------------- | --------------------------------------------------- |
| :first   | 选取第一个元素                           | $("  li:first" )选取所有<li>元素中的第一个<li>元素  |
| :last    | 选取最后一个元素                         | $("  li:last" )选取所有<li>元素中的最后一个<li>元素 |
| :even    | 选取索引是偶数的所有元素（index从0开始） | $("  li:even" )选取索引是偶数的所有<li>元素         |
| :odd     | 选取索引是奇数的所有元素（index从0开始） | $("  li:odd" )选取索引是奇数的所有<li>元素          |

| :eq(index) | 选取索引等于index的元素（index从0开始） | $("li:eq(1)" )选取索引等于1的<li>元素                        |
| ---------- | --------------------------------------- | ------------------------------------------------------------ |
| :gt(index) | 选取索引大于index的元素（index从0开始） | $("  li:gt(1)" )选取索引大于1的<li>元素（注：大于1，不包括1） |
| :lt(index) | 选取索引小于index的元素（index从0开始） | $(“li:lt(1)” )选取索引小于1的<li>元素（注：小于1，不包括1）  |

| :not(selector) | 选取去除所有与给定选择器匹配的元素 | $("  li:not(.three)" )选取class不是three的元素 |
| -------------- | ---------------------------------- | ---------------------------------------------- |
| :header        | 选取所有标题元素，如h1~h6          | $(":header" )选取网页中所有标题元素            |
| :focus         | 选取当前获取焦点的元素             | $(":focus" )选取当前获取焦点的元素             |

#### 6.2 可见性过滤选择器

可见性过滤选择器可以通过元素显示状态来选取元素

| 语法构成 | 描述               | 示例                              |
| -------- | ------------------ | --------------------------------- |
| :visible | 选取所有可见的元素 | $(":visible" )选取所有可见的元素  |
| :hidden  | 选取所有隐藏的元素 | $(":hidden" )  选取所有隐藏的元素 |

![1564713811022](img\1564713811022.png)![1564713926538](img\1564713926538.png)



![1564714213271](img\1564714213271.png)



## 二、事件

jQuery事件是对JavaScript事件的封装，常用事件分类如下：

- 基础事件
  - window事件
  - 鼠标事件
  - 键盘事件
  - 表单事件
- 复合事件是多个事件的组合
  - 鼠标光标悬停
  - 鼠标连续点击



### 2.1 鼠标事件

鼠标事件是当用户在文档上移动或单击鼠标时而产生的事件，常用鼠标事件有：

| 方法          | 描述                                        | 执行时机   |
| ------------- | ------------------------------------------- | ---------- |
| click(  )     | 触发或将函数绑定到指定元素的click事件       | 单击鼠标时 |
| mouseover(  ) | 触发或将函数绑定到指定元素的mouse  over事件 | 鼠标移过时 |
| dblclick()    | 触发或将函数绑定到指定元素的dblclick事件    | 双击鼠标时 |
| mouseout(  )  | 触发或将函数绑定到指定元素的mouse  out事件  | 鼠标移出时 |

### 2.2 键盘事件

用户每次按下或者释放键盘上的键时都会产生事件，常用键盘事件有：

| 方法         | 描述                                     | 执行时机           |
| ------------ | ---------------------------------------- | ------------------ |
| keydown(  )  | 触发或将函数绑定到指定元素的keydown事件  | 按下键盘时         |
| keyup(  )    | 触发或将函数绑定到指定元素的keyup事件    | 释放按键时         |
| keypress(  ) | 触发或将函数绑定到指定元素的keypress事件 | 产生可打印的字符时 |

`产生可打印的字符:`哪些字符不可以打印? 删除,ESC,转换大小写



### 2.3 表单事件

当元素获得焦点时，会触发focus事件，失去焦点时，会触发blur事件，详见下表：

| 方法      | 描述                                   | 执行时机     |
| --------- | -------------------------------------- | ------------ |
| focus(  ) | 触发或将函数绑定到指定元素的focus事件  | 获得焦点     |
| blur(  )  | 触发或将函数绑定到指定元素的blur事件   | 失去焦点     |
| change()  | 触发或将函数绑定到指定元素的change事件 | 内容发生改变 |



### 2.4 绑定事件

`bind`:绑定

`unbind`:解除绑定

``` javascript
//单个事件
  $("input[name=event_1]").bind("click",function() {
	   $("p").css("background-color","#F30");
   });

//多个事件
$("input[name=event_1]").bind({
		mouseover: function () {
			$("ul").css("display", "none");
		},
		mouseout: function () {
			$("ul").css("display", "block");
		},
		click:function(){
			$("h2").css("color","red");
		},
		dblclick:function(){
			$("h2").css("color","green");
			}
	});

//解绑
$("input[name='event_2']").bind("click",function(){
		//指定移除的事件  如果不指定移除的就是所有的事件
    	//$("input[name=event_1]").unbind("click");
		$("input[name=event_1]").unbind();
	});
```





### 2.5 复合事件

`toggle`:可以联系写多个事件

`hover`:替代mouseover,mouseout两个事件

``` javascript
//点击 切换 
$("body").toggle(
			function () {
				//$(this).show();
				$(this).css("background-color", "red");
				 
			},
			function () {
				$(this).css("background-color", "green"); 
			},
			function () {
				$(this).css("background-color", "blue"); 
			},
			function () {
				$(this).css("background-color", "yellow"); 
			},	function () {
				$(this).css("background-color", "black"); 
			}
     );

//hover
$("#myaccound").hover(function(){
		  	$("#menu_1").css("display","block");
		  },
		  function(){
			  $("#menu_1").css("display","none");
		  }
	);
```



## 三、动画

![1564729742447](img\1564729742447.png)

参照 api:<https://www.w3school.com.cn/jquery/jquery_ref_effects.asp>

### 3.1 显示/隐藏

- show("time",fn)    :设置显示的时间，与回调函数
- hide("time",fn)     :设置隐藏的时间
- toggle("time",fn)  :显示/隐藏的时间

``` javascript
//显示
$(".tipsbox").show(1000,function(){
			alert("--显示成功");//show()执行完毕之后的回调函数  调用该方法
}); 

//隐藏
$("input[name=cancel]").click(function() {
       $(".tipsbox").hide(1000); //1秒钟完成操作
});

//切换
 $("input[name='togglexx']").click(function(){
		$(".tipsbox").toggle(500);
 });
```







### 3.2 淡入/淡出

- fadeIn: 淡入
- fadeOut:淡出
- fadeTo: 指定透明度
- fadeToggle:  淡入淡出切换

``` javascript
//淡入
$("input[name=fadein_btn]").click(function(){
     $("img").fadeIn(1000);
});

//淡出
$("input[name=fadeout_btn]").click(function(){
	$("img").fadeOut(1000);
});

//指定透明度
 $("input[name=fadeto_btn]").click(function(){
	$("img").fadeTo(1000,0.5,function(){
		alert("成功到达...");
	});
 });

//淡入淡出切换
  $("input[name=fadeToggle_btn]").click(function(){
		$("img").fadeToggle(1000,function(){
			alert("成功到达...");
		});
});
```



### 3.3 上拉下拉

- slideUp  :上拉
- slideDown :下拉
- slideToggle :切换

``` javascript
$("h2").click(function(){
    $(".txt").slideToggle("slow");
    //$(".txt").slideDown("slow");
    //$(".txt").slideUp("slow");
 );
```



### 3.4 动画 

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>

    <style>
        #main{
            width: 100%;
            border: 1px solid black;
            height: 100px;

        }

        #first{
            width: 100px;
            height: 100px;
            background-color: gray;
        }
    </style>
    <script src="js/jquery-1.8.3.js"></script>
    <script>
        
        $(function(){

            $("#start").click(function(){

                $("#first").animate({
                    "margin-left":"1200px"
                },2000);

            });

        });
    </script>
</head>
<body>
    
    <div id="main">
        <div id="first"></div>
    </div>

    <button id="start">开始</button>

</body>
</html>
```

