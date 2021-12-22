# Java 中的 Matcher 组(String)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-group string-in-Java-method-with-examples/](https://www.geeksforgeeks.org/matcher-groupstring-method-in-java-with-examples/)

**匹配器类**的**组(字符串)**方法用于从指定的字符串中获取已经完成的匹配结果的组。

**语法:**

```java
public String group(String string)

```

**参数:**该方法取一个参数**字符串**，即需要匹配模式的组索引的字符串。

**返回值:**该方法从指定字符串中返回匹配组的**组**。

**异常:**此方法抛出:

*   如果尚未尝试匹配，或者如果先前的匹配操作失败，则**illegalstatexception**。
*   如果给定名称的模式中没有捕获组，则**indexout of BoundSexception**。

下面的例子说明了 Matcher.group()方法:

**例 1:**

```java
// Java code to illustrate end() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "\\b(?<Geeks>[A-Za-z\\s]+)";

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
            System.out.println(matcher.group("Geeks"));
        }
    }
}
```

**Output:**

> 当前 Matcher:Java . util . regex . Matcher[pattern = \ b(？ <geeks>[A-Za-z\s]+)区域=0，13 last match =]
> geeks forgeeks</geeks>

**例 2:**

```java
// Java code to illustrate end() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

       // Get the regex to be checked
        String regex = "\\b(?<GFG>[A-Za-z\\s]+)";

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
            System.out.println(matcher.group("GFG"));
        }
    }
}
```

**Output:**

> 当前 Matcher:Java . util . regex . Matcher[pattern = \ b(？ <gfg>[A-Za-z\s]+)区域=0，11 lastmatch=]
> GFG FGF GFG</gfg>

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#group-java.lang.String-)