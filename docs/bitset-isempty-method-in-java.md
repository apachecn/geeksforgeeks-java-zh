# Java 中的 BitSet isEmpty()方法

> 原文:[https://www . geesforgeks . org/bitset-isempty-method-in-Java/](https://www.geeksforgeeks.org/bitset-isempty-method-in-java/)

BitSet 是 java.util 包中定义的一个类。它创建一个由布尔值表示的位数组。

**先决条件:** [Java BitSet | Set 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)

**Bitset.isEmpty()**
此方法用于检查在指定的 Bitset 中是否有设置为 true 的位。如果该位集不包含设置为真的位，则该方法返回真。

**语法:**

```
public boolean isEmpty()
```

**返回值:**如果该位集不包含设置为真的位，该方法返回*真*。否则返回*假*。

下面的程序说明了 isEmpty()方法位集:

```
// Java program illustrating Bitset
// isEmpty() function.

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet();
        BitSet bs3 = new BitSet();

        /* set is BitSet class method
        expalined in next articles */
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

        // Printing the 2 Bitsets
        System.out.println("bs1 : " + bs1);
        System.out.println("bs2 : " + bs2);
        System.out.println("bs3 : " + bs3);

        // Performing isEmpty on bitsets
        System.out.println("Is bs1 empty : "
                           + bs1.isEmpty());
        System.out.println("Is bs2 empty : "
                           + bs2.isEmpty());
        System.out.println("Is bs3 empty : "
                           + bs3.isEmpty());
    }
}
```

**Output:**

```
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6}
bs3 : {}
Is bs1 empty : false
Is bs2 empty : false
Is bs3 empty : true

```