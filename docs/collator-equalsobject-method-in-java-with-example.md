# Java 中的排序器等于(对象)方法，示例

> 原文:[https://www . geesforgeks . org/collator-equalsobject-method-in-Java-with-example/](https://www.geeksforgeeks.org/collator-equalsobject-method-in-java-with-example/)

**java.text.Collator 类**的 **equals()** 方法用于检查两个 Collator 对象是否相同。

**语法:**

```
public boolean equals(Object that)
```

**参数**:该方法取两个**整理器对象**，两者之间进行比较。
**返回值:**如果两个排序器对象彼此相等，则返回真，否则返回假。
以下是举例说明**等于()**方法:
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

            // Creating and initializing new simple rule
            String simple = "< a< b< c< d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col_1
                = new RuleBasedCollator(simple);

            // Creating and initializing
            // Collator Object
            Collator col_2
                = Collator.getInstance(Locale.US);

            // compare both object
            // using equals() method
            boolean i = col_1.equals(col_2);

            // display result
            if (i)
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

```
java.text.RuleBasedCollator@5eb2e1c2 is not equal to java.text.RuleBasedCollator@289747d6
```