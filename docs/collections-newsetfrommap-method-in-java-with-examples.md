# Java 中的 Collections newSetFromMap()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-newsetfrommap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-newsetfrommap-method-in-java-with-examples/)

**java.util.Collections** 类的 **newSetFromMap()** 方法用于返回由指定地图支持的集合。结果集显示与支持图相同的顺序、并发性和性能特征。本质上，这个工厂方法提供了一个对应于任何 Map 实现的 Set 实现。没有必要在已经有相应的 Set 实现(如 HashMap 或 TreeMap)的 Map 实现上使用这个方法。

**语法:**

```
public static  Set newSetFromMap(Map map)
```

**参数:**该方法以打底**图**为参数

**返回值:**该方法返回地图支持的**集合**

**异常:**如果地图不为空，此方法抛出 **IllegalArgumentException** 。

以下是说明 *newSetFromMap()* 方法的示例

**例 1:**

```
// Java program to demonstrate
// newSetFromMap() method

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of Map<String, Boolean>
            Map<String, Boolean>
                map = new WeakHashMap<String, Boolean>();

            // creating object of LinkedList
            Set<String> set = Collections.newSetFromMap(map);

            // add values in set
            set.add("A");
            set.add("B");
            set.add("C");
            set.add("D");

            // set and map values are
            System.out.println("Map is: " + map);
            System.out.println("Set from Map is: " + set);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Map is: {C=true, B=true, A=true, D=true}
Set from Map is: [C, B, A, D]

```

**示例 2:** 适用于*非法文档异常*

```
// Java program to demonstrate
// newSetFromMap() method
// for IllegalArgumentException

import java.util.*;
<div class = 'outputDiv'>
<b>Output:</b>
<pre>
Set is: [C, B, A, D]
Map is: {C=true, B=true, A=true, D=true}
</pre>
</div>

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of Map<String, Boolean>
            Map<String, Boolean>
                map = new WeakHashMap<String, Boolean>();

            // putting value in map
            map.put("1", true);

            // creating object of LinkedList
            Set<String> set = Collections.newSetFromMap(map);

            // add values in set
            set.add("A");
            set.add("B");
            set.add("C");
            set.add("D");

            // set and map values are
            System.out.println("Map is: " + map);
            System.out.println("Set from Map is: " + set);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
Exception thrown : java.lang.IllegalArgumentException: Map is non-empty

```