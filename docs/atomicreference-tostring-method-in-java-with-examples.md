# Java 中 AtomicReference toString()方法，带示例

> 原文:[https://www . geesforgeks . org/atomicreference-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-tostring-method-in-java-with-examples/)

**原子引用**类的 **toString()** 方法用于返回原子引用对象当前值的字符串表示。

**语法:**

```
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回当前值的**字符串表示**。

下面的程序说明了 toString()方法:
**程序 1:**

```
// Java program to demonstrate
// AtomicReference.toString() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReference<Double> ref
            = new AtomicReference<Double>();

        // set some value
        ref.set(1234.00);

        // apply toString()
        System.out.println("Value = "
                           + ref.toString());
    }
}
```

**Output:**

```
Value = 1234.0

```

**程序 2:**

```
// Java program to demonstrate
// AtomicReference.toString() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        // which stores String.
        AtomicReference<String> ref
            = new AtomicReference<String>();

        // set some value
        ref.set("GFG");

        // apply toString()
        System.out.println("Value  = "
                           + ref.toString());
    }
}
```

**Output:**

```
Value  = GFG

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic reference . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#toString())