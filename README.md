# 一句话 js

## 获取 URL 的 GET 参数(仅浏览器可用)

```js
Object.fromEntries(new URLSearchParams(location.search).entries())
```

## 数组去重(仅限基础数据类型)

```js
Array.from(new Set([1, 1, 2, 2, 3, 3])) // output: [1, 2, 3]
```

## 数组长度翻 n 倍(相对位置不变)

```js
[1, 2, 3].flatMap(item => new Array(2).fill(item)) // output: [1, 1, 2, 2, 3, 3]
```
