# Java 中的 Month minLength()方法

> 原文:[https://www . geesforgeks . org/month-min length-method-in-Java/](https://www.geeksforgeeks.org/month-minlength-method-in-java/)

**minLength()** 方法是一种内置的 Month ENUM 方法，用于获取本月以天数表示的最小长度。例如，根据今年是否是闰年，2 月既可以有 28 天，也可以有 29 天。因此，该方法将返回 2 月的 28，因为 2 月的最小天数是 29 天。

**语法** :

```
public int minLength()

```

**参数**:该方法不接受任何参数。

**返回值**:该方法返回本月的最小长度，以天数表示。

下面的程序说明了上述方法:

**程序 1** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.FEBRUARY;

        // Print the minimum length of this Month
        System.out.println(month.minLength());
    }
}
```

**输出:**

```
28

```

**程序二** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.MAY;

        // Print the min length of this Month
        System.out.println(month.minLength());
    }
}
```

**输出:**

```
31

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # minLength–](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#minLength--)