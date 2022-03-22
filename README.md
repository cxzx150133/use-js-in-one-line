# 一句话 js

## 获取 URL 的 GET 参数(仅浏览器可用)

```js
Object.fromEntries(new URLSearchParams(location.search).entries())
```

## 数组去重(仅限基础数据类型)

```js
Array.from(new Set([1, 1, 2, 2, 3, 3]))
```
