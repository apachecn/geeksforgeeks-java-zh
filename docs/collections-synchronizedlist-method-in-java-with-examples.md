# Java 中的 Collections synchronizedList()方法，示例

> 原文:[https://www . geesforgeks . org/collections-synchronized list-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-synchronizedlist-method-in-java-with-examples/)

**java.util.Collections** 类的 **synchronizedList()** 方法用于返回由指定列表支持的同步(线程安全)列表。为了保证串行访问，通过返回的列表完成对后备列表的所有访问是至关重要的。

**语法:**

```java
public static <T> List<T>
  synchronizedList(List<T> list)
```

**参数:**该方法将**列表**作为参数“包装”在同步列表中。

**返回值:**该方法返回指定列表的**同步视图**。

以下是说明*同步列表()*方法的示例

**例 1:**

```java
// Java program to demonstrate
// synchronizedList() method for String Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of List<String>
            List<String> list = new ArrayList<String>();

            // populate the list
            list.add("A");
            list.add("B");
            list.add("C");
            list.add("D");
            list.add("E");

            // printing the Collection
            System.out.println("List : " + list);

            // create a synchronized list
            List<String> synlist = Collections
                                       .synchronizedList(list);

            // printing the Collection
            System.out.println("Synchronized list is : " + synlist);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
List : [A, B, C, D, E]
Synchronized list is : [A, B, C, D, E]

```

**例 2:**

```java
// Java program to demonstrate
// synchronizedList() method for Integer Value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of List<Integer>
            List<Integer> list = new ArrayList<Integer>();

            // populate the list
            list.add(20);
            list.add(30);
            list.add(40);
            list.add(50);
            list.add(60);

            // printing the Collection
            System.out.println("List : " + list);

            // create a synchronized list
            List<Integer> synlist = Collections
                                        .synchronizedList(list);

            // printing the Collection
            System.out.println("Synchronized list is : " + synlist);
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
List : [20, 30, 40, 50, 60]
Synchronized list is : [20, 30, 40, 50, 60]

```