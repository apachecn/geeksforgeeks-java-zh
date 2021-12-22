# Java 中的 AtomicInteger getAndAccumulate()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-getandaccumulate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-getandaccumulate-method-in-java-with-examples/)

**Java。atomicinteger . getandaccumulate()**方法是一种内置方法，通过对当前值和作为参数传递的值应用指定的操作来更新对象的当前值。它以一个整数作为参数，以一个 IntBinaryOperator 接口的对象作为参数，并将对象中指定的操作应用于这些值。它返回前一个值。

**语法:**

```
public final int getAndAccumulate(int y, 
                   IntBinaryOperator function)

```

**参数:**此方法接受两个参数:

*   **y** : the integer to which the function is to be applied.
*   **Function:** The function is applied to the current value and value y of the object.

**返回值:**该函数返回当前对象的**上一个值**。

**举例说明功能。**

```
// Java program to demonstrate
// working of getAndAccumulate() method

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
    static AtomicInteger ai
        = new AtomicInteger(1);
}

class UserThread implements Runnable {
    String name;

    UserThread(String name)
    {
        this.name = name;
        new Thread(this).start();
    }

    IntBinaryOperator ibo = (x, y) -> (x * y);

    int value = 5;
    @Override
    public void run()
    {
        for (int i = 0; i < 3; i++) {

            int ans
                = Shared.ai
                      .getAndAccumulate(value, ibo);

            System.out.println(name + " "
                               + ans);
        }
    }
}
```

**输出:**

```
Thread A 1
Thread A 5
Thread A 25
Thread B 125
Thread B 625
Thread B 3125

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html)