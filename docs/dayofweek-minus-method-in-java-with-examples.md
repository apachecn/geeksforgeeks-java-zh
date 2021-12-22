# Java 中的 DayOfWeek 减()方法，带示例

> 原文:[https://www . geeksforgeeks . org/dayofweek-减去 java 中的方法-示例/](https://www.geeksforgeeks.org/dayofweek-minus-method-in-java-with-examples/)

**java.time.DayOfWeek** 的**减()**方法是 java 中的一个内置函数，它以一个长整数作为参数，并按照传递的参数所指定的向后或向前推进几天后返回 DayOfWeek 的一个实例。计算从周一到周日在周末进行。指定的时间段可以是正数或负数。

**方法声明:**

```java
public DayOfWeek minus(long days)
```

**语法:**

```java
DayOfWeek dayOfWeekObject = dayOfWeekObject.minus(long days)

```

**参数:**该方法以*天*为参数，其中:

*   *天*–是向前或向后推进的天数。*   *dayOfWeekObject* – is an instance of DayOfWeek object.

    **返回值:**该函数在向后或向前前进几天后返回一个 DayOfWeek 的实例。

    以下程序说明了上述方法:
    **程序 1:**

    ```java
    // Java Program Demonstrate minus()
    // method of DayOfWeek
    import java.time.DayOfWeek;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Getting an instance of DayOfWeek from int value
            DayOfWeek dayOfWeek = DayOfWeek.of(2);

            // Printing the day of the week and its Int value
            System.out.println("Day of the Week : "
                               + dayOfWeek.name() + " - "
                               + dayOfWeek.getValue());

            // Number of days to advance
            long adv = 10;

            // Advancing the day
            dayOfWeek = dayOfWeek.minus(adv);

            // Printing the day of the week and its
            // Int value before adv days
            System.out.println("Day of the Week before "
                               + adv + " days: "
                               + dayOfWeek.name() + " - "
                               + dayOfWeek.getValue());
        }
    }
    ```

    **Output:**

    ```java
    Day of the Week : TUESDAY - 2
    Day of the Week before 10 days: SATURDAY - 6

    ```

    **程序 2:**

    ```java
    // Java Program Demonstrate minus()
    // method of DayOfWeek
    import java.time.DayOfWeek;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Getting an instance of DayOfWeek
            // from int value
            DayOfWeek dayOfWeek = DayOfWeek.of(7);

            // Printing the day of the week
            // and its Int value
            System.out.println("Day of the Week : "
                               + dayOfWeek.name()
                               + " - "
                               + dayOfWeek.getValue());

            // Number of days to advance
            long adv = -3;

            // Advancing the day
            dayOfWeek = dayOfWeek.minus(adv);

            // Printing the day of the week and its
            // Int value before adv days
            System.out.println("Day of the Week before "
                               + adv + " days: "
                               + dayOfWeek.name()
                               + " - "
                               + dayOfWeek.getValue());
        }
    }
    ```

    **Output:**

    ```java
    Day of the Week : SUNDAY - 7
    Day of the Week before -3 days: WEDNESDAY - 3

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html #减长-](https://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html#minus-long-)