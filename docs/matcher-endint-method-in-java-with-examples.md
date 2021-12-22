# Java 中的 Matcher end(int)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-endint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-endint-method-in-java-with-examples/)

**匹配器类**的**结束(int group)** 方法用于从指定的组中获取已经完成的匹配结果的结束索引之后的偏移量。

**语法:**

```
public int end(int group)

```

**参数:**该方法取一个参数**组**，需要匹配图案结束索引后的偏移量。

**返回值:**该方法返回指定组匹配结束索引后的**偏移量**。

**异常:**此方法抛出:

*   如果尚未尝试匹配，或者如果先前的匹配操作失败，则**illegalstatexception**。
*   如果给定组的模式中没有捕获组，则**IndexOutOfBoundsException**。

以下示例说明了 Matcher.end()方法:

**例 1:**

```
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
            // Get the last index of match result
            System.out.println(matcher.end(1));
        }
    }
}
```

**Output:**

> current Matcher:Java . util . regex . Matcher[pattern =(G * s)region = 0，13 lastmatch=]
> 5
> 13

**例 2:**

```
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
            // Get the last index of match result
            System.out.println(matcher.end(0));
        }
    }
}
```

**Output:**

> 当前匹配器:Java . util . regex . Matcher[pattern =(G * G)region = 0，11 last match =]
> 1
> 3
> 6
> 9
> 11

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#end-int-)