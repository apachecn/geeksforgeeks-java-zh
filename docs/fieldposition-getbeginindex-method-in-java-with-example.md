# Java 中的 FieldPosition getBeginIndex()方法，示例

> 原文:[https://www . geesforgeks . org/field position-getbeginindex-method-in-Java-with-example/](https://www.geeksforgeeks.org/fieldposition-getbeginindex-method-in-java-with-example/)

**java.text.FieldPosition** 类的 **getBeginIndex()** 方法用于获取 FieldPosition 对象开始字符的索引。

**语法:**

```java
public int getBeginIndex()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回 FieldPosition 对象开始字符的**索引**。

以下是说明 **getBeginIndex()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getBeginIndex() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            /// new FieldPosition Object
            FieldPosition pos
                = new FieldPosition(
                    DateFormat.Field.AM_PM);

            // getting begin index of FieldPosition Object
            // using getBeginIndex() method
            int i = pos.getBeginIndex();

            // display result
            System.out.println("begin index :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
begin index :- 0
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getBeginIndex() method

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

            // setting begin index
            pos.setBeginIndex(5);

            // getting begin index of FieldPosition Object
            // using getBeginIndex() method
            int i = pos.getBeginIndex();

            // display result
            System.out.println("begin index :- " + i);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
begin index :- 5
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/field position . html # setBeginIndex-int-T4】