# jQuery on()方法
* 多个事件绑定同一个函数
<pre>
```javascript
$(document).ready(function(){
  $("p").on("mouseover mouseout",function(){
    $("p").toggleClass("intro");
  });
});
```
</pre>
