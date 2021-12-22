# Java 中的 NavigableMap 钻地键()方法

> 原文:[https://www . geesforgeks . org/naviglamblap-floor key-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-floorkey-method-in-java/)

Java 中[naviglamblap 接口的 floorKey()方法用于返回小于等于给定键的最大键，如果没有该键则返回 null。](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)

**语法** :

```
K floorKey(K key)

```

其中，K 是该地图维护的密钥类型。

**参数**:该功能接受单个参数*键*，指的是该地图容器维护的键的类型。

**返回值**:返回小于等于给定键的最大键，如果没有该键则返回空。

下面的程序说明了 Java 中的 floorKey()方法:

**程序 1** :按键为整数时。

```
// Java code to demonstrate the working of
// floorKey() method

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

        System.out.println("The mapping with greatest"
                           + " key is : " + nmmp.floorKey(7));
    }
}
```

**输出:**

```
The mapping with greatest key is : 7

```

**程序二**:钥匙串的时候。

```
// Java code to demonstrate the working of
// floorKey() method

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

        System.out.println("The mapping associated with greatest"
                           + " key is : " + tmmp.floorKey("one"));
    }
}
```

**输出:**

```
The mapping associated with greatest key is : one

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/naviglamblemap . html #钻地(K)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#floorKey(K))