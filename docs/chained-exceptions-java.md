# Java 中的链式异常

> 原文:[https://www.geeksforgeeks.org/chained-exceptions-java/](https://www.geeksforgeeks.org/chained-exceptions-java/)

链式异常允许将一个异常与另一个异常联系起来，即一个异常描述另一个异常的原因。例如，考虑一种情况，其中一个方法由于试图除以零而引发了一个算术异常，但是异常的实际原因是一个导致除数为零的输入/输出错误。该方法将只向调用方抛出算术异常。所以打电话的人不会知道异常的真正原因。链式异常用于这种情况。

支持 java 链式异常的可抛出类的构造函数:

1.  可抛出(可抛出原因):-其中原因是导致当前异常的异常。
2.  可抛出(字符串消息，可抛出原因):-其中消息是异常消息，原因是导致当前异常的异常。

支持 java 中链式异常的可抛出类的方法:

1.  getCause()方法:-该方法返回异常的实际原因。
2.  initCause(可抛出原因)方法:-该方法设置调用异常的原因。

使用链式异常的示例:

```
// Java program to demonstrate working of chained exceptions
public class ExceptionHandling
{
    public static void main(String[] args)
    {
        try
        {
            // Creating an exception
            NumberFormatException ex =
                       new NumberFormatException("Exception");

            // Setting a cause of the exception
            ex.initCause(new NullPointerException(
                      "This is actual cause of the exception"));

            // Throwing an exception with cause.
            throw ex;
        }

        catch(NumberFormatException ex)
        {
            // displaying the exception
            System.out.println(ex);

            // Getting the actual cause of the exception
            System.out.println(ex.getCause());
        }
    }
}
```

输出:

```
java.lang.NumberFormatException: Exception
java.lang.NullPointerException: This is actual cause of the exception

```

本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。