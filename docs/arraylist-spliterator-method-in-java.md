# Java 中的数组列表拆分器()方法

> 原文:[https://www . geesforgeks . org/ArrayList-spliterator-method-in-Java/](https://www.geeksforgeeks.org/arraylist-spliterator-method-in-java/)

**[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)** 的**分割器()**方法返回一个与数组列表元素相同的分割器，但是创建的分割器是后期绑定和快速失效的。后期绑定拆分器绑定到元素源。这意味着数组列表位于第一次遍历、第一次拆分或第一次查询估计大小的位置，而不是创建拆分器的位置。它可以和 Java 8 中的 Streams 一起使用。此外，它还可以单独和批量遍历元素。Spliterator 是遍历元素的更好方法，因为它提供了对元素的更多控制。

```java
Spliterator = Splitting + Iterator
```

*   它使用 *tryAdvance()* 方法在多个线程中单独迭代元素，支持并行处理，
*   *foreachretaining()*方法在单个线程中顺序迭代元素，
*   *trySplit()* 方法将自身划分为子分裂器，支持并行处理。

分割器支持数据的顺序和并行处理。

如果您观察下面程序输出的输出，您会发现 Spliterator.forEachRemaining()方法的工作方式与 ArrayList.foreach()相同，但它提供了更好的性能。

**语法:**

```java
public Spliterator<E> spliterator()
```

**返回:**该方法在数组列表中的元素上返回一个**分隔符**。

下面的程序说明数组列表的 spliterator()方法:

**示例 1:** 演示包含电子邮件列表的 ArrayList 上的 spliterator()方法。

```java
// Java Program Demonstrate spliterator()
// method of ArrayList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayList which contains
        // emails for a group of people
        ArrayList<String> list = new ArrayList<String>();

        // Add emails to list
        list.add("abc@geeksforgeeks.org");
        list.add("user@geeksforgeeks.org");
        list.add("pqr@geeksforgeeks.org");
        list.add("random@geeksforgeeks.org");
        list.add("randomuser@geeksforgeeks.org");

        // create Spliterator of ArrayList
        // using spliterator() method
        Spliterator<String> emails = list.spliterator();

        // print result from Spliterator
        System.out.println("list of Emails:");

        // forEachRemaining method of Spliterator
        emails.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**Output:**

```java
list of Emails:
abc@geeksforgeeks.org
user@geeksforgeeks.org
pqr@geeksforgeeks.org
random@geeksforgeeks.org
randomuser@geeksforgeeks.org

```

**示例 2:** 演示包含用户列表的 ArrayList 上的 spliterator()方法。

```java
// Java Program Demonstrate spliterator()
// method of ArrayList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ArrayList which contains
        // user details from user class
        ArrayList<user> list = new ArrayList<user>();

        // Add emails to list
        list.add(new user("Aman", 24));
        list.add(new user("Suraj", 23));
        list.add(new user("Amar", 24));
        list.add(new user("Kajal", 22));

        // create Spliterator of ArrayList
        // using spliterator() method
        Spliterator<user> users = list.spliterator();

        // print result from Spliterator
        System.out.println("list of Emails:");

        // forEachRemaining method of Spliterator
        users.forEachRemaining((n) -> print(n));
    }

    public static void print(user u)
    {
        System.out.println("User name : " + u.name
                           + " and user age: " + u.age);
    }
}

// create a user class
class user {

    String name;
    int age;

    user(String name, int age)
    {
        this.name = name;
        this.age = age;
    }
}
```

**Output:**

```java
list of Emails:
User name : Aman and user age: 24
User name : Suraj and user age: 23
User name : Amar and user age: 24
User name : Kajal and user age: 22

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/ArrayList . html # spliterator()](https://docs.oracle.com/javase/10/docs/api/java/util/ArrayList.html#spliterator())