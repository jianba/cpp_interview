# 53、如果软件除了问题（Bug），如何快速定位？主要方法有哪些？

打印输出/代码调试/日志记录/分析工具/找同事讨论。

1、二分法定位技巧

无论是有多复杂的代码，利用二分法定位技巧一般都是可以定位到问题所在。

从二分法定位技巧可以延伸出一些具体的处理bug的方法，比如：对输入数据二分、对代码版本二分、注释掉部分代码、在不同位置插入试探性代码、对运行环境二分。

2、IDE调试

IDE的VS debug的功能简直就是立竿见影。它可以加断点，单步调试。

单步调试可以让我们对代码逻辑，执行顺序，以及各种中间结果更加清晰。

至于本身容易出错的BUG，用IDE调试简直是再合适不过了。

3、重新读一遍程序

相对新手程序员来说，如果代码出现bug，可以重新读一遍程序。这种方法是最有效、最快速的 Debug 方式。

4、必杀，重写一遍

如果你发现无论如何也找不到BUG，而且代码只是复杂，本身不是很长，直接重写代码吧!

5、小黄鸭调试法

小黄鸭调试法是程序员们经常使用的调试代码方法之一。

小黄鸭不懂程序，所以我们可以向他解释每一行程序的作用，以此来激发灵感。 
