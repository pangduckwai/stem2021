# Lesson 2 | Chapter 3

## 測試

### 新增以下檔案：
- `lesson-23.html`
```html
<html lang="en">
	<head>
		<meta charset="utf-8"/>
		<title>
			JavaScript Lesson 2
		</title>
	</head>

	<body>
		<h1>JavaScript Lesson 2 - Testing</h1>
	</body>

	<script src="lesson-22.js" type="text/javascript"></script>
	<script src="lesson-23.js" type="text/javascript"></script>
</html>
```

- `lesson-23.js`
```javascript
let player = 0;
let cells = [];

function init() {
	let result;

	// Test D01
	player = -1;
	cells = [
		[1, -1, 1],
		[1, -1, -1],
		[-1, 1, -1],
	];
	result = evaluate();
	if (result !== 255) {
		console.log('Test D01 ❌failed', `Expect 255, got ${result}`, cells);
	} else {
		console.log('Test D01 ✔️passed', cells);
	}

	// Test O01
	player = 1;
	cells = [
		[1, 1, 1],
		[0, -1, 0],
		[0, -1, -1],
	];
	result = evaluate();
	if (result !== player) {
		console.log('Test O01 ❌failed', `Expect ${player}, got ${result}`, cells);
	} else {
		console.log('Test O01 ✔️passed', cells);
	}

	// Test X01
	player = -1;
	cells = [
		[-1, 0, 1],
		[0, -1, 1],
		[-1, 1, -1],
	];
	result = evaluate();
	if (result !== player) {
		console.log('Test X01 ❌failed', `Expect ${player}, got ${result}`, cells);
	} else {
		console.log('Test X01 ✔️passed', cells);
	}

	// Test C01
	player = -1;
	cells = [
		[0, 0, 0],
		[0, -1, 0],
		[0, 0, 0],
	];
	result = evaluate();
	if (result !== 0) {
		console.log('Test C01 ❌failed', `Expect 0, got ${result}`, cells);
	} else {
		console.log('Test C01 ✔️passed', cells);
	}

	// Test C02
	player = -1;
	cells = [
		[1, -1, 1],
		[1, -1, -1],
		[0, 1, -1],
	];
	result = evaluate();
	if (result !== 0) {
		console.log('Test C01 ❌failed', `Expect 0, got ${result}`, cells);
	} else {
		console.log('Test C01 ✔️passed', cells);
	}
}

window.onload = () => init();
```

#### >>> 為什麼說測試是最要緊的呢？
> _答案..._
>
> [测试驱动开发](https://zh.wikipedia.org/wiki/%E6%B5%8B%E8%AF%95%E9%A9%B1%E5%8A%A8%E5%BC%80%E5%8F%91)

### 進階
- 嘗試寫一個 ｎxｎ 版本的「過ｎ關」

---

[← 上一課](lesson-22.md) | 下一課 →
