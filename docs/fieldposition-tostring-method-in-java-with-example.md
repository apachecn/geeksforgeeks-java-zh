# Java 中的 FieldPosition toString()方法，示例

> 原文:[https://www . geesforgeks . org/field position-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/fieldposition-tostring-method-in-java-with-example/)

**java.text.FieldPosition** 类的 **toString()** 方法用于以字符串的形式表示字段位置对象。

**语法:**

```
public String toString()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回该 FieldPosition 对象的**字符串表示**。

以下是说明 **toString()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// toString() method

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

            // getting the String representation
            // of this FieldPosition Object
            // using toString() method
            String str = pos.toString();

            // display result
            System.out.println("FieldPosition :- " + str);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
FieldPosition :- java.text.FieldPosition[field=-1, attribute=java.text.MessageFormat$Field(message argument field), beginIndex=0, endIndex=0]

```

**例 2:**

```
// Java program to demonstrate
// toString() method

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

            // getting the String representation
            // of this FieldPosition Object
            // using toString() method
            String str = pos.toString();

            // display result
            System.out.println("FieldPosition :- " + str);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
FieldPosition :- java.text.FieldPosition[field=-1, attribute=java.text.DateFormat$Field(am pm), beginIndex=0, endIndex=0]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/field position . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#toString--)