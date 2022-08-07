# emmet语法

* html基本结构
  * ! + tab(enter)  生成html的基本结构
* class和id
  * 标签名.类名
    * div.wrap + tab  =>  \<div class="wrap">\</div>
  * 标签名#id
    * div#wrap + tab  =>  \<div id="wrap">\</div>
* 重复（*）
  * div*2   =>  \<div>\</div>    \<br>\<div>\</div>

* 子节点（>）和兄弟节点(+)

  * div>p      =>  \<div>\<p>\</p>\</div>
  * div+p      =>  \<div>\</div>\<p>\</p>

* 属性([])

  * div>p>a[href="#"]*4

* 内容{}

  * div{00$}*2   => 

    ```
    <div>001</div>
    <div>002</div>
    ```

    

