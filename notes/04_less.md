# less

* 定义：

  * css预处理器
  * css的增强版，通过less可以编写更少的代码支持更强大的样式
  * less语法大致和css一致
  * 添加很多新特性，比如对变量的支持，mixin的支持
  * 浏览器无法直接执行less代码，要执行必须先将less转换成css，再由浏览器执行

* 注释

  * //单行注释不会编译到css文件
  * /**/多行注释才会编译到css文件里面

* 变量

  * 语法：

    * 定义新变量：@ + 变量名(驼峰)

    * 引用已有变量：$ + 属性名

      ```html
      @baseWidth:100px;
      @baseHeight:100px;
      @bgc:pink;
      
      .box{
          width:@baseWidth;
          height: @baseHeight;
          border:1px solid #000;
          background-color: @bgc;
          color:$background-color;
      
      }
      ```

  * 说明：

    * 在变量中可以储存一个任意的值

    * 编译到css文件里面会将相应的变量值赋予相应的属性

    * 一处定义，四处使用

  * 重复赋值会覆盖掉前面的定义

    ```
    @baseWidth:100px;
    @baseHeight:100px;
    @bgc:pink;
    .box{
    	@baseWidth:200px;//会覆盖掉之前的值
        width:@baseWidth;
        height: @baseHeight;
        border:1px solid #000;
        background-color: @bgc;
        color:$background-color;
    
    }
    ```

    