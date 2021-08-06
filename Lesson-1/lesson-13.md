# Lesson 1 | Chapter 3

## HTML 是什麼？
- 全名是 Hyper Text Markup Language，是用來製作網頁的。
- 叫「Hyper Text」是指網頁中的不是純文字，而是可以連結到其他資源的「超級文字」。
- 「Markup」是指 `html` 檔案中用一些標記（tag）來標示不同的功能/效果等等。

### 把 `lesson-1.html` 改為下面樣子：
- `lesson-1.html`
```html
<html lang="en"> <!-- 01 這是網頁的開始 -->
	<head> <!-- 02 這是網頁頁頭的開始 -->
		<meta charset="utf-8"/>
		<title>
			JavaScript Lesson 1.3 <!-- 03 這被＜title＞＜/title＞包著的是什麼？ -->
		</title>
	</head> <!-- 02 這是網頁頁頭的結束 -->

	<body> <!-- 04 這是網頁內容的開始 -->
		<h1>
			JavaScript Lesson 1 - Saying      Hello <!-- 05 這被＜h1＞＜/h1＞包著的是什麼？ -->
		</h1>
		<h2>
			Static HTML <!-- 06 ＜h1＞＜/h1＞跟＜h2＞＜/h2＞有什麼不同？ -->
		</h2>
		<hr></hr> <!-- 07 這是標題下的第一條橫線 -->
		<p> <!-- 08 這是一個段落的開始 -->
			Hello, <i>Paul</i> !!! <!-- 09 ＜i＞＜/i＞的功能是什麼？ -->
		</p> <!-- 08 這是一個段落的結束 -->
		<hr/> <!-- 10 這是第二條橫線，是 `07` 的縮寫 -->
		<p> <!-- 08 這是一個段落的開始 -->
			<a href="https://github.com/pangduckwai/stem2021/blob/master/Lesson-1/README.md">
				Back to the begining of Lession 1 <!-- 11 這被＜a＞＜/a＞包著的是什麼？ -->
			</a>
		</p> <!-- 08 這是一個段落的結束 -->
	</body> <!-- 04 這是網頁內容的結束 -->
</html> <!-- 01 這是網頁的結束 -->
```
- 其中用 `<` 及 `>` 包著的就是 tags，例如 <body>。每個 tag 都有開始及結束一對，例如被 <body></body> 包著的就是一個網頁的全部內容。

#### >>> 細讀上面由 01至11的註釋，並嘗試回答03、05、06、09及11的問題。
> _你的答案..._

### 那麼 html 跟 JavaScript 的關係是什麼？
- 回顧上一課的[「進階」](../Lesson-0/README.md#進階)部份：
>  - 留意 `lesson-00.js` 最後一句 `window.onload = () => init();` 意思是說在 window（指的是瀏覽器視窗）在載入的時候，就是剛打開（或剛刷新）一個網頁或 html 文件的時候，去跑一個叫做 `init()` 的東西。而這個 `init()` 就定義了在 `lesson-00.js` 的最開頭。
>  - 這叫做 event handler，意思是當有事件（event）發生時，告訴系統如何處理。
>  - 這裡就是說：「在載入或刷新事件發生時，請跑 `init()` 這個函數（function）」

---

[← 上一課](lesson-12.md) | [下一課 →](lesson-14.md)
