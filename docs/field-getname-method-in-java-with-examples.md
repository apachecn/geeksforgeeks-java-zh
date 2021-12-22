# Java 中的 Field getName()方法，带示例

> 原文:[https://www . geesforgeks . org/field-getname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getname-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getName()** 方法用于获取该 Field 对象所表示的字段的名称。当一个类包含一个字段，并且我们想要得到那个字段的名称，那么我们可以使用这个方法返回字段的名称。

**语法:**

```
public String getName()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个**字符串**，这是基础成员的简单名称。

以下程序说明 getName()方法:
**程序 1:**

```
// Java program to demonstrate getName() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Get the marks field object
        Field field = User.class
.getField("Marks");

        // Apply getName Method on User Object
        // to get the name of Marks field
        String value = field.getName();

        // print result
        System.out.println("Name"
                           + " is " + value);

        // Now Get the Fees field object
        field = User.class.getField("Fees");

        // Apply getName Method on User Object
        // to get the name of Fees field
        value = field.getName();

        // print result
        System.out.println("Name"
                           + " is " + value);

        // Now Get the name field object
        field = User.class.getField("name");

        // Apply getName Method on User Object
        // to get the name of name field
        value = field.getName();

        // print result
        System.out.println("Name"
                           + " is " + value);
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

```
Name is Marks
Name is Fees
Name is name

```

**程序 2:**

```
// Java program to demonstrate getName() method

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
            System.out.println("Name of Field:"
                               + fields[i].getName());
        }
    }
}
```

**Output:**

```
Name of Field:JANUARY
Name of Field:FEBRUARY
Name of Field:MARCH
Name of Field:APRIL
Name of Field:MAY
Name of Field:JUNE
Name of Field:JULY
Name of Field:AUGUST
Name of Field:SEPTEMBER
Name of Field:OCTOBER
Name of Field:NOVEMBER
Name of Field:DECEMBER

```

**参考文献:**