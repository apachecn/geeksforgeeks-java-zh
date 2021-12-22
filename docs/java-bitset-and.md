# Java BitSet |和

> 原文:[https://www.geeksforgeeks.org/java-bitset-and/](https://www.geeksforgeeks.org/java-bitset-and/)

**先决条件:**[Java BitSet | Set 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)
BitSet 是 java.util 包中定义的类。它创建一个由布尔值表示的位数组。
通过参数位设置，执行该目标位设置的**逻辑与**。修改该位集，以便当且仅当它最初具有值 true 并且位集参数中的相应位也具有值 true 时，其中的每个位都具有值 true。
**语法**

```java
public void and(BitSet set);
```

**例:**

```java
Input : 
set1 : {1, 2, 4}
set2 : {2, 3, 4}
Output : After performing st1.and(set2)
set2 : {2, 4}
```

**节目:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program illustrating Bitset Class constructors.
import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet(6);

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

        // Performing logical AND
        // on bs2 set with bs1
        bs2.and(bs1);

        // bs2 set after Performing AND
        System.out.println("\nAfter AND operation : ");
        System.out.println(bs2);
    }
}
```

**Output:** 

```java
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6}

After AND operation : 
{1, 2, 4}
```

**相关文章:**

1.  [位集类示例集 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)
2.  [位集类示例集 2](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)
3.  [位集类示例集 3](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/)