# Java BitSet |交集()

> 原文:[https://www.geeksforgeeks.org/java-bitset-intersects/](https://www.geeksforgeeks.org/java-bitset-intersects/)

[位集](https://www.geeksforgeeks.org/bitset-class-java-set-1)是在 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中定义的一个类。它创建了一个由 0 和 1 表示的位数组。

**语法**

```
public boolean intersects(BitSet set)
```

**参数:**该方法接受一个强制参数**集**，这是要检查交集的位集。

**返回:**该方法返回一个布尔值，指示该位集是否与指定的位集相交。

**说明:**如果指定的位集中有任何设置为真的位在该位集中也设置为真，则该方法返回真，否则返回假。

**示例:**

```
Input : 
set1 : {1, 2, 4}
set2 : {}

Output : 
false
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

        // Performing intersects on two bitset
        System.out.println("bs1 intersection bs3 = "
                           + bs1.intersects(bs2));
        System.out.println("bs3 intersection bs1 = "
                           + bs3.intersects(bs1));
    }
}
```

**输出:**

```
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6}
bs3 : {}
bs1 intersection bs3 = true
bs3 intersection bs1 = false
```

**相关文章:**

1.  [Sample set of bit set class 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)
2.  [Sample set of bit set class 2](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)
3.  [Sample set of bit set class 3](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/)