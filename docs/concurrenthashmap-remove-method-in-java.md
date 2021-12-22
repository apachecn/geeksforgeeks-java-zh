# Java 中的 ConcurrentHashMap remove()方法

> 原文:[https://www . geesforgeks . org/concurrenthashmap-remove-method-in-Java/](https://www.geeksforgeeks.org/concurrenthashmap-remove-method-in-java/)

**A .移除(对象键)**

Java 中类[的**移除(对象键)**方法用于从地图中移除映射。如果该键在地图中不存在，则该函数不执行任何操作。](https://www.geeksforgeeks.org/concurrenthashmap-in-java/)

**语法:**

```java
public V remove(Object key)
```

**参数:**

```java
This method accepts a mandatory parameter key which is the key that needs to be removed
```

**返回值:**

```java
This method returns the previous value associated with key, 
or null if there was no mapping for key.
```

**例外:**

```java
This method throws NullPointerException if the specified key is null.
```

下面是说明 remove()方法的程序:

**程序一:**

## Java

```java
// Java program to demonstrate remove() method

import java.util.*;
import java.util.concurrent.ConcurrentHashMap;

public class ConcurrentHashMapExample {

    public static void main(String[] args)
    {
        // Creating ConcurrentHashMap
        Map<String, String> my_cmmap
            = new ConcurrentHashMap<String, String>();

        // Adding elements to the map
        // using put() method
        my_cmmap.put("1", "1");
        my_cmmap.put("2", "1");
        my_cmmap.put("3", "1");
        my_cmmap.put("4", "1");
        my_cmmap.put("5", "1");
        my_cmmap.put("6", "1");

        // Printing the map
        System.out.println("Map: " + my_cmmap);
        System.out.println();

        // Removing the mapping
        // with existing key 6
        // using remove() method
        String valueRemoved = my_cmmap.remove("6");

        // Printing the map after remove()
        System.out.println(
            "After removing mapping with key 6:");
        System.out.println("Map: " + my_cmmap);
        System.out.println("Value removed: "
                           + valueRemoved);
        System.out.println();

        // Removing the mapping
        // with non-existing key 10
        // using remove() method
        valueRemoved = my_cmmap.remove("10");

        // Printing the map after remove()
        System.out.println(
            "After removing mapping with key 10:");
        System.out.println("Map: " + my_cmmap);
        System.out.println("Value removed: "
                           + valueRemoved);
    }
}
```

**输出**

```java
Map: {1=1, 2=1, 3=1, 4=1, 5=1, 6=1}

After removing mapping with key 6:
Map: {1=1, 2=1, 3=1, 4=1, 5=1}
Value removed: 1

After removing mapping with key 10:
Map: {1=1, 2=1, 3=1, 4=1, 5=1}
Value removed: null

```

**程序 2:** 用空键

## 演示 NullPointerException Java

```java
// Java program to demonstrate remove() method

import java.util.*;
import java.util.concurrent.ConcurrentHashMap;

public class ConcurrentHashMapExample {

    public static void main(String[] args)
    {
        // Creating ConcurrentHashMap
        Map<String, String> my_cmmap
            = new ConcurrentHashMap<String, String>();

        // Adding elements to the map
        // using put() method
        my_cmmap.put("1", "1");
        my_cmmap.put("2", "1");
        my_cmmap.put("3", "1");
        my_cmmap.put("4", "1");
        my_cmmap.put("5", "1");
        my_cmmap.put("6", "1");

        // Printing the map
        System.out.println("Map: " + my_cmmap);
        System.out.println();

        try {
            // Removing the mapping with null key
            // using remove() method
            my_cmmap.remove(null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出**

```java
Map: {1=1, 2=1, 3=1, 4=1, 5=1, 6=1}

Exception: java.lang.NullPointerException

```