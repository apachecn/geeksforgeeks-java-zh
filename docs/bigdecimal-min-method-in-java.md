# Java 中的 BigDecimal min()方法

> 原文:[https://www . geesforgeks . org/big decimal-min-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-min-method-in-java/)

java 中的**Java . math . BigDecimal . min(BigDecimal val)**方法用于比较两个 BigDecimal 值，并返回这两个值的**最小值**。

**语法:**

```
public BigDecimal min(BigDecimal val)
```

**参数:**函数接受一个大十进制对象*值*作为参数，其值与该大十进制对象的值进行比较，并返回最小值。

**返回值:**该方法返回大十进制数，其值是*这个*大十进制数和**值**中较小的一个。如果两者相等，则返回*这个*大十进制。

**例:**

```
Input :  a = 17.000041900, b = 17.0000418999
Output : 17.0000418999

Input : a = 235900000146, b = 236000000000
Output : 235900000146

```

下面的程序将说明 BigDecimal 类的 min()函数:

**程序 1:**

```
/*Java program to illustrate
use of BigDecimal min() 
function in Java      */
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigDecimal objects
        BigDecimal a, b;

        a = new BigDecimal("17.000041900");
        b = new BigDecimal("17.0000418999");

        // print the maximum value
        System.out.println("Minimum Value among " + a + 
                        " and " + b + " is " + a.min(b));
    }
}
```

**输出:**

```
Minimum Value among 17.000041900 and 17.0000418999 is 17.0000418999

```

**程序二:**

```
/*Java program to illustrate
use of BigDecimal min() 
to display minimum length
among two strings  */
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create 2 BigDecimal objects
        BigDecimal a, b;
        String s = "GeeksforGeeks";
        String str = "GeeksClasses";

        int l1, l2;
        l1 = s.length();
        l2 = str.length();

        a = new BigDecimal(l1);
        b = new BigDecimal(l2);

        // Print the respective lengths
        System.out.println("Length of string " + s + " is " + a);
        System.out.println("Length of string " + str + " is " + b);
        // Print the maximum value
        System.out.println("Minimum length is " + a.min(b));
    }
}
```

**输出:**

```
Length of string GeeksforGeeks is 13
Length of string GeeksClasses is 12
Minimum length is 12

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # min()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#min())