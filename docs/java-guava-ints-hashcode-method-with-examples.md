# Java 番石榴| Ints.hashCode()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-ints-hashcode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-ints-hashcode-method-with-examples/)

**Ints.hashCode()** 是番石榴库中 [Ints 类](https://www.geeksforgeeks.org/ints-class-guava-java/)的一种方法，用于返回一个 int 值的 hash 码。hashCode 是由编译器为对象计算的唯一整数值。如果对象值不变，则保持不变。

**语法:**

```
public static int hashCode(int value)

```

**参数:**该方法采用强制参数**值**，该值是一个整型值，可以找到哈希值。

**返回值:**该方法返回一个整数值，该整数值是指定值的哈希代码。

下面的程序说明了上述方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Ints.hashCode() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Ints.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 15: "
                           + Ints.hashCode(15));
    }
}
```

**输出:**

```
HashCode value of 15: 15

```

**例 2:**

```
// Java code to show implementation of
// Guava's Ints.hashCode() method

import com.google.common.primitives.Ints;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Ints.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 10: "
                           + Ints.hashCode(10));
    }
}
```

**输出:**

```
HashCode value of 10: 10

```

**参考:**[https://Google . github . io/guava/releases/22.0/API/docs/com/Google/common/primitives/ints . html # hashCode-int-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#hashCode-int-)