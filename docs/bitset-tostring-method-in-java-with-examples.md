# Java 中的 BitSet toString()方法，带示例

> 原文:[https://www . geesforgeks . org/bitset-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bitset-tostring-method-in-java-with-examples/)

java.util.BitSet.toString()是 BitSet 类的一种内置方法，用于获取以“，”分隔的一组条目形式的集合位的字符串表示形式。所以基本上 toString()方法是用来把 BitSet 的所有元素转换成 String。除此之外，对于置位状态下的每个位索引，该索引的十进制表示也包含在结果中。

**语法:**

```java
Bit_Set.toString()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回由给定位集元素的字符串表示组成的集合。

下面的程序说明了 java.util.BitSet.toString()方法的工作:
**程序 1:**

```java
// Java code to illustrate toString()
import java.util.*;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet init_bitset = new BitSet();

        // Use set() method to add elements into the Set
        init_bitset.set(40);
        init_bitset.set(25);
        init_bitset.set(31);
        init_bitset.set(100);
        init_bitset.set(53);

        // Displaying the BitSet
        System.out.println("BitSet: " + init_bitset);

        // Displaying the toString() working
        System.out.println("The String representation: "
                           + init_bitset.toString());
    }
}
```

**Output:**

```java
BitSet: {25, 31, 40, 53, 100}
The String representation: {25, 31, 40, 53, 100}

```

**程序 2:**

```java
// Java code to illustrate toString()
import java.util.*;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet init_bitset = new BitSet();

        // Use set() method to add elements into the Set
        init_bitset.set(10);
        init_bitset.set(20);
        init_bitset.set(30);
        init_bitset.set(40);
        init_bitset.set(50);

        // Displaying the BitSet
        System.out.println("BitSet: " + init_bitset);

        // Displaying the toString() working
        System.out.println("The String representation: "
                           + init_bitset.toString());
    }
}
```

**Output:**

```java
BitSet: {10, 20, 30, 40, 50}
The String representation: {10, 20, 30, 40, 50}

```