# Java 中的 BitSet previousClearBit()方法

> 原文:[https://www . geesforgeks . org/bitset-previousclearbit-method-in-Java/](https://www.geeksforgeeks.org/bitset-previousclearbit-method-in-java/)

BitSet 是 java.util 包中定义的一个类。它创建一个由布尔值表示的位数组。

**先决条件:** [Java BitSet | Set 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)

**bitset . previousclearbit()**
此方法用于查找作为参数传递的索引上或之前出现的假位。此方法返回发生在指定起始索引上或之前的设置为 false 的最近位的索引。如果不存在这样的位，或者如果给定-1 作为起始索引，则返回-1。

**语法:**

```java
public int previousClearBit(int fromIndex)
```

**参数:**该方法取 **fromIndex** 作为开始检查的索引(含)。

**返回值:**该方法返回前一个清零位的索引，如果没有该位则返回-1

**异常:**如果指定的索引小于-1，该方法抛出**indexout of boundsexception**。

下面的程序举例说明了 previousCleatBit()方法:

**程序 1:**

```java
// Java program illustrating Bitset
// previousClearBit() function

import java.util.*;
public class GFG
{
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet();
        BitSet bs3 = new BitSet();

        /* assigning values to set1*/
        bs1.set(0);
        //bs1.set(1);
        bs1.set(2);
        bs1.set(4);

        // assign values to bs2
        bs2.set(4);
        bs2.set(6);
        bs2.set(5);
        bs2.set(1);
        bs2.set(2);
        bs2.set(3);
        bs2.set(12);

        // Printing the 2 Bitsets
        System.out.println("bs1 : " + bs1);
        System.out.println("bs2 : " + bs2);
        System.out.println("bs3 : " + bs3);

        // Performing previousClearBit() on bitsets
        System.out.println("Previous Clear Bit of bs1"
+ bs1.previousClearBit(0));
        System.out.println("Previous Clear Bit of bs2"
+ bs2.previousClearBit(5));
        System.out.println("Previous Clear Bit of bs3"
+ bs3.previousClearBit(3));

    }
} 
```

**Output:**

```java
bs1 : {0, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6, 12}
bs3 : {}
Previous Clear Bit of bs1-1
Previous Clear Bit of bs20
Previous Clear Bit of bs33

```

**程序 2:** 显示 IndexOutOfBoundException 异常:

```java
// Java program illustrating Bitset
// previousClearBit() function.

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();

        // assigning values to set1
        bs1.set(0);
        bs1.set(1);
        bs1.set(2);
        bs1.set(4);

        // Printing the Bitset
        System.out.println("bs1 : " + bs1);

        try {
            // Passing -2 as parameter
            System.out.println(bs1.previousClearBit(-2));
        }
        catch (Exception e) {
            System.out.println("Exception when "
                               + "index less than -1 is passed "
                               + "as parameter : " + e);
        }
    }
}
```

**Output:**

```java
bs1 : {0, 1, 2, 4}
Exception when index less than -1 is passed as parameter : java.lang.IndexOutOfBoundsException: fromIndex < -1: -2

```