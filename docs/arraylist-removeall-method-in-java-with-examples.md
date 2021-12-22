# Java 中的 ArrayList removeAll()方法，示例

> 原文:[https://www . geesforgeks . org/ArrayList-remove all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/arraylist-removeall-method-in-java-with-examples/)

**[Java . util . ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/)**类的 **removeAll()** 方法用于从该列表中移除指定集合中包含的所有元素。

**语法:**

```
public boolean removeAll(Collection c)
```

**参数:**该方法将**集合 c** 作为包含要从该列表中移除的元素的参数。

**返回值:**如果该列表因调用而改变，则该方法返回**真**。

**异常:**如果此列表包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则此方法抛出**空指针异常**。

以下是说明 *removeAll()* 方法的示例。

**例 1:**

```
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of ArrayList<Integer>
            ArrayList<Integer>
                arrlist1 = new ArrayList<Integer>();

            // Populating arrlist1
            arrlist1.add(1);
            arrlist1.add(2);
            arrlist1.add(3);
            arrlist1.add(4);
            arrlist1.add(5);

            // print arrlist1
            System.out.println("ArrayList before "
                               + "removeAll() operation : "
                               + arrlist1);

            // Creating another object of  ArrayList<Integer>
            ArrayList<Integer>
                arrlist2 = new ArrayList<Integer>();
            arrlist2.add(1);
            arrlist2.add(2);
            arrlist2.add(3);

            // print arrlist2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + arrlist2);

            // Removing elements from arrlist
            // specified in arrlist2
            // using removeAll() method
            arrlist1.removeAll(arrlist2);

            // print arrlist1
            System.out.println("ArrayList after "
                               + "removeAll() operation : "
                               + arrlist1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayList before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : [1, 2, 3]
ArrayList after removeAll() operation : [4, 5]

```

**示例 2:** 适用于*空指针异常*

```
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of ArrayList<Integer>
            ArrayList<Integer>
                arrlist1 = new ArrayList<Integer>();

            // Populating arrlist1
            arrlist1.add(1);
            arrlist1.add(2);
            arrlist1.add(3);
            arrlist1.add(4);
            arrlist1.add(5);

            // print arrlist1
            System.out.println("ArrayList before "
                               + "removeAll() operation : "
                               + arrlist1);

            // Creating another object of  ArrayList<Integer>
            ArrayList<Integer>
                arrlist2 = null;

            // print arrlist2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + arrlist2);

            System.out.println("\nTrying to pass "
                               + "null as a specified elelemnt\n");

            // Removing elements from arrlist
            // specified in arrlist2
            // using removeAll() method
            arrlist1.removeAll(arrlist2);

            // print arrlist1
            System.out.println("ArrayList after "
                               + "removeAll() operation : "
                               + arrlist1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ArrayList before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : null

Trying to pass null as a specified elelemnt

Exception thrown : java.lang.NullPointerException

```