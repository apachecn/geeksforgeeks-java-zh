# 用示例收集 Java 中的 singletonList()方法

> 原文:[https://www . geesforgeks . org/collections-singletonlist-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-singletonlist-method-in-java-with-examples/)

**java.util.Collections** 类的 **singletonList()** 方法用于返回只包含指定对象的不可变列表。返回的列表是可序列化的。该列表将总是只包含一个元素，因此称为单例列表。当我们试图在返回的单例列表中添加/移除一个元素时，它会给出 UnsupportedOperationException。

**语法:**

```
public static  List singletonList(T o)
```

**参数:**

```
This method takes the object o as a parameter to be stored in the returned list.
```

**返回值:**

```
This method returns an immutable list containing only the specified object.
```

以下是说明*单线列表()*方法的示例

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// singletonList() method
// for <String> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // create singleton list
            // using method singletonList() method
            List<String> list = Collections.singletonList("E");

            // print the list
            System.out.println("singletonList : " + list);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output**

```
singletonList : [E]

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// singletonList() method
// for <Integer> Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // create singleton list
            // using method singletonList() method
            List<Integer> list = Collections.singletonList(20);

            // print the list
            System.out.println("singletonList : " + list);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output**

```
singletonList : [20]

```