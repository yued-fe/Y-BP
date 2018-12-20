# HTML 最佳实践

## 基础脚手架 PC

```HTML
<!-- 统一使用HTML5的DOCTYPE -->
<!DOCTYPE html>
<!-- lang使用zh-CN，考虑设备兼容 -->
<html lang="zh-CN">
<head>
	<!-- 页面编码使用UTF-8 -->
	<meta charset="UTF-8">
	
	<!-- 采用IE=Edge, chrome=1 浏览器兼容模式 -->
	<meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1">
	
	<!-- keywords,description 必须 -->
	<meta name="keywords" content="">
	<meta name="description" content="">
	
	<!-- title 必须 -->
	<title>Document</title>

	<link rel="stylesheet" href="index.css">

	<!-- @author [yourname] | @design [designer name] | @pm [pm name] -->
</head>
<body>

	<!-- start 模块名称 -->
	<!-- end 模块名称 -->

	<script src="index.js"></script>
</body>
</html>
```

## 基础脚手架 M站

```HTML
<!-- 统一使用HTML5的DOCTYPE -->
<!DOCTYPE html>
<!-- lang使用zh-CN，考虑设备兼容 -->
<html lang="zh-CN">
<head>
	<!-- 页面编码使用UTF-8 -->
	<meta charset="UTF-8">
	
	<!-- viewport -->
	<meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no">

	<!-- keywords,description 必须 -->
	<meta name="keywords" content="">
	<meta name="description" content="">
	
	<!-- title 必须 -->
	<title>Document</title>

	<link rel="stylesheet" href="index.css">

	<!-- @author [yourname] | @design [designer name] | @pm [pm name] -->
</head>
<body>

	<!-- start 模块名称 -->
	<!-- end 模块名称 -->

	<script src="index.js"></script>
</body>
</html>
```