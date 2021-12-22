# Java 中 MatchResult end(int)方法，示例

> 原文:[https://www . geesforgeks . org/match result-endint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matchresult-endint-method-in-java-with-examples/)

**匹配结果界面**的**结束(int group)** 方法用于从指定的组中获取已经完成的匹配结果的结束索引之后的偏移量。

**语法:**

```java
public int end(int group)

```

**参数:**该方法取一个参数**组**，需要匹配图案结束索引后的偏移量。

**返回值:**该方法返回指定组匹配结束索引后的**偏移量**。

**异常:**此方法抛出:

*   如果尚未尝试匹配，或者如果先前的匹配操作失败，则**illegalstatexception**。
*   如果给定组的模式中没有捕获组，则**IndexOutOfBoundsException**。

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
            System.out.println(matcher.end(1));
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
            System.out.println(matcher.end(0));
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