# Java 中的 ConcurrentHashMap putAll()方法

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-putall-method-in-Java/](https://www.geeksforgeeks.org/concurrenthashmap-putall-method-in-java/)

**java . util . concurrent . concurrenthashmap . Putall()**是 Java 中的一个内置函数，用于复制操作。该方法将所有元素(即映射)从一个 ConcurrentHashMap 复制到另一个。

**语法:**

```
new_conn_hash_map.putAll*(conn_hash_map)*
```

**参数:**函数接受一个 ConcurrentHashMap**conn _ hash _ map**作为它唯一的参数，并用*这个*映射复制它所有的映射。

**返回值:**该方法不返回值。

**异常:**当指定参数为空时，函数抛出[空指针异常](https://docs.oracle.com/javase/7/docs/api/java/lang/NullPointerException.html)。

下面的程序说明了 ConcurrentHashMap.putAll()方法:

**程序 1:** 该程序涉及将字符串值映射到整数键。

```
// Java Program Demonstrate putAll()
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

        // Displaying the existing HashMap
        System.out.println("Initial Mappings are: "
                           + chm);

        ConcurrentHashMap<Integer, String> new_chm = 
                            new ConcurrentHashMap<Integer, String>();
        new_chm.putAll(chm);

        // Displaying the new map
        System.out.println("New mappings are: "
                           + new_chm);
    }
}
```

**输出:**

```
Initial Mappings are: {100=Geeks, 101=for, 102=Geeks, 103=Gfg, 104=GFG}
New mappings are: {100=Geeks, 101=for, 102=Geeks, 103=Gfg, 104=GFG}

```

**程序 2:** 该程序涉及将整数值映射到字符串键。

```
// Java Program Demonstrate putAll()
// method of ConcurrentHashMap 

import java.util.concurrent.*;

class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {
        ConcurrentHashMap<String, Integer> chm = 
                   new ConcurrentHashMap<String, Integer>();
        chm.put("Gfg", 100);
        chm.put("GFG", 102);
        chm.put("GfG", 18);
        chm.put("gfg", 15);
        chm.put("gfG", 55);

        // Displaying the existing HashMap
        System.out.println("Initial Mappings are: "
                           + chm);

        ConcurrentHashMap<String, Integer> new_chm = 
                  new ConcurrentHashMap<String, Integer>();

        // Copying the contents
        new_chm.putAll(chm);

        // Inserting a new mapping
        new_chm.put("gFg", 22);
        // Displaying the new map
        System.out.println("New mappings are: "
                           + new_chm);
    }
}
```

**输出:**

```
Initial Mappings are: {Gfg=100, GFG=102, GfG=18, gfg=15, gfG=55}
New mappings are: {Gfg=100, GFG=102, GfG=18, gfg=15, gfG=55, gFg=22}

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrenthashmap . html # putAll()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html#putAll(java.util.Map))