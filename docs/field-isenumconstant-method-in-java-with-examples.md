# Java 中的 Field isEnumConstant()方法，带示例

> 原文:[https://www . geesforgeks . org/field-isenumconstant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-isenumconstant-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **isEnumConstant()** 方法，用于检查该字段是否表示枚举类型的元素。如果此字段表示枚举类型的元素，则方法返回 true 否则返回 false。

**语法:**

```
public boolean isEnumConstant()

```

**参数:**此方法不接受任何东西。

**返回**:当且仅当该字段表示枚举类型的元素时，该方法返回**真**。

下面的程序说明了 isEnumConstant()方法:
**程序 1:**

```
// Java program to illustrate
// isEnumConstant () method

import java.lang.reflect.Field;
import java.time.Month;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // get all declared fields of Month class
        Field[] declaredFields
            = Month.class.getDeclaredFields();

        // loop through Field array
        // and print Field name and
        // check whether the field is EnumConstant
        for (int i = 0; i < declaredFields.length; i++) {
            System.out.print(
                "Field --> Name: "
                + declaredFields[i].getName()
                + "; isEnumConstant: "
                + declaredFields[i]
                      .isEnumConstant()
                + "\n");
        }
    }
}
```

**Output:**

```
Field --> Name: JANUARY; isEnumConstant: true
Field --> Name: FEBRUARY; isEnumConstant: true
Field --> Name: MARCH; isEnumConstant: true
Field --> Name: APRIL; isEnumConstant: true
Field --> Name: MAY; isEnumConstant: true
Field --> Name: JUNE; isEnumConstant: true
Field --> Name: JULY; isEnumConstant: true
Field --> Name: AUGUST; isEnumConstant: true
Field --> Name: SEPTEMBER; isEnumConstant: true
Field --> Name: OCTOBER; isEnumConstant: true
Field --> Name: NOVEMBER; isEnumConstant: true
Field --> Name: DECEMBER; isEnumConstant: true
Field --> Name: ENUMS; isEnumConstant: false
Field --> Name: $VALUES; isEnumConstant: false

```

**程序 2:**

```
// Java program to illustrate
// isEnumConstant () method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // get all declared fields of Symbols class
        Field[] declaredFields
            = Symbols.class.getDeclaredFields();

        // loop through Field array
        // and print Field name and
        // check whether the field is EnumConstant
        for (int i = 0; i < declaredFields.length; i++) {
            System.out.print(
                "Field --> Name: "
                + declaredFields[i].getName()
                + "; isEnumConstant: "
                + declaredFields[i]
                      .isEnumConstant()
                + "\n");
        }
    }

    private static enum Symbols {
        Alpha,
        Beta,
        Gamma
    }
}
```

**Output:**

```
Field --> Name: Alpha; isEnumConstant: true
Field --> Name: Beta; isEnumConstant: true
Field --> Name: Gamma; isEnumConstant: true
Field --> Name: ENUM$VALUES; isEnumConstant: false

```

**参考文献:**