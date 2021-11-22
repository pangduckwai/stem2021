# Lesson 2 | Chapter 2

## 練習
- 改良 `lesson-21.js` 能夠偵測出遊戲是平手，還是其中一方勝出。

### 修改 `lesson-21.js` 及 `lesson-2.html` 如下：
- `lesson-21.js`
```javascript
// 更新版本
// 遊戲當前狀態
let player = 0; // '-1'代表輪到'X', '1'代表輪到'O', '0'代表遊戲未開始或已結束
let cells = [];

// Event handler: 處理滑鼠點擊方格事件
function clicked(row, col) {
	if (player === 0) {
		console.log('No game in progress');
		return ;
	}

	if (cells[row][col] !== 0) {
		console.log(`[${row}, ${col}] already occupied`);
		return;
	}

	const cell = document.getElementById(`c${row}-${col}`);
	if (player < 0) {
		cell.textContent = 'X';
		cells[row][col] = -1;
	} else {
		// 在這個位置，`player`的值是「小過零」，還是「小過等於零」呢？
		cell.textContent = 'O';
		cells[row][col] = 1;
	}

	const result = evaluate();
	if (result === 255) { // 為什麼要先檢查打和？
		document.getElementById('message').textContent = ' 打和';
		player = 0;
	} else if (result < 0) {
		document.getElementById('message').textContent = ' "X" 勝';
		player = 0;
	} else if (result > 0) {
		document.getElementById('message').textContent = ' "O" 勝';
		player = 0;
	}

	// 這裡還欠一句什麼程式才完成
	player *= -1; // 由於兩個 players 由 +1 及 -1 代表
}

// Event handler: 處理滑鼠點擊'New game' button事件
function newgame() {
	console.log('New game!!!');

	document.getElementById('c0-0').onclick = () => clicked(0, 0); // 設定 event handler
	document.getElementById('c0-1').onclick = () => clicked(0, 1); // 設定 event handler
	document.getElementById('c0-2').onclick = () => clicked(0, 2); // 設定 event handler
	document.getElementById('c1-0').onclick = () => clicked(1, 0); // 設定 event handler
	document.getElementById('c1-1').onclick = () => clicked(1, 1); // 設定 event handler
	document.getElementById('c1-2').onclick = () => clicked(1, 2); // 設定 event handler
	document.getElementById('c2-0').onclick = () => clicked(2, 0); // 設定 event handler
	document.getElementById('c2-1').onclick = () => clicked(2, 1); // 設定 event handler
	document.getElementById('c2-2').onclick = () => clicked(2, 2); // 設定 event handler

	document.getElementById('c0-0').textContent = '_';
	document.getElementById('c0-1').textContent = '_';
	document.getElementById('c0-2').textContent = '_';
	document.getElementById('c1-0').textContent = '_';
	document.getElementById('c1-1').textContent = '_';
	document.getElementById('c1-2').textContent = '_';
	document.getElementById('c2-0').textContent = '_';
	document.getElementById('c2-1').textContent = '_';
	document.getElementById('c2-2').textContent = '_';

	player = -1; // 'X' start first
	cells = [
		[0, 0, 0],
		[0, 0, 0],
		[0, 0, 0],
	];
}

function init() {
	document.getElementById('new').onclick = () => newgame(); // 設定 event handler
	newgame();
}

window.onload = () => init();
```

- `lesson-2.html`
```html
<!-- 更新版本 -->
<html lang="en">
<head>
<title>Lesson 2</title>
<meta charset="utf-8"/>
<meta name="Description" content="Lesson 2">
<link type="text/css" rel="stylesheet" href="lesson-2.css" />
</head>
<body>
	<div class="header">
		<div id="title">Lesson 2 - 3x3 Tic Tac Toe</div>
	</div>
	<div class="content">
		<div>
			<button id="new" class="controls">New game</button>
		</div>
		<div class="board">
			<div>
				<span id="c0-0">0</span>
				<span id="c0-1">1</span>
				<span id="c0-2">2</span>
			</div>
			<div>
				<span id="c1-0">3</span>
				<span id="c1-1">4</span>
				<span id="c1-2">5</span>
			</div>
			<div>
				<span id="c2-0">6</span>
				<span id="c2-1">7</span>
				<span id="c2-2">8</span>
			</div>
		</div>
		<p id="message">&nbsp;</p>
	</div>
	<div class="footer">
		<p>© 2021 SEA9.ORG</p>
	</div>
	<script src="lesson-22.js" type="text/javascript"></script>
	<script src="lesson-21.js" type="text/javascript"></script>
</body>
</html>
```

### 新增以下檔案：
- `lesson-22.js`
```javascript
// 偵測遊戲結果，返回：0 - 遊戲繼續; -1 - 'X'勝; 1 - 'O'勝; 255 - 打和
function evaluate() {
	console.log(cells);
	return 0; // 未完成！！！
}
```
- **緊記修改 `lesson-2.html` 中 `<script>` 的 `src` 連結！！！**

#### >>> 嘗試把 `lesson-22.js` 中的 function `evaluate()` 完成。
> _答案..._
> - `lesson-22.js`
> ```javascript
> // 答案版本
> // 偵測遊戲結果，返回：0 - 遊戲繼續; -1 - 'X'勝; 1 - 'O'勝; 255 - 打和
> function evaluate() {
> 	let val1, val2;
> 	let empty = 0;
> 
> 	// 橫直
> 	for (let i = 0; i < 3; i ++) {
> 		val1 = 0; // 橫
> 		val2 = 0; // 直
> 		for (let j = 0; j < 3; j ++) {
> 			val1 += cells[i][j];
> 			val2 += cells[j][i];
> 			if (cells[i][j] === 0) {
> 				empty ++;
> 			}
> 		}
> 		if ((val1 === -3) || (val2 === -3)) {
> 			return -1;
> 		} else if ((val1 === 3) || (val2 === 3)) {
> 			return 1;
> 		}
> 	}
> 
> 	val1 = 0;
> 	val2 = 0;
> 	// 斜
> 	for (let i = 0; i < 3; i ++) {
> 		val1 += cells[i][i];
> 		val2 += cells[2 - i][i];
> 	}
> 	if ((val1 === -3) || (val2 === -3)) {
> 		return -1;
> 	} else if ((val1 === 3) || (val2 === 3)) {
> 		return 1;
> 	}
> 
> 	// 為什麼最後才檢查打和？
> 	if (empty <= 0) {
> 		return 255;
> 	}
> 
> 	return 0;
> }
> ```

---

[← 上一課](lesson-21.md) | [下一課 →](lesson-23.md)
