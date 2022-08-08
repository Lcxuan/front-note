## AJAX请求

AJAX（Asychronous Javascript and XML，异步Javascript和XML），是指一种创建交互式网页应用的网页开发技术。

一种浏览器通过JS发送异步请求，局部更新页面的技术。

AJAX特点：

- 局部更新，浏览器地址栏不会发生变化，不会舍弃原来页面的内容

### 原生Javascript发送AJAX请求

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script>
      function ajaxRequest(){
          // 1.创建XMLHttpRequest
          var xmlHttpRequest = new XMLHttpRequest();
          // 2.调用open方法设置参数
          // 第一个参数：请求的类型
          // 第二个参数：文件在服务器的位置
          // 第三个参数：true 异步 false同步
          xmlHttpRequest.open("GET", "http://localhost:8080/web7/ajax?action=javascriptAjax", true);
          // 3.在send之前绑定onreadystatechange事件，处理请求完成后的操作
          xmlHttpRequest.onreadystatechange = function (){
              if (xmlHttpRequest.readyState == 4 && xmlHttpRequest.status == 200){
                  // 获取服务器相应的数据
                  var responseJson = JSON.parse(xmlHttpRequest.responseText);

                  var div1 = document.getElementById("div1");
                  div1.innerHTML = "编号为：" + responseJson.id + "，姓名为：" + responseJson.name;  
              }
          }
          // 4.发送send请求
          xmlHttpRequest.send();
      }
    </script>
</head>
<body>
  <button onclick="ajaxRequest()">AJAX Request</button>
  <div id="div1"></div>
</body>
</html>
```



### JQuery发送AJAX请求

#### $.ajax()方法

- url：表示请求地址

- type：表示请求的类型，例如：GET和POST请求

- data：表示发送给服务器的数据

- success：请求成功的响应回调函数

- dataType：响应的数据类型，常用数据类型：text、xml、json

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="./jquery-3.6.0.js"></script>
    <script>
        $(function (){
            $("#ajaxBtn").click(function (){
                $.ajax({
                    url: "http://localhost:8080/web7/ajax",
                    data: "action=jqueryAjax",
                    type: "GET",
                    success: function (msg){
                        $("#ajaxMsg").html("编号：" + msg.id + "，姓名：" + msg.name)
                    },
                    dataType: "json"
                })
            })
        })
    </script>
</head>
<body>
    <button id="ajaxBtn">AJAX方法</button>
    <div id="ajaxMsg"></div>
</body>
</html>
```

#### $.get()方法和$.post()方法

- url：表示请求地址

- data：表示发送给服务器的数据
- callback：成功的回调函数
- type：返回的数据类型

$.get()方法示例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="jquery-3.6.0.js"></script>
    <script>
        $(function (){
           $("#getBtn").click(function (){
               $.get("http://localhost:8080/web7/ajax", "action=jqueryAjax", function (msg) {
                   $("#msg").html("get 编号：" + msg.id + ", 姓名：" + msg.name)
               }, "json")
           })
        })
    </script>
</head>
<body>
    <button id="getBtn">GET请求</button>
    <div id="msg"></div>
</body>
</html>
```

$.post()方法示例：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="jquery-3.6.0.js"></script>
    <script>
        $(function (){
           $("#postBtn").click(function (){
               $.post("http://localhost:8080/web7/ajax", "action=jqueryAjax", function (msg) {
                   $("#msg").html("post 编号：" + msg.id + ", 姓名：" + msg.name)
               }, "json")
           })
        })
    </script>
</head>
<body>
    <button id="postBtn">POST请求</button>
    <div id="msg"></div>
</body>
</html>
```



#### $.getJson()方法

- url：请求的url地址
- data：发送给服务器的数据
- callback：成功的回调函数

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="jquery-3.6.0.js"></script>
    <script>
        $(function (){
           $("#getJsonBtn").click(function (){
               $.getJSON("http://localhost:8080/web7/ajax", "action=jqueryAjax", function (msg) {
                   $("#msg").html("getJSON 编号：" + msg.id + ", 姓名：" + msg.name)
               })
           })
        })
    </script>
</head>
<body>
    <button id="getJsonBtn">getJson方法</button>
    <div id="msg"></div>
</body>
</html>
```



#### 表单序列化serialize()

可以将表单中所有表单项的内容获取到，并以name=value键值对的形式进行拼接

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
	<head>
		<meta http-equiv="pragma" content="no-cache" />
		<meta http-equiv="cache-control" content="no-cache" />
		<meta http-equiv="Expires" content="0" />
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
		<title>Insert title here</title>
		<script type="text/javascript" src="jquery-3.6.0.js"></script>
		<script type="text/javascript">
			$(function(){
				// ajax请求
				$("#submit").click(function(){
					var serialize = $("#form01").serialize();
					$.get("http://localhost:8080/web7/ajax", "action=jqueryAjax&" + serialize, function (msg) {
						$("#msg").html("getJSON 编号：" + msg.id + ", 姓名：" + msg.name)
					}, "json")
				});
			});
		</script>
	</head>
	<body>
		<form id="form01" >
			用户名：<input name="username" type="text" /><br/>
			密码：<input name="password" type="password" /><br/>
			下拉单选：<select name="single">
			  	<option value="Single">Single</option>
			  	<option value="Single2">Single2</option>
			</select><br/>
		  	下拉多选：
		  	<select name="multiple" multiple="multiple">
		    	<option selected="selected" value="Multiple">Multiple</option>
		    	<option value="Multiple2">Multiple2</option>
		    	<option selected="selected" value="Multiple3">Multiple3</option>
		  	</select><br/>
		  	复选：
		 	<input type="checkbox" name="check" value="check1"/> check1
		 	<input type="checkbox" name="check" value="check2" checked="checked"/> check2<br/>
		 	单选：
		 	<input type="radio" name="radio" value="radio1" checked="checked"/> radio1
		 	<input type="radio" name="radio" value="radio2"/> radio2<br/>
		</form>			
		<button id="submit">提交--serialize()</button>
		<div id="msg"></div>
	</body>
</html>
```

