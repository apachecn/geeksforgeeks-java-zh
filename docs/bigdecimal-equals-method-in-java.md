# Java 中 BigDecimal 等于()的方法

> 原文:[https://www . geesforgeks . org/big decimal-equals-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-equals-method-in-java/)

**Java . math . BigDecimal . equals()**方法检查一个 *BigDecimal* 值与传递的对象是否相等。只有当两个大十进制对象的值和比例相等时，此方法才认为它们相等。

**语法:**

```java
public boolean equals(*Object obj*)
```

**参数:**该函数接受一个对象*对象*作为与*这个*大十进制对象进行比较的强制参数。

**返回值:**当且仅当作为参数传递的对象是一个*大十进制*且其值和比例与该*大十进制对象的值和比例相等时，该方法返回布尔真，否则返回假。因此，该函数在比较 124.0 和 124.0000 时不会返回 true。*

**示例:**

```java
Input: 
b1 = new BigDecimal("4743.00")
b2 = new BigDecimal("4743.00000")
Output: false

Input: 
b1 = new BigDecimal(4743)
b2 = new BigDecimal("4743")
Output: true

```

下面的程序说明了 BigDecimal 类的 equals()方法:
**程序 1:**

```java
// Java program to demonstrate equals() method

import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigDecimal objects
        BigDecimal b1, b2;

        b1 = new BigDecimal("4743.00");
        b2 = new BigDecimal("4743.00000");

        if (b1.equals(b2)) {
            System.out.println(b1 + " and " + b2 + " are equal.");
        }
        else {
            System.out.println(b1 + " and " + b2 + " are not equal.");
        }
    }
}
```

**Output:**

```java
4743.00 and 4743.00000 are not equal.

```

**程序 2:**

```java
// Java program to demonstrate equals() method

import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigDecimal objects
        BigDecimal b1, b2;

        b1 = new BigDecimal(67891);
        b2 = new BigDecimal("67891");

        if (b1.equals(b2)) {
            System.out.println(b1 + " and " + b2 + " are equal.");
        }
        else {
            System.out.println(b1 + " and " + b2 + " are not equal.");
        }
    }
}
```

**Output:**

```java
67891 and 67891 are equal.

```