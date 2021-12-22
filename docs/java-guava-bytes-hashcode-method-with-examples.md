# Java 番石榴| Bytes.hashCode()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-bytes-hashcode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-bytes-hashcode-method-with-examples/)

**Bytes.hashCode()** 是番石榴库中 [Bytes 类](https://www.geeksforgeeks.org/bytes-class-guava-java/)的一种方法，用于返回一个字节值的 hash 码。hashCode 是由编译器为对象计算的唯一整数值。如果对象值不变，则保持不变。

**语法:**

```
public static int hashCode(byte value)

```

**参数:**该方法采用强制参数**值**，这是一个字节值，需要为其找到哈希码。

**返回值:**该方法返回一个整数值，该整数值是指定值的哈希代码。

下面的程序说明了上述方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Bytes.hashCode() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Guava's Bytes.hashCode()
        // to get hash code for a value
        System.out.println("HashCode value of 10: "
                           + Bytes.hashCode((byte)10));
    }
}
```

**输出:**

```
HashCode value of 10: 10

```

**例 2:**

```
// Java code to show implementation of
// Guava's Bytes.hashCode() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Using Guava's Bytes.hashCode()
        // to get hash code for a value
        System.out.println("HashCode value of 15: "
                           + Bytes.hashCode((byte)15));
    }
}
```

**输出:**

```
HashCode value of 15: 15

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/bytes . html # hashCode(byte)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Bytes.html#hashCode(byte))