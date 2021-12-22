# Java 中的 FieldPosition getField()方法，示例

> 原文:[https://www . geesforgeks . org/field position-getfield-method-in-Java-with-example/](https://www.geeksforgeeks.org/fieldposition-getfield-method-in-java-with-example/)

**java.text.FieldPosition** 类的 **getField()** 方法用于检索该字段位置对象的字段标识符。
**语法:**

```
public int getField()
```

**参数**:该方法不接受任何参数作为参数。
**返回值:**该方法返回该字段位置对象的**字段标识**。
以下是举例说明 **getField()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getField() method

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
            // using getField() method
            int i = pos.getField();

            // display result
            System.out.println(
                "field attribute :- "
                + Integer.toString(i));
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
field attribute :- -1
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getField() method

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
            // using getField() method
            int i = pos.getField();

            // display result
            System.out.println(
                "field attribute :- "
                + Integer.toString(i));
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
field attribute :- -1
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/field position . html # getField–T4】