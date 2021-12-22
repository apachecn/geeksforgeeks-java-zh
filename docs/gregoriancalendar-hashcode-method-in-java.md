# Java 中的 GregorianCalendar hashCode()方法

> 原文:[https://www . geesforgeks . org/gregoriancalendar-hashcode-method-in-Java/](https://www.geeksforgeeks.org/gregoriancalendar-hashcode-method-in-java/)

**java . util . GregorianCalendar . hashcode()**是 Java 中的内置函数，它为这个 GregorianCalendar 实例生成哈希代码*。*

**语法:**

```
public int hashCode()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回一个整数值，该整数值代表*这个*格雷戈里安卡列达尔实例的哈希代码。

**示例:**

```
Input : Thu Jul 24 00:53:29 UTC 1997
Output : 2121703905

Input : Tue Jul 24 00:54:11 UTC 2018
Output : -909136554

```

下面的程序说明了 Java . util . gregoriancalendar . hashcode()函数:
**程序 1:**

```
// Java Program to illustrate hashCode() function
// of GregorianCalendar class

import java.io.*;
import java.util.*;

class GFG {
     public static void main(String[] args) {

      // Create a new calendar
      GregorianCalendar c = (GregorianCalendar) 
                GregorianCalendar.getInstance();

      // Display the current date and time
      System.out.println("Current Date and Time : "
                                    + c.getTime());

      // Display hashcode for this calendar
      System.out.println("Hash Code:" + c.hashCode());
   }
}
```

**Output:**

```
Current Date and Time : Fri Jul 27 11:43:16 UTC 2018
Hash Code:-612105832

```

**程序 2:**

```
// Java Program to illustrate hashCode() function
// of GregorianCalendar class

import java.io.*;
import java.util.*;

class GFG {
     public static void main(String[] args) {

      // Create a new calendar
      GregorianCalendar c = (GregorianCalendar) 
                 GregorianCalendar.getInstance();

      // Display the current date and time
      System.out.println("Current Date and Time : "
                                     + c.getTime());

      c.add((GregorianCalendar.YEAR), -12);
      System.out.println("Modified Date and Time : "
                                    + c.getTime());

      // Display hashcode for this calendar
      System.out.println("Hash Code of the " + 
      "modified date and time:" + c.hashCode());
   }
}
```

**Output:**

```
Current Date and Time : Fri Jul 27 11:43:18 UTC 2018
Modified Date and Time : Thu Jul 27 11:43:18 UTC 2006
Hash Code of the modified date and time:-1346149059

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/gregoriancalendar . html # hashCode()](https://docs.oracle.com/javase/7/docs/api/java/util/GregorianCalendar.html#hashCode())