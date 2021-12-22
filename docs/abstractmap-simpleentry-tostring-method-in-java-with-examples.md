# 抽象地图。Java 中的 SimpleEntry toString()方法，示例

> 原文:[https://www . geesforgeks . org/abstract map-simpleentry-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-simpleentry-tostring-method-in-java-with-examples/)

**抽象地图。简单条目< K，V >** 用于维护一个键和值条目。可以使用 setValue 方法更改该值。这个类促进了构建自定义地图实现的过程。

**toString()** 法的**抽象图。简单条目< K，V >** 返回该简单条目地图条目的字符串表示。此方法返回此映射条目的键的字符串表示形式，后跟等于字符(" = ")，后跟此条目值的字符串表示形式。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该地图条目的字符串表示。

下面的程序说明了 toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// AbstractMap.SimpleEntry.toString() method

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

            // get representation of map using toString()
            String value = map.toString();

            System.out.println(value);
        }
    }
}
```

**Output:**

```java
0=123
1=130
2=994

```

**程序 2:**

```java
// Java program to demonstrate
// AbstractMap.SimpleEntry.toString() method

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

            // get representation of map using toString()
            String value = map.toString();

            System.out.println(value);
        }
    }
}
```

**Output:**

```java
001AB = Emp 1
011AC = Emp 2
111AD = Emp 3
101BE = Emp 4
110CE = Emp 5

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/abstract map。SimpleEntry.html#toString()](https://docs.oracle.com/javase/10/docs/api/java/util/AbstractMap.SimpleEntry.html#toString())