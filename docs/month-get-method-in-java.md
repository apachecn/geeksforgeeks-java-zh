# Java 中的月 get()方法

> 原文:[https://www.geeksforgeeks.org/month-get-method-in-java/](https://www.geeksforgeeks.org/month-get-method-in-java/)

**get()** 方法是一个内置的 Month ENUM 方法，用于获取该 Month 实例指定的年月值的对应整数值。

**语法** :

```java
public int get(TemporalField field)

```

**参数**:该方法接受单个参数，该参数为时态对象，不能为空。

**返回值**:该方法返回与本月实例指定的字段对应的整数。

**异常**:方法抛出以下异常。

*   **Date and time exception** : If the value is outside the valid value range, *Date and time exception* will be thrown.
*   **Arithmetic exception** : When any numerical value overflows, a *arithmetic exception* will be thrown.

下面的程序说明了上述方法:

**程序 1** :

```java
import java.time.*;
import java.time.Month;
import java.time.*;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.MARCH;

        // Get corresponding Integer
        System.out.println(month.get(ChronoField.MONTH_OF_YEAR));
    }
}
```

**输出:**

```java
3

```

**程序二** :

```java
import java.time.*;
import java.time.Month;
import java.time.*;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.NOVEMBER;

        // Get corresponding Integer
        System.out.println(month.get(ChronoField.MONTH_OF_YEAR));
    }
}
```

**输出:**

```java
11

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # get-Java . time . temporal field-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#get-java.time.temporal.TemporalField-)