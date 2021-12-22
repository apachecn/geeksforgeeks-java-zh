# Java 中的 Field getInt()方法，带示例

> 原文:[https://www . geesforgeks . org/field-getint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getint-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getInt()** 方法用于获取 Int 的值，该值必须是静态或实例字段类型。此方法还用于通过扩展转换获取另一个可转换为 int 类型的基元类型的值。当一个类包含一个静态或实例 int 字段，并且我们想要得到该字段的值，那么我们可以使用这个方法返回 field 的值。

**语法:**

```
public int getInt(Object obj)
           throws IllegalArgumentException,
                  IllegalAccessException

```

**参数:**该方法接受单个参数**对象**，该参数是从中提取 int 值的对象。

**返回值:**该方法返回转换为 int 类型的字段的值。

**异常:**该方法抛出以下异常:

1.  **IllegalAccessException:** 如果 Field 对象正在执行 Java 语言访问控制，并且底层字段不可访问。
2.  **IllegalArgumentException:**如果指定的对象不是声明基础字段的类或接口的实例，或者如果字段值不能通过扩展转换转换为 int 类型。
3.  **NullPointRexception:**如果指定的对象为空，并且该字段是实例字段。
4.  **exceptioniniinitializerror:**如果此方法引发的初始化失败。

下面的程序说明了 getInt()方法:
**程序 1:**

```
// Java program to demonstrate getInt() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Create the Employee class object
        Employee Employee = new Employee();

        // Get the Salary field object
        Field field
            = Employee.class.getField("Salary");

        // Apply getInt Method on Employee Object
        // to get the value of Salary field
        int value = field.getInt(Employee);

        // print result
        System.out.println("Value of int Field"
                           + " Salary is " + value);
    }
}

// sample Employee class
class Employee {

    // static int values
    public static int Salary = 34113;
    public static String name = "Aman";

    public static int getSalary()
    {
        return Salary;
    }

    public static void setSalary(int Salary)
    {
        Employee.Salary = Salary;
    }

    public static String getName()
    {
        return name;
    }

    public static void setName(String name)
    {
        Employee.name = name;
    }
}
```

**Output:**

```
Value of int Field Salary is 34113

```

**程序 2:**

```
// Java program to demonstrate getInt() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Create the IntNumbers class object
        IntNumbers Int = new IntNumbers();

        // Get the value field object
        Field field
            = IntNumbers.class.getField("value");

        // Apply getInt Method on field Object
        // to get the value of value field
        int value = field.getInt(Int);

        // print result
        System.out.println("Value: " + value);
    }

    // IntNumbers class
    static class IntNumbers {

        // int field
        public static int value = 999994567;

        // getter and setter methods
        public static int getValue()
        {
            return value;
        }

        public static void setValue(int value)
        {
            IntNumbers.value = value;
        }
    }
}
```

**Output:**

```
Value: 999994567

```

**参考文献:**T2