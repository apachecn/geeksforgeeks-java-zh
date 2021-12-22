# Java 中的 Collator getCollationKey()方法，示例

> 原文:[https://www . geeksforgeeks . org/collator-getcollationkey-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-getcollationkey-method-in-java-with-example/)

**java.text.Collator 类**的 **getCollationKey()** 方法用于获取从传递到其中的字符串转换而来的一系列位。

**语法:**

```java
public abstract CollationKey
       getCollationKey(String source)
```

**参数**:该方法接受**字符串对象**作为参数。
**返回值:**该方法返回从传递给它的字符串转换而来的一系列位。

以下是说明 **getCollationKey()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getCollationKey() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new simple rule
            String simple
                = "< a < b < c < d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting series of bits
            // using getCollationKey() method
            CollationKey key
                = col.getCollationKey("Geek");

            // display result
            System.out.println(
                "Series of bits are :- "
                + key.getSourceString());
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ParseException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Series of bits are :- Geek
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getCollationKey() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // Collator Object
            Collator col
                = Collator.getInstance(Locale.UK);

            // getting series of bits
            // using getCollationKey() method
            CollationKey key
                = col.getCollationKey("CodeBlock");

            // display result
            System.out.println(
                "Series of bits are :- "
                + key.getSourceString());
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Series of bits are :- CodeBlock
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # getCollationKey-Java . lang . string-T4】