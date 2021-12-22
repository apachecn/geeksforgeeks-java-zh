# Java 中的 MessageFormat parse()方法，示例:Set–1

> 原文:[https://www . geesforgeks . org/message format-parse-method-in-Java-with-example-set-1/](https://www.geeksforgeeks.org/messageformat-parse-method-in-java-with-example-set-1/)

**java.text.MessageFormat** 类的 **parse()** 方法用于从索引的开头解析字符串对象。
**语法:**

```
public Object[] parse(String source)
               throws ParseException
```

**参数**:该方法将字符串源作为将要进行解析的参数。
**返回值:**这个方法返回对象数组作为输出。
**异常:**如果指定字符串的开头无法解析，此方法抛出 **ParseException** 。
以下是说明**解析()**方法的示例:
**示例 1:**

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

            // parsing the string
            // according to MessageFormat
            // using parse() method
            Object[] hash = mf.parse(str);

            // display the result
            System.out.println("Parsed value are :");
            for (int i = 0; i < hash.length; i++)
                System.out.println(hash[i]);
        }
        catch (ParseException e) {
            System.out.println("\nString is Null");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Parsed value are :
10.456
30.444
20.325
```

**例 2:**

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
                = new MessageFormat("{0, date}, {2, time}, {1, number}");

            // creating and initializing String source
            String str = "10, 20, 30";

            // parsing the string
            // according to MessageFormat
            // using parse() method
            Object[] hash = mf.parse(str);

            // display the result
            System.out.println("Parsed value are :");
            for (int i = 0; i < hash.length; i++)
                System.out.println(hash[i]);
        }
        catch (ParseException e) {
            System.out.println("String is Null");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
String is Null
Exception thrown : java.text.ParseException: MessageFormat parse error!
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # parse-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#parse-java.lang.String-)