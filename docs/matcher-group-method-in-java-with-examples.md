# Java 中的 Matcher group()方法，带示例

> 原文:[https://www . geesforgeks . org/matcher-group-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-group-method-in-java-with-examples/)

使用**匹配器类**的**组()**方法获取与前一个匹配结果匹配的输入子序列。

**语法:**

```java
public String group()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回**字符串**，该字符串是与前一个匹配匹配的输入子序列。

**异常:**如果还没有尝试匹配，或者如果之前的匹配操作失败，此方法将抛出**illegalstatexception**。

下面的例子说明了 Matcher.group()方法:

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

**Output:**

> current Matcher:Java . util . regex . Matcher[pattern =(G * s)region = 0，13 lastmatch=]
> s
> s

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

**Output:**

> 当前匹配器:Java . util . regex . Matcher[pattern =(G * G)region = 0，11 last match =]
> G
> G
> G
> G
> G

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#group--)