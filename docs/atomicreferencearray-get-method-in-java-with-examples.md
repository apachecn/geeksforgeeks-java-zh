# Java 中的 AtomicReferenceArray get()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicreferencearray-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-get-method-in-java-with-examples/)

一个 **AtomicReferenceArray** 类的 **get()** 方法用于返回这个 AtomicReferenceArray 对象的索引 I 处的元素的值，该对象具有读取的内存语义，就好像索引的变量被声明为变量的易失性类型。

**语法:**

```java
public final E get(int i)

```

**参数:**该方法接受**指数 i** 取值。

**返回值:**此方法返回指数 I 处的**当前值**

下面的程序说明了 get()方法:
**程序 1:**

```java
// Java program to demonstrate
// AtomicReferenceArray.get() method

import java.util.concurrent.atomic.AtomicReferenceArray;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference array object
        // which stores Integer.
        AtomicReferenceArray<Integer> array
            = new AtomicReferenceArray<Integer>(5);

        // set some value in array
        array.set(0, 12);
        array.set(1, 13);
        array.set(2, 14);
        array.set(3, 15);

        // get and print the value using get method
        for (int i = 0; i < 4; i++) {

            int value = array.get(i);
            System.out.println("value at "
                               + i + " = " + value);
        }
    }
}
```

**Output:**

```java
value at 0 = 12
value at 1 = 13
value at 2 = 14
value at 3 = 15

```

**程序 2:**

```java
// Java program to demonstrate
// AtomicReferenceArray.get() method

import java.util.concurrent.atomic.AtomicReferenceArray;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference array object
        // which stores String.
        AtomicReferenceArray<String> array
            = new AtomicReferenceArray<String>(5);

        // set some value in array
        array.set(0, "AMAN");
        array.set(1, "AMAR");

        // get and print the value using get method
        for (int i = 0; i < 2; i++) {

            String value = array.get(i);
            System.out.println("value at "
                               + i + " = " + value);
        }
    }
}
```

**Output:**

```java
value at 0 = AMAN
value at 1 = AMAR

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic referencearray . html # get(int)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#get(int))