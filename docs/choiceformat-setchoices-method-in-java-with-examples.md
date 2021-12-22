# Java 中的 ChoiceFormat setChoices()方法，示例

> 原文:[https://www . geeksforgeeks . org/choice format-set choices-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-setchoices-method-in-java-with-examples/)

**[Java . text . ChoiceFormat](https://www.geeksforgeeks.org/tag/java-choiceformat/)**类的 **setChoices()** 方法用于在 Choice format 对象中设置定义了限制和格式的新的 Choice 项。

**语法:**

```
public void setChoices(double[] limits, String[] formats)
```

**参数**:该方法取以下参数:

*   **Limit:** is a binary array containing option limit.
*   **Format:** is an array of string values, which will contain the format of choiceitem.

**返回值:**这个方法不返回任何东西。

**异常:**如果限制或格式为空，该方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

以下是说明**设置选择()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// setChoices() method

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

            // creating and initializing new double array
            double[] newlimit = { 1, 2, 3 };

            // creating and initializing new String array
            String[] newformat = { "sun", "mon", "tue" };

            // setting the limit and format in
            // ChoiceFormat Object
            // using setChoices() method
            cf1.setChoices(newlimit, newformat);

            // display the result
            System.out.print("updated Choiceformat object: "
                             + cf1.toPattern());
        }
        catch (NullPointerException e) {
            System.out.println("\nLimit or Format is null");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
updated Choiceformat object: 1.0#sun|2.0#mon|3.0#tue

```

**例 2:**

```
// Java program to demonstrate
// setChoices() method

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

            // creating and initializing new double array
            double[] newlimit = null;

            // creating and initializing new String array
            String[] newformat = { "sun", "mon", "tue" };

            // setting the limit and format in
            // ChoiceFormat Object
            // using setChoices() method
            cf1.setChoices(newlimit, newformat);

            // display the result
            System.out.print("updated Choiceformat object: "
                             + cf1.toPattern());
        }
        catch (NullPointerException e) {
            System.out.println("Limit or Format is null");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
Limit or Format is null
Exception thrown: java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/choice format . html # setChoices-double:A-Java . lang . string:A-](https://docs.oracle.com/javase/9/docs/api/java/text/ChoiceFormat.html#setChoices-double:A-java.lang.String:A-)