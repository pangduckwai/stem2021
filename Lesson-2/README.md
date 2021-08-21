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
	font-size: 10pt;
}
a:active, a:link, a:visited {
	text-decoration: none;
	color: skyblue;
}

.header {
	position: relative;
	margin: 21px 14px 0;
}
#title {
	float: left;
	color: #424242;
	font-size: 2em;
}

.content {
	clear: both;
	padding-top: 7px;
	padding-left: 14px;
	margin-bottom: 14px;
}
.content > div {
	margin-top: 7px;
}
.content p {
	color: #404040;
	font-size: 1.2em;
	line-height: 1.3;
	margin: 7px 0 7px 0;
}

.footer p {
	font-size: 0.7em;
	padding-top: 3px;
	margin-left: 14px;
	margin-right: 14px;
}

.board div {
	margin-bottom: 7px;
}
.board span {
	padding: 21px 28px 21px 28px;
	margin-right: 4px;
	display: inline-block;
	vertical-align: top;
	border: 1px solid;
	justify-content: center;
	align-items: center;
	font-size: 3em;
	cursor: pointer;
	color: #424242;
}
.board span:hover {
	background-color: #eeeeee;
}

.controls {
	vertical-align: bottom;
	margin: 4px;
}

#message {
	padding-top: 14px;
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
</head>
<body>
	<div class="header">
		<div id="title">Lesson 2 - Tic Tac Toe</div>
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
		<p id="message">&nbsp;Hello!</p>
	</div>
	<div class="footer">
		<p>© 2021 SEA9.ORG</p>
	</div>
	<script src="lesson-20.js" type="text/javascript"></script>
</body>
</html>
```

3. `lesson-20.js`
```javascript
// Event handler: 處理滑鼠點擊方格事件
function clicked(row, col) {
	console.log(row, col, 'clicked');
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
}

function init() {
	document.getElementById('new').onclick = () => newgame(); // 設定 event handler
	newgame();
}

window.onload = () => init();
```

### 在瀏覽器開啟 `lesson-2.html`。（建議用 Chrome 或 Firefox）

- 於瀏覽器在點選狀態下按鍵盤上的 F12，打開「開發者工具」，
- 打開 Console 分頁下可以見到當前 JavaScript 程式的執行結果。

#### >>> `lesson-2.html` 的執行結果是什麼？用滑鼠點擊其中一個方格會有什麼發生？
> _你的答案..._

---

← 上一課 | [下一課 →](lesson-21.md)
