# Java 中的排序器 getAvailableLocales()方法，示例

> 原文:[https://www . geeksforgeeks . org/collator-getavailable locales-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-getavailablelocales-method-in-java-with-example/)

**java.text.Collator 类**的 **getAvailablelocales()** 方法用于在初始化 Collator 对象时获取传递的 Locales 实例下所有可用的 Locales。
**语法:**

```
public static Locale[] getAvailableLocales()
```

**参数**:此方法不接受任何参数。
**返回值:**该方法返回该实例下所有可用的**地区**。
以下是举例说明 **getAvailableLocales()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getAvailableLocales() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing new simple rule
            String simple = "< a< b< c< d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting all the available locale
            // using getAvailableLocales() method
            Locale[] locale = col.getAvailableLocales();

            // display result
            System.out.println("Equivalent Locales are ");
            for (int i = 1; i <= 5; i++)
                System.out.println(locale[i]);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ParseException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Equivalent Locales are 
ar_AE
ar_JO
ar_SY
hr_HR
fr_BE
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getAvailableLocales() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col = Collator.getInstance(Locale.UK);

            // getting all the available locale
            // using getAvailableLocales() method
            Locale[] locale = col.getAvailableLocales();

            // display result
            System.out.println("Equivalent Locales are ");
            for (int i = 6; i <= 10; i++)
                System.out.println(locale[i]);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Equivalent Locales are 
es_PA
es_VE
mt_MT
bg
zh_TW
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # getAvailableLocales–T4】