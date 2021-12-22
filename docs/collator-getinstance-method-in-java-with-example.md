# Java 中的定序器 getInstance()方法，示例

> 原文:[https://www . geesforgeks . org/collator-getinstance-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-getinstance-method-in-java-with-example/)

**java.text.Collator** 类的 **getInstance()** 方法用于获取具有当前默认区域设置的新 Collator 对象。

**语法:**

```java
public static Collator getInstance()
```

**参数**:此方法不接受任何参数。
**返回值:**提供具有当前默认区域设置的**新排序器对象**。

以下是说明 **getInstance()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getInstance() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing new simple rule
            String simple = "< a< b< c< d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col_1
                = new RuleBasedCollator(simple);

            // Creating and initializing Collator Object
            // using getInstance() method
            Collator col_2 = Collator.getInstance();

            // display result
            if (col_1.equals(col_2))
                System.out.println(col_1
                                   + " is equal to "
                                   + col_2);
            else
                System.out.println(col_1
                                   + " is not equal to "
                                   + col_2);
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
java.text.RuleBasedCollator@5eb2e1c2 is not equal to java.text.RuleBasedCollator@289747d6
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getInstance() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col_1 = Collator.getInstance();

            // Creating and initializing Collator Object
            Collator col_2 = Collator.getInstance();

            // display result
            if (col_1.equals(col_2))
                System.out.println(
                    col_1
                    + " is equal to "
                    + col_2);
            else
                System.out.println(
                    col_1
                    + " is not equal to "
                    + col_2);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
java.text.RuleBasedCollator@289747d6 is equal to java.text.RuleBasedCollator@289747d6
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # getInstance–T4】