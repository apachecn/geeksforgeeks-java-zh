# Java 中的 AtomicLong toString()方法，带示例

> 原文:[https://www . geesforgeks . org/atomiclong-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-tostring-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLong . tostring()**是 Java 中的一个内置方法，它返回存储在 AtomicLong 中的当前值的字符串表示形式。

**语法:**

```java
public String toString()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回当前值的字符串表示形式。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the toString() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

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

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

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

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomiclong . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#toString--)