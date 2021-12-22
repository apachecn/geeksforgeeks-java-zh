# Java 中的 NavigableMap pollLastEntry()方法

> 原文:[https://www . geesforgeks . org/naviglamblemap-pollasterentry-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-polllastentry-method-in-java/)

Java 中[导航映射接口的 pollLastEntry()方法用于移除并返回与该映射中最大键相关联的键值映射，如果映射为空，则返回 null。](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)

**语法** :

```java
Map.Entry< K, V > pollLastEntry()

```

其中，K 是该映射维护的键的类型，V 是映射到键的值的类型。

**参数**:本功能不接受任何参数。

**返回值**:返回与该映射中最大键相关联的键值映射，如果映射为空，则返回空。

下面的程序说明了 Java 中的 pollLastEntry()方法:

**程序 1** :按键为整数时。

```java
// Java code to demonstrate the working of
// pollLastEntry() method

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

        System.out.println("Removed key-value associated with"+
                     " greatest key : " + nmmp.pollLastEntry());
    }
}
```

**输出:**

```java
Removed key-value associated with greatest key : 7=seven

```

**程序二**:钥匙串的时候。

```java
// Java code to demonstrate the working of
// pollLastEntry() method

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

        System.out.println("Removed key-value associated with"+
                  " greatest the key : " + tmmp.pollLastEntry());
    }
}
```

**输出:**

```java
Removed key-value associated with greatest the key : two=three

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/naviglamblemap . html # pollasterentry()](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#pollLastEntry())