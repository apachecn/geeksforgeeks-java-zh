# Java 中的 NavigableMap ceilingEntry()方法

> 原文:[https://www . geesforgeks . org/naviglamblemap-ceilingentry-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-ceilingentry-method-in-java/)

Java 中[导航映射接口的 cielingEntry()方法用于返回与大于或等于给定键的最小键相关联的键值映射，如果不存在这样的键，则返回 null。](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)

**语法** :

```java
Map.Entry< K, V > ceilingEntry(K key)

```

**参数**:接受单个参数*键*，这是要映射的键。

**返回值**:返回与大于等于给定键的最小键相关联的键值映射，如果不存在这样的键，则返回空值。

下面的程序说明了 Java 中的 ceilingEntry()方法:

**程序 1** :按键为整数时。

```java
// Java code to demonstrate the working of
// ceilingEntry()  method

import java.io.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the NavigableMap of Integer and String
        NavigableMap<Integer, String> navmap = new TreeMap<>();

        // assigning the values in the NavigableMap
        // using put()
        navmap.put(2, "two");
        navmap.put(7, "seven");
        navmap.put(3, "three");

        // Use of ceilingEntry()
        // returns 7=seven ( next greater key-value)
        System.out.println("The next greater key-value of 5 is : "
                           + navmap.ceilingEntry(5));

        // returns "null" as no value present
        // greater than or equal to number
        System.out.println("The next greater key-value of 8 is : "
                                      + navmap.ceilingEntry(8));
    }
}
```

**输出:**

```java
The next greater key-value of 5 is : 7=seven
The next greater key-value of 8 is : null

```

**程序 2** :当按键为字符串时。

```java
// Java code to demonstrate the working of
// ceilingEntry()  method

import java.io.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the NavigableMap of String and String
        NavigableMap<String, String> navmap = new TreeMap<String, String>();

        // assigning the values in the NavigableMap
        // using put()
        navmap.put("one", "Geeks");
        navmap.put("two", "for");
        navmap.put("three", "Geeks");

        // Use of ceilingEntry()
        // returns one = Geeks ( next greater key-value of "a")
        System.out.println("The next greater key-value of a is : "
                           + navmap.ceilingEntry("a"));

        // returns three = Geeks
        System.out.println("The next greater key-value of p is : "
                                       + navmap.ceilingEntry("p"));
    }
}
```

**输出:**

```java
The next greater key-value of a is : one=Geeks
The next greater key-value of p is : three=Geeks

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/naviglamblemap . html # ceilingEntry(K)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#ceilingEntry(K))