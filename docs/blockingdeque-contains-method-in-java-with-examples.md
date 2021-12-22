# blocking request 包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/blocking reque-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/blockingdeque-contains-method-in-java-with-examples/)

**包含**阻塞请求**的(对象 o)** 方法，检查参数中传递的元素是否存在于容器中。如果元素存在于容器中，则返回 true，否则返回 false 值。

**语法:**

```java
public boolean contains(Object o)
```

**参数:**该方法接受一个强制参数 **o** ，其在容器中的存在将在容器中被检查。

**返回:**如果元素存在，这个方法返回真，否则返回假。

**注**:阻塞请求的 contains()方法是从 Java 中的[linkedblockingdek](https://www.geeksforgeeks.org/linkedblockingdeque-in-java-with-examples/)类继承而来的。

下面的程序说明了包含()方法的阻塞请求:

**程序 1:**

```java
// Java Program Demonstrate contains()
// method of BlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<Integer> BD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of BlockingDeque
        BD.add(10);
        BD.add(20);
        BD.add(30);
        BD.add(40);

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);

        // check for presence using function
        if (BD.contains(10)) {
            System.out.println("Blocking Deque contains 10");
        }
        else {
            System.out.println("Blocking Deque does not contain 10");
        }
    }
}
```

**输出:**

```java
Blocking Deque: [10, 20, 30, 40]
Blocking Deque contains 10

```

**程序二:**

```java
// Java Program Demonstrate contains()
// method of BlockingDeque
import java.util.concurrent.LinkedBlockingDeque;
import java.util.concurrent.BlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of BlockingDeque
        BlockingDeque<String> BD
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of BlockingDeque
        BD.add("ab");
        BD.add("cd");
        BD.add("fg");
        BD.add("xz");

        // before removing print Deque
        System.out.println("Blocking Deque: " + BD);

        // check for presence using function
        if (BD.contains("go")) {
            System.out.println("Blocking Deque contains 'go'");
        }
        else {
            System.out.println("Blocking Deque does not contain 'go'");
        }
    }
}
```

**输出:**

```java
Blocking Deque: [ab, cd, fg, xz]
Blocking Deque does not contain 'go'

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedblockingrequest . html # contains(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedBlockingDeque.html#contains(java.lang.Object))