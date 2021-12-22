# 抽象地图。Java 中的 SimpleEntry hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/abstract map-simpleentry-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-simpleentry-hashcode-method-in-java-with-examples/)

**抽象地图。简单条目< K，V >** 用于维护一个键和值条目。可以使用 setValue 方法更改该值。这个类促进了构建自定义地图实现的过程。

**hashCode()** 方法的**抽象图。简单条目< K，V >** 返回该地图条目的哈希码值。
地图条目 e 的哈希代码可以通过以下方式计算:

```java
(e.getKey()==null   ? 0 : e.getKey().hashCode()) ^
   (e.getValue()==null ? 0 : e.getValue().hashCode())
```

**语法:**

```java
public int hashCode()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该映射条目的哈希码值。

下面的程序说明了 hashCode()方法:
**程序 1:**

```java
// Java program to demonstrate
// AbstractMap.SimpleEntry.hashCode() method

import java.util.*;
import java.util.AbstractMap.SimpleEntry;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        // create a ArrayList of Map
        ArrayList<AbstractMap
                      .SimpleEntry<Integer, Integer> >
            arrayList
            = new ArrayList<AbstractMap
                                .SimpleEntry<Integer, Integer> >();

        // add values
        arrayList.add(new AbstractMap.SimpleEntry(0, 123));
        arrayList.add(new AbstractMap.SimpleEntry(1, 130));
        arrayList.add(new AbstractMap.SimpleEntry(2, 994));

        // print keys
        for (int i = 0; i < arrayList.size(); i++) {

            // get map from list
            AbstractMap.SimpleEntry<Integer, Integer>
                map
                = arrayList.get(i);

            // get value from map using hashCode()
            int value = map.hashCode();

            System.out.println("HashCode = " + value);
        }
    }
}
```

**Output:**

```java
HashCode = 123
HashCode = 131
HashCode = 992

```

**程序 2:**

```java
// Java program to demonstrate
// AbstractMap.SimpleEntry.hashCode() method

import java.util.*;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        // create a ArrayList of Map
        ArrayList<AbstractMap
                      .SimpleEntry<String, String> >
            arrayList
            = new ArrayList<AbstractMap
                                .SimpleEntry<String, String> >();

        // add values
        arrayList.add(new AbstractMap
                          .SimpleEntry(" 001AB ", " Emp 1"));
        arrayList.add(new AbstractMap
                          .SimpleEntry(" 011AC ", " Emp 2"));
        arrayList.add(new AbstractMap
                          .SimpleEntry(" 111AD ", " Emp 3"));
        arrayList.add(new AbstractMap
                          .SimpleEntry(" 101BE ", " Emp 4"));
        arrayList.add(new AbstractMap
                          .SimpleEntry(" 110CE ", " Emp 5"));

        // print keys
        for (int i = 0; i < arrayList.size(); i++) {

            // get map from list
            AbstractMap.SimpleEntry<String, String>
                map
                = arrayList.get(i);

            // get hashcode value from map using hashCode()
            int value = map.hashCode();

            System.out.println("hashCode = " + value);
        }
    }
}
```

**Output:**

```java
hashCode = -873386249
hashCode = -874293612
hashCode = -910934441
hashCode = -910552137
hashCode = -910906733

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/abstract map。SimpleEntry.html#hashCode()](https://docs.oracle.com/javase/10/docs/api/java/util/AbstractMap.SimpleEntry.html#hashCode())