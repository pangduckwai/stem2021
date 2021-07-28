# Lesson 0 | Chapter 1

## Variables 變數
- 變數在一個程式中十分重要，用來儲存不同的值。
- 我們用 label 名稱來命名變數，代表了電腦記憶體中的一個記憶位置。
- 變數可用的名稱有限制，不能用 JavaScript 中的關鍵字，也要用英文字母開頭。

### 我們用 `let` 來定義變數，例如：
```javascript
function init() {
  let x = 100; // 'x' 現在的值等於 100
}
```

### 同一個變數，在一個程式中，只需要用 `let` 一次，例如：
```javascript
function init() {
  let x = 100; // 'x' 現在的值等於 100

  // do somehting here...

  x = 101; // 'x' 現在的值等於 101
}
```

### 新增以下檔案：
1. `lesson-01.js`
```javascript
function init() {
  let a = 8;
  let b = 16;
  console.log('Before', a, b); // Result: "Before 8 16"

  // ***********************************
  // 如何才可以把a與b兩個變數的數值對調呢？
  //
  // 注意！！！！不容許這樣做：
  // a = 16;
  // b = 8;
  // 要假設你不知道a與b的數值
  // ***********************************

  console.log('After ', a, b); // Wanted: "After 16 8"
}

window.onload = () => init();
```

#### 如何才可以把上面兩個變數a與b的數值對調呢？
> _你的答案..._

---

[← 上一課](README.md) | [下一課 →](lesson-01.md)
