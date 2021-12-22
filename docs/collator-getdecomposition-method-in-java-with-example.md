# Java 中的排序器 getDecomposition()方法，示例

> 原文:[https://www . geesforgeks . org/collator-get declaration-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-getdecomposition-method-in-java-with-example/)

**java.text.Collator 类**的**getdeclaration()**方法用来获取这个 Collator 的分解模式。

**语法:**

```
public int getDecomposition()
```

**参数**:此方法不接受任何参数。

**返回值:**该方法返回该排序器的**分解模式**。

下面是举例说明 **getDecomposition()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getDecomposition() method

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

            // setting decomposition mode
            // into the Collator object
            col.setDecomposition(
                Collator.CANONICAL_DECOMPOSITION);

            // getting decompostiton mode
            // using getDecomposition() mehtod
            int mode = col.getDecomposition();

            // display result
            if (mode == 0)
                System.out.println(
                    "decompostiton mode is"
                    + " :- NO_DECOMPOSITION");
            else if (mode == 1)
                System.out.println(
                    "decompostiton mode is "
                    + ":- CANONICAL_DECOMPOSITION");
            else
                System.out.println(
                    "decompostiton mode is "
                    + ":- FULL_DECOMPOSITION. ");
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

**输出:**

```
decompostiton mode is :- CANONICAL_DECOMPOSITION

```

**例 2:**

```
// Java program to demonstrate
// getDecomposition() method

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

            // getting decompostiton mode
            // using getDecomposition() mehtod
            int mode = col.getDecomposition();

            // display result
            if (mode == 0)
                System.out.println(
                    "decompostiton mode is"
                    + " :- NO_DECOMPOSITION");
            else if (mode == 1)
                System.out.println(
                    "decompostiton mode is "
                    + ":- CANONICAL_DECOMPOSITION");
            else
                System.out.println(
                    "decompostiton mode is "
                    + ":- FULL_DECOMPOSITION. ");
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
decompostiton mode is :- NO_DECOMPOSITION

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # getDecomposition–](https://docs.oracle.com/javase/9/docs/api/java/text/Collator.html#getDecomposition--)