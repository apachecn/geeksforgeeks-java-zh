# Java 中的 ConcurrentHashMap containsValue()方法

> 原文:[https://www . geesforgeks . org/concurrenthashmap-contains value-method-in-Java/](https://www.geeksforgeeks.org/concurrenthashmap-containsvalue-method-in-java/)

**java . util . concurrenthashmap . contains VaLue()**方法是 Java 中的内置函数，它接受一个值，如果一个或多个键映射到指定的值，则返回 true。此方法遍历整个哈希表。因此，它是一个比 containsKey()方法慢得多的函数。

**语法:**

```java
chm.containsValue*(Object val_element)*
```

**参数:**该方法接受对象类型的单个参数 **val_element** ，检查其是否映射到映射中的任何键。

**返回值:**如果指定的 **val_element** 映射到该*映射中的任意键，则该方法返回 true，否则返回 false。*

**异常:**当指定的**值 _ 元素**为空时，函数抛出[空指针异常](https://docs.oracle.com/javase/7/docs/api/java/lang/NullPointerException.html)。

下面的程序举例说明了**Java . util . concurrenthashmap . contains value()**方法的使用:

**程序 1:** 该程序涉及将整数值映射到字符串键。

```java
/* Java Program to demonstrate containsValue()
   method of ConcurrentHashMap */

import java.util.concurrent.*;
class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {
        ConcurrentHashMap<String, Integer> chm = 
                    new ConcurrentHashMap<String, Integer>();
        chm.put("Geeks", 120);
        chm.put("for", 11);
        chm.put("GeeksforGeeks", 15);
        chm.put("Gfg", 50);
        chm.put("GFG", 25);

        // Check whether a key is mapped to 100
        if (chm.containsValue(100)) {
            System.out.println("100 is mapped.");
        }
        else {
            System.out.println("100 is not mapped.");
        }

        // Check whether a key is mapped to 120
        if (chm.containsValue(120)) {
            System.out.println("120 is mapped.");
        }
        else {
            System.out.println("120 is not mapped.");
        }
    }
}
```

**输出:**

```java
100 is not mapped.
120 is mapped.

```

**程序 2:** 该程序涉及将字符串值映射到整数值键。

```java
/* Java Program to demonstrate containsValue()
   method of ConcurrentHashMap */

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

        // Check whether a key is mapped to Geeks
        if (chm.containsValue("Geeks")) {
            System.out.println("Geeks is mapped.");
        }
        else {
            System.out.println("Geeks is not mapped.");
        }

        // Check whether a key is mapped to GfG
        if (chm.containsValue("GfG")) {
            System.out.println("GfG is mapped.");
        }
        else {
            System.out.println("GfG is not mapped.");
        }
    }
}
```

**输出:**

```java
Geeks is mapped.
GfG is not mapped.

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrenthashmap . html # contains value()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html#containsValue(java.lang.Object))