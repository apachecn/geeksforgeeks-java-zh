# Java ConcurrentHashMap | clear()

> 原文:[https://www.geeksforgeeks.org/java-concurrenthashmap-clear/](https://www.geeksforgeeks.org/java-concurrenthashmap-clear/)

**先决条件:**[ConcurrentHashmap Java](https://www.geeksforgeeks.org/concurrenthashmap-in-java/)

**clear()方法**
使用 Java . util . concurrenthashmap . clear()方法来清除映射。它用于从 ConcurrentHashMap 中移除映射。

**语法:**

```java
public void clear()
```

```java
// Java program to demonstrate
// clear() method

import java.util.concurrent.ConcurrentHashMap;
import java.util.*;

public class ConcurrentHashMapExample {

    public static void main(String[] args)
    {

        // Creating a ConcurrentHashMap
        Map<String, String> my_cmmap = new ConcurrentHashMap<String, String>();

        // Inserting mappings in ConcurrentHashMap
        // with the help of put() method
        my_cmmap.put("1", "1");
        my_cmmap.put("2", "1");
        my_cmmap.put("3", "1");
        my_cmmap.put("4", "1");
        my_cmmap.put("5", "1");
        my_cmmap.put("6", "1");

        // Print the ConcurrentHashMap
        System.out.println("Map before use of clear(): \n"
                           + my_cmmap);

        // Now clear the map using clear()
        my_cmmap.clear();

        // Print the clea Map
        System.out.println("Map after use of clear(): "
                           + my_cmmap);
    }
}
```

**Output:**

```java
Map before use of clear(): 
{1=1, 2=1, 3=1, 4=1, 5=1, 6=1}
Map after use of clear(): {}

```

**例 2:**

```java
// Java program to demonstrate
// clear() method

import java.util.concurrent.ConcurrentHashMap;
import java.util.*;

public class ConcurrentHashMapExample {

    public static void main(String[] args)
    {
        // Creating a ConcurrentHashMap
        Map<String, String> my_map = new ConcurrentHashMap<String, String>();

        // Inserting mappings in ConcurrentHashMap
        // with the help of put() method
        my_map.put("Geeks", "100");
        my_map.put("Geek2", "150");
        my_map.put("Geeks3", "120");
        my_map.put("Geek4", "111");
        my_map.put("Geek5", "110");
        my_map.put("Geek6", "100");

        // Print the ConcurrentHashMap
        System.out.println("Map before use of clear(): \n"
                           + my_map);

        // Now clear the map using clear()
        my_map.clear();

        // Print the cleared Map
        System.out.println("Map after use of clear(): "
                           + my_map);
    }
}
```

**Output:**

```java
Map before use of clear(): 
{Geeks3=120, Geek6=100, Geek5=110, Geek4=111, Geeks=100, Geek2=150}
Map after use of clear(): {}

```