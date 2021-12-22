# Java 番石榴| Doubles.hashCode()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-hashcode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-hashcode-method-with-examples/)

**Doubles.hashCode()** 是番石榴库中 [Doubles 类](https://www.geeksforgeeks.org/doubles-class-guava-java/)的一种方法，用于返回一个双精度值的 hash 码。hashCode 是由编译器为对象计算的唯一整数值。如果对象值不变，则保持不变。

**语法:**

```
public static int hashCode(double value)

```

**参数:**该方法采用强制参数**值**，这是一个需要找到哈希码的双精度值。

**返回值:**该方法返回一个整数值，该整数值是指定值的哈希代码。

下面的程序说明了上述方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Doubles.hashCode() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Doubles.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 10.12: "
                           + Doubles.hashCode(10.12));
    }
}
```

**输出:**

```
HashCode value of 10.12: -470599859

```

**例 2:**

```
// Java code to show implementation of
// Guava's Doubles.hashCode() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Doubles.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 20.45: "
                           + Doubles.hashCode(20.45));
    }
}
```

**输出:**

```
HashCode value of 20.45: 1929854976

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitives/double . html # hashCode(double)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#hashCode(double))