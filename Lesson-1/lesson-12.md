# Lesson 1 | Chapter 2

## Object 物件
- Object 是一種常用的數據結構。
- 在 JavaScript 中的 Object，被稱為 JSON（JavaScript Object Notation），是一種 key-value-pair（鍵值對）

### JSON 結構十分簡單，但功能異常強大，幾乎能描述任何數據結構：
```javascript
	const student = {
		name: 'John',
		age: 12,
		grade: 'P6',
	};
```
- 現在大部分電腦語言，都支援 JSON 的使用，可說是 JavaScript 對電腦界的最大貢獻。

### 新增以下檔案：
- `lesson-12a.js`
```javascript
function init() {
	const student = {
		name: 'John',
		gender: 'Male',
		age: 12,
		grade: 'P6',
	};

	console.log('名字', student.name);
	console.log('性別', student['gender']);
	console.log('年齡', student['age']);
	console.log('班級', student.grade);
}

window.onload = () => init();
```
- **緊記修改 `lesson-1.html` 中 `<script>` 的 `src` 連結！！！**

#### >>> 如何存取一個 JSON Object 中的數據項？
> _你的答案..._

### JSON Object 中的數據項可以是 array，也可以是另一個 object：
```javascript
	const man = {
		name: 'Rick',
		gender: 'Male',
		spouse: {
			name: 'Liz',
			gender: 'Female',
		},
		children: [ 'Ben', 'Kate', 'Bill' ],
	};
```
- 一個 array 中的項也可以是 JSON object。

### 新增以下檔案：
- `lesson-12b.js`
```javascript
function init() {
	const students = [
		{ name: 'Mary', gender: 'Female', age: 11, grade: 'P5' },
		{ name: 'John', gender: 'Male', age: 12, grade: 'P6' },
		{ name: 'Peter', gender: 'Male', age: 10, grade: 'P4' },
		{ name: 'Sue', gender: 'Female', age: 9, grade: 'P3' },
		{ name: 'Jade', gender: 'Female', age: 11, grade: 'P5' },
	];

	for (let idx = 0; idx < students.length; idx ++) {
		console.log(students[idx]);
	}
}

window.onload = () => init();
```
- **緊記修改 `lesson-1.html` 中 `<script>` 的 `src` 連結！！！**

#### >>> 如何把程式修改為只印出年齡為11歲或以上的學生？
> _你的答案..._

---

[← 上一課](lesson-11.md) | [下一課 →](lesson-13.md)
