# 用示例列出 Java 中的 isEmpty()方法

> 原文:[https://www . geesforgeks . org/list-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-isempty-method-in-java-with-examples/)

java 中 List 接口的 **isEmpty()** 方法用于检查列表是否为空。如果列表不包含任何元素，则返回 true 否则，如果列表包含任何元素，则返回 false。

**语法:**

```java
boolean isEmpty()
```

**参数:**不接受任何参数。

**返回:**如果列表没有其他元素，则返回真，否则返回假。返回类型是布尔数据类型。

**错误和异常:**该方法没有错误或异常。

用 Java 演示 isEmpty()工作的程序:

```java
// Java code to demonstrate the working of
// isEmpty() method in List interface

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an Empty Integer List
        List<Integer> arr = new ArrayList<Integer>(10);

        // check if the list is empty or not
        // using isEmpty() function
        boolean ans = arr.isEmpty();
        if (ans == true)
            System.out.println("The List is empty");
        else
            System.out.println("The List is not empty");

        // addition of a element to
        // the List
        arr.add(1);

        // check if the list is empty or not
        // after adding an element
        ans = arr.isEmpty();
        if (ans == true)
            System.out.println("The List is empty");
        else
            System.out.println("The List is not empty");
    }
}
```

**输出:**

```java
The List is empty
The List is not empty

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/list . html # isEmpty()](https://docs.oracle.com/javase/7/docs/api/java/util/List.html#isEmpty())