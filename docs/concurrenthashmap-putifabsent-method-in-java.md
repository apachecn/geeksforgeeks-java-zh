# Java 中的 ConcurrentHashMap putIfAbsent()方法

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-putifabsent-method-in-Java/](https://www.geeksforgeeks.org/concurrenthashmap-putifabsent-method-in-java/)

**java . util . concurrenthashmap . putifbsent()**是 Java 中的内置函数，它接受一个键和值作为参数，如果指定的键没有映射到任何值，则映射它们。

**语法:**

```
chm.putIfAbsent*(key_elem, val_elem)*
```

**参数:**该函数接受两个参数，如下所述:

*   **key _ elem:** If **key _ elem** is not associated with any value, this parameter specifies the key to which the specified **val _ elem** is mapped.
*   **val _ elem:** This parameter specifies the value to be mapped to the specified **key _ elem** .

**返回值:**函数返回映射到键的现有值，如果之前没有值映射到键，则返回 null。

**异常:**当指定参数为空时，函数抛出[空指针异常](https://docs.oracle.com/javase/7/docs/api/java/lang/NullPointerException.html)。

下面的程序说明了 ConcurrentHashMap.putIfAbsent()方法:

**程序 1:** 现有键作为参数传递给函数。

```
// Java Program Demonstrate putIfAbsent()
// method of ConcurrentHashMap 

import java.util.concurrent.*;

class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {
        ConcurrentHashMap<Integer, String> chm = 
                     new ConcurrentHashMap<Integer, String>();

        chm.put(100, "Geeks");
        chm.put(101, "for");
        chm.put(102, "Geeks");
        chm.put(103, "Gfg");
        chm.put(104, "GFG");

        // Displaying the HashMap
        System.out.println("Initial Mappings are: "
                           + chm);

        // Inserting non-existing key along with value
        String returned_value = (String)chm.putIfAbsent(108, "All");

        // Verifying the returned value
        System.out.println("Returned value is: "
                           + returned_value);

        // Displayin the new map
        System.out.println("New mappings are: "
                           + chm);
    }
}
```

**输出:**

```
Initial Mappings are: {100=Geeks, 101=for, 102=Geeks, 103=Gfg, 104=GFG}
Returned value is: null
New mappings are: {100=Geeks, 101=for, 102=Geeks, 103=Gfg, 104=GFG, 108=All}

```

**程序 2:** 将一个不存在的键作为参数传递给函数。

```
// Java Program Demonstrate putIfAbsent()
// method of ConcurrentHashMap 

import java.util.concurrent.*;
class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {
        ConcurrentHashMap<Integer, String> chm = 
                          new ConcurrentHashMap<Integer, String>();

        chm.put(100, "Geeks");
        chm.put(101, "for");
        chm.put(102, "Geeks");
        chm.put(103, "Gfg");
        chm.put(104, "GFG");

        // Displaying the HashMap
        System.out.println("Initial Mappings are: "
                           + chm);

        // Inserting existing key along with value
        String returned_value = (String)chm.putIfAbsent(100, "All");

        // Verifying the returned value
        System.out.println("Returned value is: "
                           + returned_value);

        // Displayin the new map
        System.out.println("New mappings are: "
                           + chm);
    }
}
```

**输出:**

```
Initial Mappings are: {100=Geeks, 101=for, 102=Geeks, 103=Gfg, 104=GFG}
Returned value is: Geeks
New mappings are: {100=Geeks, 101=for, 102=Geeks, 103=Gfg, 104=GFG}

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrenthashmap . html # putIfAbsent()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html#putIfAbsent(java.lang.Object, java.lang.Object))