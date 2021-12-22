# 说明 Java 继承中的类加载和静态块

> 原文:[https://www . geesforgeks . org/installation-class-loading-and-static-blocks-in-Java-inheritation/](https://www.geeksforgeeks.org/illustrate-class-loading-and-static-blocks-in-java-inheritance/)

[类加载](https://www.geeksforgeeks.org/class-loading-and-static-blocks-execution-using-static-modifier-in-java/)表示读取*。类*将相应的二进制数据归档存储在方法区。对于每一个*。类*文件，JVM 会在方法区存储相应的信息。现在将继承合并到类加载中。在 java 继承中，JVM 将首先加载并初始化父类，然后加载并初始化子类。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate Class Loading

// Importing input output files
import java.io.*;

// Helper class 1
class A {

    // First static block of this class
    static
    {

        // Print message
        System.out.println(
            "Loading class A 1st static block ");
    }

    // Second static block of this class
    static
    {

        // Print message
        System.out.println(
            "Loading class A 2nd static block B.c="
            + B.c);
    }

    // Third static block of this class
    static
    {

        // Print message
        System.out.println(
            "Loading class A 3rd static block ");
    }

    static int a = 50;
    A() {}
}

// Helper class 2 extending from
// helper class 1
class B extends A {

    static
    {
        // Print message
        System.out.println(
            "Loading class B static block A.a=" + A.a);
    }

    static int c = 100;
}

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Execution statement in main class
        new B();
    }
}
```

**Output**

```java
Loading class A 1st static block 
Loading class A 2nd static block B.c=0
Loading class A 3rd static block 
Loading class B static block A.a=50
```