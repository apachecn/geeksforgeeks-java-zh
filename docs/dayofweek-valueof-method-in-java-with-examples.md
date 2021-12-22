# Java 中 DayOfWeek valueOf()方法，示例

> 原文:[https://www . geesforgeks . org/dayofweek-value of-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dayofweek-valueof-method-in-java-with-examples/)

**java . time . DayOfWeek**的 **valueOf()** 方法是 Java 中的一个内置函数，它接受一个字符串并返回与该字符串对应的 day fweek 的一个实例。该字符串必须与用于在此类型中声明星期几常量的标识符完全匹配。不允许出现多余的空白字符。

**方法声明:**

```java
 public static DayOfWeek valueOf(String name)

```

**语法:**

```java
 DayOfWeek dayOfWeekObject = DayOfWeek.valueOf(String name)

```

**参数:**该方法以*名称*为参数，其中:

*   *名称*–是一周中某一天的名称。*   *dayOfWeekObject* – is an instance of DayOfWeek.

    **返回值:**该函数返回一个对应于*名称*字符串的 DayOfWeek 实例

    以下程序说明了上述方法:
    **程序 1:**

    ```java
    // Java Program Demonstrate valueOf()
    // method of DayOfWeek

    import java.time.*;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Initializing a DayOfWeek instance
            DayOfWeek dayOfWeek
                = DayOfWeek.valueOf("MONDAY");

            // Printing the day-of-week
            System.out.println(dayOfWeek.name());
        }
    }
    ```

    **Output:**

    ```java
    MONDAY

    ```

    **程序 2:**

    ```java
    // Java Program Demonstrate valueOf()
    // method of DayOfWeek

    import java.time.*;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Initializing a DayOfWeek instance
            DayOfWeek dayOfWeek
                = DayOfWeek.valueOf("SATURDAY");

            // Printing the day-of-week
            System.out.println(dayOfWeek.name());
        }
    }
    ```

    **Output:**

    ```java
    SATURDAY

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html # value of-Java . lang . string-](https://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html#valueOf-java.lang.String-)