# 显示不同访问级别的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到显示-不同访问级别/](https://www.geeksforgeeks.org/java-program-to-show-different-access-levels/)

程序中的访问级别可以通过访问修饰符的概念来引入。java 程序中的 Access Modifier 用于指定字段、方法、构造函数甚至类的范围。因此，我们可以通过对字段、构造函数、方法和类应用访问修饰符来改变它们的访问级别。有 4 种类型的访问修饰符，即:

<figure class="table">

| 接入改性剂 | **描述** |
| --- | --- |
| 公共 | 一个公共修改器的访问等级无处不在。它可以从类内、类外、包内甚至包外访问。 |
| 私有 | 私有修饰符的访问级别只在类内，修饰符在。不能从该类外部访问它。 |
|  | 受保护修饰符的访问级别是通过子类在包内(在中提到)和包外。如果不创建子类，则不能从包外部访问它。 |
| 默认 | 默认修改器的访问级别仅在包内。不能从包外部访问它。如果不指定任何访问级别，它将被设置为默认值。 |

</figure>

**实现:**访问修饰符用法

**示例 1:** 使用单个类显示访问修饰符

## Java

```
// java Program to illustrate One Single Class for Scope of
// Access modifiers

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Method 1
    public static void method1()
    {

        // Print statement for method with public type
        System.out.println(
            "This method uses Public access modifier");
    }

    // Method 2
    private static void method2()
    {

        // Print statement for method with private type
        System.out.println(
            "This method uses Private access modifier");
    }

    // Method 3
    protected static void method3()
    {

        // Print statement for method with protected type
        System.out.println(
            "This method uses Protected access modifier");
    }

    // Method 4
    static void method4()
    {

        // Print statement for static default type method
        System.out.println(
            "This method uses Default access modifier");
    }

    // Method 5
    // Main driver method
    public static void main(String[] args)
    {

        // Display message only
        System.out.println(
            "Various access modifiers being used in the same class");

        // Calling all the above methods in main() method
        // body
        method1();
        method2();
        method3();
        method4();
    }
}
```

**输出**

```
Various access modifiers being used in the same class
This method uses Public access modifier
This method uses Private access modifier
This method uses Protected access modifier
This method uses Default access modifier
```