# Java 中的 ArrayDeque spliterator()方法

> 原文:[https://www . geesforgeks . org/arraydeque-spliterator-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-spliterator-method-in-java/)

**ArrayDeque** 的 **spliterator()** 方法返回一个与 ArrayDeque 元素相同的 **[spliterator](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)** ，但是创建的 Spliterator 是后期绑定和快速失效的。后期绑定拆分器绑定到元素源意味着数组在第一次遍历、第一次拆分或第一次查询估计大小时，而不是在创建拆分器时。它可以和 Java 8 中的 Streams 一起使用。此外，它还可以单独和批量遍历元素。Spliterator 是遍历元素的更好方法，因为它对元素提供了更多的控制。

**语法:**

```java
public Spliterator<E> spliterator()
```

**返回:**这个方法在 ArrayDeque 中的元素上返回一个**分割器**。

下面的程序说明了数组的 spliterator()方法:

**示例 1:** 演示包含数字列表的 ArrayDeque 上的 spliterator()方法。

```java
// Java Program Demonstrate spliterator()
// method of ArrayDeque

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayDeque which going to
        // contains a list of numbers
        ArrayDeque<Integer> list = new ArrayDeque<Integer>();

        // Add numbers to list
        list.add(1234);
        list.add(2345);
        list.add(3456);
        list.add(4567);

        // create Spliterator of ArrayDeque
        // using spliterator() method
        Spliterator<Integer> numbers = list.spliterator();

        // print result from Spliterator
        System.out.println("list of Numbers:");

        // forEachRemaining method of Spliterator
        numbers.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**Output:**

```java
list of Numbers:
1234
2345
3456
4567

```

**示例 2:** 演示包含字符串列表的 ArrayDeque 上的 spliterator()方法。

```java
// Java Program Demonstrate spliterator()
// method of ArrayDeque

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayDeque which going to
        // contains a list of Strings
        ArrayDeque<String> list = new ArrayDeque<String>();

        // Add Strings to list
        // each string represents city name
        list.add("Kolkata");
        list.add("Delhi");
        list.add("Mumbai");
        list.add("Jaipur");

        // create Spliterator of ArrayDeque
        // using spliterator() method
        Spliterator<String> cities = list.spliterator();

        // print result from Spliterator
        System.out.println("list of Cities:");

        // forEachRemaining method of Spliterator
        cities.forEachRemaining(
            (n) -> System.out.println("City Name: " + n));
    }
}
```

**Output:**

```java
list of Cities:
City Name: Kolkata
City Name: Delhi
City Name: Mumbai
City Name: Jaipur

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/arraydeque . html # spliterator()](https://docs.oracle.com/javase/10/docs/api/java/util/ArrayDeque.html#spliterator())