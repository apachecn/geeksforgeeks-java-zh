# Java 中的 AtomicReference getAndUpdate()方法，带示例

> 原文:[https://www . geesforgeks . org/atomic reference-getandupdate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-getandupdate-method-in-java-with-examples/)

**原子引用**类的 **getAndUpdate()** 方法用于原子更新，通过对当前值应用指定的更新函数操作来更新原子引用的当前值。它将 updateFunction 接口的一个对象作为参数，并将该对象中指定的操作应用于当前值。它返回前一个值。
**语法:**

```java
public final V getAndUpdate(UnaryOperator<V> updateFunction)
```

**参数:**该方法接受**更新功能**，这是一个无副作用的功能。
**返回值:**此方法返回**之前的值**。
以下程序说明了 getAndUpdate()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// AtomicReference.getAndUpdate() method

import java.util.concurrent.atomic.AtomicReference;
import java.util.function.UnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        // AtomicReference with value
        AtomicReference<Integer> ref
            = new AtomicReference<>(987654);

        // Declaring the updateFunction
        // applying function
        UnaryOperator twoDigits
            = (v)
            -> v.toString()
                   .substring(0, 2);

        // apply getAndUpdate()
        int value = ref.getAndUpdate(twoDigits);

        // print AtomicReference
        System.out.println(
            "The AtomicReference previous value: "
            + value);
        System.out.println(
            "The AtomicReference new value: "
            + ref.get());
    }
}
```

**Output:** 

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// AtomicReference.getAndUpdate() method

import java.util.concurrent.atomic.*;
import java.util.function.UnaryOperator;

public class GFG {
    public static void main(String args[])
    {

        // AtomicReference with value
        AtomicReference<String> ref
            = new AtomicReference<>("welcome");

        // Declaring the updateFunction
        // applying function
        UnaryOperator twoDigits
            = (v) -> v + " to gfg";

        // apply getAndUpdate()
        String value
            = ref.getAndUpdate(twoDigits);

        // print AtomicReference
        System.out.println(
            "The AtomicReference previous value: "
            + value);
        System.out.println(
            "The AtomicReference new value: "
            + ref.get());
    }
}
```

**Output:** 

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic reference . html # getAndUpdate(Java . util . function . unaryoperator)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#getAndUpdate(java.util.function.UnaryOperator))