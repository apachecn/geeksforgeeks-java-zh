# Java 中关键字的实例

> 原文:[https://www.geeksforgeeks.org/instanceof-keyword-in-java/](https://www.geeksforgeeks.org/instanceof-keyword-in-java/)

instanceof 是一个关键字，用于检查引用变量是否包含给定类型的对象引用。下面是一个展示 instanceof 不同行为的 Java 程序。此后，它被称为比较运算符，其中**实例**与返回布尔真或假的**类型**进行比较，因为在 java 中，我们没有 0 和 1 布尔返回类型。

**示例:**

## Java

```java
// Java Program to Illustrate instanceof Keyword

// Importing required I/O classes
import java.io.*;

// Main class
class GFG {
    public static void main(String[] args)
    {

        // Creating object of class inside main()
        GFG object = new GFG();

        // Returning instanceof
        System.out.println(object instanceof GFG);
    }
}
```

**输出**

```java
true
```

**实现:**这里我们将创建具有父子关系的示例类。

**例 1:**

## Java

```java
// Java program to demonstrate working of instanceof Keyword

// Class 1
// Parent class
class Parent {}

// Class 2
// Child class
class Child extends Parent {}

// Class 3
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of child class
        Child cobj = new Child();

        // A simple case
        if (cobj instanceof Child)
            System.out.println("cobj is instance of Child");
        else
            System.out.println(
                "cobj is NOT instance of Child");

        // instanceof returning true for Parent class also
        if (cobj instanceof Parent)
            System.out.println(
                "cobj is instance of Parent");
        else
            System.out.println(
                "cobj is NOT instance of Parent");

        // instanceof returns true for all ancestors

        // Note : Object is ancestor of all classes in Java
        if (cobj instanceof Object)
            System.out.println(
                "cobj is instance of Object");
        else
            System.out.println(
                "cobj is NOT instance of Object");
    }
}
```

**输出**

```java
cobj is instance of Child
cobj is instance of Parent
cobj is instance of Object
```

**示例 2:** 为空返回假的实例

## Java

```java
// Java program to demonstrate that instanceof
// returns false for null

class Test {  }

class Main
{
    public static void main(String[] args)
    {
        Test tobj = null;

        // A simple case
        if (tobj instanceof Test)
           System.out.println("tobj is instance of Test");
        else
           System.out.println("tobj is NOT instance of Test");
    }
}
```

**输出:**

```java
tobj is NOT instance of Test
```

**示例 3:** 父对象不是子对象

## Java

```java
// A Java program to show that a parent object is
// not an instance of Child

class Parent {  }
class Child extends Parent { }

class Test
{
    public static void main(String[] args)
    {
        Parent pobj = new Parent();
        if (pobj instanceof Child)
           System.out.println("pobj is instance of Child");
        else
           System.out.println("pobj is NOT instance of Child");
    }
}
```

的实例

**输出:**

```java
pobj is NOT instance of Child
```

**示例 4:** 引用子代的父代引用是子代

## Java

```java
// A Java program to show that a parent reference
// referring to a Child is an instance of Child

class Parent {  }
class Child extends Parent { }

class Test
{
    public static void main(String[] args)
    {
        // Reference is Parent type but object is
        // of child type.
        Parent cobj = new Child();
        if (cobj instanceof Child)
           System.out.println("cobj is instance of Child");
        else
           System.out.println("cobj is NOT instance of Child");
    }
}
```

的实例

**输出:**

```java
cobj is an instance of Child
```

**现在**关键词的**应用实例如下:**

我们在这里看到当父类型的引用引用子对象时，父类数据成员被访问。我们可以使用[类型转换](https://www.geeksforgeeks.org/class-type-casting-in-java/)访问子数据成员。

**语法:**

```java
((child_class_name) Parent_Reference_variable).func.name()
```

当我们进行类型转换时，检查类型转换是否有效总是一个好主意。instanceof 在这里帮助我们。我们总是可以首先使用 instancef 检查有效性，然后进行类型转换。

**例**

## 爪哇

```java
// Java program to demonstrate that non-method
// members are accessed according to reference
// type (Unlike methods which are accessed according
// to the referred object)

class Parent
{
    int value = 1000;
}

class Child extends Parent
{
    int value = 10;
}

// Driver class
class Test
{
    public static void main(String[] args)
    {
        Parent cobj = new Child();
        Parent par = cobj;

        // Using instanceof to make sure that par
        // is a valid reference before typecasting
        if (par instanceof Child)
        {
            System.out.println("Value accessed through " +
                "parent reference with typecasting is " +
                                     ((Child)par).value);
        }
    }
}
```

**输出:**

```java
Value accessed through parent reference with typecasting is 10
```

本文由**闪烁泰亚吉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。