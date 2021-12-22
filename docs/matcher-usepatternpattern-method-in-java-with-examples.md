# Matcher 在 Java 中使用 Pattern(模式)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-usepatternpattern-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-usepatternpattern-method-in-java-with-examples/)

使用**匹配器类**的 **usePattern()** 方法获取该匹配器要匹配的模式。

**语法:**

```java
public Matcher usePattern(Pattern newPattern)

```

**参数:**该方法取一个参数**新花样**，即需要设置的新花样。

**返回值:**该方法返回一个带有新花样的**匹配器**。

**异常:**如果 newPattern 为空，该方法抛出 **IllegalArgumentException** 。

下面的例子说明了 Matcher.usePattern()方法:

**例 1:**

```java
// Java code to illustrate usePattern() method

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

        // Get the new Pattern
        String newPattern = "GFG";

        // Get the Pattern using pattern method
        System.out.println("Old Pattern: "
                           + matcher.pattern());

        // Set the newPattern using usePattern() method
        matcher = matcher
                      .usePattern(
                          Pattern
                              .compile(newPattern));

        // Get the Pattern
        // using pattern method
        System.out.println("New Pattern: "
                           + matcher.pattern());
    }
}
```

**输出:**

```java
Old Pattern: Geeks
New Pattern: GFG

```

**例 2:**

```java
// Java code to illustrate usePattern() method

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
            = patter
                  n.matcher(stringToBeMatched);

        // Get the new Pattern
        String newPattern = "Geeks";

        // Get the Pattern using pattern method
        System.out.println("Old Pattern: "
                           + matcher.pattern());

        // Set the newPattern using usePattern() method
        matcher = matcher
                      .usePattern(
                          Pattern
                              .compile(newPattern));

        // Get the Pattern
        // using pattern method
        System.out.println("New Pattern: "
                           + matcher.pattern());
    }
}
```

**输出:**

```java
Old Pattern: GFG
New Pattern: Geeks

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#usePattern-java.util.regex.Pattern-)