# Java 中的 DayOfWeek plus()方法，带示例

> 原文:[https://www . geesforgeks . org/dayofweek-plus-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dayofweek-plus-method-in-java-with-examples/)

**java.time.DayOfWeek** 的 **plus()** 方法是 java 中的一个内置函数，它以一个长整数作为参数，并在按照传递的参数所指定的向前或向后前进几天后返回 DayOfWeek 的一个实例。计算从周日到周一在周末进行。指定的时间段可以是正数或负数。

**方法声明:**

```java
public DayOfWeek plus(long days)

```

**语法:**

```java
DayOfWeek dayOfWeekObject = dayOfWeekObject.plus(long days)

```

**参数:**该方法以*天*为参数，其中:

*   *天*–是向前或向后推进的天数。*   *dayOfWeekObject* – is an instance of DayOfWeek object.

    **返回值:**该函数在向前或向后前进几天后返回一个 DayOfWeek 的实例。

    以下程序说明了上述方法:
    **程序 1:**

    ```java
    // Java Program Demonstrate plus()
    // method of DayOfWeek
    import java.time.DayOfWeek;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Getting an instance of DayOfWeek from int value
            DayOfWeek dayOfWeek = DayOfWeek.of(2);

            // Printing the day of the week
            // and its Int value
            System.out.println("Day of the Week : "
                               + dayOfWeek.name()
                               + " - "
                               + dayOfWeek.getValue());

            // Number of days to advance
            long adv = 10;

            // Advancing the day
            dayOfWeek = dayOfWeek.plus(adv);

            // Printing the day of the week and its
            // Int value after adv days
            System.out.println("Day of the Week after "
                               + adv + " days: "
                               + dayOfWeek.name() + " - "
                               + dayOfWeek.getValue());
        }
    }
    ```

    **Output:**

    ```java
    Day of the Week : TUESDAY - 2
    Day of the Week after 10 days: FRIDAY - 5

    ```

    **程序 2:**

    ```java
    // Java Program Demonstrate plus()
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
            dayOfWeek = dayOfWeek.plus(adv);

            // Printing the day of the week and its
            // Int value after adv days
            System.out.println("Day of the Week after "
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
    Day of the Week after -3 days: THURSDAY - 4

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html # plus-long-](https://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html#plus-long-)