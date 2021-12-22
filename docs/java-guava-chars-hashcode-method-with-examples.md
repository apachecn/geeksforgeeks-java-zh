# Java 番石榴| Chars.hashCode()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-hashcode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-hashcode-method-with-examples/)

**Chars.hashCode()** 是番石榴库中 [Chars 类](https://www.geeksforgeeks.org/chars-class-guava-java/)的一种方法，用于返回一个 char 值的哈希代码。hashCode 是由编译器为对象计算的唯一整数值。如果对象值不变，则保持不变。

**语法:**

```java
public static int hashCode(char value)

```

**参数:**该方法采用强制参数**值**，这是一个可以找到哈希码的字符值。

**返回值:**该方法返回一个整数值，该整数值是指定值的哈希代码。

下面的程序说明了上述方法的使用:

**例 1:**

```java
// Java code to show implementation of
// Guava's Chars.hashCode() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Using Chars.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of y: "
                           + Chars.hashCode('y'));
    }
}
```

**输出:**

```java
HashCode value of y: 121

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Chars.hashCode() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Using Chars.hashCode() method to
        // get the hash code for value
        System.out.println("HashCode value of J: "
                           + Chars.hashCode('J'));
    }
}
```

**输出:**

```java
HashCode value of J: 74

```

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/primitive/chars . html # hashCode-char-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Chars.html#hashCode-char-)