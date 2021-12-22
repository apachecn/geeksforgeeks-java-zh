# 爪哇番石榴| Chars.max()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-max-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-max-method-with-examples/)

**Chars.max()** 是[番石榴库](https://www.geeksforgeeks.org/guava-library-java/)中 [Chars 类](https://www.geeksforgeeks.org/chars-class-guava-java/)的一种方法，用于查找数组中最大的**值。此方法返回的值是指定数组中最大的字符值**

****语法:****

```java
public static char max(char... array) 
```

****参数:**该方法采用强制参数 ***数组*** ，该数组是非空的 *char* 值数组。**

****返回值:**该方法返回一个字符值，该值是指定数组中的最大值。**

****异常:**阵为空则法掷***IllegalArgumentException***。**

**下面的程序说明了上述方法的使用:**

****例 1 :****

```java
// Java code to show implementation of
// Guava's Chars.max() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a character array
        char[] arr = { 'A', 'E', 'I', 'O', 'U' };

        // Using Chars.max() method to get the
        // maximum value present in the array
        System.out.println("Maximum value is : "
                           + Chars.max(arr));
    }
}
```

****输出:**

```java
Maximum value is : U

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Chars.max() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a character array
        char[] arr = {};

        try {
            // Using Chars.max() method to get the
            // maximum value present in the array
            // This should raise "IllegalArgumentException"
            // as the array is empty
            System.out.println("Maximum value is : "
                               + Chars.max(arr));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.IllegalArgumentException

```

**参考:**[https://Google . github . io/guava/releases/18.0/API/docs/com/Google/common/primitive/chars . html # max(char…)](https://google.github.io/guava/releases/18.0/api/docs/com/google/common/primitives/Chars.html#max(char...))**