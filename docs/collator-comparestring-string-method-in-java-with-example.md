# Java 中的排序器比较(字符串，String)方法与示例

> 原文:[https://www . geesforgeks . org/collator-comparistring-string-in-Java-method-with-example/](https://www.geeksforgeeks.org/collator-comparestring-string-method-in-java-with-example/)

**java.text.Collator** 类的 **compare()** 方法用于比较两个字符串的强度，它将根据结果返回 0、正值和负值作为输出。

**语法:**

```java
public abstract int compare(String source,
                            String target)
```

**参数**:此方法取**两根弦**，在这两根弦之间进行比较。
**返回值:**如果第一个字符串等于、大于或小于另一个字符串，那么它将分别返回零、正值和负值。

以下是说明**比较()**方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// compare() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col = Collator.getInstance();

            // Creating an initializing object for comparison
            String obj1 = "ab";

            // Creating an initializing Object for comparison
            String obj2 = "Ab";

            // compare both object
            // using compare() method
            int i = col.compare(obj1, obj2);

            // display result
            if (i < 0)
                System.out.println("ab is less than Ab");
            else if (i > 0)
                System.out.println("ab is greater than Ab");
            else
                System.out.println("ab is equal to Ab");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
ab is less than Ab
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// compare() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col = Collator.getInstance();

            // Creating an initializing object for comparison
            String obj1 = "ab";

            // Creating an initializing Object for comparison
            String obj2 = "cd";

            // compare both object
            // using compare() method
            int i = col.compare(obj1, obj2);

            // display result
            if (i < 0)
                System.out.println("ab is less than cd");
            else if (i > 0)
                System.out.println("ab is greater than cd");
            else
                System.out.println("ab is equal to cd");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
ab is less than cd
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # compare-Java . lang . string-Java . lang . string-T4】