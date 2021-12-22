# Java 中的月减()方法

> 原文:[https://www.geeksforgeeks.org/month-minus-method-in-java/](https://www.geeksforgeeks.org/month-minus-method-in-java/)

**减()**方法是一种内置的 Month ENUM 方法，用于以特定的月数获取当前月份之前的一个月。也就是说，此方法返回从这个月开始的指定月数之前的月份。

**语法** :

```
public Month minus(long months)

```

**参数**:该方法接受单个参数*月*，代表月数。

**返回值**:此方法从本月开始返回指定*月数*之前的月份。

下面的程序说明了上述方法:

**程序 1** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.FEBRUARY;

        // Print the month present 1
        // month before feb
        System.out.println(month.minus(1));
    }
}
```

**输出:**

```
JANUARY

```

**程序二** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.APRIL;

        // Print the month present 1
        // month before feb
        System.out.println(month.minus(2));
    }
}
```

**输出:**

```
FEBRUARY

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html #减长-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#minus-long-)