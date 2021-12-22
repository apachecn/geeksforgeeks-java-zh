# Java 中的 ArrayDeque removeAll()方法

> 原文:[https://www . geesforgeks . org/arraydeque-remove all-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-removeall-method-in-java/)

ArrayDeque 的 **removeAll()** 方法用于移除 ArrayDeque 和作为参数传递的集合中常见的所有元素。该方法首先收集集合的所有元素，然后开始从数组中移除与集合元素相同的元素。此方法执行后，此 ArrayDequeu 将不包含与集合共有的元素。如果此数组因调用此方法而改变，则此方法为 True。

**语法:**

```
public boolean removeAll(Collection<? extends E> col)
```

**参数:**这个方法取一个参数 *c* ，它代表我们想要从这个数据中移除的元素的集合。

**返回:**如果由于调用此方法而导致此数据量发生变化，则此方法返回*真*。

**异常:**如果指定的集合或其任何元素为空，此方法将引发*空指针异常*。

下面的程序演示了 ArrayDeque 的 removeAll()方法:
**程序 1:** 程序演示了 ArrayDeque 上的 removeAll()方法，该方法将从包含数字的集合中移除与元素相同的元素。

```
// Java Program Demonstrate removeAll()
// method of ArrayDeque

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {

        // create an ArrayDeque which going to
        // contains a list of Numbers
        ArrayDeque<Integer> Numbers = new ArrayDeque<Integer>();

        // Add Number to list
        Numbers.add(23);
        Numbers.add(32);
        Numbers.add(45);
        Numbers.add(63);

        // print ArrayDeque before calling removeAll()
        System.out.println("Before calling removeAll()");
        print(Numbers);

        // create a collection of Number to
        // remove elements from ArrayDeque using removeAll()
        ArrayList<Integer> col = new ArrayList<Integer>();

        // add Numbers to collection
        col.add(45);
        col.add(44);
        col.add(63);

        // remove Numbers same as elements of collection
        // from ArrayDeque using removeAll()
        Numbers.removeAll(col);

        // print ArrayDeque after calling removeAll()
        System.out.println("After calling removeAll()");
        print(Numbers);
    }

    // printing all elements of ArrayDeque
    public static void print(ArrayDeque<Integer> arDe)
    {

        arDe.forEach((n) -> System.out.print(n + " "));

        System.out.println();
    }
}
```

**Output:**

```
Before calling removeAll()
23 32 45 63 
After calling removeAll()
23 32

```

**程序 2:** 在 ArrayDeque 上演示 removeAll()方法的程序，该方法将从学生姓名集合中移除与元素相同的元素。

```
// Java Program Demonstrate removeAll()
// method of ArrayDeque

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {

        // create an ArrayDeque which going to
        // contains a list of Student names which is actually
        // string values
        ArrayDeque<String> students = new ArrayDeque<String>();

        // Add Strings to list
        // each string represents student name
        students.add("Ram");
        students.add("Mohan");
        students.add("Sohan");
        students.add("Rabi");

        // print ArrayDeque before calling removeAll()
        System.out.println("Before calling removeAll()");
        print(students);

        // create a collection of Number to
        // remove elements from ArrayDeque using removeAll()
        LinkedList<String> col = new LinkedList<String>();

        // add Names in collection
        col.add("Rabi");
        col.add("Sohan");

        // remove the elements same as collection
        // from ArrayDeque using removeAll()
        students.removeAll(col);

        // print ArrayDeque
        System.out.println("After calling removeAll()");
        print(students);
    }

    // printing all elements of ArrayDeque
    public static void print(ArrayDeque<String> arDe)
    {

        System.out.println("List of Students Name:");

        arDe.forEach((n) -> System.out.print(" | " + n + " | "));

        System.out.println("\n");
    }
}
```

**Output:**

```
Before calling removeAll()
List of Students Name:
 | Ram |  | Mohan |  | Sohan |  | Rabi | 

After calling removeAll()
List of Students Name:
 | Ram |  | Mohan |

```

**程序 3:** 演示 removeAll()方法引发异常的程序。

```
// Java Program Demonstrate Exception thrown by removeAll()
// method of ArrayDeque

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {

        // create an ArrayDeque which going to
        // contains a list of Numbers
        ArrayDeque<Integer> Numbers = new ArrayDeque<Integer>();

        // Add Number to list
        Numbers.add(223);
        Numbers.add(132);
        Numbers.add(345);
        Numbers.add(563);

        // create a collection of Number which is null
        ArrayList<Integer> col = null;

        try {
            // call removeAll() method
            Numbers.removeAll(col);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/arraydeque . html # removeAll(Java . util . collection)](https://docs.oracle.com/javase/10/docs/api/java/util/ArrayDeque.html#removeAll(java.util.Collection))