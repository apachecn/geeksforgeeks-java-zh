# Java 中 MatchResult group()方法，带示例

> 原文:[https://www . geesforgeks . org/match result-group-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matchresult-group-method-in-java-with-examples/)

使用**匹配结果界面**的**组()**方法获取与前一个匹配结果匹配的输入子序列。
**语法:**

```
public String group()
```

**参数:**该方法不取任何参数。
**返回值:**该方法返回**字符串**，该字符串是上一次匹配的输入子序列。
**异常:**如果还没有尝试匹配，或者之前的匹配操作失败，这个方法抛出**illegalstatexception**。
以下示例说明了 MatchResult.group()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate group() method

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
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the current matcher state
        MatchResult result
            = matcher.toMatchResult();
        System.out.println("Current Matcher: "
                           + result);

        while (matcher.find()) {
            // Get the group matched using group() method
            System.out.println(matcher.group());
        }
    }
}
```

**Output:** Current Matcher: java.util.regex.Matcher[pattern=(G*s) region=0,13 lastmatch=] s s  

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate group() method

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
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the current matcher state
        MatchResult result
            = matcher.toMatchResult();
        System.out.println("Current Matcher: "
                           + result);

        while (matcher.find()) {
            // Get the group matched using group() method
            System.out.println(matcher.group());
        }
    }
}
```

**Output:** Current Matcher: java.util.regex.Matcher[pattern=(G*G) region=0,11 lastmatch=] G G G G G