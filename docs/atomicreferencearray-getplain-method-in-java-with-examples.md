# Java 中的 AtomicReferenceArray getPlain()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicreferencearray-get plain-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-getplain-method-in-java-with-examples/)

一个**原子引用数组**类的 **getPlain()** 方法用于返回这个原子引用数组对象的索引 I 处的元素的值，带有读取的内存语义，就像变量被声明为非易失性的一样。
**语法:**

```
public final E getPlain(int i)
```

**参数:**该方法接受指标 **i** 取值。
**返回值:**该方法在索引 I 处返回**当前值**
下面的程序说明了 getPlain()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// AtomicReferenceArray.getPlain() method

import java.util.concurrent.atomic.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference array
        // object which stores Integer.
        AtomicReferenceArray<Integer> array
            = new AtomicReferenceArray<Integer>(5);

        // set some value in array
        array.set(0, 987);
        array.set(1, 988);
        array.set(2, 989);
        array.set(3, 986);

        // get and print the value
        // using getPlain method
        for (int i = 0; i < 4; i++) {

            int value = array.getPlain(i);
            System.out.println("value at "
                               + i + " = "
                               + value);
        }
    }
}
```

**Output:**

```
value at 0 = 987
value at 1 = 988
value at 2 = 989
value at 3 = 986
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// AtomicReferenceArray.getPlain() method

import java.util.concurrent.atomic.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a array of Strings
        String[] names
            = { "AMAN", "AMAR", "SURAJ" };

        // create an atomic reference object.
        AtomicReferenceArray<String> array
            = new AtomicReferenceArray<String>(names);

        // get and print the value
        // using getPlain method
        for (int i = 0; i < array.length(); i++) {

            String value = array.getPlain(i);
            System.out.println("value at "
                               + i + " = "
                               + value);
        }
    }
}
```

**Output:**

```
value at 0 = AMAN
value at 1 = AMAR
value at 2 = SURAJ
```

**参考文献:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic referencearray . html # getPlain(int)T4】