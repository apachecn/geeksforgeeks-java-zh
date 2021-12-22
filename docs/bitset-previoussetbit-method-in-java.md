# Java 中的 BitSet previousSetBit()方法

> 原文:[https://www . geesforgeks . org/bitset-previoussetbit-method-in-Java/](https://www.geeksforgeeks.org/bitset-previoussetbit-method-in-java/)

BitSet 是 java.util 包中定义的一个类。它创建一个由布尔值表示的位数组。

**先决条件:** [Java BitSet | Set 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)

**bitset . previoussetbit()**
此方法用于查找在指定的起始索引上或之前是否有真实位出现。
此函数返回发生在指定起始索引上或之前的设置为真的最近位的索引。如果不存在这样的位，或者如果给定-1 作为起始索引，则返回-1。

**语法:**

```java
public int previousSetBit(int fromIndex)
```

**参数:**该方法采用强制参数**从索引**开始，从该索引开始检查(含)出现在该从索引上或之前的真实位。

**返回值:**此方法返回在指定索引上或之前出现的前一个设置位的索引，如果没有该位，则返回-1。

**异常:**如果指定的索引小于-1，该方法抛出**indexout of boundsexception**。

**注意:**要迭代位集中的真位，请使用以下循环:

```java
for (int i = bs.length(); (i = bs.previousSetBit(i-1)) >= 0; ) {
     // operate on index i here
 }
```

下面的程序说明了 previousSetBit()方法:

**示例 1:** 显示 previousSetBit()函数的实现:

```java
// Java program illustrating Bitset
// previousSetBit() function.

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet();
        BitSet bs3 = new BitSet();

        /* assigning values to set1*/
        bs1.set(0);
        bs1.set(1);
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

        // Performing length() on bitsets
        System.out.println("Previous Set Bit of bs1 "
                           + bs1.previousSetBit(2));
        System.out.println("Previous Set Bit of bs2 "
                           + bs2.previousSetBit(1));
        System.out.println("Previous Set Bit of bs3 "
                           + bs3.previousSetBit(3));
    }
}
```

**Output:**

```java
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6, 12}
bs3 : {}
Previous Set Bit of bs1 2
Previous Set Bit of bs2 1
Previous Set Bit of bs3 -1

```

**示例 2:** 要显示 IndexOutOfBoundException 异常:

```java
// Java program illustrating Bitset
// previousSetBit() function.

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
            System.out.println(bs1.previousSetBit(-2));
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