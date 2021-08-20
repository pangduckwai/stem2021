# Lesson 2 | Chapter 0

## 上期回顧
> ## JavaScript 是什麼？
> - JavaScript 是一種腳本，也能稱它為程式語言。
> - 大部份瀏覽器都支援執行 JavaScript，而絕大部份電腦都已預裝瀏覽器，因此只需要一部電腦就可以開始學習 JavaScript 編程。
> - JavaScript 可以在網頁中實現出複雜的功能，初學者也能容易的編寫出很不錯的效果。
> 
> ## 預備功夫
> 
> ### 安裝一個文字編輯器 (Text Editor)
> - 如果還未做的話，請安裝一個 Text Editor
> - 建議用 Microsoft 的 [Visual Studio Code](https://code.visualstudio.com/)，免費但有足夠功能。
>
> ---
> 
> ## HTML 是什麼？
> - 全名是 Hyper Text Markup Language，是用來製作網頁的。
> - 叫「Hyper Text」是指網頁中的不是純文字，而是可以連結到其他資源的「超級文字」。
> - 「Markup」是指 `html` 檔案中用一些標記（tag）來標示不同的功能/效果等等。
> 
> ### 那麼 html 跟 JavaScript 的關係是什麼？
> - 回顧上一課的[「進階」](../Lesson-0/README.md#進階)部份：
> >  - 留意 `lesson-00.js` 最後一句 `window.onload = () => init();` 意思是說在 window（指的是瀏覽器視窗）在載入的時候，就是剛打開（或剛刷新）一個網頁或 html 文件的時候，去跑一個叫做 `init()` 的東西。而這個 `init()` 就定義了在 `lesson-00.js` 的最開頭。
> >  - 這叫做 event handler，意思是當有事件（event）發生時，告訴系統如何處理。
> >  - 這裡就是說：「在載入或刷新事件發生時，請跑 `init()` 這個函數（function）」

### 在電腦中開一個新的目錄，例如：
- `Desktop\Lesson_02\`

### 在這目錄中新增以下三個檔案：
1. `lesson-2.css`
```css
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

body {
	font-family: "Roboto",Arial,sans-serif;
	font-weight: 300;
	font-weight: normal;
	font-size: 12pt;
}
a:active, a:link, a:visited {
	text-decoration: none;
	color: skyblue;
}

#header {
	position: relative;
	margin: 21px 14px 0;
}
#header img {
	float: left;
	height: 82px;
}
#title {
	float: left;
	color: #424242;
	font-size: 2em;
}

#content {
	clear: both;
	padding-top: 7px;
	padding-left: 14px;
	margin-bottom: 35px;
}
#content > div {
	margin-top: 21px;
}
#content h1 {
	color: lightblue;
	font-size: 1.7em;
	font-variant: small-caps;
	line-height: 1.3;
	margin: 28px 0 14px 0;
	margin: 0 0 14px 0;
}
#content h1 img {
	height: 64px;
	vertical-align: middle;
	margin-right: 14px;
}
#content h3 {
	color: lightgray;
	font-size: 1.4em;
	line-height: 1.3;
	margin: 21px 0 0 7px;
}
#content h3 img {
	height: 64px;
	vertical-align: middle;
}
#content p, ol {
	color: #404040;
	font-size: 1.2em;
	line-height: 1.3;
	margin: 7px 0 7px 0;
}
#content li {
	margin: 7px 0 7px 21px;
}
#content p img {
	width: 100%;
	margin-top: 7px;
}
#content span {
	display: inline-block;
	vertical-align: top;
}

#footer div {
	float: left;
	padding-left: 14px;
	text-align: center;
}
#footer p {
	font-size: 0.7em;
	padding-top: 3px;
	margin-left: 14px;
	margin-right: 14px;
}
#footer img {
	margin-right: 14px;
}

.board {
	display: grid;
	gap: 10px;
	grid-auto-rows: 100px;
}
.cell {
	display: flex;
	border: 1px solid;
	justify-content: center;
	align-items: center;
	font-size: 3em;
	cursor: pointer;
	color: #424242;
}
.cell:hover {
	background-color: #eeeeee;
}

.controls {
	vertical-align: bottom;
	margin: 4px;
}
```

2. `lesson-2.html`
```html
<html lang="en">
<head>
<title>Lesson 2</title>
<meta charset="utf-8"/>
<meta name="Description" content="Lesson 2">
<link type="text/css" rel="stylesheet" href="lesson-2.css" />
<style id="boardcss" type="text/css">
#board {grid-template-columns: repeat(3, 100px);}
#left {width: 350px;}
</style>
</head>
<body>
	<div id="header">
		<div id="title">Lesson 2 - Tic Tac Toe</div>
	</div>
	<div id="content">
		<span id="left">
			<div id="board" class="board">
				<div id="c0-0" class="cell">0</div>
				<div id="c0-1" class="cell">1</div>
				<div id="c0-2" class="cell">2</div>
				<div id="c1-0" class="cell">3</div>
				<div id="c1-1" class="cell">4</div>
				<div id="c1-2" class="cell">5</div>
				<div id="c2-0" class="cell">6</div>
				<div id="c2-1" class="cell">7</div>
				<div id="c2-2" class="cell">8</div>
			</div>
			<p id="message">&nbsp;</p>
		</span>
		<span style="width: 150px; text-align: right;">
			<button id="new" class="controls">New game</button>
		</span>
	</div>
	<div id="footer">
		<p>© 2021 SEA9.ORG</p>
	</div>
	<script src="lesson-2.js" type="text/javascript"></script>
</body>
</html>
```

3. `lesson-2.js`
```javascript
// Game Status
// player: indicate which player's turn it is
//  - player == -1 => 'X'
//  - player == +1 => 'O'
// cells: n x n grid with value: 0 (unoccupied), -1 (occupied by 'X'), +1 (occupied by 'O')
// moves: total count
// wins: statistic for all winning conditions (n + n + 2, that is each horizontal and vertical lines plus the 2 diagonals)
//  - 0: forward diagonal, 1: backward diagonal, the rest are horizontals then vertical
const game = {
	player: 0,
	cells: [[0]],
	moves: 0,
	wins: [0],
}

function evaluate(row, col) {
	const n = game.cells.length;

	game.moves ++;
	if (row === col) {
		game.wins[0] += game.player; // forward diagonal
	}
	if ((row + col + 1) === n) {
		game.wins[1] += game.player; // backward diagonal
	}
	game.wins[col + 2] += game.player; // horizontal
	game.wins[row + n + 2] += game.player; // vertical

	if (game.wins.filter(w => w >= n).length > 0) {
		game.player = 0;
		return 1;
	} else if (game.wins.filter(w => (-1 * w) >= n).length > 0) {
		game.player = 0;
		return -1;
	} else if (game.moves >= n * n) {
		game.player = 0;
		return 255; // Draw
	} else {
		return 0;
	}
}

// Draw the clicked cell with 'O' or 'X' according to the current turn
function makeMove(row, col) {
	if (game.cells[row][col] !== 0) {
		return { moved: false, result: 0 }; // cell (row,col) already occupied
	}

	const eid = `c${row}-${col}`;
	if (game.player > 0) {
		document.getElementById(eid).textContent = 'O';
		game.cells[row][col] = 1;
	} else {
		document.getElementById(eid).textContent = 'X';
		game.cells[row][col] = -1;
	}

	switch (evaluate(row, col)) {
		case -1:
			document.getElementById('message').textContent = ' "X" won';
			return { moved: true, result: -1 };
		case 1:
			document.getElementById('message').textContent = ' "O" won';
			return { moved: true, result: 1 };
		case 255:
			document.getElementById('message').textContent = ' Draw';
			return { moved: true, result: 255 };
		default:
			return { moved: true, result: 0 };
	};
}

// Event handler for clicking a cell
function clicked(row, col) {
	if (game.player !== 0) { // game.player === 0 if game is not yet started or already finished
		const { moved, result } = makeMove(row, col);
		if (moved) {
			if (result === 0) { // game not yet concluded
				console.log('row', row, 'column', col, 'clicked');
				game.player = (game.player === -1) ? 1 : -1; // Next player
			}
		} else {
			console.log(`[${row}, ${col}] already occupied`); // TODO TEMP
		}
	} else {
		console.log('No game in progress');
	}
}

function newgame() {
	console.log('New game!!!');
	const n = 3

	// Update html
	document.getElementById('boardcss').innerHTML = `#board {grid-template-columns: repeat(${n}, 100px);}\n#left {width: ${110*n+10}px;}`; // dynamic part of the CSS

	// Initialize the Game Status object
	game.player = -1; // "X" start first
	game.moves = 0;
	game.wins = new Array(2 * n + 2);
	for (let i = 0; i < game.wins.length; i ++) {
		game.wins[i] = 0;
	}
	game.cells = new Array(n); // initial the rows

	// Build the game board
	const board = document.getElementById('board');

	let r = -1;
	let c;
	for (let i = 0; i < n * n; i ++) {
		if ((i % n) === 0) { // Note the modular operation i % n
			r ++;
			c = 0;
			game.cells[r] = new Array(n); // initial columns of row 'r'
		}

		// Initialize the cell's corresponding value in the Game Status object
		game.cells[r][c] = 0; // Delay the cell initialization to here
		const row = r;
		const col = c;
		const eid = `c${row}-${col}`;

		// Add event handlers to the new cell
		let cell = document.getElementById(eid);
		cell.textContent = '';
		cell.onclick = () => clicked(row, col);

		console.log('Initialized row', r, 'column', c);

		c ++;
	}
}

function init() {
	document.getElementById('new').onclick = () => newgame(); // Add event handler for the 'New game' button
	newgame();
}

window.onload = () => init();
```

### 在瀏覽器開啟 `lesson-2.html`。（建議用 Chrome 或 Firefox）

- 於瀏覽器在點選狀態下按鍵盤上的 F12，打開「開發者工具」，
- 打開 Console 分頁下可以見到當前 JavaScript 程式的執行結果。
