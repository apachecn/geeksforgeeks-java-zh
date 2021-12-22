# 用示例列出 Java 中的 clear()方法

> 原文:[https://www . geesforgeks . org/list-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-clear-method-in-java-with-examples/)

Java 中**列表界面**的 **clear()** 方法用于从列表容器中移除所有元素。这个方法不删除列表容器，而是从列表中删除所有元素。

**语法:**

```
public void clear()
```

**参数:**此方法接受不接受任何参数。

**返回值:**函数的返回类型为 void，不返回任何内容。

**异常**:如果此列表不支持 clear()操作，此方法将抛出**不支持操作异常**。

下面的程序说明了 List.clear()方法:

**程序 1:**

```
// Java code to illustrate clear() method
import java.io.*;
import java.util.*;

public class ListDemo {
    public static void main(String[] args)
    {

        // create an empty list with an initial capacity
        List<String> list = new ArrayList<String>(5);

        // use add() method to initially
        // add elements in the list
        list.add("Geeks");
        list.add("For");
        list.add("Geeks");

        // Remove all elements from the List
        list.clear();

        // print the List
        System.out.println(list);
    }
}
```

**输出:**

```
[]

```

**程序二:**

```
// Java code to illustrate clear() method
import java.io.*;
import java.util.*;

public class ListDemo {
    public static void main(String[] args)
    {

        // create an empty list with an initial capacity
        List<Integer> list = new ArrayList<Integer>(5);

        // use add() method to initially
        // add elements in the list
        list.add(10);
        list.add(20);
        list.add(30);

        // clear the list
        list.clear();

        // prints all the elements available in list
        System.out.println(list);
    }
}
```

**输出:**

```
[]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/list . html # clear()](https://docs.oracle.com/javase/7/docs/api/java/util/List.html#clear())