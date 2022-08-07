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

  