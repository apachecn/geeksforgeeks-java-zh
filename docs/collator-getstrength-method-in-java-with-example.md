# Java 中的整理器 getStrength()方法，示例

> 原文:[https://www . geesforgeks . org/collator-get strength-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-getstrength-method-in-java-with-example/)

**java.text.Collator 类**的 **getStrength()** 方法用于获取 Collator 对象的强度属性，这将有助于该对象进行比较。

**语法:**

```java
public int getStrength()
```

**参数**:此方法不接受任何参数。
**返回值:**此方法返回整理器对象的**强度属性**，这将在比较过程中帮助该对象。

以下是说明 **getStrength()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getStrength() method

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

            // setting strength property
            // for the Collator object
            col.setStrength(Collator.IDENTICAL);

            // getting strength property
            // using getStrength() method
            int strength = col.getStrength();

            // display result
            if (strength == 0)
                System.out.println(
                    "current strength "
                    + "property :- PRIMARY.");
            else if (strength == 1)
                System.out.println(
                    "current strength "
                    + "property :- SECONDARY.");
            else if (strength == 2)
                System.out.println(
                    "current strength"
                    + " property :-  TERTIARY.");
            else
                System.out.println(
                    "current strength "
                    + "property :- IDENTICAL.");
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
current strength property :- IDENTICAL.
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getStrength() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col = Collator.getInstance(Locale.UK);

            // getting strength property
            // using getStrength() method
            int strength = col.getStrength();

            // display result
            if (strength == 0)
                System.out.println(
                    "current strength "
                    + "property :- PRIMARY.");
            else if (strength == 1)
                System.out.println(
                    "current strength "
                    + "property :- SECONDARY.");
            else if (strength == 2)
                System.out.println(
                    "current strength "
                    + "property :-  TERTIARY.");
            else
                System.out.println(
                    "current strength "
                    + "property :- IDENTICAL.");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
current strength property :-  TERTIARY.
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # getStrength–T4】