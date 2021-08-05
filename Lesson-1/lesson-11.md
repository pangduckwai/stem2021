# Lesson 1 | Chapter １

## Array 陣列
- Array 是一種常用的數據結構。
- 一個array 是一個 variable，但可儲存多項數據。

### 每個 array 都有一個 index （指數），用來分辨它中間的每個數據，例如：
```javascript
	let n = [1, 2, 3, 4, 5]; // 首5個自然數
```

### Array 有什麼用途呢？舉例如果你要儲存並印出最開頭的7個質數，可以怎樣做？
- 可以用一個 array 儲存它們：

### 新增以下檔案：
- `lesson-11.js`
```javascript
function init() {
	let primes = [2, 3, 5, 7, 11, 13, 17]; // 首7個質數

	for (let idx = 0; idx < primes.length; idx ++) {
		console.log('第', idx, '個質數是', primes[idx]);
	}
}

window.onload = () => init();
```
- **緊記修改 `lesson-1.html` 中 `<script>` 的 `src` 連結！！！**

- **注意在上面的例子，是如何「訪問」 array 中的每一個項目。**

#### >>>根據上面的程式，我們如何找出一個 array 有多少項？
> _你的答案..._

#### >>> 上面程式的輸出有什麼問題？可以如何改進？
> _你的答案..._

### 新增以下檔案：
- `lesson-12.js`
```javascript
function init() {

}

window.onload = () => init();
```
- **緊記修改 `lesson-1.html` 中 `<script>` 的 `src` 連結！！！**
