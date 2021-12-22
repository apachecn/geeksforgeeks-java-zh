# Java 番石榴| int math 类的均值()方法

> 原文:[https://www . geesforgeks . org/Java-guava-mean-of-meth-class/](https://www.geeksforgeeks.org/java-guava-mean-method-of-intmath-class/)

[番石榴的 IntMath 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的**均值(int x，int y)** 方法接受两个参数 **x** 和 **y** ，并计算它们向负无穷大舍入的算术平均值。这种方法具有溢出弹性。

**语法:**

```java
public static int mean(int x, int y)

```

**参数**:该方法接受两个整数类型的参数 **x** 和 **y** 。

**返回值:**该方法返回 x 和 y 的算术平均值，向负无穷大舍入。

**异常:**方法没有任何异常。

**例 1 :**

```java
// Java code to show implementation of
// mean(int x, int y) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int x = 1542;
        int y = 421;

        // Using mean(int x, int y)
        // method of Guava's IntMath class
        int ans = IntMath.mean(x, y);

        // Displaying the result
        System.out.println("Mean of " + x + " and " 
                               + y + " is : " + ans);
    }
}
```

输出:

```java
Mean of 1542 and 421 is : 981

```

**例 2 :**

```java
// Java code to show implementation of
// mean(int x, int y) method of Guava's
// IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int x = 214;
        int y = 154;

        // Using mean(int x, int y)
        // method of Guava's IntMath class
        int ans = IntMath.mean(x, y);

        // Displaying the result
        System.out.println("Mean of " + x + " and " 
                                 + y + " is : " + ans);
    }
}
```

输出:

```java
Mean of 214 and 154 is : 184

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # mean-int-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#mean-int-int-)