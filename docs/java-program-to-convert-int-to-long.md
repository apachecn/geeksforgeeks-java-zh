# 将 int 转换为 long 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-int-to-long/](https://www.geeksforgeeks.org/java-program-to-convert-int-to-long/)

**Int** 是比 long 更小的数据类型。Int 是 32 位整数，long 是 64 位整数。它们都是原始数据类型，使用情况取决于数量有多大。

**示例:**

```java
Input: intnum = 5
Output: longnum = 5

Input: intnum = 56
Output: longnum = 56
```

**Int 可以通过两种简单的方式转换为 long:**

1.  用一个简单的任务。这被称为**隐式类型转换**或类型提升，编译器会自动将较小的数据类型转换为较大的数据类型。
2.  使用 java 中 long 包装类的 **valueOf()** 方法将 int 转换为 Long。

**1。** [**隐型铸造**](https://www.geeksforgeeks.org/type-conversion-java-examples/) **:**

*   在这种情况下，我们只是将整数数据类型分配给长数据类型。
*   由于与 long 相比，integer 是一种较小的数据类型，编译器会自动将 int 转换为 long，这称为隐式类型转换或类型提升。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// use of implicit type casting

import java.io.*;
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        int intnum = 5;

        // Implicit type casting , automatic
        // type conversion by compiler
        long longnum = intnum;

        // printin the data-type of longnum
        System.out.println(
            "Converted type : "
            + ((Object)longnum).getClass().getName());

        System.out.println("After converting into long:");
        System.out.println(longnum);
    }
}
```

**Output**

```java
Converted type : java.lang.Long
After converting into long:
5
```

**2。** [**龙法值**](https://www.geeksforgeeks.org/java-lang-long-valueof-method-with-examples/) **:**

*   在本例中，我们使用 long Wrapper 类的 **valueOf()** 方法将 int 转换为 Long。
*   valueOf()方法接受整数作为参数，并在转换后返回一个长值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert
// int to long using valueOf() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        int intnum = 56;
        Long longnum = Long.valueOf(intnum);

        // printing the datatype to
        // show longnum is of type
        // long contains data of intnum
        System.out.println(
            "Converted type : "
            + ((Object)longnum).getClass().getName());

        // accepts integer and
        // returns a long value
        System.out.println("After converting into long:"
                           + "\n" + longnum);
    }
}
```

**Output**

```java
Converted type : java.lang.Long
After converting into long:
56
```