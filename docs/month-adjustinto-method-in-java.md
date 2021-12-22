# Java 中的 Month adjustInto()方法

> 原文:[https://www . geesforgeks . org/month-adjustino-method-in-Java/](https://www.geeksforgeeks.org/month-adjustinto-method-in-java/)

java.time.Month ENUM 的 adjustInto()方法是 java 中的一个内置函数，它接受一个指定日期的时态对象，并返回一个与输入相同的可观察类型的新时态对象，其中月份被替换为一年中的这个月份。

**方法声明** :

```java
public Temporal adjustInto(Temporal temporal)

```

**语法** :

```java
Temporal newLocalDate = Month.ANYMONTH.adjustInto(Temporal temporal)

```

**参数**:该方法以时态为参数，其中:

*   **时间**–是需要调整的指定日期。
*   **any MONTH**–是日期要调整到的指定月份，例如，JANUARY、FEDERAL 等。
*   **新日期**–是修改日期。

**返回值**:该函数返回一个调整后的时态对象，该对象是根据指定月份调整的日期。

**异常** :

*   **Date and time exception** : This method throws this exception if adjustment cannot be made.
*   **Arithmetic exception** : If there is a numerical overflow, this exception will be thrown.

下面的程序说明了上述方法:

**程序 1** :

```java
import java.time.*;
import java.time.Month;
import java.time.temporal.Temporal;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Set a Local Date whose month is found
        LocalDate localDate1
            = LocalDate.of(1947, Month.AUGUST, 15);

        // Find the month from the Local Date
        Month monthOfYear1
            = Month.from(localDate1);

        // Printing the Local Date
        System.out.println(localDate1
                           + " which is "
                           + monthOfYear1.name());

        // Adjust the month to JANUARY from AUGUST
        Temporal localDate2
            = Month.JANUARY
                  .adjustInto(localDate1);

        // Find the day from the new Local date
        Month monthOfYear2
            = Month.from(localDate2);

        // Printing the new Local Date
        System.out.println(localDate2
                           + " which is "
                           + monthOfYear2.name());
    }
}
```

**输出:**

```java
1947-08-15 which is AUGUST
1947-01-15 which is JANUARY

```

**程序二** :

```java
import java.time.*;
import java.time.Month;
import java.time.temporal.Temporal;

class DayOfWeekExample {
    public static void main(String[] args)
    {
        // Set a Local Date whose month is found
        LocalDate localDate1
            = LocalDate.of(2019, Month.MARCH, 18);

        // Find the month from the Local Date
        Month monthOfYear1
            = Month.from(localDate1);

        // Printing the Local Date
        System.out.println(localDate1
                           + " which is "
                           + monthOfYear1.name());

        // Adjust the month to December from March
        Temporal localDate2
            = Month.DECEMBER
                  .adjustInto(localDate1);

        // Find the day from the new Local date
        Month monthOfYear2
            = Month.from(localDate2);

        // Printing the new Local Date
        System.out.println(localDate2
                           + " which is "
                           + monthOfYear2.name());
    }
}
```

**输出:**

```java
2019-03-18 which is MARCH
2019-12-18 which is DECEMBER

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # adjustInto-Java . time . temporal-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#adjustInto-java.time.temporal.Temporal-)