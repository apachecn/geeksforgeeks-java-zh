# 抽象地图。Java 中的 SimpleEntry getKey()方法，示例

> 原文:[https://www . geesforgeks . org/abstract map-simpleentry-getkey-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-simpleentry-getkey-method-in-java-with-examples/)

**抽象地图。SimpleEntry < K，V >** 用于维护一个键和值项。可以使用 setValue 方法更改该值。这个类促进了构建自定义地图实现的过程。
**getKey()** 法的 **AbstractMap。SimpleEntry < K，V >** 返回该条目对应的按键。

**语法:**

```java
public K getKey()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该条目对应的键。

以下程序说明 getKey()方法:
**程序 1:**

```java
// Java program to demonstrate
// AbstractMap.SimpleEntry.getKey() method

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

            // get key from map.getKey();
            int key = map.getKey();

            System.out.println("Key " + key);
        }
    }
}
```

**Output:**

```java
Key 0
Key 1
Key 2

```

**程序 2:**

```java
// Java program to demonstrate
// AbstractMap.SimpleEntry.get() method

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

            // get key from map.getKey()
            String key = map.getKey();

            System.out.println("Key " + key);
        }
    }
}
```

**Output:**

```java
Key  001AB 
Key  011AC 
Key  111AD 
Key  101BE 
Key  110CE

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/abstract map。SimpleEntry.html#getKey()](https://docs.oracle.com/javase/10/docs/api/java/util/AbstractMap.SimpleEntry.html#getKey())