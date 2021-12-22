# AtomicInteger toString()方法在 Java 中的示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-tostring-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicnteger . tostring()**是 Java 中的一个内置方法，它返回以整数形式存储的当前值的字符串表示形式。

**语法:**

```java
public String toString()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回当前值的字符串表示形式。

下面的程序演示了该功能:

**程序 1:**

```java
// Java program that demonstrates
// the toString() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        System.out.println("Previous value: "
                           + val);

        String s = val.toString();

        // Prints the string value
        System.out.println("String value: "
                           + s);
    }
}
```

**输出:**

```java
Previous value: 0
String value: 0

```

**程序二:**

```java
// Java program that demonstrates
// the toString() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        System.out.println("Previous value: "
                           + val);

        String s = val.toString();

        // Prints the string value
        System.out.println("String value: "
                           + s);
    }
}
```

**输出:**

```java
Previous value: 18
String value: 18

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#toString--)