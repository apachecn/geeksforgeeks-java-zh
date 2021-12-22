# 抽象映射等于()Java 中的方法，示例

> 原文:[https://www . geesforgeks . org/abstract map-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-equals-method-in-java-with-examples/)

Java 中的 **AbstractMap.equals()** 方法用于检查两个映射之间的相等性。它验证作为参数传递的一个映射的元素是否等于这个映射的元素。

**语法:**

```
AbstractMap1.equals(*AbstractMap2*)
```

**参数:**该方法接受一个抽象哈希映射类型的参数 *ihashmap2* ，并引用要用该抽象映射检查其相等性的映射。

**返回值:**如果两个对象映射相等，则方法返回真，否则返回假。

下面的程序说明了 AbstractMap.equals()方法的工作原理:

**程序 1:**

```
// Java code to illustrate the equals() method
import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<Integer, String>
            abstract_hash1 = new IdentityHashMap<Integer, String>();

        AbstractMap<Integer, String>
            abstract_hash2 = new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        abstract_hash1.put(10, "Geeks");
        abstract_hash1.put(15, "4");
        abstract_hash1.put(20, "Geeks");
        abstract_hash1.put(25, "Welcomes");
        abstract_hash1.put(30, "You");

        // Mapping string values to int keys
        abstract_hash2.put(10, "Geeks");
        abstract_hash2.put(15, "4");
        abstract_hash2.put(20, "Geeks");
        abstract_hash2.put(25, "Welcomes");
        abstract_hash2.put(30, "You");

        // Displaying the AsbstractMap
        System.out.println("First Map: "
                           + abstract_hash1);

        // Displaying the final AbstractMap
        System.out.println("Second Map: "
                           + abstract_hash2);

        // Displaying the equality
        System.out.println("Equality: "
                           + abstract_hash1.equals(abstract_hash2));
    }
}
```

**Output:**

```
First Map: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
Second Map: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
Equality: true

```

**程序 2:**

```
// Java code to illustrate the equals() method

import java.util.*;

public class Abstract_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractMap
        AbstractMap<Integer, String>
            abstract_hash1 = new IdentityHashMap<Integer, String>();

        AbstractMap<Integer, String>
            abstract_hash2 = new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        abstract_hash1.put(10, "Geeks");
        abstract_hash1.put(15, "4");
        abstract_hash1.put(20, "Geeks");
        abstract_hash1.put(25, "Welcomes");
        abstract_hash1.put(30, "You");

        // Mapping string values to int keys
        abstract_hash2.put(10, "Geeks");
        abstract_hash2.put(15, "4");
        abstract_hash2.put(20, "Geek");
        abstract_hash2.put(25, "Welcomes");
        abstract_hash2.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("First Map: "
                           + abstract_hash1);

        // Displaying the final IdentityHashMap
        System.out.println("Second Map: "
                           + abstract_hash2);

        // Displaying the equality
        System.out.println("Equality: "
                           + abstract_hash1.equals(abstract_hash2));
    }
}
```

**Output:**

```
First Map: {10=Geeks, 30=You, 20=Geeks, 25=Welcomes, 15=4}
Second Map: {10=Geeks, 30=You, 20=Geek, 25=Welcomes, 15=4}
Equality: false

```