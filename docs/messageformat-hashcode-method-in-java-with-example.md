# Java 中的 MessageFormat hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/message format-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-hashcode-method-in-java-with-example/)

**java.text.MessageFormat** 类的 **hashCode()** 方法用于获取该消息格式对象的 hashCode。
**语法:**

```
public int hashCode()
```

**参数**:该方法不把任何参数作为参数。
**返回值:**这个方法返回这个消息格式对象的哈希代码。
以下是举例说明 **hashCode()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {2, date, #.#}, {4, time}");

        // getting hash code
        // for this MessageFormat Object
        // using hashCode() method
        int hash = mf.hashCode();

        // display the result
        System.out.println("Hashcode is : " + hash);
    }
}
```

**Output:** 

```
Hashcode is : 1408
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {4, time}");

        // getting hash code
        // for this MessageFormat Object
        // using hashCode() method
        int hash = mf.hashCode();

        // display the result
        System.out.println("Hashcode is : " + hash);
    }
}
```

**Output:** 

```
Hashcode is : 44
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # hashCode–T4】