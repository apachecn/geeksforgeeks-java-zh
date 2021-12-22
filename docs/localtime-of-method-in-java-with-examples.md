# Java 中()方法的 LocalTime，示例

> 原文:[https://www . geesforgeks . org/local time-of-in-Java-method-in-examples/](https://www.geeksforgeeks.org/localtime-of-method-in-java-with-examples/)

1.  The **of(int hour, int minute)** method of the **LocalTime** class in Java is used to create an instance of **LocalTime** from the passed values of hour and minute. In this method, the hour and minute are passed in the Integer format and it returns time-based on these values. The values of second and nanosecond are set to zero by default in this method.

    **语法:**

    ```java
    public static LocalTime of(int hour,
                               int minute)

    ```

    **参数:**该方法接受两个参数:

    *   **小时**–整数类型，代表一天中的小时。从 0 到 23 不等。
    *   **分钟**–它是整数类型，代表一小时中的分钟。从 0 到 59 不等。

    **返回值:**该方法返回**本地时间**。

    **异常:**如果小时或分钟的任何参数值超出范围，该方法将抛出**日期时间异常**。

    下面的程序说明了 Java 中 LocalTime 的(小时，分钟)方法:

    **程序:**

    ```java
    // Java program to demonstrate
    // LocalTime of(int hour,
    // int minute) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // Create LocalTime object
            LocalTime localtime
                = LocalTime.of(6, 5);

            // Print time
            System.out.println("TIME: "
                               + localtime);
        }
    }
    ```

    **Output:**

    ```java
    TIME: 06:05

    ```

2.  The **of(int hour, int minute, int second)** method of the **LocalTime** class in Java is used to create an instance of **LocalTime** from the passed values of hour, minute and second. In this method, the values of the hour, minute and second are passed in an Integer format and it returns the time on the basis of the passed values. The value of the nanosecond is set to zero by default in this method.

    **语法:**

    ```java
    public static LocalTime of(int hour,
                               int minute,
                               int second)

    ```

    **参数:**该方法接受三个参数:

    *   **小时**–整数类型，代表一天中的小时。从 0 到 23 不等。
    *   **分钟**–它是整数类型，代表一小时中的分钟。从 0 到 59 不等。
    *   **秒**–整数类型，表示分钟的秒。从 0 到 59 不等。

    **返回值:**该方法返回**本地时间**。

    **异常:**如果有参数超出范围，该方法抛出**日期时间异常**。

    下面的程序说明了 Java 中 LocalTime 的(小时、分钟、秒)方法:

    **程序:**

    ```java
    // Java program to demonstrate
    // LocalTime of(int hour, int minute, int second) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // Create LocalTime object
            LocalTime localtime
                = LocalTime.of(6, 5, 40);

            // Print time
            System.out.println("TIME: "
                               + localtime);
        }
    }
    ```

    **Output:**

    ```java
    TIME: 06:05:40

    ```

3.  The **of(int hour, int minute, int second, int nanosecond)** method of the **LocalTime** class in Java is used to create an instance of **LocalTime** from given values (passed values) of hour, minute, second and nanosecond. In this method, the values of the hour, minute, second and nanosecond os passed in an Integer form and it returns time on the basis of these values. No parameter value is set to zero in this method.

    **语法:**

    ```java
    public static LocalTime of(int hour,
                               int minute,
                               int second,
                               int nanosecond)

    ```

    **参数:**该方法接受四个参数:

    *   **小时**–整数类型，代表一天中的小时。从 0 到 23 不等。
    *   **分钟**–它是整数类型，代表一小时中的分钟。从 0 到 59 不等。
    *   **秒**–整数类型，表示分钟的秒。从 0 到 59 不等。
    *   **纳秒**–整数型，代表秒的纳米。它从 0 到 999999999 不等。

    **返回值:**该方法返回**本地时间**。

    **异常:**如果小时、分钟、秒或纳秒的任何参数值超出范围，该方法将抛出**日期时间异常**。

    下面的程序说明了 Java 中 LocalTime 的(小时、分钟、秒、纳秒)方法:

    **程序:**

    ```java
    // Java program to demonstrate
    // LocalTime of(int hour, int minute,
    // int second, int nanosecond) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // Create LocalTime object
            LocalTime localtime
                = LocalTime.of(
                    6, 5, 40, 50);

            // Print time
            System.out.println("TIME: "
                               + localtime);
        }
    }
    ```

    **Output:**

    ```java
    TIME: 06:05:40.000000050

    ```

**参考文献:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # of(int，int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#of(int, int))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # of(int，int，int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#of(int, int, int))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # of(int，int，int，int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#of(int, int, int, int))