# Java 中方法重载和空错误

> 原文:[https://www . geesforgeks . org/method-overloading-null-error-Java/](https://www.geeksforgeeks.org/method-overloading-null-error-java/)

在 Java 中，重载方法是非常常见的。下面是一个有趣的 Java 程序。

```
public class Test
{
    // Overloaded methods
    public void fun(Integer i)
    {
        System.out.println("fun(Integer ) ");
    }
    public void fun(String name)
    {
        System.out.println("fun(String ) ");
    }

    // Driver code 
    public static void main(String [] args)
    {
        Test mv = new Test();

        // This line causes error
        mv.fun(null);
    }
}
```

输出:

```
22: error: reference to fun is ambiguous
        mv.fun(null);
          ^
  both method fun(Integer) in Test and method fun(String) in Test match
1 error
```

我们在上面的场景中得到编译时错误的原因是，这里的方法参数 Integer 和 String 在 Java 中都不是原始数据类型。这意味着他们接受空值。当我们将空值传递给 method1 时，编译器会混淆它必须选择哪个方法，因为两者都接受空值。
除非我们有意传递空值，否则这种编译时错误不会发生。例如，请看下面我们在编码时通常遵循的场景。

```
public class Test
{
    // Overloaded methods
    public void fun(Integer i)
    {
        System.out.println("fun(Integer ) ");
    }
    public void fun(String name)
    {
        System.out.println("fun(String ) ");
    }

    // Driver code
    public static void main(String [] args)
    {
        Test mv = new Test();

        Integer arg = null;

        // No compiler error
        mv.fun(arg);
    }
}
```

输出:

```
fun(Integer ) 

```

在上面的场景中，如果“arg”值由于表达式的结果而为 null，那么 null 值被传递给 method1。这里我们不会得到编译时错误，因为我们指定参数是整数类型，因此编译器选择 method1(Integer i)并执行其中的代码。

注意:当 overriden 方法参数是原始数据类型时，这个问题不会持续存在。因为编译器会选择最合适的方法并执行它。

本文由 **Nageswara Rao Maridu** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。