# 爪哇番石榴|短裤 max()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-短裤-max-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-max-method-with-examples/)

**短裤 max()** 是[番石榴库](https://www.geeksforgeeks.org/guava-library-java/)中[短裤类](https://www.geeksforgeeks.org/shorts-class-guava-java/)的一种方法，用于查找数组中存在的 ***最大*** 值。此方法返回的值是指定数组中最大的短值。

**语法:**

```java
public static short max(short... array)

```

**参数:**该方法取一个强制参数 ***数组*** 是一个非空的*短*值数组。

**返回值:**该方法返回一个短值，即指定数组中的最大值。

**异常:**阵为空则法掷***IllegalArgumentException***。

下面的程序说明了上述方法的使用:

**示例-1 :**

```java
// Java code to show implementation of
// Guava's Shorts.max() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = { 2, 4, 6, 10, 0, -5, 15, 7 };

        // Using Shorts.max() method to get the
        // maximum value present in the array
        System.out.println("Maximum value is : " + Shorts.max(arr));
    }
}
```

**输出:**

```java
Maximum value is : 15

```

**示例-2 :**

```java
// Java code to show implementation of
// Guava's Shorts.max() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = {};

        // Using Shorts.max() method to get the
        // maximum value present in the array
        // This should raise "IllegalArgumentException"
        // as the array is empty
        System.out.println("Maximum value is : " + Shorts.max(arr));
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.IllegalArgumentException
    at com.google.common.base.Preconditions.checkArgument(Preconditions.java:108)
    at com.google.common.primitives.Shorts.max(Shorts.java:254)
    at GFG.main(File.java:19)

```

**参考**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/primitives/短裤. html # max-short……-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#max-short...-)