# Java 中抽象 Queue clear()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract queue-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractqueue-clear-method-in-java-with-examples/)

**[抽象队列](https://www.geeksforgeeks.org/abstractqueue-in-java-with-examples/)** 的 **clear()** 方法从该队列中移除所有元素。该调用返回后，队列将为空。

**语法:**

```java
public void clear()
```

**参数:**此方法不接受任何参数。

**返回:**该方法不返回任何内容。

以下程序说明了 clear()方法:

**程序 1:**

```java
// Java program to illustrate the
// AbstractQueue clear() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        // Creating object of AbstractQueue<Integer>
        AbstractQueue<Integer>
            AQ1 = new LinkedBlockingQueue<Integer>();

        // Populating AQ1
        AQ1.add(10);
        AQ1.add(20);
        AQ1.add(30);
        AQ1.add(40);
        AQ1.add(50);

        // print AQ
        System.out.println("AbstractQueue1 contains : " + AQ1);

        AQ1.clear();
        System.out.println("AbstractQueue1 : " + AQ1);
    }
}
```

**输出:**

```java
AbstractQueue1 contains : [10, 20, 30, 40, 50]
AbstractQueue1 : []

```

**程序二:**

```java
// Java program to illustrate the
// AbstractQueue clear() method
import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        // Creating object of AbstractQueue<String>
        AbstractQueue<String>
            AQ1 = new LinkedBlockingQueue<String>();

        // Populating AQ1
        AQ1.add("gopal");
        AQ1.add("gfg");
        AQ1.add("java");

        // print AQ
        System.out.println("AbstractQueue1 contains : " + AQ1);

        AQ1.clear();
        System.out.println("AbstractQueue1 : " + AQ1);
    }
}
```

**输出:**

```java
AbstractQueue1 contains : [gopal, gfg, java]
AbstractQueue1 : []

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/abstractqueue . html # clear–](https://docs.oracle.com/javase/8/docs/api/java/util/AbstractQueue.html#clear--)