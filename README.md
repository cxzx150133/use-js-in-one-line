# 一句话 js

## 获取 URL 的 GET 参数(仅浏览器可用)

```js
let urlParams = () => Object.fromEntries(new URLSearchParams(location.search).entries())
```

## 数组去重(仅限基础数据类型)

```js
let dedup = (arr) => Array.from(new Set(arr))
```

### 使用

```js
let arr = [1, 1, 2, 2, 3, 3]
let output = duplicate(arr) // output: [1, 2, 3]
```

## 数组长度翻 n 倍(相对位置不变)

```js
let repeat = (arr, n) => arr.flatMap(item => new Array(n).fill(item))
```

### 使用

```js
let arr = [1, 2, 3]
let output = repeat(arr) // output: [1, 1, 2, 2, 3, 3]
```

## 数组长度翻 n 倍(整体翻倍)

```js
let repeat = (arr, n) => new Array(arr.length).fill(arr).flatMap(item => item)
```

### 使用

```js
let arr = [1, 2, 3]
let output = repeat(arr) // output: [1, 2, 3, 1, 2, 3, 1, 2, 3]
```
