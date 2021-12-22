# Java 程序设置最小和最大堆大小

> 原文:[https://www . geesforgeks . org/Java-程序到集合的最小和最大堆大小/](https://www.geeksforgeeks.org/java-program-to-set-minimum-and-maximum-heap-size/)

堆区域是 JVM 中存在的各种内存区域之一。每个 JVM 都有一个可用的堆区域。堆区域将在 [**JVM**](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 启动时创建。对象和相应的实例变量将存储在堆区域中。java 中的每个数组都只是对象，因此数组也将存储在堆区域中。堆区域可以被多线程访问，因此堆内存中的数据存储不是线程安全的。堆区域不必是连续的。

**显示堆内存统计的程序:**

java 应用程序可以通过使用运行时对象与虚拟机通信。java.lang 包中的运行时类，它是一个单例类。我们可以如下创建一个运行时对象:

> Runtime r= Runtime.getRuntime（）;

一旦我们获得了运行时对象，我们就可以对该对象调用以下方法:

*   **maxMemory() :** 返回分配给堆的最大内存的字节数。
*   **totalMemory() :** 返回分配给堆的总内存的字节数。
*   **freeMemory() :** 返回堆中存在的空闲内存字节数

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// import required packages
import java.io.*;
import java.lang.*;
import java.util.*;

// driver class
class heapMemory {

    // main method
    public static void main(String[] args)
    {
        // creating runtime time object
        Runtime r = Runtime.getRuntime();

        // displaying max memory of heap in bytes
        System.out.println("Max memory"
                           + " " + r.maxMemory());

        // displaying initial memory in bytes
        System.out.println("Initial memory"
                           + " " + r.totalMemory());

        // displaying free memory in bytes
        System.out.println("Free memory"
                           + " " + r.freeMemory());

        // displaying consume memory in bytes
        System.out.println(
            "Consume memory"
            + " " + (r.totalMemory() - r.freeMemory()));
    }
}
```

**Output**

```java
Max memory 134217728
Initial memory 134217728
Free memory 132286176
Consume memory 1931552
```

堆内存是有限的内存，但是根据我们的需求，我们可以设置最大和最小堆大小，也就是说，我们可以根据我们的需求增加或减少堆大小。我们可以通过在运行时使用以下 java 命令来做到这一点。

**1。-Xmx** 设置最大堆大小(最大内存)

> java -Xmx512m heapMemory

该命令将最大堆大小设置为 512Mb。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// import required packages
import java.io.*;
import java.lang.*;
import java.util.*;

// driver class
class heapMemory {

    // main method
    public static void main(String[] args)
    {
        double mb = 1000000;

        // creating runtime time object
        Runtime r = Runtime.getRuntime();

        // displaying max memory of heap in Mb
        System.out.println("Max memory"
                           + " " + r.maxMemory() / mb);

        // displaying initial memory in Mb
        System.out.println("Initial memory"
                           + " " + r.totalMemory() / mb);

        // displaying free memory in Mb
        System.out.println("Free memory"
                           + " " + r.freeMemory() / mb);

        // displaying consume memory in Mb
        System.out.println(
            "Consume memory"
            + " "
            + (r.totalMemory() - r.freeMemory()) / mb);
    }
}
```

**Output**

```java
Max memory 134.217728
Initial memory 134.217728
Free memory 132.285184
Consume memory 1.932544
```

**2。-Xms** :我们可以使用这个命令来设置最小或者初始堆大小。

> java -Xms64m heapMemory

该命令将最小大小设置为 64Mb，即 totalMemory()。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// import required packages
import java.io.*;
import java.lang.*;
import java.util.*;

// driver class
class heapMemory {

    // main method
    public static void main(String[] args)
    {
        double mb = 1000000;

        // creating runtime time object
        Runtime r = Runtime.getRuntime();

        // displaying max memory of heap in Mb
        System.out.println("Max memory"
                           + " " + r.maxMemory() / mb);

        // displaying initial memory in Mb
        System.out.println("Initial memory"
                           + " " + r.totalMemory() / mb);

        // displaying free memory in Mb
        System.out.println("Free memory"
                           + " " + r.freeMemory() / mb);

        // displaying consume memory in Mb
        System.out.println(
            "Consume memory"
            + " "
            + (r.totalMemory() - r.freeMemory()) / mb);
    }
}
```

**Output**

```java
Max memory 134.217728
Initial memory 134.217728
Free memory 132.285192
Consume memory 1.932536
```