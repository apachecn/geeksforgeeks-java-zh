# Java 中静态和非静态嵌套类的区别

> 原文:[https://www . geesforgeks . org/静态和非静态嵌套 java 类的区别/](https://www.geeksforgeeks.org/difference-between-static-and-non-static-nested-class-in-java/)

[嵌套类](https://www.geeksforgeeks.org/nested-classes-java/)分为两类，即[静态](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)和[非静态](https://www.geeksforgeeks.org/difference-between-static-and-non-static-method-in-java/)。声明为静态的嵌套类称为静态嵌套类。非静态嵌套类称为内部类。

在 java 中，类可以是静态的，也可以是非静态的。所以让一个类静态和非静态有很大的区别。Java 中有两种类，一种叫做顶层类，另一种叫做嵌套类。顾名思义，顶级类是在“*中声明的类。java'* 文件。

另一方面，嵌套类在另一个类中声明。包含嵌套类的类称为外部类。在 Java 编程语言中，您不能使顶级类成为静态的。您只能将嵌套类设为静态或非静态。如果您使嵌套类成为非静态类，那么它也被称为内部类。

**用户案例:**

*   [静态嵌套类](https://www.geeksforgeeks.org/nested-classes-java/)
*   非静态嵌套类

**示例 1:** 静态嵌套类

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate
// static nested class

// Importing input output classes
import java.io.*;
// Importing all classes from
// java.util package
import java.util.*;

// Class 1
// Helper class1
class ClassA {

    // Static variable
    static int x = 10;

    int y = 20;

    // Static variable with privare
    // access modifier in ClassA
    private static int z = 30;

    // Class 2 - Nested static class
    // Helper Class 2
    static class ClassB {

        // Method of nested static class
        void get()
        {
            // Execution statements whenever
            // function is called

            // Print and display commands
            System.out.println("x: " + x);
            System.out.println("z: " + z);
        }
    }
}

// Class 3
// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of static nested class
        // defined outside Main class
        ClassA.ClassB ob1 = new ClassA.ClassB();

        // Calling the method od static nested class
        // in main() method
        ob1.get();
    }
}
```

**Output**

```
x: 10
z: 30
```

**示例 2:** 非静态嵌套类

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Importing all input output classes
import java.io.*;

// Class 1
// Helper Class 1
class ClassA {

    // Static member variable of ClassA
    static int x = 10;

    int y = 20;
    public int z = 30;

    // Class 2 - Helper Class 2
    // Non-static nested class
    class ClassB {

        // Method of Non-static nested class
        void get()
        {
            // Execution command of get() method

            // Print and display commands
            System.out.println("x: " + x);
            System.out.println("y: " + y);
            System.out.println("z: " + z);
        }
    }
}

// Class 3
// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of Class 1 in main() method
        ClassA ob1 = new ClassA();

        // Creating object of non-static nested class in
        // main()
        ClassA.ClassB ob2 = ob1.new ClassB();

        // Calling non-static nested class method
        // in main() method
        ob2.get();
    }
}
```

**Output**

```
x: 10
y: 20
z: 30
```

**现在 Java 中静态和非静态嵌套类的区别:**

*   静态内部类可以直接访问外部类的静态成员。但是，要访问外部类的实例成员，您需要实例化外部类。
*   嵌套静态类不需要外部类的引用，但是非静态嵌套类或内部类需要外部类的引用。
*   非静态嵌套类可以完全访问嵌套在其中的类的成员。静态嵌套类没有对嵌套实例的引用，因此静态嵌套类不能调用非静态方法或访问嵌套在其中的类实例的非静态字段。
*   静态和非静态嵌套类的另一个区别是，您不能直接将非静态成员(例如方法和字段)访问到嵌套静态类中。如果你这样做，你会得到像“非静态成员不能在静态上下文中使用”这样的错误。而内部类可以访问外部类的静态和非静态成员。