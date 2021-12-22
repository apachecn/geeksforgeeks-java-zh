# Java 中的 HashMap compute()方法，示例

> 原文:[https://www . geesforgeks . org/hashmap-compute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashmap-compute-method-in-java-with-examples/)

**哈希表类**的**计算(键，双功能)**方法允许您更新哈希表中的值。compute()方法尝试计算指定键及其当前映射值的映射(如果找不到当前映射，则为 null)。该方法用于**自动更新哈希表中给定键**的值。

*   如果在计算中传递的重新映射函数返回空值，映射将从映射中移除(或者如果最初不存在，则保持不存在)。
*   如果重新映射函数引发异常，将重新引发异常，并且当前映射保持不变。
*   **在计算过程中，重映射函数不应该能够修改这个映射。**
    compute()方法可用于更新 HashMap 中的现有值。
    例如

    > 映射以增加映射的整数值:map.compute(key，(k，v) - > (v == null)？1 : v+1)

*   如果 compute()方法的重新映射函数在计算过程中修改了此映射，则此方法的默认实现无法保证检测到错误。

**异常:**
此方法的非并发实现应该覆盖此方法，如果在计算过程中检测到映射发生变化，则抛出**ConcurrentModificationException**。如果在计算过程中检测到映射发生变化，导致计算永远无法完成，那么并发实现应该覆盖这个方法，抛出**illegalstatexception**。

此方法的默认实现不保证此方法的同步或原子属性。任何提供原子性保证的实现都必须重写此方法并记录其并发属性。

**语法:**

```
default V 
       compute(K key,
             BiFunction<? super K, ? super V, ? 
                 extends V> remappingFunction)
```

**参数:**该方法接受两个参数:

*   **键**:与值关联的键。
*   **重编程功能**:计算数值的功能。

**返回:**该方法返回与指定键关联的**新值，如果没有则返回空值**。

**异常:**此方法抛出:

*   **NullPointRexception**:如果键为空，并且该映射不支持空键，或者 remappingFunction 为空。
*   **不支持操作异常**:如果该地图不支持放操作。
*   **ClassCastException** :如果键或值的类阻止其存储在该映射中。
*   **IllegalArgumentException** :如果键或值的某些属性阻止它存储在此地图中。

以下程序说明了计算(键，双功能)方法:

**程序 1:**

```
// Java program to demonstrate
// compute(Key, BiFunction) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a Map and add some values
        Map<String, String> map = new HashMap<>();
        map.put("Name", "Aman");
        map.put("Address", "Kolkata");

        // Print the map
        System.out.println("Map: " + map);

        // remap the values using compute() method
        map.compute("Name", (key, val)
                                -> val.concat(" Singh"));
        map.compute("Address", (key, val)
                                   -> val.concat(" West-Bengal"));

        // print new mapping
        System.out.println("New Map: " + map);
    }
}
```

**Output:**

```
Map: {Address=Kolkata, Name=Aman}
New Map: {Address=Kolkata West-Bengal, Name=Aman Singh}

```

**程序 2:**

```
// Java program to demonstrate
// compute(Key, BiFunction) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a Map and add some values
        Map<String, Integer> map = new HashMap<>();
        map.put("Key1", 12);
        map.put("Key2", 15);

        // print map details
        System.out.println("Map: " + map);

        // remap the values
        // using compute method
        map.compute("Key1", (key, val)
                                -> (val == null)
                                       ? 1
                                       : val + 1);
        map.compute("Key2", (key, val)
                                -> (val == null)
                                       ? 1
                                       : val + 5);

        // print new mapping
        System.out.println("New Map: " + map);
    }
}
```

**Output:**

```
Map: {Key2=15, Key1=12}
New Map: {Key2=20, Key1=13}

```

**程序 3:** 显示空指针异常

```
// Java program to demonstrate Exception thrown by
// compute(Key, BiFunction) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a Map and add some values
        Map<String, Integer> map = new HashMap<>();
        map.put("Key1", 12);
        map.put("Key2", 15);

        // print map details
        System.out.println("Map: " + map);

        try {

            // remap the values using compute() method
            // passing null value will throw exception
            map.compute(null, (key, value)
                                  -> value + 3);
            System.out.println("New Map: " + map);
        }
        catch (NullPointerException e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Map: {Key2=15, Key1=12}
Exception: java.lang.NullPointerException

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/util/hashmap . html # compute(K，Java . util . function . bifunction)](https://docs.oracle.com/javase/10/docs/api/java/util/HashMap.html#compute(K, java.util.function.BiFunction))