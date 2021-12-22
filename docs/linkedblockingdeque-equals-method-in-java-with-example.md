# 用示例

链接 Java 中的 LinkedBlockingDeque 等于()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedblockingdeque-equals-method-in-java-with-example/)

**Java . util . LinkedBlockingDeque**类的 **equals()** 方法用于将指定的对象与该 linkedblockingrequest 进行比较以获得相等性。当且仅当指定对象也是链接锁定请求，两个链接锁定请求具有相同的大小，并且两个链接锁定请求中所有对应的元素对相等时，返回 true。(两个元素 e1 和 e2 相等，如果(e1==null？e2==null : e1.equals(e2))。)换句话说，如果两个 LinkedBlockingDeques 包含相同顺序的相同元素，则它们被定义为相等。

**语法:**

```java
public boolean equals(Object o)
```

**参数:**该方法将的**对象作为参数，与该链接的锁定请求进行相等性比较。**

**返回值:**如果指定对象等于该链接锁定请求，则该方法返回**真**。

以下示例说明了 LinkedBlockingDeque.equals()方法:

**程序 1:**

```java
// Java Program Demonstrate equals()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD1
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD1.add(7855642);
        LBD1.add(35658786);
        LBD1.add(5278367);
        LBD1.add(74381793);

        System.out.println("Linked Blocking Deque 1: " + LBD1);

        // create another object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD2
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of LinkedBlockingDeque
        LBD2.add("1");
        LBD2.add("2");
        LBD2.add("3");
        LBD2.add("4");

        System.out.println("Linked Blocking Deque 2: " + LBD2);

        // using equals() function
        System.out.println("Are both Linked Blocking Deque equal: "
                           + LBD1.equals(LBD2));
    }
}
```

**Output:**

```java
Linked Blocking Deque 1: [7855642, 35658786, 5278367, 74381793]
Linked Blocking Deque 2: [1, 2, 3, 4]
Are both Linked Blocking Deque equal: false

```

**程序 2:**

```java
// Java Program Demonstrate equals()
// method of LinkedBlockingDeque
// when the list contains characters

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD1
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of LinkedBlockingDeque
        LBD1.add("1");
        LBD1.add("2");
        LBD1.add("3");
        LBD1.add("4");

        System.out.println("Linked Blocking Deque 1: " + LBD1);

        // using equals() function
        System.out.println("Is LBD1 equal to LBD1: "
                           + LBD1.equals(LBD1));
    }
}
```

**Output:**

```java
Linked Blocking Deque 1: [1, 2, 3, 4]
Is LBD1 equal to LBD1: true

```