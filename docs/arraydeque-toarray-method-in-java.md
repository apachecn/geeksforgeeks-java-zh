# Java 中的 ArrayDeque toArray()方法

> 原文:[https://www . geesforgeks . org/arraydeque-to array-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-toarray-method-in-java/)

**Java . util . arraydeque . toarray()**方法用于形成一个与 Deque 相同元素的数组。基本上，该方法将所有元素从这个 deque 复制到一个新数组中。

**语法:**

```java
Object[] arr = Array_Deque.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个包含数组中元素的数组。

下面的程序说明了 java.util.ArrayDeque.toArray()方法。
**节目一:**

```java
// Java code to illustrate toArray()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Deque
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("For");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("The ArrayDeque: " + de_que);

        // Creating the array and using toArray()
        Object[] arr = de_que.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The ArrayDeque: [Welcome, To, Geeks, For, Geeks]
The array is:
Welcome
To
Geeks
For
Geeks

```

**程序 2:**

```java
// Java code to illustrate toArray()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);
        de_que.add(25);

        // Displaying the ArrayDeque
        System.out.println("The ArrayDeque: " + de_que);

        // Creating the array and using toArray()
        Object[] arr = de_que.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The ArrayDeque: [10, 15, 30, 20, 5, 25]
The array is:
10
15
30
20
5
25

```