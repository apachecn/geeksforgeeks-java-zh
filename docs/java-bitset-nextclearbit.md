# Java 中的 BitSet nextClearBit()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-bit set-nextclearbit/

BitSet 是 java.util 包中定义的一个类。它创建一个由布尔值表示的位数组。

**先决条件:** [Java BitSet | Set 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)

**nextClearBit()方法:**
BitSet 类中的这个方法用于返回在指定的起始索引上或之后出现的第一个被设置为 false 的位的索引。

**语法:**

```
public int nextClearBit(int fromIndex)

```

**参数:**该方法采用强制参数 **fromIndex** ，即开始检查下一个错误位的索引(含)。

**返回值:**此方法返回下一个清零位的索引，即在指定的起始索引上或之后出现的第一个设置为 false 的位的索引。

**异常:**如果指定的指数为负，该方法抛出**指数。**

**示例 1:** 为了展示 nextClearBit()函数的实现:

```
// Java program illustrating Bitset
// nextClearBit() function.

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

        // Print the first clear bit of bs1
        System.out.println(bs1.nextClearBit(0));

        // Print the first clear bit of bs2 after index 3
        System.out.println(bs2.nextClearBit(3));
    }
}
```

**Output:**

```
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6, 12}
3
7

```

**示例 2:** 要显示 IndexOutOfBoundException 异常:

```
// Java program illustrating Bitset
// nextClearBit() function.

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
            System.out.println(bs1.nextClearBit(-1));
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

```
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6, 12}
Exception when negative index is passed as parameter : java.lang.IndexOutOfBoundsException: fromIndex < 0: -1

```