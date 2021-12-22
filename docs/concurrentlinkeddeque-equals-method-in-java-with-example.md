# Java 中的 ConcurrentLinkedDeque equals()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/concurrentlinkeddeque-equals-method-in-java-with-example/)

**Java . util . ConcurrentLinkedDeque**类的 **equals()** 方法用于将指定的对象与这个 concurrentlinkedeque 进行比较以获得相等性。当且仅当指定的对象也是一个 concurrentlinkedrequest，两个 concurrentlinkedrequest 具有相同的大小，并且两个 concurrentlinkedrequest 中所有对应的元素对相等时，返回 true。(两个元素 e1 和 e2 相等，如果(e1==null？e2==null : e1.equals(e2))。)换句话说，如果两个 ConcurrentLinkedDeques 包含相同顺序的相同元素，则它们被定义为相等。

**语法:**

```
public boolean equals(Object o)
```

**参数:**该方法将的**对象作为参数，与该 ConcurrentLinkedDeque 进行相等性比较。**

**返回值:**如果指定的对象等于这个 concurrentlinkedrequest，这个方法返回 **true** 。

下面的程序说明了 ConcurrentLinkedDeque.equals()方法:

**程序 1:**

```
// Java Program Demonstrate equals()
// method of ConcurrentLinkedDeque

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> CLD1
            = new ConcurrentLinkedDeque<Integer>();

        // Add numbers to end of ConcurrentLinkedDeque
        CLD1.add(7855642);
        CLD1.add(35658786);
        CLD1.add(5278367);
        CLD1.add(74381793);

        System.out.println("Linked Blocking Deque 1: " + CLD1);

        // create another object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> CLD2
            = new ConcurrentLinkedDeque<String>();

        // Add numbers to end of ConcurrentLinkedDeque
        CLD2.add("1");
        CLD2.add("2");
        CLD2.add("3");
        CLD2.add("4");

        System.out.println("Linked Blocking Deque 2: " + CLD2);

        // using equals() function
        System.out.println("Are both Linked Blocking Deque equal: "
                           + CLD1.equals(CLD2));
    }
}
```

**Output:**

```
Linked Blocking Deque 1: [7855642, 35658786, 5278367, 74381793]
Linked Blocking Deque 2: [1, 2, 3, 4]
Are both Linked Blocking Deque equal: false

```

**程序 2:**

```
// Java Program Demonstrate equals()
// method of ConcurrentLinkedDeque
// when the list contains characters

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> CLD1
            = new ConcurrentLinkedDeque<String>();

        // Add numbers to end of ConcurrentLinkedDeque
        CLD1.add("1");
        CLD1.add("2");
        CLD1.add("3");
        CLD1.add("4");

        System.out.println("Linked Blocking Deque 1: " + CLD1);

        // using equals() function
        System.out.println("Is CLD1 equal to CLD1: "
                           + CLD1.equals(CLD1));
    }
}
```

**Output:**

```
Linked Blocking Deque 1: [1, 2, 3, 4]
Is CLD1 equal to CLD1: true

```