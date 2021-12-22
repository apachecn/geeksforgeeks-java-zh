# Java 中的 Matcher start()方法，示例

> 原文:[https://www . geesforgeks . org/matcher-start-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-start-method-in-java-with-examples/)

**匹配器类**的 **start()** 方法用于获取已经完成的匹配结果的开始索引。

**语法:**

```
public int start()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回匹配的第一个字符的**索引**。0

**异常:**如果还没有尝试匹配，或者如果之前的匹配操作失败，此方法将抛出**illegalstatexception**。

下面的例子说明了 Matcher.start()方法:

**例 1:**

```
// Java code to illustrate start() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(G*k)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched = "Geeks";

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
            // Get the first index of match result
            System.out.println(matcher.start());
        }
    }
}
```

**Output:**

> current Matcher:Java . util . regex . Matcher[pattern =(G * k)region = 0，5 lastmatch=]
> 3

**例 2:**

```
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
        String stringToBeMatched = "GFG";

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
            // Get the first index of match result
            System.out.println(matcher.start());
        }
    }
}
```

**Output:**

> current Matcher:Java . util . regex . Matcher[pattern =(G * G)region = 0，3 lastmatch=]
> 0
> 2

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#start--)