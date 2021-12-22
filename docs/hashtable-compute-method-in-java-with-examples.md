# Java 中的哈希表计算()方法，示例

> 原文:[https://www . geesforgeks . org/hashtable-compute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashtable-compute-method-in-java-with-examples/)

**哈希表类**的**计算(键，双功能)**方法允许计算指定键及其当前映射值的映射(如果没有找到当前映射，则为空)。

*   如果在哈希表的 compute()中传递的重映射函数返回 null 作为返回值，则从哈希表中移除该映射(或者如果最初不存在，则保持不存在)。
*   如果重新映射函数引发异常，该异常将被重新引发，并且当前映射保持不变。
*   在计算过程中，不允许使用此方法修改此地图。
*   compute()方法可用于更新哈希表中的现有值。
    例如，该映射追加映射的字符串值:

    ```
    Hashtable.compute(key, (k, v) -> v.append("strValue"))

    ```

*   如果重新映射函数在计算期间修改了此映射，此方法将引发 ConcurrentModificationException。

**语法:**

```
public V 
       compute(K key,
             BiFunction<? super K, ? super V, ? extends V> remappingFunction)
```

**参数:**该方法接受两个参数:

*   **键**:与数值相关联的键。
*   **重编程功能**:对数值进行运算的功能。

**返回:**该方法返回与指定键关联的**新值，如果没有则返回空值**。

**异常:**此方法抛出:

*   **ConcurrentModificationException**:如果检测到重映射功能修改了该地图。

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

        // create a table and add some values
        Map<String, Integer> table = new Hashtable<>();
        table.put("Pen", 10);
        table.put("Book", 500);
        table.put("Clothes", 400);
        table.put("Mobile", 5000);

        // print map details
        System.out.println("hashTable: " + table.toString());

        // remap the values of hashTable
        // using compute method
        table.compute("Pen", (key, val)
                                 -> val + 15);
        table.compute("Clothes", (key, val)
                                     -> val - 120);

        // print new mapping
        System.out.println("new hashTable: " + table);
    }
}
```

**Output:**

```
hashTable: {Book=500, Mobile=5000, Pen=10, Clothes=400}
new hashTable: {Book=500, Mobile=5000, Pen=25, Clothes=280}

```

**输出:**

```
hashTable: {Book=500, Mobile=5000, Pen=10, Clothes=400}
new hashTable: {Book=500, Mobile=5000, Pen=25, Clothes=280}

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

        // create a table and add some values
        Map<Integer, String> table = new Hashtable<>();
        table.put(1, "100RS");
        table.put(2, "500RS");
        table.put(3, "1000RS");

        // print map details
        System.out.println("hashTable: "
                           + table.toString());

        // remap the values of hashTable
        // using compute method
        table.compute(3, (key, val)
                             -> val.substring(0, 4) + "00RS");
        table.compute(2, (key, val)
                             -> val.substring(0, 2) + "{content}quot;);

        // print new mapping
        System.out.println("new hashTable: " + table);
    }
}
```

**Output:**

```
hashTable: {3=1000RS, 2=500RS, 1=100RS}
new hashTable: {3=100000RS, 2=50$, 1=100RS}

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/util/Hashtable . html # compute(K，Java . util . function . BiFunction)](https://docs.oracle.com/javase/10/docs/api/java/util/Hashtable.html#compute(K, java.util.function.BiFunction))