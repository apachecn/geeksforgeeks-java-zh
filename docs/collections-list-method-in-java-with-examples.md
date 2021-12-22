# Java 中的集合列表()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-list-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-list-method-in-java-with-examples/)

**java.util.Collections** 类的 **list()** 方法用于返回一个数组列表，该数组列表包含指定枚举返回的元素，这些元素按照枚举返回的顺序排列。该方法提供了返回枚举的旧 API 和需要集合的新 API 之间的互操作性。

**语法:**

```java
public static ArrayList list(Enumeration e)
```

**参数:**该方法以**枚举 e** 为参数，为返回的数组列表提供元素。

**返回值:**这个方法返回**一个数组列表**，包含指定枚举返回的元素。

以下是举例说明*列表()*方法

**例 1:**

```java
// Java program to demonstrate
// list() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of List<String>
            List<String> arrlist = new ArrayList<String>();

            // creating object of Vector<String>
            Vector<String> v = new Vector<String>();

            // Adding element to Vector v
            v.add("A");
            v.add("B");
            v.add("C");
            v.add("D");
            v.add("E");

            // printing the list
            System.out.println("Current list : " + arrlist);

            // creating Enumeration
            Enumeration<String> e = v.elements();

            // getting arrlist of specified Enumeration
            // using list() method
            arrlist = Collections.list(e);

            // printing the arrlist
            System.out.println("Returned list: " + arrlist);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Current list : []
Returned list: [A, B, C, D, E]

```

**例 2:**

```java
// Java program to demonstrate
// list() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of List<String>
            List<Integer> arrlist = new ArrayList<Integer>();

            // creating object of Vector<String>
            Vector<Integer> v = new Vector<Integer>();

            // Adding element to Vector v
            v.add(10);
            v.add(20);
            v.add(30);
            v.add(40);
            v.add(50);

            // printing the list
            System.out.println("Current list : " + arrlist);

            // creating Enumeration
            Enumeration<Integer> e = v.elements();

            // getting arrlist of specified Enumeration
            // using list() method
            arrlist = Collections.list(e);

            // printing the arrlist
            System.out.println("Returned list: "
                               + arrlist);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Current list : []
Returned list: [10, 20, 30, 40, 50]

```