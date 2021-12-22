# 继承类的 Java 对象创建

> 原文:[https://www . geesforgeks . org/gfact-52-Java-对象-创建继承类/](https://www.geeksforgeeks.org/gfact-52-java-object-creation-of-inherited-classes/)

在继承中，子类获取超类属性。需要注意的一点是，创建子类对象时，不会创建超类对象的单独对象。只创建了一个具有超类变量的子类对象。

这种情况不同于通常假设的构造函数调用意味着类的一个对象被创建，所以我们不能盲目地说，每当一个类构造函数被执行时，那个类的对象就被创建或不被创建。

```java
// A Java program to demonstrate that both super class
// and subclass constructors refer to same object

// super class
class Fruit
{
    public Fruit()
    {
        System.out.println("Super class constructor");
        System.out.println("Super class object hashcode :" +
                           this.hashCode());
        System.out.println(this.getClass().getName());
    }
}

// sub class
class Apple extends Fruit
{
    public Apple()
    {
        System.out.println("Subclass constructor invoked");
        System.out.println("Sub class object hashcode :" +
                           this.hashCode());
        System.out.println(this.hashCode() + "   " +
                           super.hashCode());

        System.out.println(this.getClass().getName() + "  " +
                           super.getClass().getName());
    }
}

// driver class
public class Test
{
    public static void main(String[] args)
    {
        Apple myApple = new Apple();
    }
}
```

输出:

```java
super class constructor 
super class object hashcode :366712642
Apple
sub class constructor 
sub class object hashcode :366712642
366712642   366712642
Apple  Apple

```

我们可以看到，超类(水果)对象 hashcode 和子类(苹果)对象 hashcode 都是相同的，所以只创建了一个对象。这个对象属于苹果类(子类)，因为当我们试图打印创建的对象的类名时，它正在打印苹果子类。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。