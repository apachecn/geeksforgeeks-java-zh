# Java 中的 ConcurrentHashMap compute()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-compute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrenthashmap-compute-method-in-java-with-examples/)

**ConcurrentHashMap 类**的**计算(键，双功能)**方法用于计算指定键及其当前映射值的映射(如果没有找到当前映射，则为空)。

*   This method is used to automatically update the value of a given key in ConcurrentHashMap.
*   If the remapping function throws an exception, it throws an exception again, and the current mapping remains unchanged.
*   During the calculation, the updating process of this mapping by other threads has been blocked, so the calculation must not try to update any other mappings of this mapping.
*   For example, this mapping appends the mapped string value:

    ```java
    ConcurrentHashMap.compute(key, 
    (key, value) -> (value == null) ? msg : value.concat(msg))

    ```

**语法:**

```java
public V 
       compute(K key,
               BiFunction<? super K, ? super V, 
                  ? extends V> remappingFunction)
```

**参数:**该方法接受两个参数:

*   **键**:与数值相关联的键。
*   **重编程功能**:对数值进行运算的功能。

**返回:**该方法返回与指定键关联的**新值，如果没有则返回空值**。

**异常:**如果指定的键或 remappingFunction 为空，此方法将引发以下异常:

*   **[null pointer exception:** .
*   [T0】 llegalstatexception: 【T1] If the calculation attempts to recursively update the map, otherwise the update will never be completed.
*   **Runtime Exception:** If remappingFunction does this, the mapping will not change in this case.

以下程序说明了计算(键，双功能)方法:

**程序 1:**

```java
// Java program to demonstrate
// compute(Key, BiFunction) method.

import java.util.concurrent.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a ConcurrentHashMap and add some values
        ConcurrentHashMap<String, Integer>
            map = new ConcurrentHashMap<>();
        map.put("Book1", 10);
        map.put("Book2", 500);
        map.put("Book3", 400);

        // print map details
        System.out.println("ConcurrentHashMap: "
                           + map.toString());

        // remap the values of ConcurrentHashMap
        // using compute method
        map.compute("Book2", (key, val)
                                 -> val + 100);
        map.compute("Book1", (key, val)
                                 -> val + 512);

        // print new mapping
        System.out.println("New ConcurrentHashMap: "
                           + map);
    }
}
```

**输出:**

```java
ConcurrentHashMap: {Book3=400, Book1=10, Book2=500}
New ConcurrentHashMap: {Book3=400, Book1=522, Book2=600}

```

**程序二:**

```java
// Java program to demonstrate
// compute(Key, BiFunction) method.

import java.util.concurrent.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a ConcurrentHashMap and add some values
        ConcurrentHashMap<Integer, String>
            map = new ConcurrentHashMap<>();
        map.put(1, "Kolkata");
        map.put(2, "Nadia");
        map.put(3, "Howrah");

        // print map details
        System.out.println("ConcurrentHashMap: "
                           + map.toString());

        // remap the values of ConcurrentHashMap
        // using compute method
        map.compute(2, (key, val)
                           -> val.concat(" (West-Bengal)"));
        map.compute(3, (key, val)
                           -> val.concat(" (West-Bengal)"));

        // print new mapping
        System.out.println("New ConcurrentHashMap: "
                           + map);
    }
}
```

**输出:**

```java
ConcurrentHashMap: {1=Kolkata, 2=Nadia, 3=Howrah}
New ConcurrentHashMap: {1=Kolkata, 2=Nadia (West-Bengal), 3=Howrah (West-Bengal)}

```

**程序 3:** 显示空指针异常

```java
// Java program to demonstrate NullPointerException
// for compute(Key, BiFunction) method.

import java.util.concurrent.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a ConcurrentHashMap and add some values
        ConcurrentHashMap<Integer, String>
            map = new ConcurrentHashMap<>();
        map.put(1, "Kolkata");
        map.put(2, "Nadia");
        map.put(3, "Howrah");

        try {

            // remap the values of ConcurrentHashMap
            // using compute method
            map.compute(null, (key, val)
                                  -> val.concat(" (West-Bengal)"));
        }
        catch (NullPointerException e) {

            // print Exception
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.NullPointerException

```

参考文献:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrenthashmap . html # compute-K-Java . util . function . bifunction-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentHashMap.html#compute-K-java.util.function.BiFunction-)