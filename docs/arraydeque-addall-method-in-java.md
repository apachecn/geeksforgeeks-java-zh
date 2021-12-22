# Java 中的 ArrayDeque addAll()方法

> 原文:[https://www . geesforgeks . org/arraydeque-addall-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-addall-method-in-java/)

ArrayDeque 的 **addAll()** 方法用于在这个 ArrayDeque 的末尾插入作为参数传递的集合的所有元素。为了将集合的元素添加到 ArrayDeque 中，我们必须遍历集合，并使用 addLast(E)方法在 ArrayDeque 中添加每个元素。这种方法的工作原理与我们在此讨论的相同，但工作量较小。如果由于调用此方法而改变了此值，则此方法返回*真*。

**语法:**

```
public boolean addAll(Collection<? extends E> c)
```

**参数:**这个方法取一个参数 *c* ，它代表我们要插入到这个 deque 中的元素的集合。

**返回:**如果由于调用此方法而导致此数据量发生变化，则此方法返回*真*。

**异常:**如果指定的集合或其任何元素为空，此方法将引发*空指针异常*。

下面的程序演示了 ArrayDeque 的 addAll()方法:
**程序 1:** 程序演示了 ArrayDeque 上的 addAll()方法，该方法将添加一个包含数字的集合。

```
// Java Program Demonstrate addAll()
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

        // print ArrayDeque before calling addAll()
        System.out.println("Before calling addAll()");
        print(Numbers);

        // create a collection of Number to
        // add in ArrayDeque using addAll()
        ArrayList<Integer> col = new ArrayList<Integer>();

        // add Numbers in collection
        col.add(74);
        col.add(65);
        col.add(84);

        // add the elements of collection at the end
        // of ArrayDeque using addAll()
        Numbers.addAll(col);

        // print ArrayDeque
        System.out.println("After calling addAll()");
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
Before calling addAll()
23 32 45 63 
After calling addAll()
23 32 45 63 74 65 84

```

**程序 2:** 在 ArrayDeque 上演示 addAll()方法的程序，该方法将添加一组学生姓名。

```
// Java Program Demonstrate addAll()
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

        // print ArrayDeque before calling addAll()
        System.out.println("Before calling addAll()");
        print(students);

        // create a collection of String to
        // add in ArrayDeque using addAll()
        LinkedList<String> col = new LinkedList<String>();

        // add Names in collection
        col.add("Rohan");
        col.add("Kartik");

        // add the elements of collection at the end
        // of ArrayDeque using addAll()
        students.addAll(col);

        // print ArrayDeque
        System.out.println("After calling addAll()");
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
Before calling addAll()
List of Students Name:
 | Ram |  | Mohan |  | Sohan |  | Rabi | 

After calling addAll()
List of Students Name:
 | Ram |  | Mohan |  | Sohan |  | Rabi |  | Rohan |  | Kartik |

```

**程序 3:** 演示 addAll()方法抛出异常的程序。

```
// Java Program Demonstrate Exception thrown by addAll()
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
            // call addAll() method
            Numbers.addAll(col);
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

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/arraydeque . html # addAll(Java . util . collection)](https://docs.oracle.com/javase/10/docs/api/java/util/ArrayDeque.html#addAll(java.util.Collection))