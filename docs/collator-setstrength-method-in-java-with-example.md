# Java 中的排序器 setStrength()方法，示例

> 原文:[https://www . geesforgeks . org/collator-set strength-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-setstrength-method-in-java-with-example/)

**java.text.Collator 类**的 **setStrength()** 方法用于设置 Collator 对象的强度属性，该属性将在比较两个字符串时帮助该对象。
**语法:**

```
public void setStrength(int newStrength)
```

**参数**:该方法接受整理器对象的**强度属性**作为参数，在比较时会对该对象有所帮助。
**返回值:**这个方法没有什么可返回的。
以下是举例说明 **setStrength()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// setStrength() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing new simple rule
            String simple = "< a < b < c < d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // setting strength property for the Collator object
            // using getStrength() method
            col.setStrength(Collator.IDENTICAL);

            // getting strength property
            int strength = col.getStrength();

            // display result
            if (strength == 0)
                System.out.println(
                    "current strength"
                    + " property :- PRIMARY.");
            else if (strength == 1)
                System.out.println(
                    "current strength"
                    + " property :- SECONDARY.");
            else if (strength == 2)
                System.out.println(
                    "current strength"
                    + " property :-  TERTIARY.");
            else
                System.out.println(
                    "current strength"
                    + " property :- IDENTICAL.");
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

```
current strength property :- IDENTICAL.
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// setStrength() method

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

            // setting strength property
            // for the Collator object
            // using getStrength() method
            col.setStrength(Collator.PRIMARY);

            // getting strength property
            int strength = col.getStrength();

            // display result
            if (strength == 0)
                System.out.println(
                    "current strength"
                    + " property :- PRIMARY.");
            else if (strength == 1)
                System.out.println(
                    "current strength"
                    + " property :- SECONDARY.");
            else if (strength == 2)
                System.out.println(
                    "current strength"
                    + " property :-  TERTIARY.");
            else
                System.out.println(
                    "current strength"
                    + " property :- IDENTICAL.");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
current strength property :- PRIMARY.
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # setStrength-int-T4】