# BFC

* 块格式化上下文(block formatting context)
* 定义：
  * 一块独立的渲染区域，内部元素的渲染不会影响到边界以外的元素

* 形成BFC的常见条件
  * float属性补不为none
  * position为ablosute或fixed
  * display为inline-block，table-cell，table-caption，flex，inline-flex
  * overfloe不为visible
* 开启BFC特点作用
  * 开启BFC的元素不会被浮动元素覆盖
  * 开启BFC的元素父子外边距不会合并
  * 开启BFC的元素可以包含浮动的子元素(解决浮动高度塌陷)





