# Java 中 DayOfWeek from()方法，带示例

> 原文:[https://www . geesforgeks . org/dayofweek-from-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dayofweek-from-method-in-java-with-examples/)

**java.time.DayOfWeek** 的 **from()** 方法是 java 中的一个内置函数，它接受一个定义日期的临时处理器，并返回与该日期对应的 DayOfWeek 实例。临时处理器表示一组任意的日期和时间信息，该方法将其转换为与该日期相对应的 DayOfWeek 实例。

**方法声明:**

```java
 public static DayOfWeek from(TemporalAccessor temporal)

```

**语法:**

```java
 DayOfWeek dayOfWeekObject = DayOfWeek.from(TemporalAccessor temporal)

```

**参数:**该方法以*时态*为参数，其中:

*   *时态–*是表示日期的时态处理器。*   *dayOfWeekObject –* is an instance of DayOfWeek.

    **返回值:**该函数返回与*时间*指定的日期对应的 DayOfWeek 实例

    以下程序说明了上述方法:
    **程序 1:**

    ```java
    // Java Program Demonstrate from()
    // method of DayOfWeek

    import java.time.*;
    import java.time.DayOfWeek;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Set a local date whose day is found
            LocalDate localDate
                = LocalDate.of(1997, Month.AUGUST, 15);

            // Initialize a DayOfWeek object
            // with specified local Date
            DayOfWeek dayOfWeek
                = DayOfWeek.from(localDate);

            // Printing the day of the week
            System.out.println("Day of the Week on "
                               + localDate + " - "
                               + dayOfWeek.name());
        }
    }
    ```

    **Output:**

    ```java
    Day of the Week on 1997-08-15 - FRIDAY

    ```

    **程序 2:**

    ```java
    // Java Program Demonstrate from()
    // method of DayOfWeek

    import java.time.*;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Set a local date whose day is found
            LocalDate localDate
                = LocalDate.of(2015, Month.JULY, 13);

            // Initialize a DayOfWeek object
            // with specified local Date
            DayOfWeek dayOfWeek
                = DayOfWeek.from(localDate);

            // Printing the day of the week
            System.out.println("Day of the Week on "
                               + localDate + " - "
                               + dayOfWeek.name());
        }
    }
    ```

    **Output:**

    ```java
    Day of the Week on 2015-07-13 - MONDAY

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html # from-Java . time . temporal accessor-](https://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html#from-java.time.temporal.TemporalAccessor-)