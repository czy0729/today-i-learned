# HTML 相关问题

#### 1. 页面导入样式时，使用 link 和 @import 有什么区别？

<details><summary><b>说明</b></summary>
<p>

区别：

1.link 是 HTML 标签，@import 是 css 提供的。

2.link 引入的样式页面加载时同时加载，@import 引入的样式需等页面加载完成后再加载。

3.link 没有兼容性问题，@import 不兼容 ie5 以下。

4.link 可以通过 js 操作 DOM 动态引入样式表改变样式，而@import 不可以。

[来源](https://github.com/haizlin/fe-interview/issues/1#issuecomment-484031196)

</p>
</details>

---
