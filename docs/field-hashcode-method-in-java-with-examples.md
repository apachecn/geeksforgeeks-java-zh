# Java 中的字段 hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/field-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-hashcode-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **hashCode()** 方法用于获取该 Field 的 hashCode。Final Hashcode 被计算为基础字段的声明类名及其名称的 Hashcode 的异或。如果对象没有改变，hashcode 总是相同的。Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希相关算法进行一些操作，比如哈希表、哈希表等。也可以用这个唯一的代码搜索一个对象。

**语法:**

```
public int hashCode()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个**整数**，这是这个对象的哈希码值。

下面的程序说明了 hashCode()方法:
**程序 1:**

```
// Java program to demonstrate hashCode() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Get the marks field object
        Field field = User.class.getField("Marks");

        // Apply hashCode Method on User Object
        // to get the hashCode of Marks field
        int value = field.hashCode();

        // print result
        System.out.println("HashCode of Marks field"
                           + " is " + value);

        // Now Get the Fees field object
        field = User.class.getField("Fees");

        // Apply hashCode Method on User Object
        // to get the hashcode of Fees field
        value = field.hashCode();

        // print result
        System.out.println("HashCode of Fees field"
                           + " is " + value);

        // Now Get the name field object
        field = User.class.getField("name");

        // Apply hashCode Method on User Object
        // to get the hashCode of name field
        value = field.hashCode();

        // print result
        System.out.println("HashCode of name field"
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
HashCode of Marks field is 71482573
HashCode of Fees field is 591398
HashCode of name field is 1779040

```

**程序 2:**

```
// Java program to demonstrate hashCode() method

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
            System.out.println("HashCode of Field: "
                               + fields[i].hashCode());
        }
    }
}
```

**Output:**

```
HashCode of Field: -297508095
HashCode of Field: 1296412905
HashCode of Field: 1475695976
HashCode of Field: 1343692077
HashCode of Field: 1404020238
HashCode of Field: 1401709321
HashCode of Field: 1401709395
HashCode of Field: 538235208
HashCode of Field: 2125827066
HashCode of Field: -1718938229
HashCode of Field: -1007182215
HashCode of Field: 59532142

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # hashCode–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#hashCode--)