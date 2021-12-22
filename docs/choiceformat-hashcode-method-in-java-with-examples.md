# 用示例选择 Java 中的 hashCode()方法

> 原文:[https://www . geesforgeks . org/choice format-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-hashcode-method-in-java-with-examples/)

**[Java . text . choice format](https://www.geeksforgeeks.org/tag/java-choiceformat/)**类的 **hashCode()** 方法用于获取 choice 格式对象的 hash 代码。该 hashcode 值以整数形式返回。

**语法:**

```java
public int hashCode()
```

**参数**:此方法不接受任何参数。

**返回值:**该方法将选择格式对象的**哈希码**返回为整数。

下面是举例说明 **hashCode()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing ChoiceFormat
        ChoiceFormat cf
            = new ChoiceFormat(
                "4#wed| 5#thu | 6#fri | 7#sat");

        // getting hashcode of  ChoiceFormat object
        // using hashCode() method
        int hash = cf.hashCode();

        // display the result
        System.out.print("hashCode :- " + hash);
    }
}
```

**输出:**

```java
hashCode :- 113634 

```

**例 2:**

```java
// Java program to demonstrate hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing limit
        double[] limit = { 1, 2, 3, 4 };

        // creating and initializing format
        String[] format
            = { "add", "sub", "multiply", "divide" };

        // creating and initializing ChoiceFormat
        ChoiceFormat cf
            = new ChoiceFormat(limit, format);

        // getting hashcode of  ChoiceFormat object
        // using hashCode() method
        int hash = cf.hashCode();

        // display the result
        System.out.print("hashCode :- " + hash);
    }
}
```

**输出:**

```java
hashCode :- -1331463043

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/choice format . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/text/ChoiceFormat.html#hashCode--)