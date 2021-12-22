# Java 中的 HashMapcomputeif 缺席()方法，带示例

> 原文:[https://www . geesforgeks . org/hashmap-computeifexception-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashmap-computeifabsent-method-in-java-with-examples/)

**哈希映射类**的**计算缺失(键，函数)**方法用于使用给定的映射函数计算给定键的值，如果键还没有与值相关联(或被映射为空)，则在哈希映射中输入该计算值，否则为空。

*   If the mapping function of this method returns null, the key does not record the mapping.
*   When calculating, if the remapping function throws an exception, it throws an exception again and records the no mapping.
*   This method is not allowed to modify the map during the calculation.
*   If the remapping function modifies this mapping during calculation, this method will throw a Concurrentmodification Exception.

**语法:**

```
public V 
       computeIfAbsent(K key,
             Function<? super K, ? extends V> remappingFunction)
```

**参数:**此方法接受两个参数:

*   **Key** : The key whose value we want to calculate by mapping.
*   [T0】 remapingfunction 【T1]: the function of computing numerical values.

**返回:**此方法返回**与指定键关联的当前(现有或计算的)值，如果映射返回空值**，则返回空值。

以下程序说明了计算无(键，函数)方法:

**程序 1:**

```
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap and add some values
        HashMap<String, Integer> map
            = new HashMap<>();
        map.put("key1", 10000);
        map.put("key2", 55000);
        map.put("key3", 44300);
        map.put("key4", 53200);

        // print map details
        System.out.println("HashMap:\n "
                           + map.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        map.computeIfAbsent("key5",
                            k -> 2000 + 33000);
        map.computeIfAbsent("key6",
                            k -> 2000 * 34);

        // print new mapping
        System.out.println("New HashMap:\n "
                           + map);
    }
}
```

**输出:**

```
HashMap:
 {key1=10000, key2=55000, key3=44300, key4=53200}
New HashMap:
 {key1=10000, key2=55000, key5=35000, key6=68000, key3=44300, key4=53200}

```

**程序二:**

```
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap and add some values
        HashMap<Integer, String>
            map = new HashMap<>();
        map.put(10, "Aman");
        map.put(20, "Suraj");
        map.put(30, "Harsh");

        // print map details
        System.out.println("HashMap:\n"
                           + map.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        map.computeIfAbsent(40, k -> "Sanjeet");

        // this will not effect anything
        // because key 1 is present
        map.computeIfAbsent(10, k -> "Amarjit");

        // print new mapping
        System.out.println("New HashMap:\n" + map);
    }
}
```

**输出:**

```
HashMap:
{20=Suraj, 10=Aman, 30=Harsh}
New HashMap:
{20=Suraj, 40=Sanjeet, 10=Aman, 30=Harsh}

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/util/hashmap . html # computeifexent(K，Java . util . function . function)](https://docs.oracle.com/javase/10/docs/api/java/util/HashMap.html#computeIfAbsent(K, java.util.function.Function))