# Java 中的 Field getShort()方法，带示例

> 原文:[https://www . geesforgeks . org/field-getshort-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getshort-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getShort()** 方法用于获取 Short 的值，该值必须是静态或实例字段类型。此方法还用于通过加宽转换获取另一个可转换为 short 类型的基元类型的值。当一个类包含一个静态或实例短字段，并且我们想要得到该字段的值，那么我们可以使用这个方法返回字段的值。

**语法:**

```
public short getShort(Object obj)
             throws IllegalArgumentException,
                    IllegalAccessException

```

**参数:**该方法接受单个参数 **obj** ，该参数是从中提取短值的对象。

**返回值:**该方法返回转换为 short 类型的字段的值。

**异常:**该方法抛出以下异常:

1.  **IllegalAccessException:** 如果 Field 对象正在执行 Java 语言访问控制，并且底层字段不可访问。
2.  **IllegalArgumentException:**如果指定的对象不是声明基础字段的类或接口的实例，或者如果字段值不能通过扩展转换转换为 short 类型。
3.  **NullPointRexception:**如果指定的对象为空，并且该字段是实例字段。
4.  **exceptioniniinitializerror:**如果此方法引发的初始化失败。

以下程序说明 getShort()方法:
**程序 1:**

```
// Java program to demonstrate getShort() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Create the User class object
        User user = new User();

        // Get the marks field object
        Field field
            = User.class.getField("Marks");

        // Apply getShort Method on User Object
        // to get the value of Marks field
        short value = field.getShort(user);

        // print result
        System.out.println("Value of short Field"
                           + " Marks is " + value);
    }
}

// sample User class
class User {

    // static short values
    public static short Marks = 34;
    public static String name = "Aman";

    public static short getMarks()
    {
        return Marks;
    }

    public static void setMarks(short marks)
    {
        Marks = marks;
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
Value of short Field Marks is 34

```

**程序 2:**

```
// Java program to demonstrate getShort() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Create the SmallerNumbers class object
        SmallerNumbers smallNo
            = new SmallerNumbers();

        // Get the value field object
        Field field = SmallerNumbers.class
                          .getField("value");

        // Apply getShort Method on field Object
        // to get the value of value field
        short value = field.getShort(smallNo);

        // print result
        System.out.println("Value: " + value);
    }

    // SmallerNumbers class
    static class SmallerNumbers {

        // short field
        public static short value = 999;

        // getter and setter methods
        public static short getValue()
        {
            return value;
        }

        public static void setValue(short value)
        {
            SmallerNumbers.value = value;
        }
    }
}
```

**Output:**

```
Value: 999

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # getShort-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#getShort-java.lang.Object-)