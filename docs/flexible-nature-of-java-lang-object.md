# Java . lang . object 的灵活特性

> 原文:[https://www . geesforgeks . org/flexible-nature-of-Java-lang-object/](https://www.geeksforgeeks.org/flexible-nature-of-java-lang-object/)

**我们都喜欢 python 的机制，在这里我们不必为变量的数据类型费心(不是吗！)**

**有趣的是，我们在 Java 中也有一个类，非常相似！**

**是的，你猜对了！是 java.lang.Object**

**例如，**

```java
// A Java program to demonstrate flexible nature of
// java.lang.Object
public class GFG
{
    public static void main(String arr[])
    {
        Object y;

        y = 'A';
        System.out.println(y.getClass().getName());

        y = 1;
        System.out.println(y.getClass().getName());

        y = "Hi";
        System.out.println(y.getClass().getName());

        y = 1.222;
        System.out.println(y.getClass().getName());

        y = false;
        System.out.println(y.getClass().getName());
    }
}
```

****输出:****

```java
java.lang.Character
java.lang.Integer
java.lang.String
java.lang.Double
java.lang.Boolean
```

**这种行为可以归因于 java.lang.Object 是所有其他类的超级类。因此，对象类型的引用变量实际上可以用来引用任何类的对象。因此，我们也可以在上面的代码中分配 y =新的输入流阅读器(System.in)！**

**本文由**阿舒托什·辛格**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论**