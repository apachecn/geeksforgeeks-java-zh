# Java 中的 MessageFormat parse()方法，示例:Set–2

> 原文:[https://www . geesforgeks . org/message format-parse-method-in-Java-with-example-set-2/](https://www.geeksforgeeks.org/messageformat-parse-method-in-java-with-example-set-2/)

**java.text.MessageFormat** 类的 **parse()** 方法用于从 parse()方法中传递的解析位置开始解析字符串对象。
**语法:**

```
public Object[] parse(String source,
                      ParsePosition pos)
```

**参数**:该方法以下列参数为参数。

*   **来源:-** 解析将要执行的字符串。
*   **pos :-** 是解析的起始索引。

**返回值:**该方法返回对象数组作为输出。
**异常:**如果解析位置为空，该方法抛出**空指针异常**。
以下是举例说明**解析()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// parse() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing  MessageFormat
            MessageFormat mf
                = new MessageFormat("{0, number, #}, {2, number, #.#}, {1, number, #.##}");
            ;

            // creating and initializing String source
            String str = "10.456, 20.325, 30.444";

            // creating and initializing ParsePosition
            ParsePosition pos = new ParsePosition(3);

            // parsing the string starting from pos
            // according to MessageFormat
            // using parse() method
            Object[] hash = mf.parse(str, pos);

            // display the result
            System.out.println("Parsed value are :");
            for (int i = 0; i < hash.length; i++)
                System.out.println(hash[i]);
        }
        catch (NullPointerException e) {
            System.out.println("\nParse position is Null");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Parsed value are :
456
30.444
20.325
```