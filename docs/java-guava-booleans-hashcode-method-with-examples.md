# Java 番石榴| Booleans.hashCode()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-booleans-hashcode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-hashcode-method-with-examples/)

**Booleans.hashCode()** 是番石榴库中 [Booleans 类](https://www.geeksforgeeks.org/booleans-class-guava-java/)的一种方法，用于返回布尔值的哈希代码。hashCode 是由编译器为对象计算的唯一整数值。如果对象值不变，则保持不变。

**语法:**

```java
public static int hashCode(boolean value)

```

**参数:**该方法采用强制参数**值**，这是一个布尔值，需要为其找到哈希码。

**返回值:**该方法返回一个整数值，该整数值是指定值的哈希代码。

下面的程序说明了上述方法的使用:

**示例-1 :**

```java
// Java code to show implementation of
// Guava's Booleans.hashCode() method
import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Using Booleans.hashCode() method to
        // get the hash code for value
        System.out.println(Booleans.hashCode(true));
    }
}
```

**输出:**

```java
1231

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Booleans.hashCode() method
import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Using Booleans.hashCode() method to
        // get the hash code for value
        System.out.println(Booleans.hashCode(false));
    }
}
```

**输出:**

```java
1237

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/primitive/booleans . html # hashCode-boolean-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#hashCode-boolean-)