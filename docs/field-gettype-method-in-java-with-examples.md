# Java 中的 Field getType()方法，带示例

> 原文:[https://www . geesforgeks . org/field-gettype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-gettype-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getType()** 方法，用于获取该 Field 对象表示的字段的声明类型。此方法返回一个标识声明类型的类对象

**语法:**

```
public String getType()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回一个**类对象**，用于标识声明的类型。

以下程序说明 getType()方法:
**程序 1:**

```
// Java program to demonstrate getType() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Get the marks field object
        Field field = User.class.getField("Marks");

        // Apply getType Method on User Object
        // to get the Type of Marks field
        Class value = field.getType();

        // print result
        System.out.println("Type"
                           + " is " + value);

        // Now Get the Fees field object
        field = User.class.getField("Fees");

        // Apply getType Method on User Object
        // to get the Type of Fees field
        value = field.getType();

        // print result
        System.out.println("Type"
                           + " is " + value);
    }
}

// sample User class
class User {

    // static double values
    public static double Marks = 34.13;
    public static float Fees = 3413.99f;

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
}
```

**Output:**

```
Type is double
Type is float

```

**程序 2:**

```
// Java program to demonstrate getType() method

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
            System.out.println("Name of Field: "
                               + fields[i].getType());
        }
    }
}
```

**Output:**

```
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month
Name of Field: class java.time.Month

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # getType–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#getType--)