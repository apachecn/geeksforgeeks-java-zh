# Java 中的位集大小()方法，示例

> 原文:[https://www . geesforgeks . org/bitset-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bitset-size-method-in-java-with-examples/)

Java 中 BitSet 类的 size()方法用来知道这个 BitSet 的大小。这个大小等于比特组中每个元素所占的比特数。集合中最大的元素是大小-第一个元素

**语法:**

```
BitSet.hashCode()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回位集中存在的位数。

以下程序用于说明 BitSet.size()的工作方法:
**程序 1:**

```
// Java code to illustrate size()
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

        // Displaying the size
        System.out.println("The size is: "
                           + init_bitset.size());
    }
}
```

**Output:**

```
BitSet: {25, 31, 40, 53, 100}
The size is: 128

```

**程序 2:**

```
// Java code to illustrate size()
import java.util.*;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet init_bitset = new BitSet();

        // Displaying the BitSet
        System.out.println("BitSet: " + init_bitset);

        // Displaying the hashcode
        System.out.println("The s iizes: "
                           + init_bitset.size());
    }
}
```

**Output:**

```
BitSet: {}
The size is: 64

```

**程序 3:**

```
// Java code to illustrate size()
import java.util.*;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet init_bitset = new BitSet();

        // Use set() method to add elements into the Set
        init_bitset.set(400);

        // Displaying the BitSet
        System.out.println("BitSet: " + init_bitset);

        // Displaying the hashcode
        System.out.println("The sizeis: " + init_bitset.size());
    }
}
```

**Output:**

```
BitSet: {400}
The size is: 448

```