# jQuery on()方法
* 多个事件绑定同一个函数
```javascript
$(document).ready(function(){
  $("p").on("mouseover mouseout",function(){
    $("p").toggleClass("intro");
  });
});
````
* 多个事件绑定不同函数
```javascript
$(document).ready(function(){
  $("p").on({
    mouseover:function(){$("body").css("background-color","lightgray");},  
    mouseout:function(){$("body").css("background-color","lightblue");}, 
    click:function(){$("body").css("background-color","yellow");}  
  });
});
````
绑定自定义事件
```javascript
$(document).ready(function(){
  $("p").on("myOwnEvent", function(event, showName){
    $(this).text(showName + "! What a beautiful name!").show();
  });
  $("button").click(function(){
    $("p").trigger("myOwnEvent",["Anja"]);
  });
});
````
* 传数据到函数
```javascript
function handlerName(event) 
{
  alert(event.data.msg);
}

$(document).ready(function(){
  $("p").on("click", {msg: "You just clicked me!"}, handlerName)
});
````
适用于未创建的元素
```javascript
$(document).ready(function(){
  $("div").on("click","p",function(){
    $(this).slideToggle();
  });
  $("button").click(function(){
    $("<p>This is a new paragraph.</p>").insertAfter("button");
  });
});
````
