# Java 中的 MatchResult start(int)方法，示例

> 原文:[https://www . geesforgeks . org/match result-startint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matchresult-startint-method-in-java-with-examples/)

**匹配结果界面**的**开始(int group)** 方法用于从指定的组中获取已经完成的匹配结果的开始索引。

**语法:**

```java
public int start(int group)

```

**参数:**该方法取一个参数**组**，该组是需要匹配模式的起始索引的组。

**返回值:**该方法返回指定组中第一个匹配字符的**索引**。

**异常:**如果还没有尝试匹配，或者之前的匹配操作失败，这个方法抛出:

*   **【非法状态】** 。
*   **Index out of bounds exception** If there is no capture group in the pattern of the given index.

下面的例子说明了 MatchResult.start()方法:

**例 1:**

```java
// Java code to illustrate start() method

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
            // Get the first index of match result
            System.out.println(matcher.start(1));
        }
    }
}
```

**输出:**

```java
4
12

```

**例 2:**

```java
// Java code to illustrate start() method

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
            = "GFGFGFGFGFGFGFGFGFG";

        // Create a matcher for the input String
        MatchResult matcher
            = pattern
                  .matcher(stringToBeMatched);

        while (((Matcher)matcher).find()) {
            // Get the first index of match result
            System.out.println(matcher.start(0));
        }
    }
}
```

**输出:**

```java
0
2
4
6
8
10
12
14
16
18

```

=