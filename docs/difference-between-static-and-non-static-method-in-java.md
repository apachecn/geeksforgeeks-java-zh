# Java 中静态和非静态方法的区别

> 原文:[https://www . geesforgeks . org/静态和非静态 java 方法的区别/](https://www.geeksforgeeks.org/difference-between-static-and-non-static-method-in-java/)

一个**静态方法**是属于一个类的方法，但是它不属于那个类的实例，这个方法可以在没有那个类的实例或者对象的情况下调用。java 中的每个方法都默认为非静态方法，前面没有 **static** 关键字。**非静态**方法可以访问任何**静态**方法和**静态**变量，而无需创建对象的实例。让我们阐明这些差异，以下是这些指针之间的各种重要差异:

1.  访问成员和方法
2.  调用过程
3.  联编过程
4.  覆盖过程
5.  存储器分配

**#1:** 访问成员和方法

静态方法只能访问另一个类或同一类的静态数据成员和静态方法，但不能访问非静态方法和变量。此外，静态方法可以重写任何静态数据成员的值。

非静态方法可以访问静态数据成员和静态方法，也可以访问另一个类或同一类的非静态成员和方法，还可以更改任何静态数据成员的值

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate Calling of a Static Method

// Class 1
// Helper class
class Helper {

    // Static method
    public static int sum(int a, int b)
    {
        // Simply returning the sum
        return a + b;
    }
}

// Class 2
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Custom values for integer
        // to be summed up
        int n = 3, m = 6;

        // Calling the static method of above class
        // and storing sum in integer variable
        int s = Helper.sum(n, m);

        // Print and display the sum
        System.out.print("sum is = " + s);
    }
}
```

**Output**

```
sum is = 9
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate Calling of a Non-Static Method

// Class 1
// Helper class
class Helper {

    // Non-static method
    public int sum(int a, int b)
    {
        // Returning sum of numbers
        return a + b;
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Input integers to be summed up
        int n = 3, m = 6;

        // Creating object of above class
        Helper g = new Helper();

        // Calling above method to compute sum
        int s = g.sum(n, m);

        // Calling the non-static method
        System.out.print("sum is = " + s);
    }
}
```

**Output**

```
sum is = 9
```

**#2:** 调用过程

静态方法的内存固定在 ram 中，因此，我们不需要定义静态方法的类的对象来调用静态方法。要调用该方法，我们需要编写类名，后跟方法名

**语法:**静态方法的调用

```
class GFG{
 public static void geek()
 { }
}

// calling
GFG.geek();
```

非静态方法的内存不固定在 ram 中，所以我们需要一个类对象来调用非静态方法。要调用该方法，我们需要编写方法的名称，后跟类对象名称

**语法:**调用非静态方法

```
class GFG{
 public void geek()
 { }
}

// creating object
GFG g = new GFG();

g.geek();

// calling
```

**#3:** 绑定过程

在**静态**方法中，该方法使用编译时或早期绑定。因此，我们可以在不创建实例的情况下访问静态方法。在**非静态**方法中，该方法使用运行时或动态绑定。因此，如果不创建实例，我们就无法访问非静态方法。

**#4:** 覆盖

在**静态**方法中，由于早期绑定，我们不能覆盖静态方法。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Override of static method
class Parent {

    // static method
    static void show()
    {
        System.out.println("Parent");
    }
}

// Parent inherit in Child class
class Child extends Parent {

    // override show() of Parent
    void show()
    {
        System.out.println("Child");
    }
}

class GFG {
    public static void main(String[] args)
    {
        Parent p = new Parent();
        // calling Parent's show()
        p.show();
        // cannot override Parent's show()
    }
}
```

**输出:**

```
java:15: error: show() in Child cannot override show() in Parent
    void show()
         ^
  overridden method is static
```

在**非静态**方法中，我们可以覆盖一个非静态方法。因为对于覆盖，我们需要运行时多态性，这仅在运行时绑定中发生。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Override of non-static method

class Parent {
    void show()
    {
        System.out.println("Parent");
    }
}

// Parent inherit in Child class
class Child extends Parent {

    // override show() of Parent
    void show()
    {
        System.out.println("Child");
    }
}

class GFG {
    public static void main(String[] args)
    {
        Parent p = new Parent();
        // calling Parent's show()
        p.show();

        Parent c = new Child();
        // calling Child's show()
        c.show();
    }
}
```

**输出:**错误

```
Parent
Child
```

**#5:** 内存分配

在 **static** 方法中，内存分配只发生一次，因为 static 关键字在 ram 中为该方法固定了一个特定的内存。因此，当程序中每次调用该方法时，每次使用该特定内存时。因此，分配的内存更少。

在**非静态**方法中，这里的内存分配发生在方法被调用的时候，每次调用方法的时候都会分配内存。这里用了这么多内存。现在，最后绘制一张表格，以便大家一起掌握

<figure class="table">

| **点** | **静法** | **非静态法** |
| --- | --- | --- |
| **定义** | 一个**静态方法**是属于一个类的方法，但是它不属于那个类的实例，这个方法可以在没有那个类的实例或者对象的情况下调用。 | java 中的每个方法都默认为非静态方法，前面没有 **static** 关键字。**非静态**方法可以访问任何**静态**方法和**静态**变量，而不使用类的对象。 |
| **访问成员和方法** | 在**静态**方法中，该方法只能访问另一个类或同一个类的静态数据成员和静态方法，而不能访问非静态方法和变量。 | 在**非静态**方法中，该方法可以访问静态数据成员和静态方法，也可以访问另一个类或同一个类的非静态成员和方法。
 |
| **装订工序** | 静态方法使用编译时或早期绑定。 | 非静态方法使用运行时或动态绑定。 |
| **覆盖** | 由于早期绑定，无法重写静态方法。 | 由于运行时绑定，可以重写非静态方法。 |
| **内存分配** | 在 **static** 方法中，用于执行的内存较少，因为内存分配只发生一次，因为 static 关键字在 ram 中为该方法固定了特定的内存。
 | 在**非静态**方法中，大量内存用于执行，因为这里内存分配发生在方法被调用时，并且每次调用方法时都分配内存。
 |

</figure>