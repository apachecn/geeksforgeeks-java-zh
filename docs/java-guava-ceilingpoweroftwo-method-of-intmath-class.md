# Java 番石榴| IntMath 类的 ceilingPowerOfTwo()方法

> 原文:[https://www . geesforgeks . org/Java-guava-ceilingpoweroftwo-method-intmath-class/](https://www.geeksforgeeks.org/java-guava-ceilingpoweroftwo-method-of-intmath-class/)

[番石榴的 IntMath 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的 **ceilingPowerOfTwo(int x)** 方法接受一个参数，并计算比参数中传递的值大两的最小幂。这个方法相当于**检查流量(2，log2(x，天花板))**。

**语法:**

```
public static int ceilingPowerOfTwo(int x)

```

**参数**:该方法接受单个参数 **x** ，该参数为整数类型，返回大于参数中传递的值的 2 的最小幂。

**返回值:**大于或等于 x 的 2 的最小幂

**异常:**

*   **IllegalArgumentException:**这个方法抛出一个 IllegalArgumentException 如果 x **< =** 0。
*   **算术异常:**如果二的次高次幂不能表示为 int，即当 x **>** 2^30.时，该方法抛出算术异常

下面的例子说明了 IntMath 类的 ceilingPowerOfTwo()方法:

**例 1 :**

```
// Java code to show implementation of 
// isPrime(int n) method of Guava's 
// IntMath class
import java.math.RoundingMode; 
import com.google.common.math.IntMath; 

class GFG { 

    // Driver code 
    public static void main(String args[]) 
    { 
        int a1 = 63;

        // Using isPrime(int n) 
        // method of Guava's IntMath class
        if(IntMath.isPrime(a1))
        System.out.println(a1 + " is a prime number");
        else
        System.out.println(a1 + " is not a prime number");

        int a2 = 17;

        // Using isPrime(int n) 
        // method of Guava's IntMath class
        if(IntMath.isPrime(a2))
        System.out.println(a2 + " is a prime number");
        else
        System.out.println(a2 + " is not a prime number");
    } 
} 
```

**输出**:

```
Smallest power of 2 greater than or equal to 25 is : 32
Smallest power of 2 greater than or equal to 65 is : 128

```

**例 2 :**

```
// Java code to show implementation of 
// ceilingPowerOfTwo(int x) method of Guava's
// IntMath class
import java.math.RoundingMode; 
import com.google.common.math.IntMath; 

class GFG { 

    static int findCeilPow(int x) 
    { 
        try { 

            // Using ceilingPowerOfTwo(int x) 
            // method of Guava's IntMath class 
            // This should throw "IllegalArgumentException" 
            // as x <= 0
            int ans = IntMath.ceilingPowerOfTwo(x); 

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
        int n = -4;

        try { 
            // Function calling
            findCeilPow(n);; 
        } 
        catch (Exception e) { 
            System.out.println(e); 
        } 
    } 
} 
```

**输出**:

```
java.lang.IllegalArgumentException: x (-4) must be > 0

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # ceilingPowerOfTwo-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#ceilingPowerOfTwo-int-)