# Java 番石榴| Floats.hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-hashcode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-hashcode-method-with-examples/)

**Floats.hashCode()** 是番石榴库中 [Floats 类](https://www.geeksforgeeks.org/floats-class-guava-java/)的一种方法，用于返回浮点值的哈希代码。hashCode 是由编译器为对象计算的唯一整数值。如果对象值不变，则保持不变。

**语法:**

```java
public static int hashCode(float value)

```

**参数:**该方法采用强制参数**值**，这是一个浮点值，可以找到哈希值。

**返回值:**该方法返回一个整数值，该整数值是指定值的哈希代码。

下面的程序说明了上述方法的使用:

**例 1 :**

```java
// Java code to show implementation of
// Guava's Floats.hashCode() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Floats.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 10.12f: "
                           + Floats.hashCode(10.12f));
    }
}
```

**输出:**

```java
HashCode value of 10.12f: 1092742021

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Floats.hashCode() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Floats.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 20.24f: "
                           + Floats.hashCode(20.24f));
    }
}
```

**输出:**

```java
HashCode value of 20.24f: 1101130629

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/floats . html # hashCode(float)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#hashCode(float))