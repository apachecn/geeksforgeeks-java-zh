# Java 中(月)方法的 LocalDateTime，示例

> 原文:[https://www . geesforgeks . org/local datetime-of month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-ofmonth-method-in-java-with-examples/)

1.  **The of(int year, Month month, int dayOfMonth, int hour, int minute)** method of **LocalDateTime** class in Java is used to create an instance of **LocalDateTime** from the input year, month, day of month, hour and minute. The instance of LocalDateTime represents the date along with time. The parameters year, month and day are used to determine the date and the parameters hour and minute are used to determine the time. The second and nano-second will be set to zero by default.

    **语法:**

    ```java
    public static LocalDateTime of(int year,
                                   Month month,
                                   int dayOfMonth,
                                   int hour,
                                   int minute)

    ```

    **参数:**该方法接受 5 个参数。

    *   **年**–整数型，代表年份。它从最小年到最大年不等。
    *   **月**–为月型，代表一年中的月份。从一月到十二月不等。
    *   **dayOfMonth**–整数类型，表示一个月中的某一天。从 1 到 31 不等。
    *   **小时**–整数类型，代表一天中的小时。从 0 到 23 不等。
    *   **分钟**–它是整数类型，代表一小时中的分钟。从 0 到 59 不等。

    **返回值:**该方法返回从输入值导出的**本地日期时间**。

    **异常:**如果任何字段的值超出上述范围或者月中的某一天对于月-年无效，则该方法抛出**日期时间异常**。

    下面的程序说明了 Java 中的(年、月、月、日、小时、分钟)方法:

    **程序 1:**

    ```java
    // Java program to demonstrate
    // LocalDateTime.of(int year, Month month,
    // int dayOfMonth, int hour, int minute) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDateTime object
            LocalDateTime localdatetime
                = LocalDateTime.of(
                    2020, Month.MAY, 13, 6, 30);

            // print full date and time
            System.out.println("DateTime: "
                               + localdatetime);
        }
    }
    ```

    **Output:**

    ```java
    DateTime: 2020-05-13T06:30

    ```

    **程序 2:**

    ```java
    // Java program to demonstrate
    // LocalDateTime.of(int year, Month month,
    // int dayOfMonth, int hour, int minute) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDateTime object
            LocalDateTime localdatetime
                = LocalDateTime.of(
                    2019, Month.MAY,
                    13, 6, 30);

            // print month only
            System.out.println(
                "Month: "
                + localdatetime.getMonth());
        }
    }
    ```

    **Output:**

    ```java
    Month: MAY

    ```

2.  **The of(int year, Month month, int dayOfMonth, int hour, int minute, int second)** method of **LocalDateTime** class in Java is used to create an instance of **LocalDateTime** from the input year, month, day, hour, minute and second. The nanosecond is set to zero by default while creating the instance. In this method, only the month is passed as an instance while the others are integers. This method is used where nanosecond is not required.

    **语法:**

    ```java
    public static LocalDateTime of(int year,
                                   Month month,
                                   int dayOfMonth,
                                   int hour,
                                   int minute,
                                   int second)

    ```

    **参数:**该方法接受六个参数:

    *   **年**–整数型，代表年份。它从最小年到最大年不等。
    *   **月**–为月型，代表一年中的月份。从一月到十二月不等。
    *   **dayOfMonth**–整数类型，表示一个月中的某一天。从 1 到 31 不等。
    *   **小时**–整数类型，代表一天中的小时。从 0 到 23 不等。
    *   **分钟**–它是整数类型，代表一小时中的分钟。从 0 到 59 不等。
    *   **秒**–整数型，表示分钟的秒。从 0 到 59 不等。

    **返回值:**该方法返回**本地日期时间**。

    **异常:**如果任何字段的值超出范围或月日对于月年无效，此方法将抛出**日期时间异常**。

    下面的程序说明了 Java 中的(年、月、月、日、小时、分钟、秒)方法:

    **程序 1:**

    ```java
    // Java program to demonstrate
    // LocalDateTime.of(int year, Month month,
    // int dayOfMonth, int hour, int minute,
    // int second) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDateTime object
            LocalDateTime localdatetime
                = LocalDateTime.of(
                    2020, Month.MAY, 13,
                    6, 30, 45);

            // print full date and time
            System.out.println("DateTime: "
                               + localdatetime);
        }
    }
    ```

    **Output:**

    ```java
    DateTime: 2020-05-13T06:30:45

    ```

    **程序 2:**

    ```java
    // Java program to demonstrate
    // LocalDateTime.of(int year, Month month,
    // int dayOfMonth, int hour, int minute,
    // int second) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDateTime object
            LocalDateTime localdatetime
                = LocalDateTime.of(2019, Month.MAY,
                                   13, 6, 30, 45);

            // print year only
            System.out.println(
                "Year: "
                + localdatetime.getYear());
        }
    }
    ```

    **Output:**

    ```java
    Year: 2019

    ```

3.  **The of(int year, Month month, int dayOfMonth, int hour, int minute, int second, int nanoSecond)** method of **LocalDateTime** class in Java is used to create an instance of **LocalDateTime** from the input year, month, day, hour, minute, second and nanosecond. The instance of LocalDateTime represents the date along with time. The parameters year, month and day are used to obtain the date and parameters hour, minute, second and nanosecond are used to obtain the time.

    **语法:**

    ```java
    public static LocalDateTime of(int year,
                                   Month month,
                                   int dayOfMonth,
                                   int hour,
                                   int minute,
                                   int second,
                                   int nanoOfSecond)

    ```

    **参数:**该方法接受七个参数:

    *   **年**–整数型，代表年份。它从最小年到最大年不等。
    *   **月**–为月型，代表一年中的月份。从一月到十二月不等。
    *   **dayOfMonth**–整数类型，表示一个月中的某一天。从 1 到 31 不等。
    *   **小时**–整数类型，代表一天中的小时。从 0 到 23 不等。
    *   **分钟**–它是整数类型，代表一小时中的分钟。从 0 到 59 不等。
    *   **秒**–整数类型，表示分钟的秒。从 0 到 59 不等。
    *   **毫微秒**–整数型，代表秒的毫微秒。它从 0 到 999999999 不等。

    **返回值:**该方法返回**本地日期时间**。

    **异常:**如果任何字段的值超出范围或月日对于月年无效，此方法将抛出**日期时间异常**。

    下面的程序说明了 Java 中的(年、月、月、日、小时、分钟、秒、秒)方法:

    **程序 1:**

    ```java
    // Java program to demonstrate
    // LocalDateTime.of(int year, Month month,
    // int dayOfMonth, int hour, int minute,
    // int second, int nanoOfSecond) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDateTime object
            LocalDateTime localdatetime
                = LocalDateTime.of(
                    2020, Month.MAY, 13, 6,
                    30, 45, 20000);

            // print full date and time
            System.out.println("DateTime: "
                               + localdatetime);
        }
    }
    ```

    **Output:**

    ```java
    DateTime: 2020-05-13T06:30:45.000020

    ```

    **程序 2:**

    ```java
    // Java program to demonstrate
    // LocalDateTime.of(int year, Month month,
    // int dayOfMonth, int hour, int minute,
    // int second, int nanoOfSecond) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDateTime object
            LocalDateTime localdatetime
                = LocalDateTime.of(
                    2019, Month.DECEMBER, 31, 12,
                    30, 45, 50000);

            // print full date and time
            System.out.println("DateTime: "
                               + localdatetime);
        }
    }
    ```

    **Output:**

    ```java
    DateTime: 2019-12-31T12:30:45.000050

    ```

**参考文献:**

1.  [https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # of(int，java.time.Month，int，int，int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, java.time.Month, int, int, int))
2.  [https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # of(int，java.time.Month，int，int，int，int，int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, java.time.Month, int, int, int, int))
3.  [https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # of(int，java.time.Month，int，int，int，int，int，int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#of(int, java.time.Month, int, int, int, int, int))