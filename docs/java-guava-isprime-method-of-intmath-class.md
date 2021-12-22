# int math 类的 Java 番石榴| isPrime()方法

> 原文:[https://www . geesforgeks . org/Java-guava-is prime-method-intmath-class/](https://www.geeksforgeeks.org/java-guava-isprime-method-of-intmath-class/)

**是[番石榴的 IntMath 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的 Prime(int n)** 方法，用于检查传递给它的参数是否为素数。如果传递给它的参数是质数，则返回真，否则返回假。

如果一个数只能被 1 和数本身整除，则称它为**质数**。

**语法:**

```java
public static boolean isPrime(int n)

```

**参数**:该方法只接受一个参数 **n** ，该参数为整数类型，需要检查素性。

**返回值:**

*   **true :** 如果 n 是素数。
*   **假:**如果 n 为 0、1 或复合数。

**异常:**如果 n 为负，则方法为 Prime(int n)抛出***IllegalArgumentException***。

**例 1 :**

```java
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

输出:

```java
63 is not a prime number
17 is a prime number

```

**例 2 :**

```java
// Java code to show implementation of 
// isPrime(int n) method of Guava's 
// IntMath class
import java.math.RoundingMode; 
import com.google.common.math.IntMath; 

class GFG { 

    static boolean findPrime(int n) 
    { 
        try { 

            // Using isPrime(int n) method
            // of Guava's IntMath class
            // This should throw "IllegalArgumentException"
            // as n is negative
            boolean ans = IntMath.isPrime(n); 

            // Return the answer 
            return ans; 
        } 
        catch (Exception e) { 
            System.out.println(e); 
            return false; 
        } 
    } 

    // Driver code 
    public static void main(String args[]) 
    { 
        int a1 = -7; 

        try { 

            // Using isPrime(int n) method
            // of Guava's IntMath class
            // This should throw "IllegalArgumentException"
            // as a1 is negative
            findPrime(a1); 
        } 
        catch (Exception e) { 
            System.out.println(e); 
        } 
    } 
} 
```

输出:

```java
java.lang.IllegalArgumentException: n (-7) must be >= 0

```

**参考:**
[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/math/intmath . html # isPrime-int-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#isPrime-int-)