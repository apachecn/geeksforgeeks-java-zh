# JavaTuples fromCollection()方法

> 原文:[https://www . geesforgeks . org/Java-元组-fromcollection-method/](https://www.geeksforgeeks.org/java-tuples-fromcollection-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **fromCollection()** 方法用于以语义优雅的方式实例化元组，集合的值作为参数给出。这个方法可以用于 javatuples 库的任何元组类对象。它是每个 javatuple 类中的静态函数，它返回被调用类的 tuple 类对象，其值由集合的相应值初始化。

**方法申报:**

```java
public static <X> TupleClass<X> fromCollection(Collection<X> collection)
```

**语法:**

```java
TupleClass<X> obj = TupleClass.fromCollection(Collection<X> collection)
```

**参数:**该方法以*集合*为参数，其中:

*   **X**–表示集合中值的数据类型。
*   **集合**–表示要插入到 TupleClass 中的值的集合。
*   **类类**–代表像单位、五重奏、十年等使用的 JavaTuple 类。

**返回值:**该方法返回*类*的对象，该对象调用方法，集合的值作为参数传递。

下面的程序说明了使用 fromCollection()方法的各种方法:

**程序 1:** 使用单位类为

```java
// Below is a Java program to create
// a Unit tuple from fromCollection() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an collection with one value
        List<String> list = new ArrayList<String>();
        list.add("GeeksforGeeks");

        // Using fromCollection() method
        Unit<String> unit = Unit.fromCollection(list);

        System.out.println(unit);
    }
}
```

的 fromCollection()

**输出:**

```java
[GeeksforGeeks]
```

**程序 2:** 使用带有十进制类的 fromCollection()

**输出:**

```java
[Geeks, for, Geeks, A, Computer, Science, Portal, for, Geeks, RishabhPrabhu]
```

注意:同样，它也可以用于任何其他的 JavaTuple 类。