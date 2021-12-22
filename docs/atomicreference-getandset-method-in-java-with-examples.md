# Java 中的 AtomicReference getAndSet()方法，带示例

> 原文:[https://www . geesforgeks . org/atomic reference-getandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-getandset-method-in-java-with-examples/)

**原子引用**类的 **getAndSet()** 方法用于将原子引用对象的值原子地设置为新值，新值作为参数传递，并返回原子引用对象的旧值，内存效果由 VarHandle . GetAndSet(Java . lang . object…)指定。VarHandle . GetAndSet(Java . lang . object…)指定该变量作为设置的内存语义被处理，就好像该变量被声明为易失性的一样。

**语法:**

```java
public final V getAndSet?(V newValue)
```

**参数:**此方法接受**新值**为新值。
**返回值:**此方法返回 AtomicReference 的旧值。
以下程序说明了 getAndSet()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// AtomicReference.getAndSet() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReference<Double> ref
            = new AtomicReference<Double>();

        // set some value
        ref.set(1234.00);

        // get and replace value
        double oldValue
            = ref.getAndSet((double)3213);

        // print
        System.out.println("OLD Value = "
                           + oldValue);
        System.out.println("NEW Value = "
                           + ref.get());
    }
}
```

**Output:** 

```java
OLD Value = 1234.0
NEW Value = 3213.0
```