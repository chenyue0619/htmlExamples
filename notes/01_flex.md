##### 1、什么是弹性布局

​	**display:[flex](https://so.csdn.net/so/search?q=flex&spm=1001.2101.3001.7020)** 

* 意思是弹性布局，它能够<u>扩展</u>和<u>收缩</u> flex 容器内的元素，以最大限度地填充可用空间。
* Flex是Flexible Box的缩写，意为”弹性布局”，用来为盒状模型提供最大的灵活性。

#####  2、**设为Flex布局以后，子元素的float、clear和vertical-align属性将失效。**

它可以用于以下四个方面：

* 在不同方向排列元素
* 重新排列元素的显示顺序
* 更改元素的对齐方式
* 动态地将元素装入容器

##### 3、容器的属性

```
https://blog.csdn.net/weixin_41044151/article/details/114071215
```

##### 4、flex的原理

* flex属性 是 flex-grow、flex-shrink、flex-basis三个属性的缩写。
* flex:1即为flex-grow：1，经常用作自适应布局，将父容器的display：flex，侧边栏大小固定后，将内容区flex：1，内容区则会自动放大占满剩余空间

```
https://blog.csdn.net/Amnesiac666/article/details/122129201
```

