# Java 中的整数 rotateLeft()方法

> 原文:[https://www . geesforgeks . org/integer-rotateleft-method-in-Java/](https://www.geeksforgeeks.org/integer-rotateleft-method-in-java/)

位移位是一种按位操作，通过向左或向右移动一定数量的位来对二进制值的所有位执行。Java 只有一个逻辑左移位运算符(<< ). When the value 0001(i.e., 1) is shifted left, it becomes 0010(i.e., 2) which on shifting again to the left becomes 0100 or 4\. The same process is applied for the right shift operation.
)Java . lang . Integer . rotateleft()方法用于将整数值的位向左移位指定的位数，该整数值以二进制 2 的互补形式表示。(位向左或更高阶移动)。

**语法:**

```java
public static int rotateLeft(*int value, int shifts*)
```

**参数:**该方法取两个参数:

*   *a* :这是整数类型，指的是要进行运算的值。
*   *移位*:这也是整数类型，指的是旋转的距离。

**返回值:**该方法返回通过将指定 int 值的二进制补码二进制表示向左旋转指定数量的移位位而获得的值。
**例:**

```java
Input: 12
Output: 24
Explanation:
Consider an integer a = 12 
Binary Representation = 00001100
After 1 left shift it will become=00011000
So that is= 24

```

下面的程序说明了 java.lang.Integer.rotateLeft()方法。
**程序 1:** 为正数。

```java
// Java program to illustrate the
// Java.lang.Integer.rotateLeft() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = 2;
        int shifts = 0;
        while (shifts < 6)
        // It will return the value obtained by rotating left
        {
            a = Integer.rotateLeft(a, 2);
            System.out.println(a);
            shifts++;
        }
    }
}
```

**Output:**

```java
8
32
128
512
2048
8192

```

**程序 2:** 为负数。

```java
// Java program to illustrate the
// Java.lang.Integer.rotateLeft() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = -16;
        int shifts = 0;
        while (shifts < 2)
        // It will return the value obtained by rotating left
        {
            a = Integer.rotateLeft(a, shifts);
            System.out.println(a);
            shifts++;
        }
    }
}
```

**Output:**

```java
-16
-31

```

**程序 3:** 为十进制值和字符串。
**注意:**当十进制值和字符串作为参数传递时，它会返回一条错误消息

```java
// Java program to illustrate the
// Java.lang.Integer.rotateLeft() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = 15.71;
        int shifts = 0;
        while (shifts < 2)

        {
            a = Integer.rotateLeft(a, shifts);
            System.out.println(a);
            shifts++;
        }
        int b = "61";
        int shifts2 = 0;
        while (shifts2 < 2)

        {
            b = Integer.rotateLeft(b, shifts2);
            System.out.println(b);
            shifts2++;
        }
    }
}
```

**Output:**

```java
prog.java:9: error: incompatible types: possible lossy conversion from double to int
    int a = 15.71;
            ^
prog.java:18: error: incompatible types: String cannot be converted to int
   int    b = "61";
              ^
2 errors

```