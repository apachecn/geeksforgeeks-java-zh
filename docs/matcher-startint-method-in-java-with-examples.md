# Java 中的 Matcher start(int)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-startint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-startint-method-in-java-with-examples/)

**匹配器类**的**开始(int group)** 方法用于从指定的组中获取已经完成的匹配结果的开始索引。

**语法:**

```
public int start(int group)

```

**参数:**该方法取一个参数**组**，该组是需要匹配模式的起始索引的组。

**返回值:**该方法返回指定组中第一个匹配字符的**索引**。

**异常:**此方法抛出:

*   如果尚未尝试匹配，或者如果先前的匹配操作失败，则**illegalstatexception**。
*   如果给定索引的模式中没有捕获组，则**indexout of BoundSexception**。

下面的例子说明了 Matcher.start()方法:

**例 1:**

```
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
            System.out.println(matcher.start(1));
        }
    }
}
```

**Output:**

> current Matcher:Java . util . regex . Matcher[pattern =(G * s)region = 0，13 lastmatch=]
> 4
> 12

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
        String stringToBeMatched
            = "GFGFGFGFGFGFGFGFGFG";

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
            System.out.println(matcher.start(0));
        }
    }
}
```

**Output:**

> 当前匹配器:Java . util . regex . Matcher[pattern =(G * G)region = 0，19 last match =]
> 0
> 2
> 4
> 6
> 8
> 10
> 12
> 14
> 16
> 18

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#start-int-)