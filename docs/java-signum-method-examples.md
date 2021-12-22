# Java signum()方法示例

> 原文:[https://www.geeksforgeeks.org/java-signum-method-examples/](https://www.geeksforgeeks.org/java-signum-method-examples/)

java.lang.Math.signum()返回作为参数传递给它的值的 Sign 函数。signum()函数根据传递给它的参数返回以下值:

*   如果传递的参数大于零，signum()函数将返回 1.0。
*   如果传递的参数等于零，那么 signum()函数将返回 0。
*   如果传递的参数小于零，signum()函数将返回-1.0。

**注**:如果传递的参数是 NaN，那么结果就是 NaN。如果传递的参数是正零或负零，那么结果将与参数的结果相同。

**语法**:

```java
public static double signum(double d)
Parameter :
a : the value whose signum function is to be returned.
Return :
This method returns the signum function value of 
the argument passed to it.

```

**例 1** :展示 **java.lang.Math.signum()** 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.signum() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        // when the argument is greater than zero
        double a = 30;
        System.out.println(Math.signum(a));

        // when the argument is equals to zero
        a = 0;
        System.out.println(Math.signum(a));

        // when the argument is less than zero
        a = -30;
        System.out.println(Math.signum(a));
    }
}
```

输出:

```java
1.0
0
-1.0

```

**例 2** :展示参数为 NaN 时 **java.lang.Math.signum()** 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.signum() method
import java.lang.Math; // importing java.lang package

public class GFG {
    public static void main(String[] args)
    {

        double nan = Double.NaN;
        double result;

        // Here argument is NaN, output will be NaN
        result = Math.signum(nan);
        System.out.println(result);

        // Here argument is positive zero
        result = Math.signum(0);
        System.out.println(result);

        // Here argument is negative zero
        result = Math.signum(-0);
        System.out.println(result);
    }
}
```

输出:

```java
NaN
0.0
0.0

```