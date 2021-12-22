# Java 中()方法的 LocalDate，示例

> 原文:[https://www . geesforgeks . org/local date-of-in-Java-method-in-examples/](https://www.geeksforgeeks.org/localdate-of-method-in-java-with-examples/)

1.  **The of(int, int, int)** method of **LocalDate** class in Java is used to create an instance of **LocalDate** from the input year, month and day of the month. In this method, all the three parameters are passed in the form of integer.

    **语法:**

    ```java
    public static LocalDate of(int year,
                               int month,
                               int dayOfMonth)

    ```

    **参数:**该方法接受三个参数:

    *   **年**–整数型，代表年份。它从最小年到最大年不等。
    *   **月**–整数型，代表一年中的月份。从 1 月 1 日到 12 月 12 日不等。
    *   **dayOfMonth**–整数类型，表示一个月中的某一天。从 1 到 31 不等。

    **返回值:**此方法返回**本地日期**。

    **异常:**如果任何字段值超出范围，或者如果月日对于月年无效，则此方法抛出**日期时间异常**。

    下面的程序说明了 Java 中的(int month)方法:
    **程序 1:**

    ```java
    // Java program to demonstrate
    // LocalDate.of(int month) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDate object
            LocalDate localdate
                = LocalDate.of(2020, 5, 13);

            // print full date
            System.out.println("Date: " + localdate);
        }
    }
    ```

    **Output:**

    ```java
    Date: 2020-05-13

    ```

    **程序 2:**

    ```java
    // Java program to demonstrate
    // LocalDate.of(int month) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDate object
            LocalDate localdate
                = LocalDate.of(2020, 5, 13);

            // print year only
            System.out.println("Year: "
                               + localdate.getYear());
        }
    }
    ```

    **Output:**

    ```java
    Year: 2020

    ```

2.  **The of(int, Month, int)** method of **LocalDate** class in Java is used to obtain an instance of **LocalDate** from the input year, month and day. In this method, the parameters year and day are passed as integers but the month is passes as an instance.

    **语法:**

    ```java
    public static LocalDate of(int year,
                               Month month,
                               int dayOfMonth)

    ```

    **参数:**该方法接受三个参数。

    *   **年**–整数型，代表年份。它从最小年到最大年不等。
    *   **月**–为月型，代表一年中的月份。从一月到十二月不等。
    *   **dayOfMonth**–整数类型，表示一个月中的某一天。从 1 到 31 不等。

    **返回值:**此方法返回**本地日期**。

    **异常:**如果任何字段值超出范围或月中的某一天对于月-年无效，此方法将抛出**日期时间异常**。

    下面的程序说明了 Java 中的月方法:
    **程序 1:**

    ```java
    // Java program to demonstrate
    // LocalDate.of(Month month) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDate object
            LocalDate localdate = LocalDate.of(
                2020, Month.MAY, 13);

            // print full date
            System.out.println("Date: "
                               + localdate);
        }
    }
    ```

    **Output:**

    ```java
    Date: 2020-05-13

    ```

    **程序 2:**

    ```java
    // Java program to demonstrate
    // LocalDate.of(Month month) method

    import java.time.*;
    import java.time.temporal.*;

    public class GFG {
        public static void main(String[] args)
        {
            // create LocalDate object
            LocalDate localdate = LocalDate.of(
                2020, Month.MAY, 13);

            // print month only
            System.out.println("Month: "
                               + localdate.getMonth());
        }
    }
    ```

    **Output:**

    ```java
    Month: MAY

    ```

**参考文献:**

1.  [https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # of(int，int，int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#of(int, int, int))
2.  [https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # of(int，java.time.Month，int)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#of(int, java.time.Month, int))