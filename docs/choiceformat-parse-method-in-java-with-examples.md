# 用示例选择 Java 中的 Format parse()方法

> 原文:[https://www . geesforgeks . org/choice format-parse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-parse-method-in-java-with-examples/)

**[Java . text . ChoiceFormat](https://www.geeksforgeeks.org/tag/java-choiceformat/)**类的 **parse()** 方法用于获取 choice format 对象中特定格式的限制值。

**语法:**

```
public Number parse(String text, ParsePosition status)
```

**参数**:该方法取以下参数:

*   **Text:** is the text whose limit value must be found in string format.
*   **Status:** is the index where this option exists, and the limit value of this index can be found.

**返回值:**这个方法返回一个指定类型的**数组**，它是附加到 ChoiceFormat 对象的格式。

**异常:**如果字符串文本或状态为空，该方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

以下是说明**解析()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// getFormats() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // creating and initializing ChoiceFormat
            ChoiceFormat cf1
                = new ChoiceFormat(
                    "4#wed| 5#thu | 6#fri | 7#sat");

            // creating and initializing ParsePosition
            ParsePosition par = new ParsePosition(0);

            // getting limit of particular format
            // of ChoiceFormat Object
            // using getFormats() method
            Number limit
                = cf1.parse("wed", par);

            // display the result
            System.out.print("limit: "
                             + limit.intValue());
        }
        catch (NullPointerException e) {
            System.out.println("\nString is Null");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
limit: 4

```

**例 2:**

```
// Java program to demonstrate
// getFormats() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // creating and initializing ChoiceFormat
            ChoiceFormat cf1
                = new ChoiceFormat(
                    "4#wed| 5#thu | 6#fri | 7#sat");

            // creating and initializing ParsePosition
            ParsePosition par = new ParsePosition(0);

            // getting limit of particular format
            // of ChoiceFormat Object
            // using getFormats() method
            Number limit
                = cf1.parse(null, par);

            // display the result
            System.out.print("limit: "
                             + limit.intValue());
        }
        catch (NullPointerException e) {
            System.out.println("String is Null");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
String is Null
Exception thrown: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/choice format . html # parse-Java . lang . string-Java . text . parse position-](https://docs.oracle.com/javase/9/docs/api/java/text/ChoiceFormat.html#parse-java.lang.String-java.text.ParsePosition-)