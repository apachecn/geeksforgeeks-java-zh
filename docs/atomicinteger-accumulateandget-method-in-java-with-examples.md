# Java 中的 AtomicInteger accumulateAndGet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicinteger-accumulatedget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-accumulateandget-method-in-java-with-examples/)

**Java。atomicinteger . accumulateedget()**方法是一种内置方法，它通过对当前值和作为参数传递的值应用指定的操作来更新对象的当前值。它以一个整数作为参数，以一个 IntBinaryOperator 接口的对象作为参数，并将对象中指定的操作应用于这些值。它返回更新后的值。

**语法:**

```java
public final int accumulateAndGet(int y, 
             IntBinaryOperator function)
```

**参数:**该方法接受整数值 **y** 和整数运算函数**函数**作为参数。它将给定的函数应用于对象的当前值和值 y。

**返回值:**函数返回当前对象的更新值。

**举例说明功能。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// AtomicInteger accumulateAndGet() method

import java.util.concurrent.atomic.AtomicInteger;
import java.util.function.IntBinaryOperator;

public class Demo {
    public static void main(String[] args)
    {
        new UserThread("Thread A");
        new UserThread("Thread B");
    }
}

class Shared {
    static AtomicInteger ai = new AtomicInteger(0);
}

class UserThread implements Runnable {
    String name;
    UserThread(String name)
    {
        this.name = name;
        new Thread(this).start();
    }
    IntBinaryOperator ibo = (x, y) -> (x + y);
    int value = 5;
    @Override
    public void run()
    {
        for (int i = 0; i < 3; i++) {
            int ans = Shared.ai
                          .accumulateAndGet(value, ibo);
            System.out.println(name + " " + ans);
        }
    }
}
```

**Output:** 

```java
Thread A 5
Thread A 10
Thread A 15
Thread B 20
Thread B 25
Thread B 30
```

**参考:**T2T4】