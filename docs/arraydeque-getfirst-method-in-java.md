# Java 中的 ArrayDeque getFirst()方法

> 原文:[https://www . geesforgeks . org/arraydeque-get first-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-getfirst-method-in-java/)

java 中的 java.util.ArrayDeque.getFirst()方法用于检索或获取 ArrayDeque 的第一个元素。在这个过程中，该方法并不从 deque 中删除元素，而是返回 deque 的第一个元素。

**语法:**

```java
Array_Deque.getFirst()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回德格中存在的第一个元素。

下面的程序说明了 Java.util.ArrayDeque.getFirst()方法:

**程序 1:**

```java
// Java code to illustrate getFirst()
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

        // Displaying the first element
        System.out.println("The first element is: " + 
                                    de_que.getFirst());
    }
}
```

**Output:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
The first element is: Welcome

```

**程序 2:**

```java
// Java code to illustrate getFirst()
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

        // Displaying the first element
        System.out.println("The first element is: " + 
                                      de_que.getFirst());
    }
}
```

**Output:**

```java
ArrayDeque: [10, 15, 30, 20, 5]
The first element is: 10

```