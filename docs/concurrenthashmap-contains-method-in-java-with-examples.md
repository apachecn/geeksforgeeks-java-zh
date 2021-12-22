# ConcurrentHashMap 包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/concurrenthashmap-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrenthashmap-contains-method-in-java-with-examples/)

**包含()**方法的**Java . util . concurrenthashmap**用来检查是否有一些关键点映射到这个表中的指定值。这是执行特定任务的传统方法。该操作类似于 ConcurrentHashMap 的 containsValue()方法。

**语法:**

```
ConcurrentHashMap.contains(*Object Value*)
```

**参数:**该方法只取一个对象类型的参数*值*，并引用其映射应该由映射内任何键检查的值。

**返回值:**如果检测到值的映射，则该方法返回布尔值 true，否则返回 false。

下面的程序用来说明 concurrenthashmap . contains value()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the contains() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty HashMap
        ConcurrentHashMap<Integer, String>
            hash_map = new ConcurrentHashMap<Integer,
                                             String>();

        // Mapping string values to int keys
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Displaying the ConcurrentHashMap
        System.out.println("Initial Mappings are: "
                           + hash_map);

        // Checking for the Value 'Geeks'
        System.out.println("Is the value 'Geeks' present? "
                           + hash_map.containsValue("Geeks"));

        // Checking for the Value 'World'
        System.out.println("Is the value 'World' present? "
                           + hash_map.containsValue("World"));
    }
}
```

**输出:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Is the value 'Geeks' present? true
Is the value 'World' present? false

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the contains() method

import java.util.*;
import java.util.concurrent.*;

public class ConcurrentHashMapDemo {
    public static void main(String[] args)
    {

        // Creating an empty ConcurrentHashMap
        ConcurrentHashMap<String, Integer>
            hash_map = new ConcurrentHashMap<String,
                                             Integer>();

        // Mapping int values to string keys
        hash_map.put("Geeks", 10);
        hash_map.put("4", 15);
        hash_map.put("Geeks", 20);
        hash_map.put("Welcomes", 25);
        hash_map.put("You", 30);

        // Displaying the ConcurrentHashMap
        System.out.println("Initial Mappings are: "
                           + hash_map);

        // Checking for the Value 'Geeks'
        System.out.println("Is the value 'Geeks' present? "
                           + hash_map.contains(25));

        // Checking for the Value 'World'
        System.out.println("Is the value 'World' present? "
                           + hash_map.contains(35));
    }
}
```

**输出:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
Is the value 'Geeks' present? true
Is the value 'World' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。