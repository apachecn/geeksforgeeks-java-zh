# 为什么 Java 中没有继承构造函数？

> 原文:[https://www . geesforgeks . org/constructors-非继承-java/](https://www.geeksforgeeks.org/constructors-not-inherited-java/)

构造函数是一个代码块，它允许您创建一个类的对象，该对象与没有显式返回类型的类同名。

每当一个类(子类)扩展另一个类(父类)时，子类以变量和方法的形式从其超类继承状态和行为，但它不继承超类的构造函数，原因如下:

*   构造函数是特殊的，与类名同名。因此，如果构造函数在子类中被继承，那么子类将包含父类构造函数，这违反了构造函数应该与类名同名的约束。例如，请参见下面的代码:

    ```java
    class Parent {
        public Parent()
        {
        }

        public void print()
        {
        }
    }

    public class Child extends Parent {
        public Parent()
        {
        }
        public void print()
        {
        }

        public static void main(String[] args)
        {
            Child c1 = new Child(); // allowed
            Child c2 = new Parent(); // not allowed
        }
    }
    ```

    如果我们在子类中定义父类构造函数，它将给出返回类型的编译时错误，并将其视为一种方法。但是对于 print 方法，它不会产生任何编译时错误，并将其视为覆盖方法。

*   Now suppose that if constructors can be inherited, encapsulation is impossible. Because by using the constructor of the superclass, we can access/initialize the private members of the class.
*   Constructor cannot be called as a method. It is called when the object of the class is created, so it is meaningless to use the parent class constructor symbol to create a subclass object. That is, child c = new parent ();
*   Parent constructors are not inherited in subclasses, which is why super () is automatically added to subclasses constructors if there is no explicit call to super or this.

本文由**赛义德阿里汗**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。