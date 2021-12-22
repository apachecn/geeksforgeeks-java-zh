# Java 8 中的默认方法

> 原文:[https://www.geeksforgeeks.org/default-methods-java/](https://www.geeksforgeeks.org/default-methods-java/)

在 Java 8 之前，接口只能有抽象方法。这些方法的实现必须在单独的类中提供。因此，如果要在接口中添加新方法，那么它的实现代码必须在实现相同接口的类中提供。为了克服这个问题，Java 8 引入了默认方法的概念，它允许接口拥有带有实现的方法，而不影响实现接口的类。

```
// A simple program to Test Interface default
// methods in java
interface TestInterface
{
    // abstract method
    public void square(int a);

    // default method
    default void show()
    {
      System.out.println("Default Method Executed");
    }
}

class TestClass implements TestInterface
{
    // implementation of square abstract method
    public void square(int a)
    {
        System.out.println(a*a);
    }

    public static void main(String args[])
    {
        TestClass d = new TestClass();
        d.square(4);

        // default method executed
        d.show();
    }
}
```

输出:

```
 16
 Default Method Executed

```

引入默认方法是为了提供向后兼容性，以便现有接口可以使用 lambda 表达式，而无需实现实现类中的方法。默认方法也称为**防御者方法**或**虚拟扩展方法**。

**静态方法:**
接口也可以有静态方法，类似于类的静态方法。

```
// A simple Java program to TestClassnstrate static
// methods in java
interface TestInterface
{
    // abstract method
    public void square (int a);

    // static method
    static void show()
    {
        System.out.println("Static Method Executed");
    }
}

class TestClass implements TestInterface
{
    // Implementation of square abstract method
    public void square (int a)
    {
        System.out.println(a*a);
    }

    public static void main(String args[])
    {
        TestClass d = new TestClass();
        d.square(4);

        // Static method executed
        TestInterface.show();
    }
}
```

输出:

```
 16
 Static Method Executed
```

**缺省方法和多重继承**
如果两个实现的接口都包含具有相同方法签名的缺省方法，那么实现类应该明确指定使用哪个缺省方法，或者应该覆盖缺省方法。

```
// A simple Java program to demonstrate multiple
// inheritance through default methods.
interface TestInterface1
{
    // default method
    default void show()
    {
        System.out.println("Default TestInterface1");
    }
}

interface TestInterface2
{
    // Default method
    default void show()
    {
        System.out.println("Default TestInterface2");
    }
}

// Implementation class code
class TestClass implements TestInterface1, TestInterface2
{
    // Overriding default show method
    public void show()
    {
        // use super keyword to call the show
        // method of TestInterface1 interface
        TestInterface1.super.show();

        // use super keyword to call the show
        // method of TestInterface2 interface
        TestInterface2.super.show();
    }

    public static void main(String args[])
    {
        TestClass d = new TestClass();
        d.show();
    }
}
```

输出:

```
Default TestInterface1
Default TestInterface2
```

**要点:**

1.  接口可以有默认方法，稍后在 Java 8 中实现。
2.  接口也可以有静态方法，类似于类中的静态方法。
3.  引入默认方法是为了给旧接口提供向后兼容性，这样它们就可以拥有新的方法，而不会影响现有的代码。

本文由**阿卡什·奥哈**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。