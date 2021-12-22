# Java 中的 ArrayDeque removefirst occurrence()方法

> 原文:[https://www . geeksforgeeks . org/arraydeque-removefirst occurrence-method-in-Java/](https://www.geeksforgeeks.org/arraydeque-removefirstoccurrence-method-in-java/)

java 中的 Java . util . arraydeque . removefirst occurrence(*Object*)方法用于从该对象中移除特定元素的第一次出现。如果该元素只出现一次，则移除该元素并返回 true。如果没有删除这样的元素，则返回 false。

**语法:**

```
Array_Deque.removeFirstOccurrence(*Object O*)
```

**参数:**该方法取 ArrayDeque 类型的一个参数 *O* ，指的是第一次出现的元素要被移除。

**返回值:**如果元素存在于地图中，该方法返回真，否则返回假。

下面的程序说明了 Java . util . arraydeque . removefirst occurrence()方法:

**程序 1** :

```
// Java code to illustrate removeFirstOccurrence()
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
        System.out.println("Initial ArrayDeque: " + de_que);

        // Removing elements using removeFirstOccurrence() method
        de_que.removeFirstOccurrence("Geeks");
        de_que.removeFirstOccurrence("For");

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output:**

```
Initial ArrayDeque: [Welcome, To, Geeks, For, Geeks]
ArrayDeque after removing elements: [Welcome, To, Geeks]

```

**程序 2:**

```
// Java code to illustrate removeFirstOccurrence()
import java.util.*;

public class ArrayDequeDemo {
    public static void main(String args[])
    {
        // Creating an empty ArrayDeque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Deque
        de_que.add(10);
        de_que.add(10);
        de_que.add(30);
        de_que.add(10);
        de_que.add(30);

        // Displaying the ArrayDeque
        System.out.println("Initial ArrayDeque: " + de_que);

        // Removing elements using removeFirstOccurrence() method
        de_que.removeFirstOccurrence(30);
        de_que.removeFirstOccurrence(5);

        // Displaying the ArrayDeque after removal
        System.out.println("ArrayDeque after removing "
                           + "elements: " + de_que);
    }
}
```

**Output:**

```
Initial ArrayDeque: [10, 10, 30, 10, 30]
ArrayDeque after removing elements: [10, 10, 10, 30]

```