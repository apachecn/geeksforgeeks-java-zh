# Java 中的 ConcurrentHashMapcomputeif 缺席()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrenthashmap-computeifexception-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrenthashmap-computeifabsent-method-in-java-with-examples/)

**ConcurrentHashMap 类**的**计算不存在(键，函数)**方法，如果键是**但还没有与值**相关联(或被映射为空)，则尝试使用指定键的给定映射函数计算其值，并将该计算值输入到 map else null 中。

*   如果此方法的映射函数返回 null，则映射中没有记录新键的值。
*   此方法用于自动更新 ConcurrentHashMap 中给定键的值。
*   如果重新映射函数抛出异常，异常将被重新引发，并且不记录映射。
*   在计算过程中，不允许使用此方法修改此映射，因为其他线程也可以使用此映射。

**语法:**

```
public V 
       computeIfAbsent(K key,
             Function<? super K, ? extends V> remappingFunction)
```

**参数:**该方法接受两个参数:

*   **键**:与数值相关联的键。
*   **重编程功能**:对数值进行运算的功能。

**返回:**此方法返回**与指定键关联的当前(现有或计算的)值，如果映射返回空值**，则返回空值。
**异常:**此法抛出:

*   **NullPointRexception:**如果指定的键或 remappingFunction 为空。
*   **llegalstatexception:**如果计算试图对该地图进行递归更新，否则该更新将永远不会完成。
*   **RuntimeException:** 如果 remappingFunction 这样做，在这种情况下映射不变。

以下程序说明了计算缺席(键，函数)方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.concurrent.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a ConcurrentHashMap and
        // add some values
        ConcurrentHashMap<String, Integer> map
            = new ConcurrentHashMap<>();
        map.put("Pencil", 1000);
        map.put("Laptop", 55000);
        map.put("Clothes", 4400);
        map.put("Mobile", 5300);

        // print map details
        System.out.println("ConcurrentHashMap :\n "
                           + map.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        map.computeIfAbsent("PC", k -> 60000);
        map.computeIfAbsent("Charger", k -> 800);

        // print new mapping
        System.out.println("new ConcurrentHashMap :\n "
                           + map);
    }
}
```

**Output:** 

```
ConcurrentHashMap :
 {Laptop=55000, Clothes=4400, Pencil=1000, Mobile=5300}
new ConcurrentHashMap :
 {Laptop=55000, PC=60000, Clothes=4400, Pencil=1000, Charger=800, Mobile=5300}
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.concurrent.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a ConcurrentHashMap and
        // add some values
        ConcurrentHashMap<Integer, String> map
            = new ConcurrentHashMap<>();
        map.put(1, "1000RS");
        map.put(2, "5009RS");
        map.put(3, "1300RS");

        // print map details
        System.out.println("ConcurrentHashMap : \n"
                           + map.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        map.computeIfAbsent(4, k -> "6000RS");

        // this will not effect anything
        // because key 1 is present
        map.computeIfAbsent(1, k -> "8000RS");

        // print new mapping
        System.out.println("new ConcurrentHashMap :\n"
                           + map);
    }
}
```

**Output:** 

```
ConcurrentHashMap : 
{1=1000RS, 2=5009RS, 3=1300RS}
new ConcurrentHashMap :
{1=1000RS, 2=5009RS, 3=1300RS, 4=6000RS}
```

**程序 3:** 显示空指针异常

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate NullPointerException of
// computeIfAbsent(Key, Function) method.

import java.util.concurrent.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a ConcurrentHashMap and
        // add some values
        ConcurrentHashMap<String, Integer> map
            = new ConcurrentHashMap<>();
        map.put("Pencil", 1000);
        map.put("Laptop", 55000);
        map.put("Clothes", 4400);
        map.put("Mobile", 5300);

        try {

            // provide value for new key which is absent
            // using computeIfAbsent method
            map.computeIfAbsent(null, k -> 60000);
        }
        catch (Exception e) {

            // print new mapping
            System.out.println("Exception: "
                               + e);
        }
    }
}
```

**Output:** 

```
Exception: java.lang.NullPointerException
```

参考文献:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrenthashmap . html # computeifexent-K-Java . util . function . function-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentHashMap.html#computeIfAbsent-K-java.util.function.Function-)