# Java 中的 NavigableMap floorEntry()方法

> 原文:[https://www . geeksforgeeks . org/navigablemap-floor entry-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-floorentry-method-in-java/)

Java 中 [NavigableMap 接口的 floorEntry()方法用于返回与小于或等于给定键的最大键相关联的键值映射，如果没有这样的键，则返回 null。](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)

**语法** :

```
Map.Entry<K, V> floorEntry(K key)

```

其中，key 是该地图维护的密钥。

**参数**:键–键

**返回值**:返回最大键值小于等于键值的条目，如果没有键值，返回空值。

下面的程序说明了 Java 中的 floorEntry()方法:

**程序 1** :按键为整数时。

```
// Java code to demonstrate the working of
// floorEntry() method

import java.io.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the NavigableMap of Integer and String
        NavigableMap<Integer, String> nmmp = new TreeMap<>();

        // assigning the values in the NavigableMap
        // using put()
        nmmp.put(2, "two");
        nmmp.put(7, "seven");
        nmmp.put(3, "three");

        System.out.println("The mapping with greatest key is : "
                           + nmmp.floorEntry(2));
    }
}
```

**输出:**

```
The mapping with greatest key is : 2=two

```

**程序二**:钥匙串的时候。

```
// Java code to demonstrate the working of
// floorEntry() method

import java.io.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the NavigableMap of Integer and String
        NavigableMap<String, String> tmmp = new TreeMap<>();

        // assigning the values in the NavigableMap
        // using put()
        tmmp.put("one", "two");
        tmmp.put("six", "seven");
        tmmp.put("two", "three");

        System.out.println("The mapping associated with greatest key is : "
                           + tmmp.floorEntry("one"));
    }
}
```

**输出:**

```
The mapping associated with greatest key is : one=two

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/naviglamblemap . html # floor entry(K)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#floorEntry(K))