# Java 中的 NavigableMap higherEntry()方法

> 原文:[https://www . geesforgeks . org/naviglamblap-higher entry-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-higherentry-method-in-java/)

Java 中[导航映射接口的 higherEntry()方法用于返回与严格大于给定键的最小键相关联的键值映射，如果不存在这样的键，则返回 null。](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)

**语法** :

```
Map.Entry< K, V > higherEntry(K key)

```

其中，K 是该映射维护的键的类型，V 是映射到键的值的类型。

**参数**:该功能接受单个参数*键*，指的是该地图容器维护的键的类型。

**返回值**:返回与严格大于给定键的最小键相关联的键值映射，如果不存在这样的键，则返回空值。

下面的程序说明了 Java 中的 higherEntry()方法:

**程序 1** :按键为整数时。

```
// Java code to demonstrate the working of
// higherEntry() method

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

        System.out.println("The mapping with least key is : "
                           + nmmp.higherEntry(2));
    }
}
```

**输出:**

```
The mapping with least key is : 3=three

```

**程序二**:钥匙串的时候。

```
// Java code to demonstrate the working of
// higherEntry() method

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

        System.out.println("The mapping associated with the least key is : "
                           + tmmp.higherEntry("one"));
    }
}
```

**输出:**

```
The mapping associated with the least key is : six=seven

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/naviglamblemap . html # higher entry(K)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#higherEntry(K))