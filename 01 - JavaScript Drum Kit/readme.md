# JavaScript30 Day01

>作者：W_peach
>简介：[JavaScript30](https://javascript30.com) 是 [Wes Bos](https://github.com/wesbos) 推出的一个 30 天挑战。
项目免费提供了 30 个视频教程、30 个挑战的起始文档和 30 个挑战解决方案源代码。
目的是帮助人们用纯 JavaScript 来写东西，不借助框架和库，也不使用编译器和引用。你现在看到的是我模拟Wes Bos大神写的第一个项目：鼓的模拟音乐盒子

## 实现效果

模拟一个打鼓页面，用户按下按钮或点击页面中的图标，如果出现页面中提示的几个键位，对应的鼓点音乐响起

## 实现逻辑

* 按键与对应键盘事件中的keyCode对应
* 点击事件与对应的keyCode对应
* 事件触发执行主题逻辑

## 注意事项

* 尽可能使用事件委托，减少for循环嵌套
* 关注方法的兼容问题，尽可能多的兼容大多数浏览器
* 函数主要逻辑中进行判断是否存在需要执行的事件目标，可以优化性能

## 我的实现方法

* 首先分析下这个需求，是要将页面中的按钮盒子和用户按钮行为关联起来。那我们是不是可以先取到所有的按钮盒子中的data-key属性值，并按顺序存储在一个数组中
* 然后先进行keydown事件委托，如果当前按下键位存在于按钮盒子['A', 'S', 'D', 'F', 'G', 'H', 'J', 'K', 'L']中，那么执行主要逻辑
* 主要逻辑包括取当前按键对应数组索引，用这个索引查找对应页面的DOM元素以及查找对应音频元素，给DOM执行动画并播放音频，动画执行完以后立即删除动画类名（playing）
* 执行完keydown事件以后，来完成click事件委托。首先点击页面元素，判断事件对象是否为按钮盒子或者其子元素，分别对点击按钮盒子和点击到按钮盒子的子元素进行处理，取出index
* 根据index来完成主要逻辑，方法与以上第3点类似。

## 与Wes Bos大神实现方法对比不足之处

* Wes使用的是es6方法，所以看起来代码简洁一些
* 在利用事件委托查找到当前事件对象对应的按钮盒子和音频元素的实现方法方面，我走了弯路，我是利用索引来关联；Wes是直接利用事件对象的keyCode对应查找页面中的当前元素，这种方法很nice
* 之前我利用定时器来移除动画类名(playing)，这是不好的，能不使用定时器尽量不要使用定时器。
后来我发现Wes利用了transitionend事件来进行处理，这是我没想到的，虽然有些兼容性问题，但是影响不大。而且性能上优化很多
* 写完这个项目发现自己对于基础知识的把握还很肤浅，没有去钻研。