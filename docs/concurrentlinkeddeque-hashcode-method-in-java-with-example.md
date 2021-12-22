# Java 中的 ConcurrentLinkedDeque hashCode()方法搭配示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkeddequee-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/concurrentlinkeddeque-hashcode-method-in-java-with-example/)

Java 中**concurrentlinkedeque**的 **hashCode()** 方法用于获取这个 concurrentlinkedeque 实例的 hashCode 值。它返回一个整数值，该整数值是这个 ConcurrentLinkedDeque 实例的 hashCode 值。

**语法:**

```java
public int hashCode()
```

**参数:**该功能没有参数。

**返回值:**该方法返回一个**整数值**，这是这个并发链接请求实例的哈希值。

下面的程序说明了 concurrentlinkedrequest . hashcode()方法:

**程序 1:**

```java
// Java Program Demonstrate hashCode()
// method of ConcurrentLinkedDeque

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<Integer> CLD
            = new ConcurrentLinkedDeque<Integer>();

        // Add numbers to end of ConcurrentLinkedDeque
        CLD.add(7855642);
        CLD.add(35658786);
        CLD.add(5278367);
        CLD.add(74381793);

        System.out.println("Linked Blocking Deque: " + CLD);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + CLD.hashCode());
    }
}
```

**Output:**

```java
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
HashCode value: 2101973421

```

**程序 2:**

```java
// Java Program Demonstrate hashCode()
// method of ConcurrentLinkedDeque
// when the list contains characters

import java.util.concurrent.ConcurrentLinkedDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> CLD
            = new ConcurrentLinkedDeque<String>();

        // Add numbers to end of ConcurrentLinkedDeque
        CLD.add("1");
        CLD.add("2");
        CLD.add("3");
        CLD.add("4");

        System.out.println("Linked Blocking Deque: " + CLD);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + CLD.hashCode());
    }
}
```

**Output:**

```java
Linked Blocking Deque: [1, 2, 3, 4]
HashCode value: 2101973421

```