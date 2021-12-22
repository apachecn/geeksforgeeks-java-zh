# Java 中的 Field get()方法，示例

> 原文:[https://www . geesforgeks . org/field-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-get-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **get()** 方法用于获取字段对象的值。如果字段具有基本类型，则字段的值会自动包装在对象中。如果字段是静态字段，则忽略 obj 的参数；它可能为空。否则，基础字段是实例字段。如果指定的对象参数为空，则此方法引发 NullPointerException 如果指定的对象不是声明基础字段的类或接口的实例，则引发 IllegalArgumentException。如果该字段隐藏在 obj 类型中，则根据前面的规则获取该字段的值。

**语法:**

```
public double get(Object obj)
             throws IllegalArgumentException,
                    IllegalAccessException

```

**参数:**该方法接受单个参数 **obj** ，该参数是从中提取字段值的对象。

**返回值:**该方法返回对象 obj 中表示字段的值；原始值在返回之前被包装在适当的对象中。

**异常:**该方法抛出以下异常:

1.  **IllegalAccessException**–如果此字段对象正在实施 Java 语言访问控制，并且基础字段不可访问。
2.  **IllegalArgumentException**–如果指定的对象不是声明基础字段的类或接口(或其子类或实现者)的实例。
3.  **NullPointRexception**–如果指定的对象为空，并且该字段是实例字段。
4.  **exceptioniniinitializerror**–如果此方法引发的初始化失败。

下面的程序说明 get()方法:
**程序 1:**

```
// Java program to demonstrate get() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Create the User class object
        User user = new User();

        // Get the all field objects of User class
        Field[] fields = User.class.getFields();

        for (int i = 0; i < fields.length; i++) {

            // get value of the fields
            Object value = fields[i].get(user);

            // print result
            System.out.println("Value of Field "
                               + fields[i].getName()
                               + " is " + value);
        }
    }
}

// sample User class
class User {

    // static double values
    public static double Marks = 34.13;
    public static int Fees = 34199;
    public static String name = "Aman";

    public static double getMarks()
    {
        return Marks;
    }

    public static void setMarks(double marks)
    {
        Marks = marks;
    }

    public static int getFees()
    {
        return Fees;
    }

    public static void setFees(int fees)
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
Value of Field Marks is 34.13
Value of Field Fees is 34199
Value of Field name is Aman

```

**程序 2:**

```
// Java program to demonstrate get() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Create the RealNumbers class object
        Fields field = new Fields();

        // Get the all field objects of User class
        Field[] fieldsOfFieldClass
            = Fields.class.getFields();

        for (int i = 0;
             i < fieldsOfFieldClass.length; i++) {

            // get value
            Object value = fieldsOfFieldClass[i]
                               .get(field);

            // print result
            System.out.println(
                "Value of Field "
                + fieldsOfFieldClass[i].getName()
                + " is " + value);
        }
    }

    // RealNumbers class
    static class Fields {

        // double field
        public static final double doubleValue
            = 9999999.34567;
        public static final int intValue
            = 9999999;
        public static final float floatValue
            = 9999999.34567f;
        public static final
            boolean booleanValue
            = true;
    }
}
```

**Output:**

```
Value of Field doubleValue is 9999999.34567
Value of Field intValue is 9999999
Value of Field floatValue is 9999999.0
Value of Field booleanValue is true

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # get-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#get-java.lang.Object-)