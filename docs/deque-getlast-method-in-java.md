# Java 中的 Deque getLast()方法

> 原文:[https://www.geeksforgeeks.org/deque-getlast-method-in-java/](https://www.geeksforgeeks.org/deque-getlast-method-in-java/)

[**得克接口**](https://www.geeksforgeeks.org/deque-interface-java-example/) 的 **getLast()** 方法返回得克的最后一个元素或尾部。它不会删除元素。当 Deque 为空时，它会引发异常。

**语法:**

```java
E getLast()

```

**参数:**此方法不接受任何参数。

**返回:**蒂耶方法返回最后一个元素或德格的尾部，但不删除它。

**异常:**当德格为空，函数被调用时，函数抛出*nosucheelementexception*。

下面的程序说明了 getLast()方法的德格:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate getLast()
// method of Deque
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedList<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**Output:** 

```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 74381793

```

**程序二:**借助 **ArrayDeque** 。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate getLast()
// method of Deque
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ArrayDeque<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**Output:** 

```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 74381793

```

**程序 3:** 在**的帮助下，并发链接请求**。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate getLast()
// method of Deque
import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new ConcurrentLinkedDeque<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**Output:** 

```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 74381793

```

**程序 4:** 在**的帮助下链接锁定程序**。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate getLast()
// method of Deque
import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**Output:** 

```java
Deque: [7855642, 35658786, 5278367, 74381793]
Deque's head: 74381793

```

**程序 5:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate getLast()
// method of Deque when it is empty
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Deque
        Deque<Integer> DQ
            = new LinkedList<Integer>();

        // Add numbers to end of Deque
        DQ.add(7855642);
        DQ.add(35658786);
        DQ.add(5278367);
        DQ.add(74381793);

        // print Deque
        System.out.println("Deque: " + DQ);

        // print head
        System.out.println("Deque's head: " + DQ.getLast());

        DQ.clear();

        // Deque is empty now hence exception
        System.out.println("Deque's head: " + DQ.getLast());
    }
}
```

**输出:**

```java
Exception in thread "main" java.util.NoSuchElementException
    at java.util.LinkedList.getLast(LinkedList.java:257)
    at GFG.main(GFG.java:29)

```

**参考:**[https://docs . Oracle . com/javae/8/docs/API/Java/util/deue . html # get ast】](https://docs.oracle.com/javase/8/docs/api/java/util/Deque.html#getLast--)