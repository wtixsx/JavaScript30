# JavaScript30 Day02

>作者：W_peach
>简介：[JavaScript30](https://javascript30.com) 是 [Wes Bos](https://github.com/wesbos) 推出的一个 30 天挑战。
项目免费提供了 30 个视频教程、30 个挑战的起始文档和 30 个挑战解决方案源代码。
目的是帮助人们用纯 JavaScript 来写东西，不借助框架和库，也不使用编译器和引用。你现在看到的是我模拟Wes Bos大神写的第二个项目：模拟时钟

## 实现效果

模拟时钟运行，每秒钟更新一下，对应的时分秒针分别进行跳动

## 实现逻辑

* 获取本地时间，取出对应的时、分、秒的数值
* 利用该数值换算出指针应该过渡的角度
* 没秒触发一次设置时间函数

## 注意事项

* 在时钟初始化的时候需要将所有指针指向0时刻

## 总结

这个功能模拟作者的写法写的，只不过我用es5的语法，没有特别值得提醒的地方，主要是Date()的运用