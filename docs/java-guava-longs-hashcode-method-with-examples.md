# Java 番石榴| Longs.hashCode()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-hashcode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-hashcode-method-with-examples/)

**Longs.hashCode()** 是番石榴库中 [Longs 类](https://www.geeksforgeeks.org/longs-class-guava-java/)的一种方法，用于返回长值的哈希码。hashCode 是由编译器为对象计算的唯一整数值。如果对象值不变，则保持不变。

**语法:**

```java
public static int hashCode(long value)

```

**参数:**该方法采用强制参数**值**，这是一个长值，需要找到哈希值。

**返回值:**该方法返回一个整数值，该整数值是指定值的哈希代码。

下面的程序说明了上述方法的使用:

**例 1:**

```java
// Java code to show implementation of
// Guava's Longs.hashCode() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Using Longs.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 15: "
                           + Longs.hashCode(15));
    }
}
```

**Output:**

```java
HashCode value of 15: 15

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Longs.hashCode() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Using Longs.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of 10: "
                           + Longs.hashCode(10));
    }
}
```

**Output:**

```java
HashCode value of 10: 10

```

**参考:**
[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/primitive/longs . html # hashCode-long-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#hashCode-long-)