# 实例变量隐藏在 Java 中

> 原文:[https://www . geesforgeks . org/g-fact-46-instance-variable-hiding-in-Java/](https://www.geeksforgeeks.org/g-fact-46-instance-variable-hiding-in-java/)

在 Java 中，如果一个方法中有一个与实例变量同名的局部变量，那么这个局部变量就会隐藏这个实例变量。如果我们想反映对实例变量所做的更改，这可以借助[这个引用](http://geeksquiz.com/this-reference-in-java/)来实现。

```
class Test
{
    // Instance variable or member variable
    private int value = 10; 

    void method()
    {
        // This local variable hides instance variable
        int value = 40;

        System.out.println("Value of Instance variable :"
                            + this.value);
        System.out.println("Value of Local variable :"
                            + value);
    }
}

class UseTest
{
    public static void main(String args[])
    {
        Test obj1 = new Test();
        obj1.method();
    }
}
```

输出:

```
Value of Instance variable :10
Value of Local variable :40
```

本文由**闪烁泰亚吉**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论