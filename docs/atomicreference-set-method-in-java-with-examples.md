# Java 中的 AtomicReference set()方法，带示例

> 原文:[https://www . geesforgeks . org/atomicreference-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-set-method-in-java-with-examples/)

一个**原子引用**类的 **set()** 方法用于设置这个原子引用对象的值，其内存语义为读取，就好像该变量被声明为变量的易失性类型。

**语法:**

```
public final void set(V newValue)

```

**参数:**此方法接受新值，即要设置的新值。

**返回值:**此方法不返回任何内容。

下面的程序说明了 set()方法:
**程序 1:**

```
// Java program to demonstrate
// AtomicReference.set() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        // which stores Integer.
        AtomicReference<Integer> ref
            = new AtomicReference<Integer>();

        // set some value using set method
        ref.set(13243546);

        // print value
        System.out.println("value 1 = " + ref.get());
    }
}
```

**Output:**

```
value 1 = 13243546

```

**程序 2:**

```
// Java program to demonstrate
// AtomicReference.set() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        // which stores String.
        AtomicReference<String> ref
            = new AtomicReference<String>();

        // set some value
        ref.set("WELCOME TO GEEKS FOR GEEKS");

        // print value
        System.out.println("V  = " + ref.get());
    }
}
```

**Output:**

```
V  = WELCOME TO GEEKS FOR GEEKS

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic reference . html # set(V)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#set(V))