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
			JavaScript Lesson 1.5
		</title>
	</head>

	<body>
		<h1>
			JavaScript Lesson 1 - Saying Hello
		</h1>
		<h2>
			Interactive HTML
		</h2>
		<hr/>
		<p>
			The time now is <i id="telltime"></i>...
			<br/><br/>
			Hello, what is your name?
			<br/>
			My name is <input id="name" type="text" value="..."/>
			<button id="go">GO -></button>
		</p>
		<hr/>
		<p>
			<a href="https://github.com/pangduckwai/stem2021/blob/master/Lesson-1/README.md">
				Back to the begining of Lession 1
			</a>
		</p>
	</body>
	<script src="lesson-15.js" type="text/javascript"></script>
</html>
```

### 新增以下檔案：
- `lesson-15.js`
```javascript
function press() {
  let name = document.getElementById('name').value;
  console.log(`Hello, ${name}`);
}

function init() {
	document.getElementById('telltime').textContent = `${new Date()}`;
  document.getElementById('go').onclick = press;
}

window.onload = () => init();
```

#### >>> 嘗試輸入你的名字，再按 ＜ＧＯ＞ ，會有什麼反應？
> _你的答案..._

#### >>> 試結合 [`lession-14`](lesson-14.md) 把輸入的名字顯示到網頁上。
> _你的答案..._

### 你已有齊所需的技巧，下一堂可以開始寫「過三關」遊戲了。

---

[← 上一課](lesson-14.md) | 下一課 →
