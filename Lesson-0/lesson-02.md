# Lesson 0 | Chapter 2

## Flow control 流程控制
- 從[上一課](lesson-01.md)我們知道，一個程式是由上至下逐句指令執行的。
- 用邏輯運算，加上流程控制，可以做到按情況執行不同指令的效果。

### 我們用 `if`，`else`，`else if` 來控制流程，例如：
```javascript
	let score = ???; // 不知道 'score' 現在的值

	if (score === 0) {
		console.log('肥佬');
	} else if (score === 100) {
		console.log('滿分');
	} else {
		console.log('分數是', score);
	}
```

### 注意一點，在電腦語言中，「等號」有多種意思：
- **設定一個 variable 的值 (Variable Assignment)**
  - 「單等號」設定一個 variable 的值
  - 例如：`score = 79;`
- **邏輯運算中的「相等」 (Equality)**
  - 「雙等號」在很多電腦語言中表示「相等」，例如 C++, Java, Golang 等等。
  -  JavaScript 中可以用「雙等號」`==` 或「三等號」`===` ，**_一般建議用「三等號」_**。

### 新增以下檔案：
- `lesson-02.js`
```javascript
function init() {
	let x = 64;

	if (x > 50) {
		console.log(x, 'is more than 50'); // 結果 1
	} else {
		console.log(x, 'is less than 50'); // 結果 2
	}
}

window.onload = () => init();
```
- **緊記修改 `lesson-0.html` 中 `<script>` 的 `src` 連結！！！**

#### >>> 執行是什麼？是「結果 1」還是「結果 2」會被執行？如果第一句改為 `let x = 45;` 會有什麼不同效果？
> _答案..._
> 執行結果是「結果 1」（`64 is more than 50`），因為 variable `x` 等於 64，大過 50。
> 如果 variable `x` 改為等於 45，執行結果會變為「結果 2」（`45 is less than 50`）。

#### >>> 如果第一句改為 `let x = 50;` 會有什麼結果？這個結果對嗎？要怎樣改才行？
> _答案..._
> - 執行結果是「結果 2」（`50 is less than 50`）。原因是 `else` 的意思就是跟原本的狀況（`x > 50`）相反。
> - 而「`x` 大過 50」的相反是「`x` <ins>細過或等於</ins> 50」，所以當 `x` 等於 50 的時候也會跑「結果 2」而得出 `50 is less than 50` 這不合理的結果。
> - 可以把程式如下改：
> - `lesson-02.js`
> ```javascript
> 	function init() {
> 		// 更正版本
> 		let x = 50;
> 
> 		if (x > 50) {
> 			console.log(x, 'is more than 50'); // 結果 1
> 		} else if (x === 50) {
> 			console.log(x, 'is equal to 50'); // 結果 3
> 		} else {
> 			console.log(x, 'is less than 50'); // 結果 2
> 		}
> 	}
> 
> 	window.onload = () => init();
> ```

---

[← 上一課](lesson-01.md) | [下一課 →](lesson-03.md)
