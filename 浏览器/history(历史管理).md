# history(历史管理)

标签（空格分隔）： 浏览器

---

## 历史管理

 1. onhashchange:改变hash值来管理
 2. history:
    -history.pushState事件: 三个参数:数据 标题(没有实现) 地址(可选)
    -onpopstate事件: 读取数据 event.state
    -注意:网址是虚假的,需要在服务器指定对应页面,不然刷新找不到页面

```
<script type="text/javascript">
	var btn = document.getElementById('btn');
	var info = document.getElementById('info');
	console.log(window.location)
	window.onhashchange = function(){
		console.log(window.location)
	}

	btn.onclick = function(){
		var number = randomNum(35,7);
		info.innerHTML = number;
	}

	console.log(btn)

	function randomNum(alls,now){
		var arr = [];
		var newArr = [];
		for(var i=1;i<alls;i++){
			arr.push(i)
		}

		for(var i=0;i<now;i++){
			newArr.push(arr.splice(Math.floor(Math.random()*arr.length),1))
		}

		return newArr;
	}
</script>
```
```
<script type="text/javascript">
	var btn = document.getElementById('btn');
	var info = document.getElementById('info');
	var oRE = {};
	window.onhashchange = function(){
		var num = window.location.hash.substring(1);  
		info.innerHTML = oRE[num] || '';

	}

	btn.onclick = function(){
		var number = randomNum(35,7);
		var random = Math.random();
		oRE[random] = number;
		window.location.hash = random;

	}

	function randomNum(alls,now){
		var arr = [];
		var newArr = [];
		for(var i=1;i<alls;i++){
			arr.push(i)
		}

		for(var i=0;i<now;i++){
			newArr.push(arr.splice(Math.floor(Math.random()*arr.length),1))
		}

		return newArr;
	}
</script>
```
```
<script type="text/javascript">
	var btn = document.getElementById('btn');
	var info = document.getElementById('info');
	var oRE = {};
	window.onhashchange = function(){
		var num = window.location.hash.substring(1);  
		info.innerHTML = oRE[num] || '';

	}
	var n = 1;

	window.onpopstate = function(ev){
		console.log(ev)
		var num = ev.state || '';
		info.innerHTML = num;
	}

	btn.onclick = function(){
		var number = randomNum(35,7);		
		info.innerHTML = number;
		window.history.pushState(number,'',n++)
		
	}

	function randomNum(alls,now){
		var arr = [];
		var newArr = [];
		for(var i=1;i<alls;i++){
			arr.push(i)
		}
		for(var i=0;i<now;i++){
			newArr.push(arr.splice(Math.floor(Math.random()*arr.length),1))
		}

		return newArr;
	}
</script>
```
