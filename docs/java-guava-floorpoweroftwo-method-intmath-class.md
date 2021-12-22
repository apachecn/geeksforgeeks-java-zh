# Java 番石榴| floorPowerOfTwo()方法 IntMath Class

> 原文:[https://www . geesforgeks . org/Java-guava-floweroftwo-method-int math-class/](https://www.geeksforgeeks.org/java-guava-floorpoweroftwo-method-intmath-class/)

[番石榴的 IntMath 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的**floweroftwo()**方法接受一个参数，并返回比参数中传递的值小 2 的最大幂。这相当于:**检查流量(2，log2(x，FLOOR))** 。

**语法:**

```java
public static int floorPowerOfTwo(int x)

```

**参数**:该方法接受单个参数 x，x 为整数值。

**返回值:**该方法返回小于或等于 x 的 2 的最大幂。

**异常:**方法 floorPowerOfTwo(int x)抛出***IllegalArgumentException***if x**<=**0。

**例 1 :**

```java
// Java code to show implementation
// of floorPowerOfTwo(int x) method
// of Guava's IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int n1 = 10;

        // Using floorPowerOfTwo(int x) method
        // of Guava's IntMath class
        int ans1 = IntMath.floorPowerOfTwo(n1);

        System.out.println("Largest power of 2 less "
                           + "than or equal to " + n1 + " is : " + ans1);

        int n2 = 127;

        // Using floorPowerOfTwo(int x) method
        // of Guava's IntMath class
        int ans2 = IntMath.floorPowerOfTwo(n2);

        System.out.println("Largest power of 2 less "
                           + "than or equal to " + n2 + " is : " + ans2);
    }
}
```

输出:

```java
Largest power of 2 less than or equal to 10 is : 8
Largest power of 2 less than or equal to 127 is : 64

```

**例 2 :**

```java
// Java code to show implementation
// of floorPowerOfTwo(int x) method
// of Guava's IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findFloorPow(int x)
    {
        try {
            // Using floorPowerOfTwo(int x)
            // method of Guava's IntMath class
            // This should raise "IllegalArgumentException"
            // as x <= 0
            int ans = IntMath.floorPowerOfTwo(x);

            // Return the answer
            return ans;
        }
        catch (Exception e) {
            System.out.println(e);
            return -1;
        }
    }

    // Driver code
    public static void main(String args[])
    {
        int x = -3;

        try {
            // Function calling
            findFloorPow(x);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

输出:

```java
java.lang.IllegalArgumentException: x (-3) must be > 0

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # floweroftwo-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#floorPowerOfTwo-int-)