# Java 中 MatchResult end()方法，带示例

> 原文:[https://www . geesforgeks . org/match result-end-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matchresult-end-method-in-java-with-examples/)

**匹配结果界面**的 **end()** 方法用于获取匹配结果中最后一个匹配字符后的偏移量。

**语法:**

```java
public int end()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回最后一个匹配字符后的**偏移量**

**异常:**如果还没有尝试匹配，或者如果之前的匹配操作失败，此方法将抛出**illegalstatexception**。

以下示例说明了 MatchResult.end()方法:

**例 1:**

```java
// Java code to illustrate end() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(G*s)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GeeksForGeeks";

        // Create a matcher for the input String
        MatchResult matcher
            = pattern
                  .matcher(stringToBeMatched);

        while (((Matcher)matcher).find()) {
            // Get the last index of match result
            System.out.println(matcher.end());
        }
    }
}
```

**Output:**

```java
5
13

```

**例 2:**

```java
// Java code to illustrate end() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(G*G)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFG FGF GFG";

        // Create a matcher for the input String
        MatchResult matcher
            = pattern
                  .matcher(stringToBeMatched);

        while (((Matcher)matcher).find()) {
            // Get the last index of match result
            System.out.println(matcher.end());
        }
    }
}
```

**Output:**

```java
1
3
6
9
11

```