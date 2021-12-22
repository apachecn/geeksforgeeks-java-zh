# Java 中的位集长度()方法，示例

> 原文:[https://www . geesforgeks . org/bitset-length-in-Java-method-with-examples/](https://www.geeksforgeeks.org/bitset-length-method-in-java-with-examples/)

Java 中 BitSet 类的 length()方法用来知道这个 BitSet 的逻辑大小。该逻辑大小等于位集的最高位加 1。

**语法:**

```
BitSet.hashCode()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回位集的逻辑大小，等于位集的最高位加 1。如果位集为空，该方法返回零。

以下程序用于说明 BitSet.length()的工作方法:
**程序 1:**

```
// Java code to illustrate length()
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

        // Displaying the length or logical size
        System.out.println("The Length is: "
                           + init_bitset.length());
    }
}
```

**Output:**

```
BitSet: {25, 31, 40, 53, 100}
The Length is: 101

```

**程序 2:**

```
// Java code to illustrate length()
import java.util.*;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet init_bitset = new BitSet();

        // Displaying the BitSet
        System.out.println("BitSet: " + init_bitset);

        // Displaying the hashcode
        System.out.println("The Length is: "
                           + init_bitset.length());
    }
}
```

**Output:**

```
BitSet: {}
The Length is: 0

```