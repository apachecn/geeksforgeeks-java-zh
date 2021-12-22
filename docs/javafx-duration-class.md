# JavaFX |持续时间类

> 原文:[https://www.geeksforgeeks.org/javafx-duration-class/](https://www.geeksforgeeks.org/javafx-duration-class/)

Duration 类是 JavaFX 的一部分。持续时间类定义了一段时间。Duration 类是不可变的，所以它被替换而不是修改。创建持续时间类有两种方法:

1.  **使用构造器**
2.  **使用静态构建方法之一，如秒(双倍)或分钟(双倍)**

**类的构造函数:**

*   **持续时间(双倍 m)** :以毫秒为单位创建一个指定持续时间的新持续时间对象。

**常用方法:**

<figure class="table">

| 方法 | 说明 |
| --- | --- |
| 添加(持续时间 d) | 将持续时间 d 添加到持续时间对象 |
| 减去(持续时间 d) | 从持续时间对象中减去持续时间 d |
| 除(持续时间 d) | 将持续时间 d 除以持续时间对象 |
| 乘数(持续时间 d) | 将持续时间 d 乘以持续时间对象 |
| 毫(双倍米) | 以毫秒为单位返回指定持续时间的持续时间对象 |
| 秒(双倍 m) | 以秒为单位返回指定持续时间的持续时间对象 |
| 分钟(双倍 m) | 返回指定持续时间的持续时间对象，以分钟为单位 |
| 小时(双倍 m) | 返回指定持续时间的持续时间对象，以小时为单位 |
| 富礼() | 返回这段时间内的毫秒数 |
| 至秒() | 返回这段时间的秒数 |
| toMinutes() | 返回这段时间的分钟数 |
| toHours() | 返回此期间的小时数 |
| 小于(持续时间 d) | 如果指定的持续时间小于此实例的( |
| 更长时间(持续时间 d) | 如果指定的持续时间大于(>)此实例，则返回 true。 |
| greaterthanorequalto(持续时间) | 如果指定的持续时间大于或等于(> =)此实例，则返回 true。 |
| lesthanorequal(duration d) | 如果指定的持续时间小于或等于(< =)此实例，则返回 true。 |

</figure>

下面的程序说明了 Duration 类的使用:

*   **Java 程序创建两个 Duration 对象，并以毫秒、秒、分、小时为单位显示时间:**该程序创建两个 Duration 对象，命名为 *duration_1* 和 *duration_2* 。毫秒数作为参数传递。调用*显示功能*，并将*持续时间对象*作为参数传递。使用功能*至*、*至*、*至*、*至*将持续时间转换为小时、分钟、秒和毫秒，并显示结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to create two Duration objects and
// display the time in milliseconds seconds,
// minutes and hours
import javafx.util.Duration;
import java.util.*;

class Duration_1 {

    // Main Method
    public static void main(String args[])
    {

        try {

            // duration object
            Duration duration_1 = new Duration(1000000);
            Duration duration_2 = new Duration(100012);

            // display the duration
            System.out.println("Duration 1");
            display(duration_1);
            System.out.println("");
            System.out.println("Duration 2");
            display(duration_2);
        }

        catch (Exception e)
        {
            System.err.println(e.getMessage());
        }
    }

    // display function
    public static void display(Duration duration)
    {

        // display the details of a duration
        System.out.println("Duration in milliseconds: "
                               + duration.toMillis());

        System.out.println("Duration in seconds: "
                          + duration.toSeconds());

        System.out.println("Duration in minutes: "
                         + duration.toMinutes());

        System.out.println("Duration in hours: "
                          + duration.toHours());
    }
}
```

**输出:**

```java
Duration 1
Duration in milliseconds: 1000000.0
Duration in seconds: 1000.0
Duration in minutes: 16.666666666666668
Duration in hours: 0.2777777777777778

Duration 2
Duration in milliseconds: 100012.0
Duration in seconds: 100.012
Duration in minutes: 1.6668666666666667
Duration in hours: 0.02778111111111111
```

*   **Java 程序创建四个 Duration 对象并显示它们并相加两个对象，相乘两个对象，除两个对象并减去两个对象并显示结果:**该程序创建四个 Duration 对象，命名为 *duration_1* 、 *duration_2* 、 *duration_3* 和 *duration_4* 。调用*显示*功能，持续时间对象作为参数传递。使用功能*至*、*至*、*至*、*至*将持续时间转换为小时、分钟、秒和毫秒，并显示结果。将*持续时间 _1* 和*持续时间 _2* 相加和相减，并显示结果对象。类似地， *duration_3* 和 *duration_4* 被除和乘，结果对象被显示。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create four Duration object and
// display them and add two objects, multiply two
// objects, divide two objects and subtract two
// objects and display the results.
import javafx.util.Duration;
import java.util.*;

class Duration_2 {

    // Main Method
    public static void main(String args[])
    {

        try {

            // duration object
            Duration duration_1 = Duration.millis(1000000);
            Duration duration_2 = Duration.seconds(100012);
            Duration duration_3 = Duration.hours(18912);
            Duration duration_4 = Duration.minutes(45634);

            // display the duration
            System.out.println("\nDuration 1\n");
            display(duration_1);
            System.out.println("\nDuration 2\n");
            display(duration_2);
            System.out.println("\nDuration 3\n");
            display(duration_3);
            System.out.println("\nDuration 4\n");
            display(duration_4);

            System.out.println("\nAdd duration 1 and duration 2\n");
            display(duration_1.add(duration_2));

            System.out.println("\nDivide duration 3 and duration 4\n");
            display(duration_3.divide(duration_4));

            System.out.println("\nMultiply duration 3 and duration 4\n");
            display(duration_3.multiply(duration_4));

            System.out.println("\nSubtract duration 1 and duration 2\n");
            display(duration_1.subtract(duration_2));
        }

        catch (Exception e)
        {
            System.err.println(e.getMessage());
        }
    }

    // display method
    public static void display(Duration duration)
    {

        // display the details of a duration
        System.out.println("Duration in milliseconds: "
                               + duration.toMillis());

        System.out.println("Duration in seconds: "
                          + duration.toSeconds());

        System.out.println("Duration in minutes: "
                           + duration.toMinutes());

        System.out.println("Duration in hours: "
                           + duration.toHours());
    }
}
```

**输出:**

```java
Duration 1

Duration in milliseconds: 1000000.0
Duration in seconds: 1000.0
Duration in minutes: 16.666666666666668
Duration in hours: 0.2777777777777778

Duration 2

Duration in milliseconds: 1.00012E8
Duration in seconds: 100012.0
Duration in minutes: 1666.8666666666666
Duration in hours: 27.781111111111112

Duration 3

Duration in milliseconds: 6.80832E10
Duration in seconds: 6.80832E7
Duration in minutes: 1134720.0
Duration in hours: 18912.0

Duration 4

Duration in milliseconds: 2.73804E9
Duration in seconds: 2738040.0
Duration in minutes: 45634.0
Duration in hours: 760.5666666666667

Add duration 1 and duration 2

Duration in milliseconds: 1.01012E8
Duration in seconds: 101012.0
Duration in minutes: 1683.5333333333333
Duration in hours: 28.058888888888887

Divide duration 3 and duration 4

Duration in milliseconds: 24.86567033352325
Duration in seconds: 0.02486567033352325
Duration in minutes: 4.1442783889205417E-4
Duration in hours: 6.907130648200903E-6

Multiply duration 3 and duration 4

Duration in milliseconds: 1.86414524928E20
Duration in seconds: 1.86414524928E17
Duration in minutes: 3.1069087488E15
Duration in hours: 5.178181248E13

Subtract duration 1 and duration 2

Duration in milliseconds: -9.9012E7
Duration in seconds: -99012.0
Duration in minutes: -1650.2
Duration in hours: -27.503333333333334
```

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/util/duration . html](https://docs.oracle.com/javase/8/javafx/api/javafx/util/Duration.html)