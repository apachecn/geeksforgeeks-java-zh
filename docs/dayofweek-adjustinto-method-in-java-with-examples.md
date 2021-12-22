# DayOfWeek Java 中的 adjustInto()方法，带示例

> 原文:[https://www . geeksforgeeks . org/dayofweek-adjustin to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dayofweek-adjustinto-method-in-java-with-examples/)

**java.time.DayOfWeek** 的 **adjustInto()** 方法是 java 中的一个内置函数，它接受一个指定日期的时态对象，并返回一个与输入相同的可观察类型的新时态对象，其中星期几被更改为与指定的 DayOfWeek 常量相同。请注意，此方法在周一到周日的一周内向前或向后调整。

**方法声明:**

```java
 public Temporal adjustInto(Temporal temporal)

```

**语法:**

```java
 Temporal newLocalDate = DayOfWeek.ANYWEEKDAY.adjustInto(Temporal temporal)

```

**参数:**该方法以*时态*为参数，其中:

*   *时态–*是需要调整的指定日期。*   *any weekday–*是日期要调整到的指定日期，例如，星期一、星期二等。*   *newLocalDate –* is the modified date.

    **返回值:**该函数返回一个调整后的时态对象，该对象是根据指定的星期几调整的日期。

    以下程序说明了上述方法:
    **程序 1:**

    ```java
    import java.time.*;
    import java.time.DayOfWeek;
    import java.time.temporal.Temporal;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Set a Local Date whose day is found
            LocalDate localDate1
                = LocalDate.of(1947, Month.AUGUST, 15);

            // Find the day from the Local Date
            DayOfWeek dayOfWeek1
                = DayOfWeek.from(localDate1);

            // Printing the Local Date
            System.out.println(localDate1
                               + " which is "
                               + dayOfWeek1.name());

            // Adjust the Date to Monday from Friday
            Temporal localDate2
                = DayOfWeek.MONDAY
                      .adjustInto(localDate1);

            // Find the day from the new Local date
            DayOfWeek dayOfWeek2
                = DayOfWeek.from(localDate2);

            // Printing the new Local Date
            System.out.println(localDate2
                               + " which is "
                               + dayOfWeek2.name());
        }
    }
    ```

    **Output:**

    ```java
    1947-08-15 which is FRIDAY
    1947-08-11 which is MONDAY

    ```

    **程序 2:**

    ```java
    import java.time.*;
    import java.time.DayOfWeek;
    import java.time.temporal.Temporal;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Set a Local Date whose day is found
            LocalDate localDate1
                = LocalDate.of(2019, Month.MARCH, 18);

            // Find the day from the Local Date
            DayOfWeek dayOfWeek1
                = DayOfWeek.from(localDate1);

            // Printing the Local Date
            System.out.println(localDate1
                               + " which is "
                               + dayOfWeek1.name());

            // Adjust the Date to Wednesday from Monday
            Temporal localDate2
                = DayOfWeek.WEDNESDAY
                      .adjustInto(localDate1);

            // Find the day from the new Local date
            DayOfWeek dayOfWeek2
                = DayOfWeek.from(localDate2);

            // Printing the new Local Date
            System.out.println(localDate2
                               + " which is "
                               + dayOfWeek2.name());
        }
    }
    ```

    **Output:**

    ```java
    2019-03-18 which is MONDAY
    2019-03-20 which is WEDNESDAY

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html # adjustInto-Java . time . temporal-](https://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html#adjustInto-java.time.temporal.Temporal-)