# 如何在 Java 中获取数据类型的大小、最小值和最大值？

> 原文:[https://www . geesforgeks . org/如何获取 java 中数据类型的大小最小值和最大值/](https://www.geeksforgeeks.org/how-to-get-size-minimum-and-maximum-value-of-data-types-in-java/)

数据类型的**大小**由(数据类型名称)给出。大小**最大值**由(数据类型名称)给出。最大值。其可存储的**最小值**由(数据类型名称)给出。最小值。

> 总是用大写字母写数据类型的第一个单词。

**示例:**

**1。**如果要打印浮点数据类型的大小，请使用浮点。大小

**2。**如果您想打印字节的大小和值，请使用以下代码

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Print size, minimum value and maximum
// value of Byte data types in java
import java.io.*;

class ValuesOfByte {
    public static void main(String[] args)
    {
        System.out.println("Byte\t" + Byte.SIZE + "\t"
                           + Byte.MIN_VALUE + "\t"
                           + Byte.MAX_VALUE);
    }
}
```

**Output**

```
Byte    8    -128    127
```

**3。**要打印大小，所有原始数据类型的最大值和最小值使用以下代码

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Print size, minimum value and 
// maximum value of data types in java
public class RangeOfDataTypes {
    public static void main(String args[])
    {
        System.out.println(
            "S.No.\t  Data Type\t  Size\t  Min. Value\t\t  Max. Value\t");
        System.out.println("1\t  Byte\t\t" + Byte.SIZE
                           + "\t" + Byte.MIN_VALUE
                           + "\t\t\t" + Byte.MAX_VALUE);
        System.out.println("2\t  Short\t\t" + Short.SIZE
                           + "\t" + Short.MIN_VALUE
                           + "\t\t\t" + Short.MAX_VALUE);
        System.out.println("3\t  Integer\t" + Integer.SIZE
                           + "\t" + Integer.MIN_VALUE
                           + "\t\t" + Integer.MAX_VALUE);
        System.out.println("4\t  Float\t\t" + Float.SIZE
                           + "\t" + Float.MIN_VALUE
                           + "\t\t\t" + Float.MAX_VALUE);
        System.out.println("5\t  Long\t\t" + Long.SIZE
                           + "\t" + Long.MIN_VALUE + "\t"
                           + Long.MAX_VALUE);
        System.out.println("6\t  Double\t" + Double.SIZE
                           + "\t" + Double.MIN_VALUE
                           + "\t\t" + Short.MAX_VALUE);
        System.out.println("7\t  Character\t"
                           + Character.SIZE);
    }
}
```

**输出:**

```
S.No.      Data Type      Size          Min. Value                Max. Value
1           Byte           8             -128                       127
2           Short         16             -32768                     32767
3           Integer       32             -2147483648                2147483647
4           Float         32              1.4E-45                   3.4028235E38
5           Long          64             -9223372036854775808       9223372036854775807
6           Double        64              4.9E-324                  1.7976931348623157E308
7           Character     16

```