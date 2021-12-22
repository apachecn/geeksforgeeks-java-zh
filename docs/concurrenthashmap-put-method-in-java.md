# Java 中的 ConcurrentHashMap put()方法

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-put-method-in-Java/](https://www.geeksforgeeks.org/concurrenthashmap-put-method-in-java/)

Java 中类[的 **put()** 方法 ConcurrentHashmap](https://www.geeksforgeeks.org/concurrenthashmap-in-java/)用来在这个映射中插入一个映射。它将参数作为(键、值)对。如果现有的键被传递了一个值，那么这个方法更新该键的值。否则，如果传递了一个新的对，那么这个对就会作为一个整体被插入。

**语法:**

```
public V put(K key, V value)
```

**参数:**该方法接受两个强制参数:

*   **键**:–与指定值相关联的键
*   **值**:–与指定键相关联的值

**返回值:**此方法返回与键关联的前一个值，如果没有键映射，则返回空值。

**异常:**如果指定的键或值为空，该方法将抛出**空指针异常**

下面是举例说明 put()方法:

**程序 1:** 当键时，传递的值是新的。

```
// Java program to demonstrate
// put() method

import java.util.concurrent.ConcurrentHashMap;
import java.util.*;

public class ConcurrentHashMapExample {

    public static void main(String[] args)
    {
        // Creating ConcurrentHashMap
        Map<String, String>
            my_cmmap = new ConcurrentHashMap<String, String>();

        // Adding elements to the map
        // using put() method
        my_cmmap.put("1", "1");
        my_cmmap.put("2", "1");
        my_cmmap.put("3", "1");
        my_cmmap.put("4", "1");
        my_cmmap.put("5", "1");
        my_cmmap.put("6", "1");

        // Printing the map
        System.out.print(my_cmmap);
    }
}
```

**Output:**

```
{1=1, 2=1, 3=1, 4=1, 5=1, 6=1}

```

**程序 2:** 当一个现有的键，值被传递。

```
// Java program to demonstrate
// put() method

import java.util.concurrent.ConcurrentHashMap;
import java.util.*;

public class ConcurrentHashMapExample {

    public static void main(String[] args)
    {
        // Creating ConcurrentHashMap
        Map<String, String>
            my_map = new ConcurrentHashMap<String, String>();

        // Variable to get the returned value by put()
        String returnedValue;

        // Adding elements to the map
        // using put() method
        // and printing the returned value each time
        returnedValue = my_map.put("Geek", "100");
        System.out.println("Map: " + my_map);
        System.out.println("Returned Value: " + returnedValue);
        System.out.println();

        returnedValue = my_map.put("Geek", "200");
        System.out.println("Map: " + my_map);
        System.out.println("Returned Value: " + returnedValue);
        System.out.println();

        returnedValue = my_map.put("Geek", "300");
        System.out.println("Map: " + my_map);
        System.out.println("Returned Value: " + returnedValue);
        System.out.println();

        returnedValue = my_map.put("Geek", "400");
        System.out.println("Map: " + my_map);
        System.out.println("Returned Value: " + returnedValue);
        System.out.println();

        returnedValue = my_map.put("Geek", "500");
        System.out.println("Map: " + my_map);
        System.out.println("Returned Value: " + returnedValue);
        System.out.println();

        System.out.print(my_map);
    }
}
```

**Output:**

```
Map: {Geek=100}
Returned Value: null

Map: {Geek=200}
Returned Value: 100

Map: {Geek=300}
Returned Value: 200

Map: {Geek=400}
Returned Value: 300

Map: {Geek=500}
Returned Value: 400

{Geek=500}

```

**程序 3:** 演示空指针异常

```
// Java program to demonstrate
// put() method

import java.util.concurrent.ConcurrentHashMap;
import java.util.*;

public class ConcurrentHashMapExample {

    public static void main(String[] args)
    {
        // Creating ConcurrentHashMap
        Map<String, String>
            my_cmmap = new ConcurrentHashMap<String, String>();

        // Adding elements to the map
        // using put() method
        my_cmmap.put("1", "1");
        my_cmmap.put("2", "1");
        my_cmmap.put("3", "1");
        my_cmmap.put("4", "1");
        my_cmmap.put("5", "1");
        my_cmmap.put("6", "1");

        // Printing the map
        System.out.println(my_cmmap + "\n");

        // When null key is passed
        try {
            System.out.println("When (null, \"10\") "
                               + "is passed as parameter:");
            my_cmmap.put(null, "10");
        }
        catch (Exception e) {
            System.out.println("Exception: " + e + "\n");
        }

        // When null value is passed
        try {
            System.out.println("When (\"10\", null) "
                               + "is passed as parameter:");
            my_cmmap.put("10", null);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e + "\n");
        }
    }
}
```

**Output:**

```
{1=1, 2=1, 3=1, 4=1, 5=1, 6=1}

When (null, "10") is passed as parameter:
Exception: java.lang.NullPointerException

When ("10", null) is passed as parameter:
Exception: java.lang.NullPointerException

```