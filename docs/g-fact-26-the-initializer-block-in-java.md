# Java 中的初始化器块

> 原文:[https://www . geesforgeks . org/g-fact-26-the-initializer-block-in-Java/](https://www.geeksforgeeks.org/g-fact-26-the-initializer-block-in-java/)

初始值设定项块包含每当创建实例时总是执行的代码。它用于声明/初始化类的各种构造函数的公共部分。例如

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;
public class GFG
{
    // Initializer block starts..
    {
        // This code is executed before every constructor.
        System.out.println("Common part of constructors invoked !!");
    }
    // Initializer block ends

    public GFG()
    {
        System.out.println("Default Constructor invoked");
    }
    public GFG(int x)
    {
        System.out.println("Parameterized constructor invoked");
    }
    public static void main(String arr[])
    {
        GFG obj1, obj2;
        obj1 = new GFG();
        obj2 = new GFG(0);
    }
}
```

**输出:**

```java
Common part of constructors invoked!!
Default Constructor invoked
Common part of constructors invoked!!
Parameterized constructor invoked 
```

我们可以注意到，初始化器块的内容是在任何构造函数被调用时执行的(在构造函数的内容之前)
初始化构造函数和初始化器块的顺序无关紧要，初始化器块总是在构造函数之前执行。详见[本](https://ide.geeksforgeeks.org/X6V1dR)举例。
**关于实例初始化的更多细节，请参考下面的文章:**
[Java 中的实例初始化块(IIB)](https://www.geeksforgeeks.org/instance-initialization-block-iib-java/)
**如果我们想对一个类的所有对象执行一次一些代码，会怎么样？**
我们在 Java 中使用[静态块](https://www.geeksforgeeks.org/g-fact-79/)
本文由 **Ashutosh Singh** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息