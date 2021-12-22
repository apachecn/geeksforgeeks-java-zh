# 用示例

在 Java 中映射 clear()方法

> 原文:[https://www . geesforgeks . org/map-clear-method-in-Java-with-example/](https://www.geeksforgeeks.org/map-clear-method-in-java-with-example/)

java 中的 java.util.Map.clear()方法用于从指定的 Map 集合中清除和移除所有元素或映射。

**语法:**

```
void clear()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

下面的程序用来说明 java.util.Map.clear()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the clear() method
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

        // Clearing the map using clear()
        map.clear();

        // Displaying the final HashMap
        System.out.println("Finally the maps look like this: " + map);
    }
}
```

**输出:**

```
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Finally the maps look like this: {}

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the clear() method
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

        // Clearing the map using clear()
        map.clear();

        // Displaying the final Map
        System.out.println("Finally the maps look like this: " + map);
    }
}
```

**输出:**

```
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
Finally the maps look like this: {}

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # clear()](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#clear())