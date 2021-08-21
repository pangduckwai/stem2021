# Lesson 2 | Chapter 1

## 練習
- 改良 `lesson-21.js` 能夠偵測出遊戲是平手，還是其中一方勝出。

### 提示：新增以下檔案：
- `lesson-22.js`
```javascript
// 遊戲當前狀態
let player = 0; // '-1'代表輪到'X', '1'代表輪到'O', '0'代表遊戲未開始或已結束
let cells = [];
let moves; // 代表遊戲的第幾步

// 偵測遊戲結果，返回：0 - 遊戲繼續; -1 - 'X'勝; 1 - 'O'勝; 255 - 打和
function evaluate() {
	console.log(cells);
	return 0;
}

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

	player *= -1;
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
	moves = 0; // no player has move yet
}

function init() {
	document.getElementById('new').onclick = () => newgame(); // 設定 event handler
	newgame();
}

window.onload = () => init();
```
- **緊記修改 `lesson-2.html` 中 `<script>` 的 `src` 連結！！！**

#### >>> 嘗試把 function `evaluate()` 完成。
> _你的答案..._

---

[← 上一課](lesson-21.md) | [下一課 →](lesson-23.md)
