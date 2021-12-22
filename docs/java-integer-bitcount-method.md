# Java Integer bitCount()方法

> 原文:[https://www.geeksforgeeks.org/java-integer-bitcount-method/](https://www.geeksforgeeks.org/java-integer-bitcount-method/)

java.lang 包的 Integer 类的 **bitCount()** 方法返回一个 int 值的二进制补码二进制表示中一位数的计数。该功能有时被称为**人口计数**。

**语法:**

```java
public static int bitCount(int n)
Parameter :
n : the value whose bits are to be counted
Return :
This method returns the count of the number of one-bits in the two's complement 
binary representation of an int value.

```

**示例:**展示**Java . lang . integer . bitcount()**方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Integer.bitCount() method
import java.lang.Integer;

class Gfg {
    // driver code
    public static void main(String args[])
    {
        int a = 10;

        // Convert integer number to binary  format
        System.out.println(Integer.toBinaryString(a));

        // to print number of 1's in the number a
        System.out.println(Integer.bitCount(a));
    }
}
```

**输出:**

```java
1010
2

```