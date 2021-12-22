# Java 接口方法

> 原文:[https://www . geesforgeks . org/g-fact-47-Java-interface-methods/](https://www.geeksforgeeks.org/g-fact-47-java-interface-methods/)

有一个规则[接口的每一个成员都是唯一且唯一公开的，不管你是否定义](https://www.geeksforgeeks.org/g-fact-73/)。因此，当我们在实现接口的类中定义接口的方法时，我们必须给予它公共访问权，因为[子类不能将较弱的访问权分配给方法](https://www.geeksforgeeks.org/g-fact-69/)。
正如定义的那样，无论我们是否声明，接口中的每个方法都是公开的和抽象的。因此，在接口内部，以下方法声明是相同的。

```
void methodOne();
public Void methodOne();
abstract Void methodOne();
public abstract Void methodOne();

```

**public :** 使该方法可用于每个实现类。
**摘要:**实现类负责提供实现。
同样，我们不能对接口方法使用以下修饰符。

*   私人的
*   保护
*   最后的
*   静电
*   同步的
*   当地的
*   严格 fp

```
// A Simple Java program to demonstrate that
// interface methods must be public in 
// implementing class
interface A
{
    void fun();
}

class B implements A
{ 
    // If we change public to anything else,
    // we get compiler error
    public void fun()
    {
        System.out.println("fun()");
    }
}

class C
{
    public static void main(String[] args)
    {
        B b = new B();
        b.fun();
    }
}
```

输出:

```
fun()
```

如果我们在 B 类中将 fun()更改为任何非公共的内容，我们会得到编译器错误“试图分配较弱的访问权限；是公开的”

本文由**闪烁泰亚吉**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论