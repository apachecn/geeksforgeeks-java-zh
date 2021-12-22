# Java 中的抽象集 removeAll()方法，示例

> 原文:[https://www . geesforgeks . org/abstract set-remove all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractset-removeall-method-in-java-with-examples/)

**[Java 抽象集](https://www.geeksforgeeks.org/abstractset-class-in-java-with-examples/)** 类的 **removeAll()** 方法用于从该集中移除指定集合中包含的所有元素。

**语法:**

```java
public boolean removeAll(Collection c)
```

**参数:**该方法将**集合 c** 作为包含要从该集合中移除的元素的参数。

**返回值:**如果该设置因调用而改变，则该方法返回**真**。

**异常:**该方法抛出三种类型的异常:

*   *不支持操作异常*–如果该设置不支持该操作，则抛出该异常。
*   *class castexception*–当这个集合的元素的类与指定的集合不兼容时抛出。
*   *NullPointRexception*–当该集合包含空元素并且指定的集合不允许空元素时，或者如果集合为空，则会引发该异常。

以下是说明 *removeAll()* 方法的示例。

**程序 1:**

```java
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] args) throws Exception
    {

        try {

            // Creating object of AbstractSet<Integer>
            AbstractSet<Integer>
                abs_set = new TreeSet<Integer>();

            // Populating abs_set
            abs_set.add(1);
            abs_set.add(2);
            abs_set.add(3);
            abs_set.add(4);
            abs_set.add(5);

            // print abs_set
            System.out.println("AbstractSet before "
                               + "removeAll() operation : "
                               + abs_set);

            // Creating another object of ArrayList<Integer>
            Collection<Integer>
                arrlist2 = new ArrayList<Integer>();
            arrlist2.add(1);
            arrlist2.add(2);
            arrlist2.add(3);

            // print arrlist2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + arrlist2);

            // Removing elements from AbstractSet
            // specified in arrlist2
            // using removeAll() method
            abs_set.removeAll(arrlist2);

            // print arrlist1
            System.out.println("AbstractSet after "
                               + "removeAll() operation : "
                               + abs_set);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
AbstractSet before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : [1, 2, 3]
AbstractSet after removeAll() operation : [4, 5]

```

**示例 2:** 适用于*空指针异常*

```java
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] args) throws Exception
    {

        try {

            // Creating object of AbstractSet<Integer>
            AbstractSet<Integer>
                abs_set = new TreeSet<Integer>();

            // Populating abs_set
            abs_set.add(1);
            abs_set.add(2);
            abs_set.add(3);
            abs_set.add(4);
            abs_set.add(5);

            // print abs_set
            System.out.println("AbstractSet before "
                               + "removeAll() operation : "
                               + abs_set);

            // Creating another object of ArrayList<Integer>
            Collection<Integer>
                arrlist2 = new ArrayList<Integer>();
            arrlist2 = null;

            // print arrlist2
            System.out.println("Collection Elements"
                               + " to be removed : "
                               + arrlist2);

            // Removing elements from AbstractSet
            // specified in arrlist2
            // using removeAll() method
            abs_set.removeAll(arrlist2);

            // print arrlist1
            System.out.println("AbstractSet after "
                               + "removeAll() operation : "
                               + abs_set);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
AbstractSet before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : null
Exception thrown : java.lang.NullPointerException

```