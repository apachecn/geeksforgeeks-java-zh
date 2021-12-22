# Java 中的 FieldPosition hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/field position-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/fieldposition-hashcode-method-in-java-with-example/)

**java.text.FieldPosition** 类的 **hashCode()** 方法用于获取 FieldPosition 对象的 hashCode。

**语法:**

```java
public int hashCode()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**这个方法返回这个 FieldPosition 对象的 **hashcode** 。

下面是举例说明 **hashCode()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// hashCode() method

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

            // getting hash code of this
            // field position object
            // using hashCode() mehtod
            int i = pos.hashCode();

            // display result
            System.out.println("hashCode. :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
hashCode. :- -16777216

```

**例 2:**

```java
// Java program to demonstrate
// hashCode() method

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

            // getting hash code of this
            // field position object
            // using hashCode() mehtod
            int i = pos.hashCode();

            // display result
            System.out.println("hashCode. :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
hashCode. :- -16777216

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/field position . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/text/FieldPosition.html#hashCode--)