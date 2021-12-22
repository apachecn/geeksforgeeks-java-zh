# Java 中的字段 toString()方法，示例

> 原文:[https://www . geesforgeks . org/field-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-tostring-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **toString()** 方法用于获取描述该 Field 的字符串。返回字符串的格式是字段的访问修饰符(如果有)，后跟字段类型、空格、声明字段的类的完全限定名、句点和字段名称。

**例如:**

```java
public static final Month java.time.Month.APRIL
```

修饰符按照“Java 语言规范”指定的规范顺序放置。首先是公共的、受保护的或私有的，然后是其他修饰符，顺序如下:静态的、最终的、暂时的、易变的。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回描述该字段的**字符串**。

下面的程序说明了 toString()方法:
**程序 1:**

```java
// Java program to illustrate toString() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Get the array of field object
        Field[] fields = User.class.getFields();

        // loop
        for (int i = 0; i < fields.length; i++) {

            // get the string representation of each field
            String field = fields[i].toString();

            System.out.println("Field: " + field);
        }
    }
}

// sample User class
class User {

    // static double values
    public static double Marks = 34.13;
    public static float Fees = 3413.99f;
    public static String name = "Aman";

    public static double getMarks()
    {
        return Marks;
    }

    public static void setMarks(double marks)
    {
        Marks = marks;
    }

    public static float getFees()
    {
        return Fees;
    }

    public static void setFees(float fees)
    {
        Fees = fees;
    }

    public static String getName()
    {
        return name;
    }

    public static void setName(String name)
    {
        User.name = name;
    }
}
```

**Output:**

```java
Field: public static double User.Marks
Field: public static float User.Fees
Field: public static java.lang.String User.name

```

**程序 2:**

```java
// Java program to illustrate toString() method

import java.lang.reflect.Field;
import java.time.Month;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Get all field objects of Month class
        Field[] fields = Month.class.getFields();

        for (int i = 0; i < fields.length; i++) {

            // print name of Fields
            System.out.println("toString of Field:\n"
                               + fields[i].toString());
        }
    }
}
```

**Output:**

> 字段的 toString:
> 公共静态最终 java.time.Month Java . time . month . 1 月
> 字段的 toString:
> 公共静态最终 Java . time . month Java . time . month . 2 月
> 字段的 toString:
> 公共静态最终 Java . time . month Java . time . month . 3 月
> 字段的 toString:
> 公共静态最终 Java . time . month Java . time . month . April
> 字段的 toString:
> 公共静态最终 Java . time . month of Field:
> public static final Java . time . month Java . time . month .九月
> to string of Field:
> public static final Java . time . month Java . time . month .十月
> to string of Field:
> public static final Java . time . month Java . time . month .十一月
> to string of Field:
> public static final Java . time . month Java . time . month .十二月

**参考文献:**