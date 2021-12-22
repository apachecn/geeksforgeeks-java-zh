# 用示例列出 Java 中的 get()方法

> 原文:[https://www . geesforgeks . org/list-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-get-method-in-java-with-examples/)

Java 中 List 接口的 **get()** 方法用于获取这个列表中给定特定索引处存在的元素。

**语法:**

```java
E get(int index)

Where, E is the type of element maintained
by this List container.

```

**参数:**该方法接受整数类型的单个参数*索引*，该索引表示该列表中要返回的元素的索引。

**返回值:**返回给定列表中指定索引处的元素。

**错误和异常:**如果索引超出范围(索引=大小())，该方法将抛出**indexout of boundsexception**。

下面的程序说明了 get()方法:

**程序 1 :**

```java
// Java code to demonstrate the working of
// get() method in List

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an Empty Integer List
        List<Integer> arr = new ArrayList<Integer>(4);

        // using add() to initialize values
        // [10, 20, 30, 40]
        arr.add(10);
        arr.add(20);
        arr.add(30);
        arr.add(40);

        System.out.println("List: " + arr);

        // element at index 2
        int element = arr.get(2);

        System.out.println("The element at index 2 is " + element);
    }
}
```

**输出:**

```java
List: [10, 20, 30, 40]
The element at index 2 is 30

```

**程序 2** :演示错误的程序。

```java
// Java code to demonstrate the error of
// get() method in List

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an Empty Integer List
        List<Integer> arr = new ArrayList<Integer>(4);

        // using add() to initialize values
        // [10, 20, 30, 40]
        arr.add(10);
        arr.add(20);
        arr.add(30);
        arr.add(40);

        try {
            // Trying to access element at index 8
            // which will throw an Exception
            int element = arr.get(8);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.IndexOutOfBoundsException: Index: 8, Size: 4

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/list . html # get(int)](https://docs.oracle.com/javase/7/docs/api/java/util/List.html#get(int))