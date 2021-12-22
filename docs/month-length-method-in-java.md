# 月长()法在 Java 中

> 原文:[https://www.geeksforgeeks.org/month-length-method-in-java/](https://www.geeksforgeeks.org/month-length-method-in-java/)

**length()** 方法是 Month ENUM 的内置方法，用于获取本月实例中的天数。一个月中的天数可以是 28 天、30 天或 31 天。闰年二月的天数是 29 天。

此方法接受一个布尔标志变量，该变量指示今年是否是闰年。

**语法** :

```java
public int length(boolean leapYear)

```

**参数**:该方法接受单个参数 *leapYear* ，表示今年是否是 leapYear。

**返回值**:该方法返回本月的长度，以天数表示。

下面的程序说明了上述方法:

**程序 1** :

```java
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.MAY;

        // Print the length of this Month
        System.out.println(month.length(false));
    }
}
```

**输出:**

```java
31

```

**程序二** :

```java
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.FEBRUARY;

        // Print the length of this Month
        System.out.println(month.length(true));
    }
}
```

**输出:**

```java
29

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # length-boolean-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#length-boolean-)