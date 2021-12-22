# Java 中的 FieldPosition setBeginIndex()方法，示例

> 原文:[https://www . geeksforgeeks . org/field position-setbeginindex-method-in-Java-with-example/](https://www.geeksforgeeks.org/fieldposition-setbeginindex-method-in-java-with-example/)

**java.text.FieldPosition** 类的 **setBeginIndex()** 方法用于设置 FieldPosition 对象开始字符的索引。
**语法:**

```
public void setBeginIndex(int index)
```

**参数**:该方法取**整数值**作为 FieldPosition 对象起始字符的新索引。
**返回值:**这个方法没有什么可返回的。
以下是举例说明 **setBeginIndex()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// setBeginIndex() method

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
                = new FieldPosition(DateFormat.Field.AM_PM);

            // setting begin index of FieldPosition Object
            // using setBeginIndex() method
            pos.setBeginIndex(5);

            // getting begin index of FieldPosition Object
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

```
begin index :- 5
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// setBeginIndex() method

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

            // setting begin index of FieldPosition Object
            // using setBeginIndex() method
            pos.setBeginIndex(10);

            // getting begin index of FieldPosition Object
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

```
begin index :- 10
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/field position . html # setBeginIndex-int-T4】