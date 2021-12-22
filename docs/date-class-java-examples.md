# Java 中的日期类(带示例)

> 原文:[https://www.geeksforgeeks.org/date-class-java-examples/](https://www.geeksforgeeks.org/date-class-java-examples/)

日期类表示特定的时间瞬间，精度为毫秒。java.util 包的 Date 类实现了可序列化、可克隆和可比较的接口。它提供了用 java 处理日期和时间的构造函数和方法。

**施工人员**

*   **Date()** :创建表示当前日期和时间的日期对象。
*   **日期(长毫秒)**:从 1970 年 1 月 1 日 00:00:00 GMT 开始，为给定的毫秒创建日期对象。
*   **日期(年内、月内、日内)**
*   **日期(整年、整月、整日、整小时、整分钟)**
*   **日期(整年、整月、整日、整小时、整分钟、整秒)**
*   **Date(String s)**

    **注意:**日期类的最后 4 个构造函数被弃用。

    ```
    // Java program to demonstrate constuctors of Date
    import java.util.*;

    public class Main
    {
        public static void main(String[] args)
        {
            Date d1 = new Date();
            System.out.println("Current date is " + d1);
            Date d2 = new Date(2323223232L);
            System.out.println("Date represented is "+ d2 );
        }
    }
    ```

    输出:

    ```
    Current date is Tue Jul 12 18:35:37 IST 2016
    Date represented is Wed Jan 28 02:50:23 IST 1970

    ```

    **重要方法**

    *   **布尔值在(日期日期)之后:**测试当前日期是否在给定日期之后。
    *   **布尔值在(日期日期)之前:**测试当前日期是否在给定日期之前。
    *   **内部比较(日期日期):**将当前日期与给定日期进行比较。如果参数“日期”等于“日期”，则返回 0；如果日期在日期参数之前，则值小于 0；如果日期在日期参数之后，则为大于 0 的值。
    *   **long getTime()** :返回自 1970 年 1 月 1 日 00:00:00 GMT 以来该 Date 对象表示的毫秒数。
    *   **void setTime(长时间)**:将当前日期和时间更改为给定时间。

    ```
    // Program to demonstrate methods of Date class
    import java.util.*;

    public class Main
    {
        public static void main(String[] args)
        {
            // Creating date
            Date d1 = new Date(2000, 11, 21);
            Date d2 = new Date();  // Current date
            Date d3 = new Date(2010, 1, 3);

            boolean a = d3.after(d1);
            System.out.println("Date d3 comes after " +
                               "date d2: " + a);

            boolean b = d3.before(d2);
            System.out.println("Date d3 comes before "+
                               "date d2: " + b);

            int c = d1.compareTo(d2);
            System.out.println(c);

            System.out.println("Miliseconds from Jan 1 "+
                    "1970 to date d1 is " + d1.getTime());

            System.out.println("Before setting "+d2);
            d2.setTime(204587433443L);
            System.out.println("After setting "+d2);
        }
    }
    ```

    输出:

    ```
    Date d3 comes after date d2: true
    Date d3 comes before date d2: false
    1
    Miliseconds from Jan 1 1970 to date d1 is 60935500800000
    Before setting Tue Jul 12 13:13:16 UTC 2016
    After setting Fri Jun 25 21:50:33 UTC 1976

    ```

    本文由**拉胡尔·阿格沃尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。