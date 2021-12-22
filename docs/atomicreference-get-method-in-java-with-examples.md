# Java 中的 AtomicReference get()方法，示例

> 原文:[https://www . geesforgeks . org/atomicreference-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-get-method-in-java-with-examples/)

一个**原子引用**类的 **get()** 方法用于返回这个原子引用对象的值，其内存语义为读取，就好像该变量被声明为变量的易失性类型。

**语法:**

```
public final V get()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该原子引用的当前值。

下面的程序说明了 get()方法:
**程序 1:**

```
// Java program to demonstrate
// AtomicReference.get() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        // which stores Integer.
        AtomicReference<Integer> ref
            = new AtomicReference<Integer>();

        // set some value
        ref.set(12);

        // get and print value
        int value = ref.get();
        System.out.println("value  = " + value);
    }
}
```

**Output:**

```
value  = 12

```

**程序 2:**

```
// Java program to demonstrate
// AtomicReference.get() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        // which stores String.
        AtomicReference<String> ref
            = new AtomicReference<String>();

        // set some value
        ref.set("GEEKS FOR GEEKS");

        // get and print value
        String value = ref.get();
        System.out.println("V  = " + value);
    }
}
```

**Output:**

```
V  = GEEKS FOR GEEKS

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic Reference . html # get()](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#get())