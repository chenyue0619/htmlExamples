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

  