# Matcher 用示例匹配 Java 中的()方法

> 原文:[https://www . geesforgeks . org/matcher-matches-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-matches-method-in-java-with-examples/)

使用**匹配器类**的**匹配()**方法得到该模式是否与该匹配器匹配的结果。它返回一个显示相同内容的布尔值。

**语法:**

```java
public boolean matches()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个**布尔值**，表示该模式是否与该匹配器匹配。

以下示例说明了 Matcher.matches()方法:

**例 1:**

```java
// Java code to illustrate matches() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "Geeks";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GeeksForGeeks";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the result state
        // using matches() method
        System.out.println("Result: "
                           + matcher.matches());
    }
}
```

**输出:**

```java
Result: false

```

**例 2:**

```java
// Java code to illustrate matches() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "GFG";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFGFGFGFGFGFGFGFGFG";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the result state
        // using matches() method
        System.out.println("Result: "
                           + matcher.matches());
    }
}
```

**输出:**

```java
Result: false

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#matches--)