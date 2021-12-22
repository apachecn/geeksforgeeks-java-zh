# 在 Java 中将 XMLGregorianCalendar 转换为日期

> 原文:[https://www . geesforgeks . org/converting-xmlgregoriancalendar-to-date-in-Java/](https://www.geeksforgeeks.org/converting-xmlgregoriancalendar-to-date-in-java/)

XMLGregorianCalendar 可以根据需要转换为 [java.util.Date](https://www.geeksforgeeks.org/date-class-java-examples/) 或 [java.sql.Date](https://www.geeksforgeeks.org/how-to-convert-java-sql-date-to-java-util-date-in-java/) 。JAXB(Java API/XML Bindings Architecture)是从 Java 对象创建 XML 文档和从 Java 对象创建 XML 文件的通用框架。JAXB 还允许 XML Schema 文件构造 Java 类(。XSD 文件)。默认情况下，JAXB 将 Java 中的 xs:date、xs:time 和 xs:dateTime 映射到 XMLGregorianCalendar，但是您可以自定义 XJC 来构造 java.util.Date 对象，而不是 javax . XML . datatype . XMLGregorianCalendar。

由于 java.util.Date 是处理 java 日期和时间最常用的方法，所以我们总是需要将 XMLGregorianCalendar 的实例转换为 Java date 实例。

使用 Java API，我们可以在 Java 中轻松地将 XMLGregorianCalendar 转换为 XMLGregorianCalendar 日期和日期。

顺便说一下，很高兴地注意到，有三种不同形式的 XML Schema 可以表示日期、时间或两者，而 java.util.Date 包含日期和时间的详细信息。

这是一个 Java 程序，它将 XMLGregorianCalendar 转换为 Date。所以我们将获取 XMLGregorianCalendar 并返回 java.util.Date。

**代码:**

## Java

```
// Convert XMLGregorianCalendar to Date in Java
import java.io.*;
import java.util.*;
import java.util.Date;
import java.util.GregorianCalendar;
import java.util.logging.Level;
import java.util.logging.Logger;
import javax.xml.datatype.DatatypeConfigurationException;
import javax.xml.datatype.DatatypeFactory;
import javax.xml.datatype.XMLGregorianCalendar;

class GFG {
    public static void main(String[] args)
    {
        Date today = new Date();

        // Converting date to XMLGregorianCalendar
        XMLGregorianCalendar xml
            = toXMLGregorianCalendar(today);
        System.out.println(
            "XMLGregorianCalendar from Date in Java      : "
            + xml);

        // Converting XMLGregorianCalendar to java.util.Date
        // in Java
        Date date = toDate(xml);
        System.out.println(
            "java.util.Date from XMLGregorianCalendar in Java : "
            + date);
    }

    public static XMLGregorianCalendar
    toXMLGregorianCalendar(Date date)
    {
        GregorianCalendar gCalendar
            = new GregorianCalendar();
        gCalendar.setTime(date);
        XMLGregorianCalendar xmlCalendar = null;
        try {
            xmlCalendar
                = DatatypeFactory.newInstance()
                      .newXMLGregorianCalendar(gCalendar);
        }
        catch (DatatypeConfigurationException ex) {
            System.out.println(ex);
        }
        return xmlCalendar;
    }

    public static Date toDate(XMLGregorianCalendar calendar)
    {
        if (calendar == null) {
            return null;
        }
        return calendar.toGregorianCalendar().getTime();
    }
}
```

**输出**

```
XMLGregorianCalendar from Date in Java      : 2021-02-22T17:10:28.732Z
java.util.Date from XMLGregorianCalendar in Java : Mon Feb 22 17:10:28 UTC 2021
```

**那么现在关于 XMLGregorianCalendar 和日期的重点:**

*   XML Schema has various date, time and dateTime data types, such as xsd:date, xsd:time and xsd:dateTime. By default, JAXB XJC is used to map to XMLGregorianCalendar in Java.
*   When constructing the GregorianCalendar case, it is better to use the constructor instead of calling GregorianCalendar.getInstance (), because it is similar to Calendar.getInstance () and can return different calendar types according to local settings, such as Thai local Buddhist calendar or Japanese Imperial Calendar. You can also exclude type conversion when using constructors, because getInstance () returns the java.util.Calendar instance and prevents ClassCastException from appearing in java.
*   For xs:date, xs:time and xs:dateTime data types, XJC can be configured to generate date instead of XMLGregorianCalendar. I will write this later, but this option can still be explored.

这都是关于如何将 XMLGregorianCalendar 转换为 Java 日期和 XMLGregorianCalendar 日期。