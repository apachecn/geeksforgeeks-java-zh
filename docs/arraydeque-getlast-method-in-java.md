# Java 中的 ArrayDeque getLast()方法

> 原文:[https://www . geesforgeks . org/arraydeque-get last-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-getlast-method-in-java/)

java 中的 java.util.ArrayDeque.getLast()方法用于检索或获取 ArrayDeque 的最后一个元素。在这个过程中，该方法并不从 deque 中删除元素，而是返回 deque 的最后一个元素。
**语法:**

```java
Array_Deque.getLast()

```

**参数:**该方法不取任何参数。
**返回值:**该方法返回德格中存在的最后一个元素。
**异常:**这个方法抛出 NoSuchElementException，如果这个 deque 被调用时是空的。

下面的程序说明了 Java.util.ArrayDeque.getLast()方法:

**节目 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate getLast() method of ArrayDeque
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        ArrayDeque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Deque
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the Last element
        System.out.println("The last element is: " + de_que.getLast());

        // clear the deque
        de_que.clear();
        try {
           de_que.getLast();
        } catch(Exception ex) {
           System.out.println("Exception  "+ ex);
         }
    }
}
```

**Output:** 

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The last element is: Geeks

```

**程序 2:** 将整数元素加入到德格中。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate getLast() method of ArrayDeque
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        ArrayDeque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Displaying the Last element
        System.out.println("The last element is: " + de_que.getLast());
    }
}
```

**Output:** 

```java
ArrayDeque: [10, 15, 30, 20, 5]
The last element is: 5

```