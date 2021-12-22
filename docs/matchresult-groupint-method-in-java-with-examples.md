# Java 中 MatchResult 组(int)方法，示例

> 原文:[https://www . geesforgeks . org/match result-group int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matchresult-groupint-method-in-java-with-examples/)

**匹配结果界面**的**组(int group)** 方法用于从指定的组中获取已经完成的匹配结果的组索引。

**语法:**

```java
public String group(int group)

```

**参数:**该方法取一个参数**组**，该组是需要匹配模式的组索引的组。

**返回值:**该方法返回指定组中第一个匹配字符的**索引**。

**异常:**此方法抛出:

*   如果尚未尝试匹配，或者如果先前的匹配操作失败，则**illegalstatexception**。
*   如果给定索引的模式中没有捕获组，则**indexout of BoundSexception**。

下面的例子说明了 MatchResult.group()方法:

**例 1:**

```java
// Java code to illustrate group() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(Geeks)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "Geeks For Geeks";

        // Create a matcher for the input String
        MatchResult matcher
            = pattern
                  .matcher(stringToBeMatched);

        while (((Matcher)matcher).find()) {
            // Get the group matched using group() method
            System.out.println(matcher.group(1));
        }
    }
}
```

**Output:**

```java
Geeks
Geeks

```

**例 2:**

```java
// Java code to illustrate group() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(GFG)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFG FGFGFGFGFGFGF GFG";

        // Create a matcher for the input String
        MatchResult matcher
            = pattern
                  .matcher(stringToBeMatched);

        while (((Matcher)matcher).find()) {
            // Get the group matched using group() method
            System.out.println(matcher.group(0));
        }
    }
}
```

**Output:**

```java
GFG
GFG
GFG
GFG
GFG

```