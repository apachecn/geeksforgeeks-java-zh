# Java 中用户自定义异常

> 原文:[https://www . geesforgeks . org/g-fact-32-用户定义-自定义-java 中的异常/](https://www.geeksforgeeks.org/g-fact-32-user-defined-custom-exception-in-java/)

Java 为我们创建自己的异常提供了便利，这些异常基本上是[异常](https://docs.oracle.com/javase/7/docs/api/java/lang/Exception.html)的派生类。例如，下面代码中的 MyException 扩展了异常类。

我们将字符串传递给超类的构造函数——异常，它是使用“getMessage()”函数在创建的对象上获得的。

```java
// A Class that represents use-defined expception
class MyException extends Exception
{
    public MyException(String s)
    {
        // Call constructor of parent Exception
        super(s);
    }
}

// A Class that uses above MyException
public class Main
{
    // Driver Program
    public static void main(String args[])
    {
        try
        {
            // Throw an object of user defined exception
            throw new MyException("GeeksGeeks");
        }
        catch (MyException ex)
        {
            System.out.println("Caught");

            // Print the message from MyException object
            System.out.println(ex.getMessage());
        }
    }
}
```

输出:

```java
Caught
GeeksGeeks
```

在上面的代码中，MyException 的构造函数需要一个字符串作为参数。使用 super()将字符串传递给父类 Exception 的构造函数。[异常](https://docs.oracle.com/javase/7/docs/api/java/lang/Exception.html)类的构造函数也可以不带参数调用，对 super 的调用不是强制的。

```java
// A Class that represents use-defined expception
class MyException extends Exception
{

}

// A Class that uses above MyException
public class setText
{
    // Driver Program
    public static void main(String args[])
    {
        try
        {
            // Throw an object of user defined exception
            throw new MyException();
        }
        catch (MyException ex)
        {
            System.out.println("Caught");
            System.out.println(ex.getMessage());
        }
    }
}
```

输出:

```java
Caught
null
```

本文由**普拉哈尔·马图尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。