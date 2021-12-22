# Java 中的 DayOfWeek getDisplayName()方法，带示例

> 原文:[https://www . geesforgeks . org/dayofweek-getdisplayname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dayofweek-getdisplayname-method-in-java-with-examples/)

**java.time.DayOfWeek** 的 **getDisplayName()** 方法是 java 中的内置函数，它根据指定的 Locale 类参数和 TextStyle 返回一周中某一天的文本表示。TextStyle 定义了三个元素“FULL”、“SHORT”和“窄带”。Locale 类表示世界上的一种特定语言和地区。

**方法声明:**

```java
 public String getDisplayName(TextStyle style, Locale locale)

```

**语法:**

```java
 String text = dayOfWeekObject.getDisplayName(TextStyle style, Locale locale)

```

**参数:**该方法取两个参数:

*   *样式*–是 TestStyle，可以是“FULL”、“SHORT”和“窄带”三个元素。*   *地区*–代表世界上特定的语言和地区。默认区域设置是美国*   *dayOfWeekObject* – is an instance of DayOfWeek.

    **返回值:**函数返回根据指定的 Locale 类参数和 TextStyle 返回星期几的文本表示。

    以下程序说明了上述方法:
    **程序 1:**

    ```java
    // Java Program Demonstrate getDisplayName()
    // method of DayOfWeek

    import java.time.*;
    import java.time.format.TextStyle;
    import java.util.Locale;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Initializing a DayOfWeek instance
            DayOfWeek dayOfWeek = DayOfWeek.MONDAY;

            // Get textual representation of the
            // day-of-week in FULL style
            String full_name
                = dayOfWeek
                      .getDisplayName(TextStyle.FULL,
                                      Locale.getDefault());

            // Get textual representation of the
            // day-of-week in SHORT style
            String short_name
                = dayOfWeek
                      .getDisplayName(TextStyle.SHORT,
                                      Locale.getDefault());

            // Get textual representation of the
            // day-of-week in NARROW style
            String narrow_name
                = dayOfWeek
                      .getDisplayName(TextStyle.NARROW,
                                      Locale.getDefault());

            // Printing the textual names of the day-of-week
            System.out.println(full_name);

            System.out.println(short_name);

            System.out.println(narrow_name);
        }
    }
    ```

    **Output:**

    ```java
    Monday
    Mon
    M

    ```

    **程序 2:**

    ```java
    // Java Program Demonstrate getDisplayName()
    // method of DayOfWeek

    import java.time.*;
    import java.time.DayOfWeek;
    import java.time.format.TextStyle;
    import java.util.Locale;

    class DayOfWeekExample {
        public static void main(String[] args)
        {
            // Initializing a DayOfWeek instance
            DayOfWeek dayOfWeek = DayOfWeek.WEDNESDAY;

            // Get textual representation of the
            // day-of-week in FULL style
            String full_name
                = dayOfWeek
                      .getDisplayName(TextStyle.FULL,
                                      Locale.getDefault());

            // Get textual representation of the
            // day-of-week in SHORT style
            String short_name
                = dayOfWeek
                      .getDisplayName(TextStyle.SHORT,
                                      Locale.getDefault());

            // Get textual representation of the
            // day-of-week in NARROW style
            String narrow_name
                = dayOfWeek
                      .getDisplayName(TextStyle.NARROW,
                                      Locale.getDefault());

            // Printing the textual names of the day-of-week
            System.out.println(full_name);

            System.out.println(short_name);

            System.out.println(narrow_name);
        }
    }
    ```

    **Output:**

    ```java
    Wednesday
    Wed
    W

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/dayofweek . html # getDisplayName-Java . time . format . textstyle-Java . util . locale-](https://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html#getDisplayName-java.time.format.TextStyle-java.util.Locale-)