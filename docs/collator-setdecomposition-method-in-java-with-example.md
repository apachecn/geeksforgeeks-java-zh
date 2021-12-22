# Java 中的排序器集合分解()方法，示例

> 原文:[https://www . geesforgeks . org/collator-set declaration-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-setdecomposition-method-in-java-with-example/)

**java.text.Collator 类**的**set declaration()**方法用于设置该 Collator 的分解模式。
**语法:**

```
public void setDecomposition(int decompositionMode)
```

**参数**:该方法以**整数值**作为参数，代表该整理器的等效分解模式。
**返回值:**这个方法没有什么可返回的。
以下是举例说明 **setDecomposition()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// setDecomposition() method

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

            // setting decomposition mode
            // into the Collator object
            // using setDecomposition() mehtod
            col.setDecomposition(
                Collator.CANONICAL_DECOMPOSITION);

            // getting decomposition mode
            int mode = col.getDecomposition();

            // display result
            if (mode == 0)
                System.out.println(
                    "decompostiton mode"
                    + " is :- NO_DECOMPOSITION");
            else if (mode == 1)
                System.out.println(
                    "decompostiton mode is"
                    + " :- CANONICAL_DECOMPOSITION");
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

**Output:** 

```
decompostiton mode is :- CANONICAL_DECOMPOSITION
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// setDecomposition() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing Collator Object
            Collator col = Collator.getInstance(Locale.UK);

            // setting decomposition mode
            // into the Collator object
            // using setDecomposition() mehtod
            col.setDecomposition(Collator.FULL_DECOMPOSITION);

            // getting decompostiton mode
            int mode = col.getDecomposition();

            // display result
            if (mode == 0)
                System.out.println(
                    "decompostiton mode"
                    + " is :- NO_DECOMPOSITION");
            else if (mode == 1)
                System.out.println(
                    "decompostiton mode is"
                    + " :- CANONICAL_DECOMPOSITION");
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

**Output:** 

```
decompostiton mode is :- FULL_DECOMPOSITION. 
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collator . html # setDecomposition-int-T4】