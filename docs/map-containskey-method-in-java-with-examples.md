# 用示例将 containsKey()方法映射到 Java 中

> 原文:[https://www . geesforgeks . org/map-contains key-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-containskey-method-in-java-with-examples/)

java.util.Map.containsKey()方法用于检查特定的键是否被映射到映射中。它将关键元素作为参数，如果该元素在映射中被映射，则返回 True。

**语法:**

```java
boolean containsKey(*key_element*)
```

**参数:**该方法只取一个参数 *key_element* ，该参数是指映射应该在地图内部检查的键。

**返回值:**如果检测到键的存在，则该方法返回布尔值 true，否则返回 false。

下面的程序用来说明 java.util.Map.containsKey()方法的工作原理:

**程序 1:** 将字符串值映射到整数键。

```java
// Java code to illustrate the containsKey() method
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

        // Checking for the key_element '20'
        System.out.println("Is the key '20' present? "
                           + map.containsKey(20));

        // Checking for the key_element '5'
        System.out.println("Is the key '5' present? "
                           + map.containsKey(5));
    }
}
```

**输出:**

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Is the key '20' present? true
Is the key '5' present? false

```

**程序 2:** 将整数值映射到字符串键。

```java
// Java code to illustrate the containsKey() method

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

        // Checking for the key_element 'Welcomes'
        System.out.println("Is the key 'Welcomes' present? "
                           + map.containsKey("Welcomes"));

        // Checking for the key_element 'World'
        System.out.println("Is the key 'World' present? "
                           + map.containsKey("World"));
    }
}
```

**输出:**

```java
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
Is the key 'Welcomes' present? true
Is the key 'World' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # contains key(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#containsKey(java.lang.Object))