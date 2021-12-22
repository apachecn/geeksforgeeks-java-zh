# 将日期转换为 Java 中的 XMLGregorianCalendar

> 原文:[https://www . geesforgeks . org/convert-date-to-xmlgregoriancalendar-in-Java/](https://www.geeksforgeeks.org/convert-date-to-xmlgregoriancalendar-in-java/)

XML 公历:在 XML *模式*标准中定义了以 XML 格式指定日期的规则。Java 1.5 中引入的 Java XMLGregorianCalendar 类是 W3C XML Schema 1.0 日期/时间数据类型的表示，需要使用 XML 格式。

在这种方法中，我们首先将标准日期更改为公历日期格式，然后使用 DatatypeFactory()将其更改为 XML 公历日期。新实例方法，创建新的对象，将 xml 映射到 Java 对象或从 Java 对象映射。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Convert Date to XMLGregorianCalendar

// importing necessary packages
import java.util.Date;
import java.util.GregorianCalendar;
import javax.xml.datatype.DatatypeFactory;
import javax.xml.datatype.XMLGregorianCalendar;

public class DateToXMLGregorianCalendar {

    public static void main(String[] args)
    {

        // Create Date Object
        Date current_date = new Date();

        // current date time in standard format
        System.out.println("Standard Format :- "
                           + current_date);

        XMLGregorianCalendar xmlDate = null;

        // Gregorian Calendar object creation
        GregorianCalendar gc = new GregorianCalendar();

        // giving current date and time to gc
        gc.setTime(current_date);

        try {
            xmlDate = DatatypeFactory.newInstance()
                          .newXMLGregorianCalendar(gc);
        }
        catch (Exception e) {
            e.printStackTrace();
        }

        // current date time in XMLGregorain Calendar format
        System.out.println("XMLGregorianCalendar Format :- "
                           + xmlDate);
    }
}
```

**Output**

```java
Standard Format :- Tue Feb 16 17:44:25 UTC 2021
XMLGregorianCalendar Format :- 2021-02-16T17:44:25.164Z
```