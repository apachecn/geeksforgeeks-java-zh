# Java 中的 FieldPosition getFieldAttribute()方法，示例

> 原文:[https://www . geesforgeks . org/field position-getfield attribute-method-in-Java-with-example/](https://www.geeksforgeeks.org/fieldposition-getfieldattribute-method-in-java-with-example/)

**java.text.FieldPosition** 类的 **getFieldAttribute()** 方法用于获取 Format.field 形式的字段标识符。

**语法:**

```
public Format.Field getFieldAttribute()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法以 Format.field 的形式返回**字段标识符**。

以下是说明 **getFieldAttribute()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getFieldAttribute() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new FieldPosition Object
            FieldPosition pos
                = new FieldPosition(
                    MessageFormat.Field.ARGUMENT);

            // getting Field attribute
            // of FieldPosition object
            // using getField() mehtod
            Format.Field i = pos.getFieldAttribute();

            // display result
            System.out.println("field identifier. :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
field identifier. :- java.text.MessageFormat$Field(message argument field)

```

**例 2:**

```
// Java program to demonstrate
// getFieldAttribute() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new FieldPosition Object
            FieldPosition pos
                = new FieldPosition(
                    DateFormat.Field.AM_PM);

            // getting Field attribute
            // of FieldPosition object
            // using getField() mehtod
            Format.Field i = pos.getFieldAttribute();

            // display result
            System.out.println("field identifier. :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
field identifier. :- java.text.DateFormat$Field(am pm)

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/field position . html # getfield attribute–](https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#getFieldAttribute--)