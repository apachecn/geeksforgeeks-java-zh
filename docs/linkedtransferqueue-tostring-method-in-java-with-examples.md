# 用示例链接 Java 中的 TransferQueue toString()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedtransferqueue-tostring-method-in-java-with-examples/)

[java . util . concurrent . linkedtransferqueue](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/)的 **toString()** 方法是一个内置的 Java 函数，用于返回集合的字符串表示形式。字符串表示由包含在“ **[]** ”中并由“**、**分隔的集合元素组成。spring 表示中元素的顺序按照迭代的顺序出现。

**语法:**

```java
public String toString ()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回集合的字符串表示，该集合包含相同顺序的元素。

**异常:**不存在异常。

下面的程序说明了 LinkedTransferQueue 类的 toString()函数:

**程序 1:**

```java
// Java Program Demonstrate LinkedTransferQueue
// toString() method

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {
        // create object of LinkedTransferQueue
        // using LinkedTransferQueue() constructor
        LinkedTransferQueue<Integer> LTQ
            = new LinkedTransferQueue<Integer>();

        // Add numbers to end of LinkedTransferQueue
        LTQ.add(101);
        LTQ.add(202);
        LTQ.add(58);
        LTQ.add(796);
        LTQ.add(641);

        // Store the string representation of the
        // collection String object st
        String st = LTQ.toString();

        // Print String representation
        System.out.println("String Representation: "
                           + st);
    }
}
```

**输出:**

```java
String Representation: [101, 202, 58, 796, 641]

```

**程序二:**

```java
// Java Program Demonstrate LinkedTransferQueue
// toString() method

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {
        // create object of LinkedTransferQueue
        // using LinkedTransferQueue() constructor
        LinkedTransferQueue<String> LTQ
            = new LinkedTransferQueue<String>();

        // Add numbers to end of LinkedTransferQueue
        LTQ.add("GeeksforGeeks");
        LTQ.add("Gfg");
        LTQ.add("gfg");
        LTQ.add("Geeks");
        LTQ.add("geeks");

        // Store the string representation of the
        // collection String object st
        String st = LTQ.toString();

        // Print String representation
        System.out.println("String Representation: "
                           + st);
    }
}
```

**输出:**

```java
String Representation: [GeeksforGeeks, Gfg, gfg, Geeks, geeks]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrent/linkedtransferqueue . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/LinkedTransferQueue.html#toString--)