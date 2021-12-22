# 列表包含 Java 中的 All()方法，示例

> 原文:[https://www . geesforgeks . org/list-contains all-in-Java-method-with-examples/](https://www.geeksforgeeks.org/list-containsall-method-in-java-with-examples/)

Java 中 List 接口的 containsAll()方法用于检查此 List 是否包含指定集合中的所有元素。所以基本上它是用来检查一个列表是否包含一组元素。

**语法:**

```java
boolean containsAll(Collection col)
```

**参数:**该方法接受集合类型的强制参数 **col** 。这是一个集合，需要检查它的元素是否在列表中。

**返回值:**如果集合*列*中的所有元素都在列表中，则该方法返回**真**，否则返回**假**。

**异常:**如果指定的集合为空，该方法将抛出**空指针异常**。

下面的程序说明了 containsAll()方法:

**程序 1:**

```java
// Java code to illustrate containsAll() method
import java.util.*;

public class ListDemo {
    public static void main(String args[])
    {
        // Creating an empty list
        List<String> list = new ArrayList<String>();

        // Use add() method to add elements
        // into the List
        list.add("Welcome");
        list.add("To");
        list.add("Geeks");
        list.add("4");
        list.add("Geeks");

        // Displaying the List
        System.out.println("List: " + list);

        // Creating another empty List
        List<String> listTemp = new ArrayList<String>();

        listTemp.add("Geeks");
        listTemp.add("4");
        listTemp.add("Geeks");

        System.out.println("Are all the contents equal? "
                           + list.containsAll(listTemp));
    }
}
```

**输出:**

```java
List: [Welcome, To, Geeks, 4, Geeks]
Are all the contents equal? true

```

**程序二:**

```java
// Java code to illustrate containsAll() method
import java.util.*;

public class ListDemo {
    public static void main(String args[])
    {
        // Creating an empty list
        List<Integer> list = new ArrayList<Integer>();

        // Use add() method to add elements
        // into the List
        list.add(10);
        list.add(15);
        list.add(30);
        list.add(20);
        list.add(5);

        // Displaying the List
        System.out.println("List: " + list);

        // Creating another empty List
        List<Integer> listTemp = new ArrayList<Integer>();

        listTemp.add(30);
        listTemp.add(15);
        listTemp.add(5);

        System.out.println("Are all the contents equal? "
                           + list.containsAll(listTemp));
    }
}
```

**输出:**

```java
List: [10, 15, 30, 20, 5]
Are all the contents equal? true

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/list . html # contains all(Java . util . collection)](https://docs.oracle.com/javase/7/docs/api/java/util/List.html#containsAll(java.util.Collection))