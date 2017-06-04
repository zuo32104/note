# HTML5屏幕适配标签

标签（空格分隔）： 浏览器

---

## 开发HTML5游戏中，我们常用的一些mata标签:
```
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no, minimal-ui" /> 
```

    width: viewport 的宽度 （范围从 200 到 10,000 ，默认为 980 像素 ）
    
    height: viewport 的高度 （范围从 223 到 10,000 ）
    
    initial-scale: 初始的缩放比例 （范围从>0到 10 ）
    
    minimum-scale: 允许用户缩放到的最小比例
    
    maximum-scale: 允许用户缩放到的最大比例
    
    user-scalable: 用户是否可以手动缩放

### 下面是我们经常用到的一些标签，由于浏览器的差异，并不能百分百兼容。



	<!-- 是否删除默认的苹果工具栏和菜单栏 -->
	<meta name="apple-mobile-web-app-capable" content="yes" />
	
	<!-- 其他的meta设置 -->
	<!-- 启用360浏览器的极速模式(webkit) -->
	<meta name="renderer" content="webkit">
	
	<!-- 避免IE使用兼容模式 -->
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	
	<!-- 针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓 -->
	<meta name="HandheldFriendly" content="true">
	
	<!-- 微软的老式浏览器 -->
	<meta name="MobileOptimized" content="320">
	
	<!-- uc强制竖屏 -->
	<meta name="screen-orientation" content="portrait">
	
	<!-- QQ强制竖屏 -->
	<meta name="x5-orientation" content="portrait">
	
	<!-- UC强制全屏 -->
	<meta name="full-screen" content="yes">
	
	<!-- QQ强制全屏 -->
	<meta name="x5-fullscreen" content="true">
	
	<!-- UC应用模式 -->
	<meta name="browsermode" content="application">
	
	<!-- QQ应用模式 -->
	<meta name="x5-page-mode" content="app">
	
	<!-- windows phone 点击无高光 -->
	<meta name="msapplication-tap-highlight" content="no">



## 此外，apple还有两个有趣的标签：

 1.apple-touch-icon

```
< link  rel= "apple-touch-icon"  sizes= "76x76"  href= "touch-icon-ipad.png">

```
如果 apple-mobile-web-app-capable 设置为 yes 了，那么在苹果机的safari上可以通过添加到主屏按钮将网站添加到主屏幕上。而设置相应 apple-touch-icon 标签，则添加到主屏上的图标就会使用我们指定的图片。

 2.apple-touch-startup-image
 
```
< link rel= "apple-touch-startup-image" href= "/startup.png">
```

基于 apple-mobile-web-app-capable 设置为 yes ，可以为WebApp设置一个类似NativeApp的启动画面。和 apple-touch-icon 不同， apple-mobile-web-app-capable 不支持sizes属性，要使用media来加载不同的启动画面。详细查询 大漠的文章 。

	// iPhone
	<link href="apple-touch-startup-image-320x460.png" media="(device-width: 320px)" rel="apple-touch-startup-image" />
	// iPhone Retina
	<link href="apple-touch-startup-image-640x920.png" media="(device-width: 320px) and 
			(-webkit-device-pixel-ratio: 2)" rel="apple-touch-startup-image" />


