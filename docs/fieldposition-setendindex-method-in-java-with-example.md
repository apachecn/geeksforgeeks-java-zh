# Java 中的 FieldPosition setEndIndex()方法，示例

> 原文:[https://www . geesforgeks . org/field position-setendindex-method-in-Java-with-example/](https://www.geeksforgeeks.org/fieldposition-setendindex-method-in-java-with-example/)

**java.text.FieldPosition** 类的 **setEndIndex()** 方法用于设置 FieldPosition 对象中最后一个字符前面的字符的索引。

**语法:**

```java
public void setEndIndex(int ei)
```

**参数**:该方法对 FieldPosition 对象中最后一个字符之前的字符的新索引取**整数值**索引。

**返回值:**这个方法没有什么可返回的。

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
                    MessageFormat.Field.ARGUMENT);

            // setting end index
            pos.setEndIndex(10);

            // getting end index of FieldPosition Object
            // using getEndIndex() mehtod
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
end index :- 10

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
            // using getEndIndex() mehtod
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

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/field position . html # setEndIndex-int-](https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#setEndIndex-int-)