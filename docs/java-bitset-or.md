# Java BitSet | or()

> 原文:[https://www.geeksforgeeks.org/java-bitset-or/](https://www.geeksforgeeks.org/java-bitset-or/)

**先决条件:**[Java BitSet | Set 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)
BitSet 是在 **java.util** 包中定义的类。它创建一个由布尔值表示的位数组。
它用被调用的位集执行调用方位集的**逻辑或**。只有当该位集为真且位集参数的值为真时，才会设置该位集。
**语法:**

```java
public void and(BitSet set);
```

**示例:**

```java
Input : 
set1 : {1, 2, 4}
set2 : {2, 3, 4}

Output : After performing set1.or(set2)
set2 : {1, 2, 3, 4}
```

**程序:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program illustrating Bitset Class or() function.
import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet set1 = new BitSet();
        BitSet set2 = new BitSet(6);

        /* set is BitSet class method
        explained in next articles */
        set1.set(21);
        set1.set(45);
        set1.set(8);
        set1.set(23);

        // assign values to set2
        set2.set(12);
        set2.set(89);
        set2.set(21);
        set2.set(78);
        set2.set(93);
        set2.set(3);

        // Printing the 2 Bitsets
        System.out.println("set1 : " + set1);
        System.out.println("set2 : " + set2);

        // Performing logical AND
        // on set2 set with set1
        set2.or(set1);

        // set2 set after Performing AND
        System.out.println("After Performing OR :");
        System.out.println(set2);
    }
}
```

**Output:** 

```java
set1 : {8, 21, 23, 45}
set2 : {3, 12, 21, 78, 89, 93}
After Performing OR :
{3, 8, 12, 21, 23, 45, 78, 89, 93}
```

**相关文章:**

1.  [位集类示例集 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)
2.  [位集类示例集 2](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)
3.  [位集类示例集 3](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/)