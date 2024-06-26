# 159、Qt当中的show和exec区别？

在Qt中，show和exec都是用来显示对话框的方法，它们的主要区别在于它们的运行机制和返回值。

show方法是在当前线程中显示对话框并立即返回，该方法不会阻塞当前线程，因此当对话框显示后，程序会继续执行后续代码。如果在对话框显示期间需要执行一些其他操作，可以在对话框关闭事件中处理，或者使用Qt的事件循环机制（如QEventLoop）来阻塞程序执行。

exec方法是在当前线程中显示对话框，并且阻塞当前线程，直到用户关闭对话框为止。在执行exec方法后，程序会进入一个事件循环（QEventLoop），直到对话框关闭事件被触发。因此，如果需要在对话框关闭之前执行一些其他操作，需要在对话框关闭事件之前处理。

需要注意的是，show方法和exec方法都可以用来显示对话框，但是它们的使用场景不同。show方法通常用于显示模态对话框和非模态对话框，而exec方法通常用于显示模态对话框。如果需要在对话框显示期间执行一些其他操作，建议使用show方法，如果需要等待用户关闭对话框后再执行其他操作，建议使用exec方法。
