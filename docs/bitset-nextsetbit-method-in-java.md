# Java 中的 BitSet nextSetBit()方法

> 原文:[https://www . geesforgeks . org/bitset-next setbit-method-in-Java/](https://www.geeksforgeeks.org/bitset-nextsetbit-method-in-java/)

BitSet 是 java.util 包中定义的一个类。它创建一个由布尔值表示的位数组。

**先决条件:** [Java BitSet | Set 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)

**nextSetBit()方法:**
BitSet 类中的这个方法用于返回设置为 true 的第一位的索引，该索引出现在指定的起始索引上或之后。如果不存在这样的位，则返回-1。

**语法:**

```java
public int nextSetBit(int fromIndex)

```

**参数:**该方法采用强制参数 **fromIndex** ，该参数是开始检查下一个真位的索引(含)。

**返回值:**该方法返回下一个设置位的索引，如果没有该位，则返回-1

**异常:**如果指定的指数为负，该方法抛出**指数。**

**注意:**要迭代位集中的真位，请使用以下循环:

```java
for (int i = bs.nextSetBit(0); i >= 0; i = bs.nextSetBit(i+1)) {
     // operate on index i here
 }
```

**例 1:** 为了展示 nextSetBit()函数的实现:

```java
// Java program illustrating Bitset
// nextSetBit() function.

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

        // Performing nextSetBit() on bitsets
        System.out.println(bs1.nextSetBit(2));
        System.out.println(bs2.nextSetBit(0));
        System.out.println(bs3.nextSetBit(3));
    }
}
```

**Output:**

```java
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6, 12}
bs3 : {}
2
1
-1

```

**示例 2:** 要显示 IndexOutOfBoundException 异常:

```java
// Java program illustrating Bitset
// nextSetBit() function.

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet();

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

        try {
            // Passing -1 as parameter
            System.out.println(bs1.nextSetBit(-1));
        }
        catch (Exception e) {
            System.out.println("Exception when "
                               + "negative index is passed "
                               + "as parameter : " + e);
        }
    }
}
```

**Output:**

```java
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6, 12}
Exception when negative index is passed as parameter : java.lang.IndexOutOfBoundsException: fromIndex < 0: -1

```