# Java 中的 MessageFormat toPattern()方法，示例

> 原文:[https://www . geesforgeks . org/message format-topattern-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-topattern-method-in-java-with-example/)

**java.text.MessageFormat** 类的 **toPattern()** 方法用于获取该消息格式对象的当前模式的字符串表示。
**语法:**

```
public String toPattern()
```

**参数**:该方法不把任何参数作为参数。
**返回值:**这个方法返回这个消息格式对象当前模式的字符串表示。
以下是举例说明 **toPattern()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toPattern() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {2, date, #.#}, {4, time}");

        // getting the pattern
        // of this MessageFormat Object
        // using toPattern() method
        String patt = mf.toPattern();

        // display the result
        System.out.println("current pattern of MessageFormat Object : " + patt);
    }
}
```

**Output:** 

```
current pattern of MessageFormat Object : {0, number, #}, {2, date, #.#}, {4, time}
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toPattern() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {4, time}");

        // getting the pattern
        // of this MessageFormat Object
        // using toPattern() method
        String patt = mf.toPattern();

        // display the result
        System.out.println("current pattern of MessageFormat Object : " + patt);
    }
}
```

**Output:** 

```
current pattern of MessageFormat Object : {0, number, #}, {4, time}
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # toPattern–T4】