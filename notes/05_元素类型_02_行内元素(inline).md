# 行内元素(inline)

* 常见的行内元素
  * span  b  i  em  img  strong
* 行内元素 === 内联元素
* 特点
  * 不独占一行
  * 不可以设置宽高
    * 例外：img可以设置宽高
    * img是行内元素也是置换元素，特点与行内块元素一样
  * 默认宽高都为0，由里面的文字撑开
  * 左右外边距内边距边框有效，上下外边距内边距边框无效，对排版布局无效
  * 结构上：
    * 内部不能放块元素
    * 例外：a标签可以包裹块级元素(区域连接)
  * 解析空格