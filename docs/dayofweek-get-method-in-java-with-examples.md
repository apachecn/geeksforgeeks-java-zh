# Java 中的 DayOfWeek get()方法，示例

> 原文:[https://www . geesforgeks . org/dayofweek-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dayofweek-get-method-in-java-with-examples/)

**java.time.DayOfWeek** 的 **get()** 方法是 java 中的一个内置函数，它以一个**临时字段**为参数，从这个星期几获取指定字段的值作为 int。时间字段是一个日期时间字段，例如一年中的月份或一分钟中的小时。日期和时间用这样的字段表示。如果字段是星期几，则返回星期几的值，从 1 到 7。所有其他时间域实例都将抛出一个 unsupportedtemporaltypexception。int 值遵循 ISO-8601 标准，从 1(星期一)到 7(星期日)。

**方法声明:**

```java
public int get(TemporalField field);
```

**语法:**

```java
int val = DayOfWeekObject.get(TemporalField field);

```

**参数:**该方法以*字段*为参数，其中:

*   *场*–是一个类似于编年史场的时间场。星期几。*   *DayOfWeekObject* – represents the DayOfWeek object.

    **参数:**该方法不接受任何参数。

    **返回值:**函数返回一周中某一天的 int 值，例如，1 代表星期一，2 代表星期二，以此类推。

    以下程序说明了上述方法:
    **程序 1:**

    ```java
    // Java Program Demonstrate get()
    // method of DayOfWeek

    import java.time.*;
    import java.time.DayOfWeek;
    import java.time.temporal.ChronoField;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Set a local date whose day is found
            LocalDate localDate
                = LocalDate.of(1947,
                               Month.AUGUST, 15);

            // Find the day from the local date
            DayOfWeek dayOfWeek
                = DayOfWeek.from(localDate);

            // Printing the day of the week
            // and its Int value
            System.out.println("Day of the Week on "
                               + localDate + " - "
                               + dayOfWeek.name());

            int val
                = dayOfWeek.get(ChronoField.DAY_OF_WEEK);

            System.out.println("Int Value of "
                               + dayOfWeek.name()
                               + " - " + val);
        }
    }
    ```

    **Output:**

    ```java
    Day of the Week on 1947-08-15 - FRIDAY
    Int Value of FRIDAY - 5

    ```

    **程序 2:**

    ```java
    // Java Program Demonstrate get()
    // method of DayOfWeek
    import java.time.*;
    import java.time.DayOfWeek;
    import java.time.temporal.ChronoField;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Set a local date whose day is found
            LocalDate localDate
                = LocalDate.of(2015,
                               Month.JULY, 13);

            // Find the day from the local date
            DayOfWeek dayOfWeek
                = DayOfWeek.from(localDate);

            // Printing the day of the week
            // and its Int value
            System.out.println("Day of the Week on "
                               + localDate + " - "
                               + dayOfWeek.name());

            int val
                = dayOfWeek.get(ChronoField.DAY_OF_WEEK);

            System.out.println("Int Value of "
                               + dayOfWeek.name()
                               + " - " + val);
        }
    }
    ```

    **Output:**

    ```java
    Day of the Week on 2015-07-13 - MONDAY
    Int Value of MONDAY - 1

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html # get-Java . time . temporal field-](https://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html#get-java.time.temporal.TemporalField-)