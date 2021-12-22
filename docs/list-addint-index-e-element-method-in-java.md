# Java 中的 List add(int index，E 元素)方法

> 原文:[https://www . geesforgeks . org/list-addint-index-e-element-method-in-Java/](https://www.geeksforgeeks.org/list-addint-index-e-element-method-in-java/)

Java 中**列表界面**的 **add(int index，E ele)** 方法用于在当前列表中给定的索引处插入指定的元素。

**语法:**

```java
public void add(int index, E element)
```

**参数:**这个方法接受两个参数，如上面的语法所示:

*   **Index** : This parameter specifies the index to insert the given element.
*   **Element** : This parameter specifies the element to be inserted in the list.

**返回值:**函数的返回类型为 void，不返回任何内容。

**异常** :

*   **Unsupported operation exception** –If this list does not support the add () operation, it will throw this exception.
*   **classcastexception** –If the class of the specified element prevents it from being added to this list, it will throw this exception.
*   **null pointerexception** –If the specified element is empty and the list does not allow empty elements, it will throw this exception.
*   **IllegalException** –If some attributes of this element prevent it from being added to this list, it will throw this exception.

下面的程序说明了 List.add(int index，E 元素)方法:

**程序 1:**

```java
// Java code to illustrate add(int index, E elements)
import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {

        // create an empty list with an initial capacity
        List<String> list = new ArrayList<String>(5);

        // use add() method to initially
        // add elements in the list
        list.add("Geeks");
        list.add("For");
        list.add("Geeks");

        // Add a new element at index 0
        list.add(0, "Hello");

        // prints all the elements available in list
        for (String str : list) {
            System.out.print(str + " ");
        }
    }
}
```

**输出:**

```java
Hello Geeks For Geeks

```

**程序二:**

```java
// Java code to illustrate add(int index, E elements)
import java.io.*;
import java.util.*;

public class ArrayListDemo {
    public static void main(String[] args)
    {

        // create an empty list with an initial capacity
        List<Integer> list = new ArrayList<Integer>(5);

        // use add() method to initially
        // add elements in the list
        list.add(10);
        list.add(20);
        list.add(30);

        // Add a new  25 at index 2
        list.add(2, 25);

        // prints all the elements available in list
        for (Integer num : list) {
            System.out.print(num + " ");
        }
    }
}
```

**输出:**

```java
10 20 25 30

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/list . html # add(int，%20E)](https://docs.oracle.com/javase/7/docs/api/java/util/List.html#add(int, %20E))