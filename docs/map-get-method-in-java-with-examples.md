# Java 中的 Map get()方法，示例

> 原文:[https://www . geesforgeks . org/map-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-get-method-in-java-with-examples/)

Java 中 Map 接口的 get()方法用于检索或获取参数中提到的特定键映射的值。当映射不包含键的这种映射时，它返回空值。

**语法:**

```
thisMap.get(*Object key_element*)
```

**参数:**该方法取一个对象类型的参数 *key_element* ，指的是应该取关联值的键。

**返回值:**该方法返回与该地图集合中的*关键元素*相关联的值。

下面的程序说明了 java.util.Map.get()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the get() method
import java.util.*;

public class Map_Demo {
    public static void main(String[] args)
    {
        // Creating an empty Map
        Map<Integer, String> map = new HashMap<Integer, String>();

        // Mapping string values to int keys
        map.put(10, "Geeks");
        map.put(15, "4");
        map.put(20, "Geeks");
        map.put(25, "Welcomes");
        map.put(30, "You");

        // Displaying the Map
        System.out.println("Initial Mappings are: " + map);

        // Getting the value of 25
        System.out.println("The Value is: " + map.get(25));

        // Getting the value of 10
        System.out.println("The Value is: " + map.get(10));
    }
}
```

**输出:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The Value is: Welcomes
The Value is: Geeks

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the get() method

import java.util.*;

public class Map_Demo {
    public static void main(String[] args)
    {
        // Creating an empty Map
        Map<String, Integer> map = new HashMap<String, Integer>();

        // Mapping int values to string keys
        map.put("Geeks", 10);
        map.put("4", 15);
        map.put("Geeks", 20);
        map.put("Welcomes", 25);
        map.put("You", 30);

        // Displaying the Map
        System.out.println("Initial Mappings are: " + map);

        // Getting the value of "Geeks"
        System.out.println("The Value is: " + map.get("Geeks"));

        // Getting the value of "You"
        System.out.println("The Value is: " + map.get("You"));
    }
}
```

**输出:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The Value is: 20
The Value is: 30

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # get(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#get(java.lang.Object))