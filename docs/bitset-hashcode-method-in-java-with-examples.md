# Java 中的 BitSet hashCode 方法示例

> 原文:[https://www . geesforgeks . org/bitset-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bitset-hashcode-method-in-java-with-examples/)

Java 中 BitSet 类的 hashCode()方法用于获取特定这个 BitSet 的哈希代码值。这个返回的散列码值取决于被传递的位组的设置位。

**语法:**

```
BitSet.hashCode()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回位集的 hashcode 值。

以下程序用于说明 BitSet.hashCode()方法:
**程序 1:**

```
// Java code to illustrate HashCode()
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

        // Displaying the hashcode
        System.out.println("The HashCode: "
                           + init_bitset.hashCode());
    }
}
```

**Output:**

```
BitSet: {10, 20, 30, 40, 50}
The HashCode: 1075053010

```

**程序 2:**

```
// Java code to illustrate HashCode()
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
        init_bitset.set(48);
        init_bitset.set(53);

        // Displaying the BitSet
        System.out.println("BitSet: " + init_bitset);

        // Displaying the hashcode
        System.out.println("The HashCode: "
                           + init_bitset.hashCode());
    }
}
```

**Output:**

```
BitSet: {25, 31, 40, 48, 53}
The HashCode: -2111765038

```