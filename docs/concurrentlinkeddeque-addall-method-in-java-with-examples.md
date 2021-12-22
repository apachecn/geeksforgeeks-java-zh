# Java 中的 concurrentlinkedrequeaddall()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-addall-method-in-java-with-examples/)

的 **addAll(Collection col)** 以 col 为参数，其中 col 是元素的集合(List、ArrayList、LinkedList 等)。整个集合被追加或添加到出列的末尾。这个方法就像 add()方法一样，如果集合被追加到 Deque，则返回 true。

**语法:**

```
public boolean addAll(Collection c)
```

**参数:**该函数接受一个参数**列**，该参数是要添加的元素的集合。

**返回值:**该方法返回 ***一个布尔值*** ，说明集合是否被追加到了 Deque。

**异常:**此方法接受两个异常:

*   **[null pointerexception:** If any element in the collection is null or the collection is null.
*   **IllegalArgumentException:** If the passed set is the existing deque itself.

以下示例说明了 addAll()方法:

**示例 1:** 将数字集合添加到第一个 ConcurrentLinkedDeque 集合

```
// Java program to illustrate addAll() method

import java.util.concurrent.ConcurrentLinkedDeque;

public class Example1 {
    public static void main(String[] args)
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> ld1
            = new ConcurrentLinkedDeque<Integer>();

        // Add elements
        ld1.add(1);
        ld1.add(2);
        ld1.add(3);
        ld1.add(4);

        // print ld1
        System.out.println("LD1: " + ld1);

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> ld2
            = new ConcurrentLinkedDeque<Integer>();

        ld2.add(8);
        ld2.add(1);
        ld2.add(3);
        ld2.add(5);

        // print ld2
        System.out.println("LD2: " + ld2);

        // Adding elements of ld2 to ld1 at its end.
        ld1.addAll(ld2);

        System.out.println("After adding the ld2 to ld1: "
                           + ld1);
    }
}
```

**输出:**

```
LD1: [1, 2, 3, 4]
LD2: [8, 1, 3, 5]
After adding the ld2 to ld1: [1, 2, 3, 4, 8, 1, 3, 5]

```

**示例 2:** 显示 IllegalArgumentException

```
// Java program to illustrate addAll() method

import java.util.concurrent.ConcurrentLinkedDeque;

public class Example2 {
    public static void main(String[] args)
    {
        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> ld1
            = new ConcurrentLinkedDeque<String>();

        // Add elements
        ld1.add("John");
        ld1.add("Johnathan");
        ld1.add("Jones");
        ld1.add("James");

        // print ld1
        System.out.println("LD1: " + ld1);

        try {
            ld1.addAll(ld1);
        }
        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown while "
                               + "adding deque to "
                               + "itself is: "
                               + e);
        }
    }
}
```

**输出:**

```
LD1: [John, Johnathan, Jones, James]
Exception thrown while adding deque to itself is: java.lang.IllegalArgumentException

```

**示例 3:** 显示空指针异常

```
// Java program to illustrate addAll() method

import java.util.concurrent.ConcurrentLinkedDeque;

public class Example3 {
    public static void main(String[] args)
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> ld1
            = new ConcurrentLinkedDeque<String>();

        // Add elements
        ld1.add("John");
        ld1.add("Johnathan");
        ld1.add("Jones");
        ld1.add("James");

        // print ld1
        System.out.println("LD1: " + ld1);

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> ld2 = null;

        // print ld2
        System.out.println("LD2: " + ld2);

        try {

            System.out.println("After adding the ld2 to ld1: ");
            ld2.addAll(ld1);
        }
        catch (NullPointerException e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
LD1: [John, Johnathan, Jones, James]
LD2: null
After adding the ld2 to ld1: 
java.lang.NullPointerException

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrentlinkedrequest . html](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html)