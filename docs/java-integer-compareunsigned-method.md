# Java 整数比较符号()方法

> 原文:[https://www . geeksforgeeks . org/Java-integer-compare unsigned-method/](https://www.geeksforgeeks.org/java-integer-compareunsigned-method/)

java.lang 包的 Integer 类的**comparensigned()**方法比较作为参数给定的两个整数值(x，y)，**将这些值视为无符号的**，如果(x==y)，则返回值零，如果(x < y，则返回值小于零，如果(x > y，则返回值大于零。

**语法:**

```
public static int compareUnsigned(int x, int y)
Parameter :
x : the first int to compare
y : the second int to compare
Return :
This method returns the value zero if (x==y), 
if (x < y) then it returns a value less than zero 
and if (x > y) then it returns a value greater than zero,
treating the values(x, y) as unsigned.

```

**示例:**展示**Java . lang . integer . comparensigned()**方法的工作。

```
// Java program to demonstrate working
// of java.lang.Integer.compareUnsigned() method
import java.lang.Integer;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        int a = 100;
        int b = 200;

        // as 100 less than 200, Output will be a value less than zero
        System.out.println(Integer.compareUnsigned(a, b));

        int x = 28;
        int y = 28;

        // as 28 equals 28, Output will be zero
        System.out.println(Integer.compareUnsigned(x, y));

        int w = 15;
        int z = 8;

        // as 15 is greater than 8, Output will be a value greater than zero
        System.out.println(Integer.compareUnsigned(w, z));

        int m = 15;
        int n = -8;

        // as 15 is greater than -8,
        // but -8 will be treated as an unsigned number
        // which will be greater than 15
        // Output will be a value less than zero
        System.out.println(Integer.compareUnsigned(m, n));
    }
}
```

**输出:**

```
-1
0
1
-1

```