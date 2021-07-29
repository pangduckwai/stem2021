# Lesson 0 | Chapter 3

## Loop 迴圈
- Loop 也是流程控制的一種，可以把一段程式代碼重複執行的。
- 使用時要注意使 loop 停止的條件，不然形成了 infinite loop，程式就不能正常跑完。

### 最基本的叫 `while` loop，例如：
```javascript
	let count = 0; // 首先設定 count 等於 0

	// 當條件是「是」（true）的時候，執行 {...} 內的代碼，直到條件變為「非」（false）
	while (count < 5) { // 當 count 少於 5 時條件是「true」，否則為「false」
		console.log('Hello', count);
		count = count + 1; // 將 count 的值加 1，例如當 count 等於 3 時，行完這句 count 變成等於 4
	}
```
- 這程式跑出來的結果如下：
```
Hello 0
Hello 1
Hello 2
Hello 3
Hello 4
```

#### >>> 為什麼跑到 4 就停？
> _你的答案..._

### 另一個常用的叫 `for` loop，例如：
```javascript
	for (let count = 0; count < 5; count = count + 1) {
		console.log('Hello', count);
	}
```
- 這段程式跟上面用 `while` 的功能完全一樣。它只是把分開的3句（1. `let count = 0;` 2. `count < 5` 3. `count = count + 1`）寫到 `for` 一句下面吧。

### 新增以下檔案：
- `lesson-03.js`
```javascript
function init() {
  let total = 0;
  let count = 0;

  // 計算 1 + 2 + 3 + 4 + 5 的結果
  while (count < 5) {
    total = total + count;
    count = count + 1;
    console.log(count, total);
  }

  console.log('total is', total, 'count', count);
}

window.onload = () => init();
```
- **緊記修改 `lesson-0.html` 中 `<script>` 的 `src` 連結！！！**

#### >>> 程式 `lesson-03.js` 計出的答案是錯的。錯在哪裡？如何修正？
> _你的答案..._

### 如果將 `lesson-03.js` 變成下面的樣子，會發生什麼事？試試看。
- `lesson-03.js`
```javascript
function init() {
	// 第2版本
  let total = 0;

  // 計算 1 + 2 + 3 + 4 + 5 的結果
  for (let count = 0; count < 5; count = count + 1) {
    total = total + count;
    console.log(count, total);
  }

  console.log('total is', total, 'count', count);
}

window.onload = () => init();
```

#### >>> 為什麼第2版本的 `lesson-03.js` 跑出來會有這個效果？
> _你的答案..._

---

[← 上一課](lesson-02.md) | [下一課 →](lesson-04.md)
