# Java 是严格按值传递的！

> 原文:[https://www . geesforgeks . org/g-fact-31-Java-is-严格按值传递/](https://www.geeksforgeeks.org/g-fact-31-java-is-strictly-pass-by-value/)

考虑下面的 Java 程序，它传递一个**原语类型**来运行。

```
public class Main
{
    public static void main(String[] args)
    {
        int x = 5;
        change(x);
        System.out.println(x);
    }
    public static void change(int x)
    {
        x = 10;
    }
}
```

输出:

```
5
```

我们向函数“change()”传递一个 int，结果该整数的值的变化没有反映在 main 方法中。像 C/C++一样，Java 创建一个在方法中传递的变量的副本，然后进行操作。因此，这种变化没有反映在主要方法中。

**物体或参照物怎么样？**

在 Java 中，像 int、char 等所有原语都类似于 C/C++，但所有非原语(或任何类的对象)总是引用。因此，当我们将对象引用传递给方法时，这变得很棘手。Java 创建引用的副本并将其传递给方法，但它们仍然指向相同的内存引用。意思是如果设置一些其他对象来引用在方法内部传递的对象，调用方法的对象及其引用将不受影响。

**如果我们将对象本身更改为引用某个其他位置或对象**
则更改不会反映回来如果我们将引用分配给某个其他位置，则更改不会反映回 main()。

```
// A Java program to show that references are also passed
// by value.
class Test
{
    int x;
    Test(int i) { x = i; }
    Test()      { x = 0; }
}

class Main
{
    public static void main(String[] args)
    {
        // t is a reference
        Test t = new Test(5);

        // Reference is passed and a copy of reference
        // is created in change()
        change(t);

        // Old value of t.x is printed
        System.out.println(t.x);
    }
    public static void change(Test t)
    {
        // We changed reference to refer some other location
        // now any changes made to reference are not reflected
        // back in main
        t = new Test();

        t.x = 10;
    }
}
```

输出:

```
5
```

**如果我们不将引用分配给新的位置或对象，更改会被反射回来:**
如果我们不将引用更改为引用其他对象(或内存位置)，我们可以对成员进行更改，这些更改会被反射回来。

```
// A Java program to show that we can change members using using
// reference if we do not change the reference itself.
class Test
{
    int x;
    Test(int i) { x = i; }
    Test()      { x = 0; }
}

class Main
{
    public static void main(String[] args)
    {
        // t is a reference
        Test t = new Test(5);

        // Reference is passed and a copy of reference
        // is created in change()
        change(t);

        // New value of x is printed
        System.out.println(t.x);
    }

    // This change() doesn't change the reference, it only
    // changes member of object referred by reference
    public static void change(Test t)
    {
        t.x = 10;
    }
}
```

输出:

```
10
```

**练习:**预测以下 Java 程序的输出

```
//  Test.java
class Main {
   // swap() doesn't swap i and j
   public static void swap(Integer i, Integer j) 
   {
      Integer temp = new Integer(i);
      i = j;
      j = temp;
   }
   public static void main(String[] args) 
   {
      Integer i = new Integer(10);
      Integer j = new Integer(20);
      swap(i, j);
      System.out.println("i = " + i + ", j = " + j);
   }
}
```

本文由**普拉哈尔·马图尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论