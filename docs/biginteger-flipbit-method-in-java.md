# Java 中的 BigInteger flipBit()方法

> 原文:[https://www . geesforgeks . org/big integer-flipbit-method-in-Java/](https://www.geeksforgeeks.org/biginteger-flipbit-method-in-java/)

先决条件:[大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)
**方法返回一个大整数，用于翻转大整数中的特定位位置。该方法计算(大整数^ (1 < < n))。bigInteger 的二进制表示的索引 n 处的位将被翻转。也就是说，如果位位置为 0，它将被转换为 1，反之亦然。
**语法:**** 

```java
public BigInteger flipBit(int index)
```

**参数:**该方法接受一个整数类型的参数*索引*，并引用要翻转的位的位置。
**返回值:**该方法在位置*索引*翻转位后返回大整数。
**抛出:**当索引值为负时，该方法抛出*算术异常*。
**举例:**

```java
Input: value = 2300 , index = 1
Output: 2302
Explanation:
Binary Representation of 2300 = 100011111100
bit at index 1 is 0 so flip the bit at index 1 and it becomes 1\. 
Now Binary Representation becomes 100011111110
and Decimal equivalent of 100011111110 is 2302

Input: value = 5482549 , index = 5
Output: 5482517
```

下面的程序说明了 BigInteger 的 flipBit(索引)方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
/*
*Program Demonstrate flipBit() method of BigInteger
*/
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating  BigInteger object
        BigInteger biginteger = new BigInteger("5482549");

        // Creating an int i for index
        int i = 5;

        // Call flipBit() method on bigInteger at index i
        // store the return BigInteger
        BigInteger changedvalue = biginteger.flipBit(i);

        String result = "After applying flipBit at index " + i +
        " of " + biginteger+ " New Value is " + changedvalue;

        // Print result
        System.out.println(result);
    }
}
```

**Output:** 

```java
After applying flipBit at index 5 of 5482549 New Value is 5482517
```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # clearBit(int)T4】