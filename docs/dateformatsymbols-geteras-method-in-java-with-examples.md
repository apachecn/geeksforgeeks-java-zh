# Java 中的日期格式符号 getEras()方法，带示例

> 原文:[https://www . geesforgeks . org/dateformatsymbols-geteras-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-geteras-method-in-java-with-examples/)

Java 中 **DateFormatSymbols 类**的 **getEras()方法**用于获取字符串格式的 Era 字符串。例如，“公元前”和“公元”。

**语法:**

```java
public String[] getEras()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回纪元字符串。

下面的程序说明了 getEras()方法的使用。
**例 1:**

```java
// Java code to demonstrate getEras()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {
        int i;

        // Initializing DateFormatSymbols
        String eras[]
            = new DateFormatSymbols().getEras();

        for (i = 0; i < eras.length; i++) {

            // Displaying the eraString
            System.out.println("EraString " + i
                               + " = " + eras[i]);
        }
    }
}
```

**Output:**

```java
EraString 0 = BC
EraString 1 = AD

```

**例 2:**

```java
// Java code to demonstrate getEras()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {
        int i;

        // Initializing DateFormatSymbols
        String eras[]
            = new DateFormatSymbols().getEras();

        for (i = 0; i < eras.length / 2; i++) {

            // Displaying the eraString
            System.out.println("EraString " + i
                               + " = " + eras[i]);
        }
    }
}
```

**Output:**

```java
EraString 0 = BC

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/text/dateformatsymbols . html # getEras–](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#getEras--)