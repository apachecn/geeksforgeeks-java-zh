# Java BitSet | cardinality()

> 原文:[https://www.geeksforgeeks.org/java-bitset-cardinality/](https://www.geeksforgeeks.org/java-bitset-cardinality/)

[位集](https://www.geeksforgeeks.org/bitset-class-java-set-1)是在 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中定义的一个类。它创建了一个由 0 和 1 表示的位数组。

**语法**

```
public int cardinality()
```

**说明:**

该方法返回该位集中的 1 个数。

**示例:**

```
Input : 
set1 : {1, 2, 4}
set2 : {}

Output : 
3
0
```

## Java

```
// Java program illustrating Bitset Class functions.
import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet();
        BitSet bs3 = new BitSet();

        /* set is BitSet class method
        explained in next articles */
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

        // Performing logical AND
        // on bs2 set with bs1
        System.out.println(bs1.cardinality());
        System.out.println(bs2.cardinality());
        System.out.println(bs3.cardinality());
    }
}
```

**输出:**

```
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6}
bs3 : {}
4
6
0
```

**相关文章:**

1.  [Sample set of bit set class 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)
2.  [Sample set of bit set class 2](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)
3.  [Sample set of bit set class 3](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/)