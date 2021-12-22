# Java 中的 BitSet 克隆()方法，示例

> 原文:[https://www . geesforgeks . org/bitset-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bitset-clone-method-in-java-with-examples/)

clone()方法 Java.util.BitSet 类用于创建现有 BitSet 的副本。新的位集与现有的位集完全相同，只是先前位集的副本。

**语法:**

```java
Bit_Set.clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法只是返回现有位集的另一个副本。

下面的程序说明了 BitSet clone()方法在 Java 中的工作原理。
**节目一:**

```java
// Java code to illustrate clone()
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
        System.out.println("Initial BitSet: " + init_bitset);

        // Creating a new cloned set
        BitSet cloned_set = new BitSet();

        // Cloning the set using clone() method
        cloned_set = (BitSet)init_bitset.clone();

        // Displaying the new Set after Cloning
        System.out.println("The new BitSet: " + cloned_set);
    }
}
```

**Output:**

```java
Initial BitSet: {10, 20, 30, 40, 50}
The new BitSet: {10, 20, 30, 40, 50}

```

**程序 2:**

```java
// Java code to illustrate clone()
import java.util.*;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet init_bitset = new BitSet();

        // Use set() method to add elements into the Set
        init_bitset.set(40);
        init_bitset.set(25);
        init_bitset.set(80);
        init_bitset.set(95);
        init_bitset.set(5);

        // Displaying the BitSet
        System.out.println("Initial BitSet: " + init_bitset);

        // Creating a new cloned set
        BitSet cloned_set = new BitSet();

        // Cloning the set using clone() method
        cloned_set = (BitSet)init_bitset.clone();

        // Displaying the new Set after Cloning
        System.out.println("The new BitSet: " + cloned_set);
    }
}
```

**Output:**

```java
Initial BitSet: {5, 25, 40, 80, 95}
The new BitSet: {5, 25, 40, 80, 95}

```