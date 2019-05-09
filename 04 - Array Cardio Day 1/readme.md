# JavaScript30 Day04

>作者：W_peach
>简介：[JavaScript30](https://javascript30.com) 是 [Wes Bos](https://github.com/wesbos) 推出的一个 30 天挑战。
项目免费提供了 30 个视频教程、30 个挑战的起始文档和 30 个挑战解决方案源代码。
目的是帮助人们用纯 JavaScript 来写东西，不借助框架和库，也不使用编译器和引用。你现在看到的是我模拟Wes Bos大神写的第四个项目：数组方法的运用

## 主要知识点

1. `Array.prototype.filter:` （数组过滤）得到一个满足所有条件的数组，返回一个新数组
2. `Array.prototype.map:` （数组映射）每个元素调用一个提供的函数后返回一个新数组
3. `Array.prototype.sort:` （数组排序）对原始数组进行排序并返回数组，默认排序顺序是根据字符串Unicode码点
4. `Array.prototype.reduce:` (数组累计器) 对数组的每个元素执行一个由您提供的reduce函数(升序执行)，将结果汇总为单个返回值

## 碰到的问题

+ 刚开始不知道怎么使用reduce方法，计算出的结果是一个字符串拼接出来的值，需要给reduce赋第二个参数，也就是初始值。
+ 排序默认是按照字符串Unicode码点比较，所以一般情况下是指定一个比较函数