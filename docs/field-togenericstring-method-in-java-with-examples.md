# Java 中的 Field toGenericString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/field-togenericstring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-togenericstring-method-in-java-with-examples/)

**java.lang.reflect.Field** 的**togetnericstring()**方法用于返回表示该 Field 的字符串，包括其泛型类型。字符串的格式是字段的访问修饰符(如果有)，后跟泛型字段类型、空格、声明字段的类的完全限定名、句点和字段名称。

修饰符按照“Java 语言规范”指定的规范顺序放置。首先是公共的、受保护的或私有的，然后是其他修饰符，顺序如下:静态的、最终的、暂时的、易变的。

**语法:**

```
public String toGenericString()

```

**参数:**此方法不接受任何东西。

**返回**:这个方法返回一个描述这个字段的**字符串**，包括它的泛型类型。

下面的程序说明了 toGenericString()方法:
**程序 1:**

```
// Java program to illustrate
// toGenericString() method

import java.lang.reflect.Field;
import java.time.Month;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Get all field objects of the Month class
        Field[] fields
            = Month.class.getFields();

        for (int i = 0; i < fields.length; i++) {

            // print name of Fields
            System.out.println(
                "toGenericString of Field:\n"
                + fields[i].toGenericString());
        }
    }
}
```

**Output:**

> 公共静态最终 java.time.Month java.time.Month . 1 月
> 公共静态最终 java.time.Month Java . time . month .月
> 公共静态最终 Java . time . month .月
> 公共静态最终 Java . time . month Java . time . month . March
> 公共静态最终 Java . time . month Java . time . month . April
> 公共静态最终 of Field:
> public static final Java . time . month Java . time . month .九月
> for Field:
> public static final Java . time . month Java . time . month .十月
> for Field:
> public static final Java . time . month Java . time . month .十一月
> for Field:
> public static final Java . time . month Java . time . month .十二月

**程序 2:**

```
// Java program to illustrate
// toGenericString() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create Numbers object
        Numbers no = new Numbers();

        // Get the value field object
        Field field
            = Numbers.class.getField("value");

        // print value of isActive
        System.out.println(
            "toGenericString is\n"
            + field.toGenericString());
    }
}

// sample Numbers class
class Numbers {

    // static short value
    public static short value = 13685;
}
```

**Output:**

```
toGenericString is 
public static short Numbers.value

```

**参考文献:**