# 如何在 Java 中设置双精度值的精度？

> 原文:[https://www . geesforgeks . org/如何在 java 中设置双精度值/](https://www.geeksforgeeks.org/how-to-set-precision-for-double-values-in-java/)

给定一个双精度值 **val** ，任务是将其精度值设置为特定的小数位。
**例:**

```
Input: val = 1 
Output: 1.0000
Upto 4 decimal places

Input : 12.5
Output : 12.500000
Upto 6 decimal places
```

**<u>方法:使用 string . format()</u>** <u>我们可以使用 [String.format()](https://www.geeksforgeeks.org/java-string-format-examples/) 方法将十进制数格式化为某种特定的格式。</u>

<u>**语法:**</u>

```
String.format("%.Df", decimalValue);

where D is the number required number of Decimal places.
```

<u>下面是上述方法的实现:</u>

## <u>Java 语言(一种计算机语言，尤用于创建网站)</u>

```
import java.io.*;
import java.lang.*;

class GFG {
  public static void main(String[] args) {

    double a = 0.9;

    // Setting the precision to 20 places
    System.out.println(
      String.format("%.20f", a));

    double b = 1;

    // Setting the precision to 5 places
    System.out.println(
      String.format("%.5f", b));
  }
}
```

<u>**Output**

```
0.90000000000000000000
1.00000
```</u>