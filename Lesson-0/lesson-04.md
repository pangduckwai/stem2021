# Lesson 0 | Chapter 4

## 練習
- 寫一個程式計算頭50個 [Fibonacci number](https://en.wikipedia.org/wiki/Fibonacci_number)。
- Fibonacci number 是一個數列，除了開頭第1與第2項之外，其他每一項是上兩個項加起來的和。
  - F<sub>n</sub> = F<sub>n-2</sub> + F<sub>n-1</sub>

### 新增以下檔案：
- `lesson-04.js`
```javascript
function init() {
	let count = 2;
	let fn2 = 0; // 第 n-2 項
	let fn1 = 1; // 第 n-1 項
	let fn; // 第 n 項

	while (count < 50) {
		// 提示：先計算 fn 等於多少

		console.log(count, fn);
		count ++; // 跟 count = count + 1 是完全相同
	}
}

window.onload = () => init();
```
- **緊記修改 `lesson-0.html` 中 `<script>` 的 `src` 連結！！！**

#### >>> 試完成 `lesson-04.js`：
> _答案..._
> - 首先計算 `fn` 等於 `fn1 + fn2`。
> - 然後預備計算下一個數。注意下一個數 F<sub>n+1</sub> = F<sub>n-1</sub> + F<sub>n</sub>：
> - 所以先把 `fn1` 的值抄進 `fn2`，然後把 `fn` 的值抄進 `fn1`：
> - `lesson-04.js`
> ```javascript
> // 答案版本
> function init() {
> 	let count = 2;
> 	let fn2 = 0; // 第 n-2 項
> 	let fn1 = 1; // 第 n-1 項
> 	let fn; // 第 n 項
> 
> 	while (count < 50) {
> 		fn = fn1 + fn2;
> 		fn2 = fn1;
> 		fn1 = fn;
> 
> 		console.log(count, fn);
> 		count ++; // 跟 count = count + 1 是完全相同
> 	}
> }
> 
> window.onload = () => init();
> ```

---

[← 上一課](lesson-03.md) | 下一課 →
