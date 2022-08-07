# HTML与CSS面试

* 手写clearfix => 清除浮动代码

  ```html
  <style>
      .clearfix::after{
          content:"";
          display:block;
          clear:none;
      }
  </style>
  ```

* flex实现三色骰子

  * align-self主轴的对齐方式

  ```html
  <style>
          .wrap{
              display:flex;
              width: 120px;
              height: 120px;
              border: 1px solid #000;
          }
          .wrap .item{
              width: 40px;
              height: 40px;
              border-radius: 50%;
              background-color: #ccc;
          }
          .wrap .item:nth-child(2){
              align-self: center;
          }
          .wrap .item:nth-child(3){
              align-self: flex-end;
          }
      </style>
  </head>
  <body>
      <div class="wrap">
          <div class="item"></div>
          <div class="item"></div>
          <div class="item"></div>
      </div>
  </body>
  ```

* relative与absolute定位规则

  * relative相对自身定位
    * 不脱离文档流
  * absolute相对上一个有定位属性的祖先元素定位，若没有则body定位
    * 脱离文档流
      * 脱离文档流的方式
        * float
        * absolute
        * fixed相对于浏览器窗口html进行定位

* 元素水平居中(3 + 3)

  * inline/inlilne-block元素：text-align:center;
  * block元素：margin:0 auto;
  * absolute元素：left:50%;margin-left:负值一半元素宽度
  * absolute元素：left,right = 0;margin:0 auto;
  * absolute元素：left:50%;transform:translateX(-50%)
  * 弹性元素：默认父元素display:flex;justify-content:center;

* 垂直居中

  * line-height:center;
  * absolute元素：top:0;margin-top:负值一半元素的高度
  * absolute元素：top/bottom = 0;margin:auto 0;
  * absolute元素：top:50%;transform:translateY:-50%;
  * 弹性flex元素：父元素display:flex;子元素align-item:center;
  * 单元格table-cell元素：父元素display:table-cell;vertical-align:middle

* line-height如何继承

  * 父元素写具体数值，如30px，子元素则继承该数值
  * 父元素写比例，如2/1.5，子元素则继承该比例，子元素字体*该比例
  * 父元素写百分比，如200%，子元素则继承计算出来的值（父元素字体大小*该百分比）

* 单行文本溢出

  ```html1
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  ```

* 多行文本溢出

  ```
  overflow:hidden;
  text-overflow:ellipsis;//超出显示“……”
  display:-webkit-box;//将元素作为弹性伸缩盒子模型显示
  -webkit-line-clamp:2;//用来限制在一个块级元素显示的文本的行数
  -webkit-box-orient:vertical;//设置或检索伸缩盒对象的子元素的排列方式
  ```

* css消除图片底部间隙的方法
  * 图片块状化-无基线对齐：img{display:block;}
  * 图片底部对齐：img{vertical-align:bottom;}
  * 父级设置：font-size:0;
  * 行高足够小-基线位置上移：.box{line-height:0};
* rem是什么
  * px像素(Pixell)，绝对单位。像素px是相对于显示器屏幕分辨率而言的
  * em，相对长度单位，相对于父元素，不常用
  * rem，(root em)，相对长度单位，相对于根元素**html的字体大小**，常用语响应式布局
* 响应式布局的常用方案
  * media-query，根据不同的屏幕宽度设置根元素font-size
  * rem，基于根元素的相对单位
* transition和animation的区别
  * transition：用于做过渡效果，没有帧概念，只有开始和结束状态，性能开销较小，被动触发
  * animate：用于做动画有帧的概念，可以重复触发且有中间状态，性能开销较大，主动触发
* 使一个元素显示以及隐藏的方式
  * display:none;
    * 结构上：元素在页面上将彻底消失，元素不占据空间且无法点击
    * 继承性：父元素设置了display:none;子元素无论怎磨设置都无法显示
    * 性能：会引起浏览器重绘重排，性能消耗较大
  * opacity:0;
    * 结构上：元素在页面消失，其占据的空间依旧会保留，无法点击；
    * 继承性：visibility:hidden;会被子元素继承，但是子元素可以通过设置visibility:visible;来取消隐藏
    * 性能：只会导致浏览器重绘，性能消耗相对小
  * 其他方法
    * 设置元素的position与left/right/top/bottom等，将元素移除屏幕
    * 设置元素的position与z-index，将z-index设置成尽量小的负数
* css中Sprites是什么，它的优势和劣势是什么？
  * Sprites精灵图，把一堆小的图片整合到一张大的图片上
  * 优势：
    * 很好额减少网页的请求，大大提高页面的性能；
    * 减少图片的字节
    * 解决了网页设计师在图片命名上的困扰
    * 更换风格方便，维护方便
  * 劣势：
    * 图片合并时须预留好足够的空间，宽屏、高分辨率的屏幕下已出现背景断裂；
    * 开发较麻烦，测量繁琐（可食使用样式生成器）；
    * 维护麻烦，背景少许改动有可能影响整图片，似的字节增加还要改动css
* 什么是Css Hack?ie6,7,8的hack分别是什么?
  * 解决各浏览器对css解释不同所采取的，区别不同浏览器制作不同css样式的设置叫做css Hack.
  * 针对不同浏览器设置不同的css样式
* 什么是css预处理器/后处理器？大家为什么要使用他们？
  * 预处理器例如：LESS、Sass、Stylus，用来预编译Sass或less，增强了css代码的复用性，还有层级、mixin、变量、循环、函数等，具有很方便的UI组件模块化开发能力，极大地提高工作效率
  * 后处理器，例如：PostCSS，通常被视为在完成的样式表中根据css规范处理css，让其更有效；目前最常做的是给css属性添加浏览器私有前缀，实现跨浏览器兼容性的问题
* 介绍对浏览器内核的理解
  * 主要分为两部分：渲染引擎和js引擎
  * 渲染引擎：将代码转换成页面输出到浏览器界面
  * js引擎：解析和执行javascript来实现网页的动态效果
  * 最开始渲染引擎和js引擎并没有区分的很明确，后来js越来越独立，内核就倾向于只指渲染引擎
* 描述下渐进增强和优雅降级
  * 渐进增强：针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能，达到更好的用户体验
  * 优雅降级：一开始就构建完整的功能，然后再针对低版本的浏览器进行兼容