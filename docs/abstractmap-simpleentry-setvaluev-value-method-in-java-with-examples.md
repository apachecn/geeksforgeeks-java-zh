# 抽象地图。Java 中的 SimpleEntry setValue(V 值)方法，示例

> 原文:[https://www . geesforgeks . org/abstract map-simpleentry-setvaluev-value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractmap-simpleentry-setvaluev-value-method-in-java-with-examples/)

**抽象地图。简单条目< K，V >** 用于维护一个键和值条目。可以使用 setValue 方法更改该值。这个类促进了构建自定义地图实现的过程。

**设定值(V 值)**方法的**抽象图。简单输入< K，V >** 用于用作为参数传递的指定值替换地图的当前值。

**语法:**

```
public V setValue(V value)

```

**参数:**这个方法接受我们要设置的值。

**返回值:**该方法返回条目对应的旧值。

下面的程序说明了设置值(V 值)的方法:
**程序 1:**

```
// Java program to demonstrate
// AbstractMap.SimpleEntry.setValue() method

import java.util.*;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        AbstractMap.SimpleEntry<Integer, Integer>
            map
            = new AbstractMap
                  .SimpleEntry(0, 123);

        // change value to 2122425
        Integer newValue = 2122425;
        Integer oldValue = map.setValue(newValue);

        System.out.println("Value changed from " + oldValue
                           + " to " + map.getValue());
    }
}
```

**Output:**

```
Value changed from 123 to 2122425

```

**程序 2:**

```
// Java program to demonstrate
// AbstractMap.SimpleEntry.setValue() method

import java.util.*;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        AbstractMap.SimpleEntry<String, String> map
            = new AbstractMap
                  .SimpleEntry<String, String>("Captain:", "Dhoni");

        // change value to Kohli
        String newValue = "Kohli";
        String oldValue = map.setValue(newValue);

        System.out.println("Value changed from " + oldValue
                           + " to " + map.getValue());
    }
}
```

**Output:**

```
Value changed from Dhoni to Kohli

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/abstract map。simpleentry . html # setValue(V)](https://docs.oracle.com/javase/10/docs/api/java/util/AbstractMap.SimpleEntry.html#setValue(V))