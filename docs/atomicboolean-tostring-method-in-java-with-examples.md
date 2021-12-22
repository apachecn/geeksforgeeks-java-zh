# Java 中的 AtomicBoolean toString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicboolean-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicboolean-tostring-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicboolean . tostring()**是 Java 中的一个内置方法，它返回当前值的字符串表示形式，该字符串表示形式存储在布尔值中。

**语法:**

```
public String toString()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回当前值的字符串表示形式。

以下程序说明了上述功能:

**程序 1:**

```
// Java program that demonstrates
// the toString() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as true
        AtomicBoolean val
            = new AtomicBoolean(true);

        String s = val.toString();

        // Prints the string value
        System.out.println("String value: "
                           + s);
    }
}
```

**输出:**

```
String value: true

```

**程序二:**

```
// Java program that demonstrates
// the toString() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as false
        AtomicBoolean val
            = new AtomicBoolean(false);

        String s = val.toString();

        // Prints the string value
        System.out.println("String value: "
                           + s);
    }
}
```

**输出:**

```
String value: false

```

**参考:**https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicboolean . html # toString–