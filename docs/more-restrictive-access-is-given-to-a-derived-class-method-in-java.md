# 对 Java 中派生类方法的更严格的访问

> 原文:[https://www . geeksforgeeks . org/更严格的访问是给 java 中的派生类方法的/](https://www.geeksforgeeks.org/more-restrictive-access-is-given-to-a-derived-class-method-in-java/)

因为私有、受保护和公共(访问修饰符)影响字段的可访问性和范围。因此，从类外部调用的方法不能是私有的。

在程序 1 中:我们为派生类创建对象并调用 foo 函数，但是这个 foo 函数是私有的，也就是说，它的作用域只在派生类中，当我们想通过 Main 类访问时，派生类会给出错误。

在程序 2 中:我们为派生类创建对象并调用 foo 函数，这个 foo 函数是公共的，所以这不会产生错误，因为我们可以从包中的任何地方访问它。

在程序 3 中:这里我们为基类创建对象，然后调用 foo 函数，现在派生类和基类中的 foo 函数都必须是公共的或受保护的(决不是私有的)，因为私有方法只在该范围内具有可访问性。

注意:被调用的函数永远不会是私有的，因为它的作用域只在花括号({})中。如果被调用的函数在基类中并且被派生类重写，那么派生类中被重写的方法也是公共的或受保护的。

**程序 1**

## Java

```java
// file name: Main.java
class Base {
    public void foo() { System.out.println("Base"); }
}

class Derived extends Base {

    // compiler error
    private void foo() { System.out.println("Derived"); }
}

public class Main {
    public static void main(String args[])
    {
        Derived d = new Derived();
        d.foo();
    }
}
```

**输出:**

```java
prog.java:10: error: foo() in Derived cannot override foo() in Base
    private void foo() { System.out.println("Derived"); } 
                 ^
  attempting to assign weaker access privileges; was public
prog.java:16: error: foo() has private access in Derived
        d.foo();
         ^
2 errors
```

**程序二**

T5】JavaT0T10**输出**T1

**程序 3**

## Java

```java
// file name: Main.java

class Base {
    public void foo() { System.out.println("Base"); }
}

class Derived extends Base {
    // if foo is private in derived class then it will
    // generate an error
    public void foo() { System.out.println("Derived"); }
}

public class Main {
    public static void main(String args[])
    {
        Base d = new Base();
        d.foo();
    }
}
```

**输出**

```java
Base

```

本文由 Khushi Agarwal 供稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。