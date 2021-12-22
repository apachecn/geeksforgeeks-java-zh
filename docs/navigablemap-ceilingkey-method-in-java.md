# Java 中的 NavigableMap ceilingKey()方法

> 原文:[https://www . geesforgeks . org/naviglamblap-ceiling key-method-in-Java/](https://www.geeksforgeeks.org/navigablemap-ceilingkey-method-in-java/)

Java 中[导航映射接口的 ceilingKey()方法用于返回大于等于给定键的最小键，如果不存在这样的键，则返回 null。](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)

**语法** :

```java
K ceilingKey(K key)

```

其中，K 是此地图容器维护的密钥类型。

**参数**:接受单个参数*键*，该键是要映射的键，属于该集合接受的键类型。

**返回值**:返回大于等于给定键的最小键，如果不存在这样的键，则返回空。

下面的程序说明了 Java 中的 ceilingKey()方法:

**程序 1** :按键为整数时。

```java
// Java code to demonstrate the working of
// ceilingKey()  method

import java.io.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the NavigableMap of Integer and String
        NavigableMap<Integer, String> tmmp = new TreeMap<>();

        // assigning the values in the NavigableMap
        // using put()
        tmmp.put(2, "two");
        tmmp.put(7, "seven");
        tmmp.put(3, "three");

        // Use of ceilingKey()
        // returns 7( next greater key)
        System.out.println("The next greater key of 6 is : "
                           + tmmp.ceilingKey(6));

        // returns "null" as no value present
        // greater than or equal to number
        System.out.println("The next greater key of 3 is : " 
                                       + tmmp.ceilingKey(3));
    }
}
```

**输出:**

```java
The next greater key of 6 is : 7
The next greater key of 3 is : 3

```

**程序二**:钥匙串的时候。

```java
// Java code to demonstrate the working of
// ceilingKey()  method

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

        // Use of ceilingKey()
        // returns 7( next greater key)
        System.out.println("The next greater key of five is : "
                           + tmmp.ceilingKey("five"));

        // returns "null" as no value present
        // greater than or equal to number
        System.out.println("The next greater key of six is : " + 
                                         tmmp.ceilingKey("six"));
    }
}
```

**输出:**

```java
The next greater key of five is : one
The next greater key of six is : six

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/naviglamblemap . html # ceiling key(K)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableMap.html#ceilingKey(K))