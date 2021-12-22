# Java 中的 CopyOnArrayList replaceAll()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copyonarraylist-replace all-in-Java-method-with-examples/](https://www.geeksforgeeks.org/copyonarraylist-replaceall-method-in-java-with-examples/)

java 中的**Java . util . concurrent . copyonarraylist . replace all()**方法用对元素应用运算符的结果来替换这个列表的每个元素。

**语法:**

```java
 public void replaceAll(UnaryOperator operator)
```

**参数:**该方法接受一个强制参数运算符，该运算符将应用于每个元素。

**返回类型:**该方法没有返回值。

下面的程序说明了 Java 中 CopyOnArrayList 的 replaceAll()方法:

**程序 1:** 该程序涉及字符串类型的 CopyOnArraylist replaceAll()方法:

```java
// Java Program to illustrate CopyOnArrayList
// replaceAll() method

import java.util.concurrent.CopyOnWriteArrayList;
import java.util.*;
import java.util.function.UnaryOperator;

public class GFG {
    public static void main(String[] args)
    {
        CopyOnWriteArrayList<String> ArrLis1
            = new CopyOnWriteArrayList<String>();

        // Add elements
        ArrLis1.add("White");

        ArrLis1.add("Red");

        ArrLis1.add("Blue");

        ArrLis1.add("Green");

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList: "
                           + ArrLis1);

        // check using function
        ArrLis1.replaceAll(new MyOperator());

        // print CopyOnWriteArrayList
        System.out.println("After replacement CopyonWriteArrayList: "
                           + ArrLis1);
    }
}

class MyOperator implements UnaryOperator<String> {
    public String apply(String t)
    {
        return t.replaceAll("Red", "White");
    }
}
```

**Output:**

```java
CopyOnWriteArrayList: [White, Red, Blue, Green]
After replacement CopyonWriteArrayList: [White, White, Blue, Green]

```