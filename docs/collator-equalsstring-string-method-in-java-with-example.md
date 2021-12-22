# Java 中的排序器等于(字符串，字符串)方法，示例

> 原文:[https://www . geesforgeks . org/collator-equals string-in-Java-method-with-example/](https://www.geeksforgeeks.org/collator-equalsstring-string-method-in-java-with-example/)

**java.text.Collator 类**的 **equals()** 方法用于检查两个字符串是否相同。

**语法:**

```
public boolean equals(String source,
                      String target)
```

**参数**:该方法取两个**字符串**，在这两个字符串之间进行比较。

**返回值:**如果两个字符串相等，则返回**真**否则返回**假**。

以下是说明**等于()**方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            // Collator Object
            Collator col = Collator.getInstance();

            // Creating an initializing
            // object for comparison
            String obj1 = "a";

            // Creating an initializing
            // Object for comparison
            String obj2 = "A";

            // compare both object
            // using equals() method
            boolean i = col.equals(obj1, obj2);

            // display result
            if (i)
                System.out.println(obj1
                                   + " is equal to "
                                   + obj2);
            else
                System.out.println(obj1
                                   + " is not equal to "
                                   + obj2);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
a is not equal to A
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            // Collator Object
            Collator col = Collator.getInstance();

            // Creating an initializing
            // object for comparison
            String obj1 = "a";

            // Creating an initializing
            // Object for comparison
            String obj2 = "a";

            // compare both object
            // using equals() method
            boolean i = col.equals(obj1, obj2);

            // display result
            if (i)
                System.out.println(obj1
                                   + " is equal to "
                                   + obj2);
            else
                System.out.println(obj1
                                   + " is not equal to "
                                   + obj2);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
a is equal to a
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # equals-Java . lang . string-Java . lang . string-T4】