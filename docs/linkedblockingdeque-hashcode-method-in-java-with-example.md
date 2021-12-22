# 用示例

链接 Java 中的锁死请求 hashCode()方法

> 原文:[https://www . geeksforgeeks . org/link edblockingeque-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedblockingdeque-hashcode-method-in-java-with-example/)

Java 中**linkedblockingrequest**的 **hashCode()** 方法用于获取 linkedblockingrequest 的这个实例的 hashCode 值。它返回一个整数值，该整数值是 linkedblockingrequest 实例的 hashCode 值。

**语法:**

```
public int hashCode()
```

**参数:**此功能无参数。

**返回:**该方法返回一个**整数值**，这是 linkedblockingrequest 实例的哈希值。

以下示例说明了 LinkedBlockingDeque.hashCode()方法:

**程序 1:**

```
// Java Program Demonstrate hashCode()
// method of LinkedBlockingDeque

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<Integer> LBD
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add(7855642);
        LBD.add(35658786);
        LBD.add(5278367);
        LBD.add(74381793);

        System.out.println("Linked Blocking Deque: " + LBD);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + LBD.hashCode());
    }
}
```

**Output:**

```
Linked Blocking Deque: [7855642, 35658786, 5278367, 74381793]
HashCode value: 2101973421

```

**程序 2:**

```
// Java Program Demonstrate hashCode()
// method of LinkedBlockingDeque
// when the list contains characters

import java.util.concurrent.LinkedBlockingDeque;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of LinkedBlockingDeque
        LinkedBlockingDeque<String> LBD
            = new LinkedBlockingDeque<String>();

        // Add numbers to end of LinkedBlockingDeque
        LBD.add("1");
        LBD.add("2");
        LBD.add("3");
        LBD.add("4");

        System.out.println("Linked Blocking Deque: " + LBD);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + LBD.hashCode());
    }
}
```

**Output:**

```
Linked Blocking Deque: [1, 2, 3, 4]
HashCode value: 2101973421

```