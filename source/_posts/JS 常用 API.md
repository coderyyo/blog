---
title: JS 常用 API
categories:
  - JavaScript
---

## Array 数组

### 1. concat

- 定义：连接两个或多个数组
- 语法：array1.concat(array2, array3,..., arrayX)
- 例子：

```
let a = ['a']
let b = ['b']
console.log(a.concat(b)) // [ 'a', 'b' ]
```

### 2. forEach

- 定义：遍历数组的所有元素
- 注意：不会对空数组进行检查，不会改变原数组
- 例子：

```
let forEachArr = [
  {
    id: 1
  },
  {
    id: 2
  },
  {
    id: 3
  }
]
let res = forEachArr.forEach((a, b, c) => {
  // console.log(1) // 1 1 1
  console.log(a, b, c) // 当前元素 当前元素索引 当前元素所属的数组对象
})
console.log(res) // undefined
```

### 3. some（某个）

- 定义：检测数组所有元素是否有符合指定条件
  - 如果有一个元素满足，则表达式返回 true，且剩余元素不再检测
  - 没有元素满足条件，则返回 false
- 注意：不会对空数组进行检查，不会改变原数组
- 例子：

```
let someArr = ['a', 'b', 'c']
let res = someArr.some(i => {
  console.log(1) // 1 1
  return i === 'b'
})
console.log(res) // true
```

### 4. every（所有）

定义：检测数组所有元素是否都符合指定条件

- 如果有一个元素不满足条件，则表达式返回 false，且剩余元素不再检测
- 全部元素满足条件，则表达式返回 true
  注意：不会对空数组进行检查，不会改变原数组
  例子：
  let everyArr = ['a', 'b', 'c']
  let res = everyArr.every(i => {
  console.log(1) // 1 1
  return i === 'a'
  })
  console.log(res) // false

### 5. find（第一个）

- 定义：找到数组中符合指定条件的第一个元素值
  - 如果元素符合条件，则返回该元素值，且剩余元素不再检测
  - 如果没有元素符合条件，则返回 undefined
- 注意：不会对空数组进行检查，不会改变原数组
- 例子：

```
let findArr = [
  {
    id: 1
  },
  {
    id: 2
  },
  {
    id: 3
  }
]
let res = findArr.find(i => {
  console.log(1) // 1 1
  return i.id === 2
})
console.log(res) // { id: 2 }
```

### 6. findIndex（第一个索引）

- 定义：找到数组中符合指定条件的第一个元素的索引
  - 如果元素符合条件，则返回该元素索引，且剩余元素不再检测
  - 如果没有元素符合条件，则返回 -1
- 注意：不会对空数组进行检查，不会改变原数组
- 例子：

```
let findIndexArr = [
  {
    id: 1
  },
  {
    id: 2
  },
  {
    id: 3
  }
]
let res = findIndexArr.findIndex(i => {
  console.log(1) // 1 1
  return i.id === 2
})
console.log(res) // 1
```

### 7. filter（筛选）

- 定义：筛选出符合条件的所有元素，返回一个新数组
- 注意：不会对空数组进行检查，不会改变原数组
- 例子：

```
let filterArr = [
  {
    id: 1
  },
  {
    id: 2
  },
  {
    id: 3
  }
]
let res = filterArr.filter(i => {
  console.log(1) // 1 1 1
  return i.id === 2
})
console.log(res) // [ { id: 2 } ]
```

### 8. map（处理）

- 定义：返回调用函数处理后的值，组成一个新数组
- 注意：不会对空数组进行检查，不会改变原数组
- 例子：

```
let mapArr = [
  {
    id: 1
  },
  {
    id: 2
  },
  {
    id: 3
  }
]
let res = mapArr.map(i => {
  console.log(1) // 1 1 1
  return i.id
})
console.log(res) // [1,2,3]
```

### 9. reduce

- 语法：arr.reduce((total,current,currentIndex,arr)=>{},initialValue)
- 例子：

```
// 求总和
let reduceArr = [1, 2, 3, 4]
let res = reduceArr.reduce((total, cur) => {
  console.log(1) // 1 1 1 1
  return total + cur
}, 0)
console.log(res) // 10
```

```
// 元素出现次数
let reduceArr = ['a', 'b', 'c', 'a']
let res = reduceArr.reduce((prev, cur) => {
  if (cur in prev) {
    prev[cur]++
  } else {
    prev[cur] = 1
  }
  return prev
}, {})
console.log(res) // { a: 2, b: 1, c: 1 }
```

```
// 数组去重
let reduceArr = ['1', '2', '4', '2']
let res = reduceArr.reduce((prev, cur) => {
  if (!prev.includes(cur)) {
    return prev.push(cur)
  }
  return prev
}, [])
console.log(res)
```
