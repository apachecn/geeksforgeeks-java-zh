# Java 中的 Collections synchronizedMap()方法，示例

> 原文:[https://www . geesforgeks . org/collections-synchronized map-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-synchronizedmap-method-in-java-with-examples/)

**java.util.Collections** 类的 **synchronizedMap()** 方法用于返回由指定映射支持的同步(线程安全)映射。为了保证串行访问，通过返回的映射完成对后备映射的所有访问是至关重要的。

**语法:**

> 公共静态<k v="">地图<k v="">同步地图(地图<k v="">米)</k></k></k>

**参数:**该方法将**地图**作为参数“包裹”在同步地图中。

**返回值:**该方法返回指定地图的**同步视图**。

以下是说明 *synchronizedMap()* 方法的示例。

**例 1:**

```
// Java program to demonstrate
// synchronizedMap() method
// for <String, String> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of Map<String, String>
            Map<String, String>
                map = new HashMap<String, String>();

            // populate the map
            map.put("Value1", "20");
            map.put("Value2", "30");
            map.put("Value3", "40");

            // printing the Collection
            System.out.println("Map : " + map);

            // create a synchronized map
            Map<String, String>
                synmap = Collections.synchronizedMap(map);

            // printing the Collection
            System.out.println("Synchronized map is : "
                               + synmap);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Map : {Value3=40, Value1=20, Value2=30}
Synchronized map is : {Value3=40, Value1=20, Value2=30}

```

****例 2:****

```
// Java program to demonstrate
// synchronizedMap() method
// for <String, Boolean> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of Map<String, Boolean>
            Map<String, Boolean>
                map = new HashMap<String, Boolean>();

            // populate the map
            map.put("Bramha", true);
            map.put("Vishnu", true);
            map.put("Mahesh", true);

            // printing the Collection
            System.out.println("Map : " + map);

            // create a synchronized map
            Map<String, Boolean>
                synmap = Collections.synchronizedMap(map);

            // printing the Collection
            System.out.println("Synchronized map is : "
                               + synmap);
        }
        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Map : {Bramha=true, Vishnu=true, Mahesh=true}
Synchronized map is : {Bramha=true, Vishnu=true, Mahesh=true}

```