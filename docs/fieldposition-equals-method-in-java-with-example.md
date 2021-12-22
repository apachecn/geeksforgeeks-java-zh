# Java 中的 FieldPosition equals()方法，示例

> 原文:[https://www . geesforgeks . org/field position-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/fieldposition-equals-method-in-java-with-example/)

**java.text.FieldPosition** 类的 **equals()** 方法用于检查两个 FieldPosition 对象是否相同。

**语法:**

```java
public boolean equals(Object obj)
```

**参数**:该方法取 **FieldPosition** 对象，与当前 FieldPosition 对象进行比较。
**返回值:**如果两个**字段位置对象**彼此相等，则返回真，否则返回假。
以下是说明**等于()**方法的示例:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// equals() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new FieldPosition Object
            FieldPosition pos_1
                = new FieldPosition(
                    DateFormat.Field.AM_PM);

            // Creating and initializing
            // new FieldPosition Object
            FieldPosition pos_2
                = new FieldPosition(
                    DateFormat.Field.AM_PM);

            // compare both object
            // using equals() method
            boolean i = pos_1.equals(pos_2);

            // display result
            if (i)
                System.out.println(
                    "pos_1 is equals to pos_2");
            else
                System.out.println(
                    "pos_1 is not equal to pos_2");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
pos_1 is equals to pos_2
```