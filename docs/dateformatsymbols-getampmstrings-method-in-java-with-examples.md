# Java 中的日期格式符号 getAmPmStrings()方法，带示例

> 原文:[https://www . geesforgeks . org/dateformatsymbols-getampmstrings-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-getampmstrings-method-in-java-with-examples/)

Java 中 **DateFormatSymbols 类**的 **getAmPmStrings()** 方法用于获取 AM 和 PM 的字符串格式。例如，“上午”和“下午”。

**语法:**

```
public String[] getAmPmStrings()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以字符串格式返回 AM 和 PM。

下面的程序说明了 getAmPmStrings()方法的使用。
**例 1:**

```
// Java code to demonstrate getAmPmStrings()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {
        int i;

        // Initializing DateFormatSymbols
        String AMPM[]
            = new DateFormatSymbols().getAmPmStrings();

        for (i = 0; i < AMPM.length; i++) {

            // Displaying the AMPM
            System.out.println("Time " + i
                               + " = " + AMPM[i]);
        }
    }
}
```

**Output:**

```
Time 0 = AM
Time 1 = PM

```

**例 2:**

```
// Java code to demonstrate getAmPmStrings()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {
        int i;

        // Initializing DateFormatSymbols
        String AMPM[]
            = new DateFormatSymbols().getAmPmStrings();

        for (i = 0; i < AMPM.length / 2; i++) {

            // Displaying the AMPM
            System.out.println("Time " + i
                               + " = " + AMPM[i]);
        }
    }
}
```

**Output:**

```
Time 0 = AM

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/text/date format symbols . html # getAmPmStrings–](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#getAmPmStrings--)