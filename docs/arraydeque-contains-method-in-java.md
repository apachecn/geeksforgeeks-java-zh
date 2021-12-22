# ArrayDeque 包含 Java 中的()方法

> 原文:[https://www . geesforgeks . org/arraydeque-contains-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-contains-method-in-java/)

Java 中的 Java.util.ArrayDeque.contains()方法用于检查或验证一个特定的元素是否存在于 Deque 中。

**语法:**

```java
Array_Deque.contains(*Object element*)
```

**参数:**参数*元素*属于数组类型。这是需要测试的元素，无论它是否存在于 deque 中。

**返回值:**如果元素存在于对象中，该方法返回真，否则返回假。

下面的程序说明了 Java.util.ArrayDeque.contains()方法:
**程序 1:**

```java
// Java code to illustrate contains()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<String> de_que = new ArrayDeque<String>();

        // Use add() method to add elements into the Queue
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Check for "Geeks" in the deque
        System.out.println("Does the deque contains 'Geeks'? "
                           + de_que.contains("Geeks"));

        // Check for "4" in the deque
        System.out.println("Does the deque contains '4'? "
                           + de_que.contains("4"));

        // Check if the deque contains "No"
        System.out.println("Does the deque contains 'No'? "
                           + de_que.contains("No"));
    }
}
```

**Output:**

```java
ArrayDeque: [Welcome, To, Geeks, 4, Geeks]
Does the deque contains 'Geeks'? true
Does the deque contains '4'? true
Does the deque contains 'No'? false

```

**程序 2:**

```java
// Java code to illustrate contains()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Queue
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the ArrayDeque
        System.out.println("ArrayDeque: " + de_que);

        // Check for '15' in the Deque
        System.out.println("Does the Deque contains '15'? "
                           + de_que.contains(15));

        // Check for '2' in the Deque
        System.out.println("Does the Deque contains '2'? "
                           + de_que.contains(2));

        // Check if the Deque contains '10'
        System.out.println("Does the Deque contains '10'? "
                           + de_que.contains(10));
    }
}
```

**Output:**

```java
ArrayDeque: [10, 15, 30, 20, 5]
Does the Deque contains '15'? true
Does the Deque contains '2'? false
Does the Deque contains '10'? true

```