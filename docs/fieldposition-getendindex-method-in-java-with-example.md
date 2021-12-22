# Java 中的 FieldPosition getEndIndex()方法，示例

> 原文:[https://www . geesforgeks . org/field position-getendindex-method-in-Java-with-example/](https://www.geeksforgeeks.org/fieldposition-getendindex-method-in-java-with-example/)

**java.text.FieldPosition** 类的 **getEndIndex()** 方法用于获取 FieldPosition 对象中最后一个字符前面的字符的索引。

**语法:**

```java
public int getEndIndex()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回 FieldPosition 对象中最后一个字符前面的字符的**索引**。

以下是说明 **getEndIndex()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getEndIndex() method

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

            // getting end index of FieldPosition Object
            // using getEndIndex() method
            int i = pos.getEndIndex();

            // display result
            System.out.println("end index :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
end index :- 0

```

**例 2:**

```java
// Java program to demonstrate
// getEndIndex() method

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

            // setting end index
            pos.setEndIndex(5);

            // getting end index of FieldPosition Object
            // using getEndIndex() method
            int i = pos.getEndIndex();

            // display result
            System.out.println("end index :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
end index :- 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/field position . html # getEndIndex–](https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#getEndIndex--)