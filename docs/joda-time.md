# 【fuck-time】

> 原文:[https://www.geeksforgeeks.org/joda-time/](https://www.geeksforgeeks.org/joda-time/)

Joda-Time 是由*joda.org*创建的一个 API，它提供了比 java.util 包中的类(如 Calendar、Gregorian Calendar、date 等)更好的类，并且有更有效的方法来处理日期和时间。这个应用编程接口包含在 Java 8.0 的 java.time 包中。

**要包含我们需要导入的内容:**

```
import java.time.*;
```

**JODA 时间的基本特征**

*   它使用简单的字段访问器，如 *getYear()，getDayOfWeek()，getDayofYear()。*
*   它支持 7 种日历系统，如佛教、科普特语、埃塞俄比亚语、公历、公历、伊斯兰教、儒略历。
*   有一个条款来创建我们自己的日历系统。
*   它提供了一套丰富的日期和时间计算方法。
*   它使用时区数据库。这个数据库在一年中手动更新了几次。
*   与 java 7.0 的早期方法相比，它的方法执行得更快；因此，提供了更好的性能
*   它的对象是不可变的。所以，它们是线程安全的

**Java . time 包中的重要类。**

1.  **DateTime :** Immutable replacement for JDK Calendar.

    ```
        DateTime dt = new DateTime(); 
    ```

    //它创建一个 datetime 对象，表示由系统时钟确定的当前日期和时间(以毫秒为单位)。它是使用默认时区的国际标准化组织日历构建的。

2.  **LocalDate :** 这个类以年-月-日的形式表示日期，用于表示没有时间和时区的日期。

    ```
    LocalDate today = LocalDate.now()
    //gives System date into LocalDate object using now method.

    System.out.println(today) 
    // 2018-08-03
    int d = today.getDayOfMonth(); 
    // 03

    ```

3.  **LocalTime :** 这个类代表一天中没有时区的时间。

    ```
    LocalTime time = LocalTime.now(); //gives System time into localTime object
    System.out.println(time); // 10:19:58

    ```

4.  **LocalDateTime :** This class handles both date and time without considering the time zone.

    ```
    // get current date and time
    LocalDateTime dt = LocalTime.now(); 
    System.out.println("%s", dt);

    ```

    **设置环境**

    1.  在 eclipse 中创建您的 java 项目。
    2.  下载最新的 JodaTime .tar.gz 文件[点击这里](http://www.joda.org/joda-time/installation.html)，提取其内容。
    3.  在 Eclipse 中，在包资源管理器中查找您的项目，右键单击它，然后将其称为新建->文件夹-> libs
    4.  将 joda-time-2.1.jar 复制/拖动到新创建的 libs 文件夹中。
    5.  再次右键单击您的项目(在包资源管理器中)，然后选择属性-> Java 构建路径->库->添加 jar-> joda-time-2.1 . jar
    6.  现在你可以用这个代码进行测试:

        ```
        DateTime test = new DateTime();
        ```

    **基本示例**

    ```
    // Java program to illustrate
    // functions of JODA time
    import org.joda.time.DateTime;
    import org.joda.time.LocalDateTime;
    public class JodaTime {
        public static void main(String[] args)
        {
            DateTime now = new DateTime();
            System.out.println("Current Day: " + now.dayOfWeek().getAsText());
            System.out.println("Current Month: " + now.monthOfYear().getAsText());
            System.out.println("Current Year: " + now.year().getAsText());
            System.out.println("Current Year is Leap Year: " + now.year().isLeap());

            // get current date and time
            LocalDateTime dt = LocalDateTime.now();

            System.out.println(dt);
        }
    }
    ```

    **输出**

    ```
    Current Day: Monday
    Current Month: August
    Current Year: 2018
    Current Year is Leap Year: false
    2018-08-06T13:12:16.672

    ```

    **优势:**

    *   跨多个 Java 平台的类似用法。
    *   支持其他日历，如佛教和埃塞俄比亚文日历。
    *   自报表现更好。
    *   简单的互操作性:库内部使用毫秒级的瞬间，这与 JDK 相同，也与其他常见的时间表示相似。这使得互操作性变得容易，Joda-Time 提供了现成的 JDK 互操作性。

    **缺点:**

    *   需要安装软件包，也许从 Joda.org 更新。

    **参考资料**
    [包组织层级时间](http://joda-time.sourceforge.net/apidocs/org/joda/time/package-tree.html)
    [http://www.joda.org/joda-time/](http://www.joda.org/joda-time/)
    [http://www.joda.org/joda-time/quickstart.html](http://www.joda.org/joda-time/quickstart.html)