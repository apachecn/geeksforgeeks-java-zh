# 用示例在 Java 中映射 entrySet()方法

> 原文:[https://www . geesforgeks . org/map-entryset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-entryset-method-in-java-with-examples/)

java 中的 java.util.Map.entrySet()方法用于创建一组包含在地图中的相同元素。它基本上返回地图的集合视图，或者我们可以创建一个新的集合并将地图元素存储到其中。

**语法:**

```
map.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个与哈希映射具有相同元素的集合。

下面的程序展示了 java.util.Map.entrySet()方法:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the entrySet() method

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

        // Using entrySet() to get the set view
        System.out.println("The set is: " + map.entrySet());
    }
}
```

**输出:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The set is: [20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4]

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the entrySet() method
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

        // Using entrySet() to get the set view
        System.out.println("The set is: " + map.entrySet());
    }
}
```

**输出:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The set is: [4=15, Geeks=20, You=30, Welcomes=25]

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # entrySet()](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#entrySet())