# Lesson 1 | Chapter 3

## Dynamic / Interactive HTML with JavaScript 建立動態/互動的網頁
- 加上 JavaScript 能使網頁變成動態，更可以建立互動的網頁。

### 把 `lesson-1.html` 改為下面樣子：
- `lesson-1.html`
```html
<html lang="en">
	<head>
		<meta charset="utf-8"/>
		<title>
			JavaScript Lesson 1.4
		</title>
	</head>

	<body>
		<h1>
			JavaScript Lesson 1 - Saying Hello
		</h1>
		<h2>
			Dynamic HTML
		</h2>
		<hr/>
		<p>
			Hello, <span id="greeting"></span> !!!
			<br/><br/>
			The time now is <i id="telltime"></i>...
		</p>
		<hr/>
		<p>
			<a href="https://github.com/pangduckwai/stem2021/blob/master/Lesson-1/README.md">
				Back to the begining of Lession 1
			</a>
		</p>
	</body>
	<script src="lesson-14.js" type="text/javascript"></script>
</html>
```

### 新增以下檔案：
- `lesson-14.js`
```javascript
function init() {
	document.getElementById('greeting').textContent = 'Yvonne';
  document.getElementById('telltime').textContent = `${new Date()}`;
}

window.onload = () => init();
```

#### >>> 試把上面改為向你打招呼的網頁（改為顯示你的名字）。
> _你的答案..._

---

[← 上一課](lesson-13.md) | [下一課 →](lesson-15.md)
