# Java 中的 BigDecimal compareTo()函数

> 原文:[https://www . geesforgeks . org/big decimal-compare to-function-in-Java/](https://www.geeksforgeeks.org/bigdecimal-compareto-function-in-java/)

**Java . math . BigDecimal . compare to(BigDecimal BG)**方法检查作为参数传递的*这个* BigDecimal 和 BigDecimal 对象 **bg** 是否相等。该方法考虑两个相等的大十进制对象，即使它们的值相等，与比例无关。

**语法:**

```
public int compareTo(*BigDecimal bg*)
```

**参数:**该函数只接受一个*大十进制类型的大十进制对象*与*这个*大十进制对象进行比较。

**返回值:**这个方法可以返回值如下:

*   **0** :如果*这个*大十进制的值等于*作为参数传递的大十进制对象的值。*
*   **1** :如果*这个*大十进制的值大于作为参数传递的大十进制对象的值*。*
*   **-1** :如果*这个*大十进制的值小于作为参数传递的大十进制对象的值*。*

**注意:**该函数在比较 124.0 和 124.0000 时返回 true，因为它不比较两个 BigDecimal 对象的比例。

**示例:**

```
Input : b1 = new BigDecimal("4743.0008"),  b2 = new BigDecimal("4743.00001")
        b1.compareTo(b2)
Output : 1

Input : b1 = new BigDecimal(4743),  b2 = new BigDecimal("4743.00");
        b1.compareTo(b2)
Output : 0

```

下面的程序说明了 BigDecimal 类的 compareTo()函数的工作:
**程序 1:** 对于大于条件:

```
// Java program to demonstrate compareTo() method

import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigDecimal objects
        BigDecimal b1, b2;

        b1 = new BigDecimal(67891);
        b2 = new BigDecimal(12346);

        if (b1.compareTo(b2) == 0) {
            System.out.println(b1 + " and " + b2 + " are equal.");
        }
        else if (b1.compareTo(b2) == 1) {
            System.out.println(b1 + " is greater than " + b2 + ".");
        }
        else {
            System.out.println(b1 + " is lesser than " + b2 + ".");
        }
    }
}
```

**Output:**

```
67891 is greater than 12346.

```

**程序 2:** 同等条件下:

```
// Java program to demonstrate compareTo() method

import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigDecimal objects
        BigDecimal b1, b2;

        b1 = new BigDecimal(67891);
        b2 = new BigDecimal("67891.000");

        if (b1.compareTo(b2) == 0) {
            System.out.println(b1 + " and " + b2 + " are equal.");
        }
        else if (b1.compareTo(b2) == 1) {
            System.out.println(b1 + " is greater than " + b2 + ".");
        }
        else {
            System.out.println(b1 + " is lesser than " + b2 + ".");
        }
    }
}
```

**Output:**

```
67891 and 67891.000 are equal.

```

**程序 3:** 小于条件:

```
// Java program to demonstrate compareTo() method

import java.io.*;
import java.math.*;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigDecimal objects
        BigDecimal b1, b2;

        b1 = new BigDecimal("4743.00001");
        b2 = new BigDecimal("4743.0008");

        if (b1.compareTo(b2) == 0) {
            System.out.println(b1 + " and " + b2 + " are equal.");
        }
        else if (b1.compareTo(b2) == 1) {
            System.out.println(b1 + " is greater than " + b2 + ".");
        }
        else {
            System.out.println(b1 + " is lesser than " + b2 + ".");
        }
    }
}
```

**Output:**

```
4743.00001 is lesser than 4743.0008.

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # compare to(Java . math . bigdecimal)](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#compareTo(java.math.BigDecimal))