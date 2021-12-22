# 用示例选择 Java 中的 applyPattern()方法

> 原文:[https://www . geesforgeks . org/choice format-apply pattern-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-applypattern-method-in-java-with-examples/)

**java.text.ChoiceFormat** 类的 **applyPattern()** 方法用于通过覆盖当前限制和格式来设置当前 ChoiceFormat 的新模式文本。这个新模式将是 ChoiceFormat
的极限和格式的结合**语法:**

```
public void applyPattern(String newPattern)
```

**参数**:该方法以**新模式**为参数，为 ChoiceFormat 的新文本模式。
**返回值:**此方法不返回任何内容。
**异常:**如果指定的 newPattern 为空，该方法抛出 **NullPointerException** 。
以下是举例说明 **applyPattern()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate applyPattern() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing limit
        double[] limit = { 1, 2, 3 };

        // creating and initializing format
        String[] format = { "sun", "mon", "tue" };

        // creating and initializing ChoiceFormat
        ChoiceFormat cf
            = new ChoiceFormat(limit, format);

        // display the result
        System.out.println("current pattern : "
                           + cf.toPattern());

        // applying the new pattern
        // using applyPattern() method
        cf.applyPattern("4#wed| 5#thu | 6#fri | 7#sat");

        // display the result
        System.out.println("\nnew pattern : "
                           + cf.toPattern());
    }
}
```

**Output:** 

```
current pattern : 1.0#sun|2.0#mon|3.0#tue

new pattern : 4.0#wed|5.0#thu |6.0#fri |7.0#sat
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate applyPattern() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing limit
            double[] limit = { 1, 2, 3 };

            // creating and initializing format
            String[] format = { "sun", "mon", "tue" };

            // creating and initializing ChoiceFormat
            ChoiceFormat cf
                = new ChoiceFormat(limit, format);

            // display the result
            System.out.println("current pattern : "
                               + cf.toPattern());

            // applying the new pattern
            // using applyPattern() method
            cf.applyPattern(null);

            // display the result
            System.out.println("\nnew pattern : "
                               + cf.toPattern());
        }
        catch (NullPointerException e) {
            System.out.println("\nString is Null");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
current pattern : 1.0#sun|2.0#mon|3.0#tue

String is Null
Exception thrown : java.lang.NullPointerException
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/choice format . html # apply pattern-Java . lang . string-T4】