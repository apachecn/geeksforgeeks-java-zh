# 用示例列出 Java 中的 listIterator()方法

> 原文:[https://www . geesforgeks . org/list-listiterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-listiterator-method-in-java-with-examples/)

这个方法从列表中的指定位置开始，返回一个列表迭代器，遍历上述列表中的元素(按照正确的顺序)。

**语法:**

```
ListIterator listIterator(int index)
```

**参数:**这个方法只有一个参数，即 index–从列表迭代器返回的第一个元素的索引(通过调用 next)。

**返回:**这个方法从列表中的指定位置开始，返回列表迭代器，遍历列表中的元素(按照正确的顺序)。

**异常:**该方法抛出异常*indexout of boundsexception*–如果索引超出范围(索引大小())

下面的程序展示了这种方法的实现。

**程序 1:**

```
// Java program to demonstrate
// listIterator() method
// for List interface
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Creating object of List<Integer>
            List<Integer> arrlist = new ArrayList<>();

            // adding element to arrlist
            arrlist.add(1);
            arrlist.add(3);
            arrlist.add(6);
            arrlist.add(9);

            // print arrlist
            System.out.println("ArrayList: "
                               + arrlist);

            // Creating object of ListIterator<String>
            // using listIterator() method
            ListIterator<Integer>
                iterator = arrlist.listIterator();

            // Printing the iterated value
            System.out.println("\nUsing ListIterator:\n");
            while (iterator.hasNext()) {
                System.out.println("Value is : "
                                   + iterator.next());
            }
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayList: [1, 3, 6, 9]

Using ListIterator:

Value is : 1
Value is : 3
Value is : 6
Value is : 9

```

**程序 2:** 下面是使用 Linkedlist 展示 list.subList()实现的代码。

```
// Java program to demonstrate
// listIterator() method
// for List interface
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Creating object of List<Integer>
            List<String> arrlist = new ArrayList<String>();

            // adding element to arrlist
            arrlist.add("A");
            arrlist.add("B");
            arrlist.add("C");
            arrlist.add("D");

            // print arrlist
            System.out.println("ArrayList: "
                               + arrlist);

            // Creating object of ListIterator<String>
            // using listIterator() method
            ListIterator<String>
                iterator = arrlist.listIterator();

            // Printing the iterated value
            System.out.println("\nUsing ListIterator:\n");
            while (iterator.hasNext()) {
                System.out.println("Value is : "
                                   + iterator.next());
            }
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayList: [A, B, C, D]

Using ListIterator:

Value is : A
Value is : B
Value is : C
Value is : D

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))