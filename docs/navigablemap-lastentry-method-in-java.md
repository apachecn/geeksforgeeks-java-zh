# Java 中的 NavigableMap lastEntry()方法

> 原文:[https://www . geesforgeks . org/naviglamblap-last entry-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-lastentry-method-in-java/)

Java 中[导航映射接口的 lastEntry()方法用于返回与该映射中最大键相关联的键值映射，如果该映射为空，则返回 null。](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)

**语法** :

```java
Map.Entry< K, V > lastEntry()

```

其中，K 是该映射维护的键的类型，V 是映射到键的值的类型。

**参数**:不接受任何参数。

**返回值**:返回与该映射中最大键相关联的键值映射，如果映射为空，则返回空。

下面的程序说明了 Java 中的 lastEntry()方法:

**程序 1** :按键为整数时。

```java
// Java code to demonstrate the working of
// lastEntry() method

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
                           + nmmp.lastEntry());
    }
}
```

**输出:**

```java
The mapping with greatest key is : 7=seven

```

**程序二**:钥匙串的时候。

```java
// Java code to demonstrate the working of
// lastEntry() method

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
                           + tmmp.lastEntry());
    }
}
```

**输出:**

```java
The mapping associated with greatest key is : two=three

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/naviglamblemap . html # LastEntry()](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#lastEntry())