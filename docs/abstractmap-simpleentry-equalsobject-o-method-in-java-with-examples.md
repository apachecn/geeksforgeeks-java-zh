# 抽象地图。Java 中的 SimpleEntry 等于(Object o)方法，示例

> 原文:[https://www . geesforgeks . org/abstract map-simpleentry-equalsobject-o-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-simpleentry-equalsobject-o-method-in-java-with-examples/)

**抽象地图。简单条目< K，V >** 用于维护一个键和值条目。可以使用等号来更改该值。方法。这个类促进了构建自定义地图实现的过程。

**等于**抽象地图的(对象 o)** 方法。简单条目< K，V >** 用于将作为参数传递的指定对象与该条目进行比较，以获得相等性。如果给定对象也包含一个映射条目，并且这两个条目表示相同的映射，则方法返回 true。

两个条目 e1 和 e2 表示相同的映射 if

```
 (e1.getKey()==null ?
    e2.getKey()==null :
    e1.getKey().equals(e2.getKey()))
   &&
   (e1.getValue()==null ?
    e2.getValue()==null :
    e1.getValue().equals(e2.getValue()))
```

**语法:**

```
public V equals(Object o)

```

**参数:**此方法接受要与此地图条目进行相等比较的对象。

**返回值:**如果指定对象等于该地图条目，则该方法为真。

下面的程序说明了 equals(Object o)方法:
**程序 1:**

```
// Java program to demonstrate
// AbstractMap.SimpleEntry.equals() method

import java.util.*;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        // create two maps
        AbstractMap.SimpleEntry<Integer, Integer> map1
            = new AbstractMap.SimpleEntry(0, 123);

        AbstractMap.SimpleEntry<Integer, Integer> map2
            = new AbstractMap.SimpleEntry(0, 123);

        // compare both maps
        boolean answer = map1.equals(map2);

        // print result
        System.out.println("Map 1 is equal to Map2 -> "
                           + answer);
    }
}
```

**Output:**

```
Map 1 is equal to Map2 -> true

```

**程序 2:**

```
// Java program to demonstrate
// AbstractMap.SimpleEntry.equals() method

import java.util.*;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        // create two maps
        AbstractMap.SimpleEntry<String, String> map1
            = new AbstractMap
                  .SimpleEntry<String, String>("Captain:", "Dhoni");
        AbstractMap.SimpleEntry<String, String> map2
            = new AbstractMap
                  .SimpleEntry<String, String>("Captain:", "Kohli");

        // compare both maps
        boolean answer = map1.equals(map2);

        // print result
        System.out.println("Map 1 is equal to Map2 -> "
                           + answer);
    }
}
```

**Output:**

```
Map 1 is equal to Map2 -> false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/abstract map。simpleentry . html # # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/util/AbstractMap.SimpleEntry.html##equals(java.lang.Object))