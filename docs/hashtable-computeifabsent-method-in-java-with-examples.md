# Java 中的哈希表计算缺席()方法，示例

> 原文:[https://www . geesforgeks . org/hashtable-computeifexception-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashtable-computeifabsent-method-in-java-with-examples/)

**哈希表类**的**计算缺少(键，函数)**方法，如果键还没有与值相关联(或被映射为空)，该方法允许您计算指定键的映射值。

*   If the mapping function of this method returns null, the mapping is not recorded.
*   If the remapping function throws an exception, it throws an exception again and records the no mapping.
*   This method is not allowed to modify the map during the calculation.
*   If the remapping function modifies this mapping during calculation, this method will throw a Concurrentmodification Exception.

**语法:**

```
public V 
       computeIfAbsent(K key,
             Function<? super K, ? extends V> remappingFunction)
```

**参数:**此方法接受两个参数:

*   **key** : the key with which the value is to be associated.
*   [T0】 remapingfunction 【T1]: the function of computing numerical values.

**返回:**此方法返回**与指定键关联的当前(现有或计算的)值，如果映射返回空值**，则返回空值。

**异常:**此方法抛出:

*   **Concurrentmodification Exception** : If it is detected that the remapping function has modified this map.

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

        // create a table and add some values
        Map<String, Integer> table = new Hashtable<>();
        table.put("Pen", 10);
        table.put("Book", 500);
        table.put("Clothes", 400);
        table.put("Mobile", 5000);

        // print map details
        System.out.println("hashTable: "
                           + table.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        table.computeIfAbsent("newPen", k -> 600);
        table.computeIfAbsent("newBook", k -> 800);

        // print new mapping
        System.out.println("new hashTable: "
                           + table);
    }
}
```

**输出:**

```
hashTable: {Book=500, Mobile=5000, Pen=10, Clothes=400}
new hashTable: {newPen=600, Book=500, newBook=800, Mobile=5000, Pen=10, Clothes=400}

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

        // create a table and add some values
        Map<Integer, String> table = new Hashtable<>();
        table.put(1, "100RS");
        table.put(2, "500RS");
        table.put(3, "1000RS");

        // print map details
        System.out.println("hashTable: "
                           + table.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        table.computeIfAbsent(4, k -> "600RS");

        // this will not effect anything
        // because key 1 is present
        table.computeIfAbsent(1, k -> "800RS");

        // print new mapping
        System.out.println("new hashTable: "
                           + table);
    }
}
```

**输出:**

```
hashTable: {3=1000RS, 2=500RS, 1=100RS}
new hashTable: {4=600RS, 3=1000RS, 2=500RS, 1=100RS}

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/util/Hashtable . html # computeifIncement(K，Java . util . function . function)](https://docs.oracle.com/javase/10/docs/api/java/util/Hashtable.html#computeIfAbsent(K, java.util.function.Function))