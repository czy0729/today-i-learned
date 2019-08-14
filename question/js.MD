# JS 相关问题

#### 1. 用递归算法实现，数组长度为 5 且元素的随机数在 2-32 间不重复的值

描述：

这是一道大题目，把考点拆成了 4 个小项；需要侯选人用递归算法实现（限制 15 行代码以内实现；限制时间 10 分钟内完成）：

a) 生成一个长度为 5 的空数组 arr。

b) 生成一个（2－32）之间的随机整数 rand。

c) 把随机数 rand 插入到数组 arr 内，如果数组 arr 内已存在与 rand 相同的数字，则重新生成随机数 rand 并插入到 arr 内[需要使用递归实现，不能使用 for/while 等循环]

d) 最终输出一个长度为 5，且内容不重复的数组 arr。

<details><summary><b>解答</b></summary>
<p>

```js
// 6 行写完
function buildArray(arr, length, min, max) {
  var num = Math.floor(Math.random() * (max - min + 1)) + min;
  if (!arr.includes(num)) {
    arr.push(num);
  }
  return arr.length === length ? arr : buildArray(arr, length, min, max);
}
var result = buildArray([], 5, 2, 32);
console.table(result);
```

补充：

题目要求”生成一个（2－32）之间的随机整数 rand“，既然是随机，我觉得意为取值到区间内各数的概率应该是相等的。所以像这样的写法是不严谨的：

```
// 在 2 - 5 区间内生成随机数
var min = 2, max = 5;
var result = Math.max(min, Math.ceil(Math.random() * max));
// 参数一 p1 恒等于2
// 参数二 p2 在 [0, 5] 之间等概取值
// 可能性见下
// p1 2 2 2 2 2 2
// p2 0 1 2 3 4 5
// result 2 2 2 3 4 5
```

可见 result 取到 2 的概率大于 3/4/5。 @linghucq1

[来源](https://github.com/haizlin/fe-interview/issues/3#issuecomment-498971913)

</p>
</details>

---
