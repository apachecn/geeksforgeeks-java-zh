# java 中 Java . lang . arrayindexoofboundsexception 示例

> 原文:[https://www . geesforgeks . org/Java-lang-arrayindexoutofboundsexception-in-Java-with-examples/](https://www.geeksforgeeks.org/java-lang-arrayindexoutofboundsexcepiton-in-java-with-examples/)

[是一个运行时异常，只在程序的执行状态下抛出。Java 编译器在编译过程中从不检查这个错误。](https://www.geeksforgeeks.org/understanding-array-indexoutofbounds-exception-in-java/)

java . lang . arrayindexoutofboundsexception 是 Java 中最常见的异常之一。 当程序员尝试访问数组中无效索引处的元素值时，就会出现这种情况。 这个异常是从 1.0 版开始用 Java 引入的。ArrayIndexOutOfBoundsException 可能由于许多原因而发生，例如当我们试图在负索引或大于数组-1 的大小的索引处访问数组中元素的值时。

下面是代码示例，显示了可能出现此错误的情况，并使用[试捕块](https://www.geeksforgeeks.org/try-catch-throw-and-throws-in-java/)处理和显示错误。

**情况 1:-在负指数下访问元素的值**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to show the ArrayIndexOutOfBoundsException
// while accessing element at negative index

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        try {
            int array[] = new int[] { 4, 1, 2, 6, 7 };
            // accessing element at index 2
            System.out.println("The element at index 2 is "
                               + array[2]);
            // accessing element at index -1
            // this will throw the
            // ArrayIndexOutOfBoundsException
            System.out.println("The element at index -1 is "
                               + array[-1]);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output**

```java
The element at index 2 is 2
java.lang.ArrayIndexOutOfBoundsException: Index -1 out of bounds for length 5

```

**情况 2:-** **访问索引大于数组大小的元素-1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to show the ArrayIndexOutOfBoundsException
// while accessing element at index greater then size of
// array -1

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        try {
            int array[] = new int[] { 4, 1, 2, 6, 7 };
            // accessing element at index 4
            System.out.println("The element at index 4 is "
                               + array[4]);
            // accessing element at index 6
            // this will throw the
            // ArrayIndexOutOfBoundsException
            System.out.println("The element at index 6 is "
                               + array[6]);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output**

```java
The element at index 4 is 7
java.lang.ArrayIndexOutOfBoundsException: Index 6 out of bounds for length 5

```