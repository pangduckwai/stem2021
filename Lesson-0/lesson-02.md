# Lesson 0 | Chapter 2

## Flow control 流程控制
- 從[上一課](lesson-01.md)我們知道，一個程式是由上至下逐句指令執行的。
- 用邏輯運算，加上流程控制，可以做到按情況執行不同指令的效果。

### 我們用 `if`，`else`，`else if` 來控制流程，例如：
```javascript
function init() {
  let score = ???; // 不知道 'score' 現在的值

  if (score === 0) {
    console.log('肥佬');
  } else if (score === 100) {
    console.log('滿分');
  } else {
    console.log('分數是', score);
  }
}
```

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

#### 執行是什麼？是「結果 1」還是「結果 2」會被執行？如果第一句改為 `let x = 45;` 會有什麼不同效果？
> _你的答案..._

#### 如果第一句改為 `let x = 50;` 會有什麼結果？這個結果對嗎？要怎樣改才行？
> _你的答案..._

---

[← 上一課](README.md) | 下一課 →
