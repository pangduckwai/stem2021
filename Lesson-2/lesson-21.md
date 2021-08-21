# Lesson 2 | Chapter 1

## 練習
- 改良 `lesson-20.js` 讓兩個玩家輪流在方格內填 `X` 與 `O`。

### 提示：新增以下檔案：
- `lesson-21.js`
```javascript
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

	// 這裡還欠一句什麼程式才完成
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
- **緊記修改 `lesson-2.html` 中 `<script>` 的 `src` 連結！！！**

#### >>> function `clicked()` 要加上一句什麼才算完成呢？
> _你的答案..._

---

[← 上一課](README.md) | [下一課 →](lesson-22.md)
