# Java 中的 Matcher pattern()方法，带示例

> 原文:[https://www . geesforgeks . org/matcher-pattern-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-pattern-method-in-java-with-examples/)

**匹配器类**的**模式()**方法用于获取该匹配器要匹配的模式。

**语法:**

```java
public Pattern pattern()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个**模式**，即该匹配器要匹配的模式。

以下示例说明了 Matcher.pattern()方法:

**例 1:**

```java
// Java code to illustrate pattern() method

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
            = pattern.matcher(stringToBeMatched);

        // Get the Pattern using pattern() method
        System.out.println("Pattern: "
                           + matcher.pattern());
    }
}
```

**输出:**

```java
Pattern: Geeks

```

**例 2:**

```java
// Java code to illustrate pattern() method

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
            = pattern.matcher(stringToBeMatched);

        // Get the Pattern using pattern() method
        System.out.println("Pattern: "
                           + matcher.pattern());
    }
}
```

**输出:**

```java
Pattern: GFG

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#pattern--)