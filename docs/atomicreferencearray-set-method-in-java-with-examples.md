# Java 中的 AtomicReferenceArray set()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicreferencearray-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-set-method-in-java-with-examples/)

**原子引用数组**类的 **set()** 方法用于将索引 I 处的元素的值设置为新值。索引 I 和 newValue 都作为参数传递给该方法。这个方法用内存读取语义设置值，就像变量被声明为易失性类型的变量一样。

**语法:**

```
public final void set(int i, E newValue)

```

**参数:**该方法接受:

*   **i** 是执行操作的原子引用数组的索引，
*   **新值**是要设置的新值。

**返回值:**此方法不返回任何内容。

下面的程序说明了 set()方法:
**程序 1:**

```
// Java program to demonstrate
// AtomicReferenceArray.set() method

import java.util.concurrent.atomic.*;

public class GFG {

    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReferenceArray<Integer> ref
            = new AtomicReferenceArray<Integer>(5);

        // set some value and print
        ref.set(0, 2345);
        ref.set(1, 543);
        ref.set(2, 322);

        System.out.println("Value of index 0 = "
                           + ref.get(0));
        System.out.println("Value of index 1 = "
                           + ref.get(1));
        System.out.println("Value of index 2 = "
                           + ref.get(2));
    }
}
```

**Output:**

```
Value of index 0 = 2345
Value of index 1 = 543
Value of index 2 = 322

```

**程序 2:**

```
// Java program to demonstrate
// AtomicReferenceArray.set() method

import java.util.concurrent.atomic.*;

public class GFG {

    public static void main(String[] args)
    {

        // create an atomic reference object.c
        AtomicReferenceArray<String> ref
            = new AtomicReferenceArray<String>(5);

        // set some value
        ref.set(0, "C");
        ref.set(1, "PYTHON");
        ref.set(2, "TS");
        ref.set(3, "C++");
        ref.set(4, "C");

        // print
        for (int i = 0; i < 5; i++) {
            System.out.println(ref.get(i));
        }
    }
}
```

**Output:**

```
C
PYTHON
TS
C++
C

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic referencearray . html # set(int，E)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#set)