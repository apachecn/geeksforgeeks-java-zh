# Java 中的 HashSet spliterator()方法

> 原文:[https://www . geesforgeks . org/hashset-spliterator-method-in-Java/](https://www.geeksforgeeks.org/hashset-spliterator-method-in-java/)

HashSet 的 **spliterator()** 方法返回一个 **[Spliterator](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)** ，其元素与 **[HashSet](https://www.geeksforgeeks.org/hashset-in-java/)** 相同。返回的拆分器是**后期绑定和快速失效**拆分器。后期绑定拆分器绑定到元素的源意味着在第一次遍历、第一次拆分或第一次查询估计大小时有一个集合，而不是在创建拆分器时。它可以和 Java 8 中的 Streams 一起使用。此外，它还可以单独和批量遍历元素。Spliterator 是遍历元素的更好方法，因为它对元素提供了更多的控制。

**语法:**

```
public Spliterator<E> spliterator()
```

**返回:**该方法在哈希集中的元素上返回一个**分隔符**。

下面的程序说明了 HashSet 的 spliterator()方法:

**示例 1:** 演示包含一组数字的 HashSet 上的 spliterator()方法。

```
// Java Program Demonstrate spliterator()
// method of HashSet

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {

        // create an HashSet which going to
        // contains a list of Numbers
        HashSet<Integer> Numbers = new HashSet<Integer>();

        // Add Number to list
        Numbers.add(23);
        Numbers.add(32);
        Numbers.add(45);
        Numbers.add(63);

        // using spliterator() method
        Spliterator<Integer> numbers = Numbers.spliterator();

        // print result from Spliterator
        System.out.println("list of Numbers:");

        // forEachRemaining method of Spliterator
        numbers.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**输出:**

```
list of Numbers:
32
23
45
63

```

**示例 2:** 演示包含一组学生姓名的 HashSet 上的 spliterator()方法。

```
// Java Program Demonstrate spliterator()
// method of HashSet

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {

        // create an HashSet which going to
        // contains a list of string values
        HashSet<String> students = new HashSet<String>();

        // Add Strings to list
        students.add("Ram");
        students.add("Mohan");
        students.add("Sohan");
        students.add("Rabi");

        // using spliterator() method
        Spliterator<String> names = students.spliterator();

        // print result from Spliterator
        System.out.println("list of Students:");

        // forEachRemaining method of Spliterator
        names.forEachRemaining(
            (n) -> System.out.println("Student Name: " + n));
    }
}
```

**输出:**

```
list of Students:
Student Name: Rabi
Student Name: Mohan
Student Name: Sohan
Student Name: Ram

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/hashset . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html#spliterator--)