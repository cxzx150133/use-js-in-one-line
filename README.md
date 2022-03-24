# 又名《如何在不牺牲可读性的情况下用一行 javascript 代码实现项目实际开发中所用到的功能》

> 注意: 不考虑浏览器向下兼容性，不考虑运行效率，不考虑异常，请勿随意用于生产环境。

## 获取 URL 的 GET 参数(仅浏览器可用)

```js
let getUrlParams = () => Object.fromEntries(new URLSearchParams(location.search).entries())
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
let repeat = (arr, n) => new Array(n).fill(arr).flatMap(item => item)
```

### 使用

```js
let arr = [1, 2, 3]
let output = repeat(arr) // output: [1, 2, 3, 1, 2, 3]
```

## 深拷贝(慢，但是普适）

```js
let deepClone = (v) => JSON.parse(JSON.stringify(v))
```

### 使用

```js
let obj = { a: 0 }
let obj_copy = deepClone(obj)
obj.a = 1
console.log(obj) // { a: 1 }
console.log(obj_copy) // { a: 0 }
```

## 获取类型

```js
let getType = (v) => Object.prototype.toString.call(v).slice(8, -1)
```

### 使用

```js
getType(null) // Null
getType(undefined) // Undefined
getType(true) // Boolean
getType(0) // Number
getType(0n) // BigInt
getType('') // String
getType(Symbol()) // Symbol
getType({}) // Object
getType([]) // Array
getType(() => []) // Function
getType(new Set()) // Set
getType(new Map()) // Map
getType(new FormData()) // FormData
```

## 获取指定区间内的随机整数

```js
let random = (min, max) => Math.floor(Math.random() * (max - min + 1) + min);
```

### 使用

```js
random(0, 100)
```

# 拓展阅读

+ https://1loc.dev/
+ https://www.30secondsofcode.org/
+ [33个非常实用的JavaScript一行代码，建议收藏！](https://juejin.cn/post/7025771605422768159)
+ [一行 JS (以分号结束)能实现什么丧心病狂的功能？](https://www.zhihu.com/question/48187821)
+ [这些一行 JS 实现功能的代码，让你看起来像一个前端专家](https://juejin.cn/post/6921509748785283086)
