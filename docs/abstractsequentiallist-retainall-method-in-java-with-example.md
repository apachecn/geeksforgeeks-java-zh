# Java 中的抽象顺序列表 retainAll()方法，示例

> 原文:[https://www . geeksforgeeks . org/abstractsequentialist-retainnal-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-retainall-method-in-java-with-example/)

**Java . util . abstractsequentialist**类的**retainnal()**方法用于从该列表中保留指定集合中包含的所有元素。

**语法:**

```java
public boolean retainAll(Collection c)
```

**参数:**该方法将**集合 c** 作为包含要从该列表中保留的元素的参数。

**返回值:**如果该列表因调用而改变，则该方法返回**真**。

**异常:**如果此列表包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则此方法抛出**空指针异常**。

以下是说明*retainal()*方法的例子。

**例 1:**

```java
// Java program to demonstrate
// retainAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of AbstractSequentialList<Integer>
            AbstractSequentialList<Integer>
                arrlist1 = new LinkedList<Integer>();

            // Populating arrlist1
            arrlist1.add(1);
            arrlist1.add(2);
            arrlist1.add(3);
            arrlist1.add(4);
            arrlist1.add(5);

            // print arrlist1
            System.out.println("AbstractSequentialList before "
                               + "retainAll() operation : "
                               + arrlist1);

            // Creating another object of  AbstractSequentialList<Integer>
            AbstractSequentialList<Integer>
                arrlist2 = new LinkedList<Integer>();
            arrlist2.add(1);
            arrlist2.add(2);
            arrlist2.add(3);

            // print arrlist2
            System.out.println("Collection Elements"
                               + " to be retaind : "
                               + arrlist2);

            // Removing elements from arrlist
            // specified in arrlist2
            // using retainAll() method
            arrlist1.retainAll(arrlist2);

            // print arrlist1
            System.out.println("AbstractSequentialList after "
                               + "retainAll() operation : "
                               + arrlist1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
AbstractSequentialList before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retaind : [1, 2, 3]
AbstractSequentialList after retainAll() operation : [1, 2, 3]

```

**示例 2:** 适用于*空指针异常*

```java
// Java program to demonstrate
// retainAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {

        try {

            // Creating object of AbstractSequentialList<Integer>
            AbstractSequentialList<Integer>
                arrlist1 = new LinkedList<Integer>();

            // Populating arrlist1
            arrlist1.add(1);
            arrlist1.add(2);
            arrlist1.add(3);
            arrlist1.add(4);
            arrlist1.add(5);

            // print arrlist1
            System.out.println("AbstractSequentialList before "
                               + "retainAll() operation : "
                               + arrlist1);

            // Creating another object of  AbstractSequentialList<Integer>
            AbstractSequentialList<Integer>
                arrlist2 = null;

            // print arrlist2
            System.out.println("Collection Elements"
                               + " to be retaind : "
                               + arrlist2);

            System.out.println("\nTrying to pass "
                               + "null as a specified element\n");

            // Removing elements from arrlist
            // specified in arrlist2
            // using retainAll() method
            arrlist1.retainAll(arrlist2);

            // print arrlist1
            System.out.println("AbstractSequentialList after "
                               + "retainAll() operation : "
                               + arrlist1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
AbstractSequentialList before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retaind : null

Trying to pass null as a specified element

Exception thrown : java.lang.NullPointerException

```