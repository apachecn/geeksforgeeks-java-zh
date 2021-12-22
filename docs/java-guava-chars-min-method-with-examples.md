# 爪哇番石榴| Chars.min()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-min-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-min-method-with-examples/)

**Chars.min()** 是[番石榴库](https://www.geeksforgeeks.org/guava-library-java/)中 [Chars 类](https://www.geeksforgeeks.org/chars-class-guava-java/)的一种方法，用于查找数组中最少出现的**值。此方法返回的值是指定数组中最小的字符值。**

****语法:****

```
public static char min(char... array) 
```

****参数:**该方法采用强制参数 ***数组*** ，该数组是非空的 *char* 值数组。**

****返回值:**该方法返回一个字符值，该值是指定数组中的最小值。**

****异常:**阵为空则法掷***IllegalArgumentException***。**

**下面的程序说明了上述方法的使用:**

****例 1 :****

```
// Java code to show implementation of
// Guava's Chars.min() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a character array
        char[] arr = { 'A', 'E', 'I', 'O', 'U' };

        // Using Chars.min() method to get the
        // minimum value present in the array
        System.out.println("Minimum Value is : "
                           + Chars.min(arr));
    }
}
```

****输出:**

```
Minimum Value is : A

```

**例 2 :**

```
// Java code to show implementation of
// Guava's Chars.min() method

import com.google.common.primitives.Chars;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a character array
        char[] arr = {};

        try {
            // Using Chars.min() method to get the
            // minimum value present in the array
            // This should raise "IllegalArgumentException"
            // as the array is empty
            System.out.println("Minimum Value is : "
                               + Chars.min(arr));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.lang.IllegalArgumentException

```

**参考:**[https://Google . github . io/guava/releases/18.0/API/docs/com/Google/common/primitive/chars . html # min(char…)](https://google.github.io/guava/releases/18.0/api/docs/com/google/common/primitives/Chars.html#min(char...))**