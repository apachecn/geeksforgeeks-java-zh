# Java 中()方法的月份

> 原文:[https://www.geeksforgeeks.org/month-of-method-in-java/](https://www.geeksforgeeks.org/month-of-method-in-java/)

()的**方法是一个内置的 Month ENUM 方法，用于从整数值生成 Month 实例。整数值应该在 1-12 的范围内，表示 12 个月中的任何一个月，并且该方法根据它生成一个 Month 实例，表示一年中的某个月。**

****语法** :**

```java
public static Month of(int month) 
```

****参数**:该方法接受单个参数*月*，为整数型。**

****返回值**:该方法返回使用传递的参数生成的对应的月实例。**

****异常**:如果传递给参数的月份无效，该方法抛出*日期时间异常*。**

**下面的程序说明了上述方法:**

****程序 1** :**

```java
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.of(2);

        // Print the month Instance
        System.out.println(month);
    }
}
```

****输出:**

```java
FEBRUARY

```

**程序二** :

```java
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.of(12);

        // Print the month Instance
        System.out.println(month);
    }
}
```

**输出:**

```java
DECEMBER

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # of-int-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#of-int-)**