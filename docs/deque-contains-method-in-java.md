# Java 中的 Deque 包含()方法

> 原文:[https://www . geesforgeks . org/deque-contains-method-in-Java/](https://www.geeksforgeeks.org/deque-contains-method-in-java/)

**包含[得克接口](https://www.geeksforgeeks.org/deque-interface-java-example/)的(E e)** 方法，检查得克容器中是否存在元素 E。如果 Deque 包含元素的一次出现，则它返回 true，否则它返回 false。

**语法:**

```java
boolean contains(Object o)
```

**参数:**该方法接受一个强制参数 o，该参数是需要测试的元素，如果它是否存在于德格中。

**返回值:**如果元素存在于德格中，该方法返回*真*，否则返回*假。*

**异常:**函数抛出两个异常，如下所示:

*   **class castexception**–如果指定元素的类型与此 deque 不兼容。它是可选的。
*   **NullPointRexception**–如果指定的元素为空，并且该 Deque 不允许空元素(可选)。它是可选的。

下面的程序说明了 Java 中的 contains()方法:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```java
// Java code to illustrate contains()
// method of Deque in Java
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<String> de_que = new LinkedList<String>();

        // Use add() method to add elements into the Queue
        de_que.add("Welcome");
        de_que.add("To");
        de_que.add("Geeks");
        de_que.add("4");
        de_que.add("Geeks");

        // Displaying the Deque
        System.out.println("Deque: " + de_que);

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
Deque: [Welcome, To, Geeks, 4, Geeks]
Does the deque contains 'Geeks'? true
Does the deque contains '4'? true
Does the deque contains 'No'? false

```

**程序 2:**

```java
// Java code to illustrate contains()
// method of Deque in Java
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<Integer> de_que = new LinkedList<Integer>();

        // Use add() method to add elements into the Queue
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the Deque
        System.out.println("Deque: " + de_que);

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
Deque: [10, 15, 30, 20, 5]
Does the Deque contains '15'? true
Does the Deque contains '2'? false
Does the Deque contains '10'? true

```

**程序 3:** 借助 **ArrayDeque** 。

```java
// Java code to illustrate contains()
// method of Deque in Java
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<Integer> de_que = new ArrayDeque<Integer>();

        // Use add() method to add elements into the Queue
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the Deque
        System.out.println("Deque: " + de_que);

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
Deque: [10, 15, 30, 20, 5]
Does the Deque contains '15'? true
Does the Deque contains '2'? false
Does the Deque contains '10'? true

```

**程序 4:** 在**的帮助下，并发链接请求**。

```java
// Java code to illustrate contains()
// method of Deque in Java
import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<Integer> de_que = new ConcurrentLinkedDeque<Integer>();

        // Use add() method to add elements into the Queue
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the Deque
        System.out.println("Deque: " + de_que);

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
Deque: [10, 15, 30, 20, 5]
Does the Deque contains '15'? true
Does the Deque contains '2'? false
Does the Deque contains '10'? true

```

**程序 5:** 在**的帮助下链接锁定程序**。

```java
// Java code to illustrate contains()
// method of Deque in Java
import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Deque
        Deque<Integer> de_que = new LinkedBlockingDeque<Integer>();

        // Use add() method to add elements into the Queue
        de_que.add(10);
        de_que.add(15);
        de_que.add(30);
        de_que.add(20);
        de_que.add(5);

        // Displaying the Deque
        System.out.println("Deque: " + de_que);

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
Deque: [10, 15, 30, 20, 5]
Does the Deque contains '15'? true
Does the Deque contains '2'? false
Does the Deque contains '10'? true

```

**注意:**异常依赖于编译器，因此不能在程序中显示。
**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/deque . html # contains-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#contains-java.lang.Object-)