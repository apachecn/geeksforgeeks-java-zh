# Java 中的 BigDecimal max()方法

> 原文:[https://www . geesforgeks . org/big decimal-max-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-max-method-in-java/)

Java 中的**Java . math . BigDecimal . max(BigDecimal val)**方法用于比较两个 BigDecimal 值并返回两者的**最大值**。这与 Java 中的 BigDecimal max()方法相反。

**语法:**

```
public BigDecimal max(BigDecimal val)
```

**参数:**函数接受一个大十进制对象*值*作为参数，其值与该大十进制对象的值进行比较，并返回最大值。

**返回值:**该方法返回大十进制数，其值为*这个*大十进制数和**值**中的较大值。如果两者相等，则返回*这个*大十进制。

**示例:**

```
Input :  a = 17.000041900, b = 17.0000418999
Output : 17.000041900

Input : a = 235900000146, b = 236000000000
Output : 236000000000

```

下面的程序将说明 BigDecimal 类的 max()函数。

**程序 1:**

```
// Java program to illustrate use of
// BigDecimal max() function in Java      
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // create 2 BigDecimal objects
        BigDecimal a, b;

        a = new BigDecimal("235900000146");
        b = new BigDecimal("236000000000");

        // print the maximum value
        System.out.println("Maximum Value among " + a + 
                       " and " + b + " is " + a.max(b));
    }
}
```

**Output:**

```
Maximum Value among 235900000146 and 236000000000 is 236000000000

```

**程序 2:**

```
// Java program to illustrate use of BigDecimal max() 
// to display maximum length among two strings in Java  
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
        System.out.println("Maximum length is " + a.max(b));
    }
}
```

**Output:**

```
Length of string GeeksforGeeks is 13
Length of string GeeksClasses is 12
Maximum length is 13

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # max()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#max())