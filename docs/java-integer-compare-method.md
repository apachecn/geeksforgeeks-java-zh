# Java Integer compare()方法

> 原文:[https://www.geeksforgeeks.org/java-integer-compare-method/](https://www.geeksforgeeks.org/java-integer-compare-method/)

java.lang 包的 Integer 类的 **compare()** 方法比较给定的两个整数值(x，y)
作为参数，如果(x==y)则返回值零，如果(x < y)则返回值小于零，
如果(x > y)则返回值大于零。

**语法:**

```java
public static int compare(int x, int y)
Parameter :
x : the first int to compare
y : the second int to compare
Return :
This method returns the value zero if (x==y), 
if (x < y) then it returns a value less than zero 
and if (x > y) then it returns a value greater than zero.

```

**示例:**展示**Java . lang . integer . compare()**方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Integer.compare() method
import java.lang.Integer;

class Gfg {
    // driver code
    public static void main(String args[])
    {
        int a = 10;
        int b = 20;

        // as 10 less than 20, Output will be a value less than zero
        System.out.println(Integer.compare(a, b));

        int x = 30;
        int y = 30;

        // as 30 equals 30, Output will be zero
        System.out.println(Integer.compare(x, y));

        int w = 15;
        int z = 8;

        // as 15 is greater than 8, Output will be a value greater than zero
        System.out.println(Integer.compare(w, z));
    }
}
```

**输出:**

```java
-1
0
1

```