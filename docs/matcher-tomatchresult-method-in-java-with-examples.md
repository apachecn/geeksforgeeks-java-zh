# Java 中 Matcher toMatchResult()方法，带示例

> 原文:[https://www . geesforgeks . org/matcher-to matchresult-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-tomatchresult-method-in-java-with-examples/)

**匹配器类**的 **toMatchResult()** 方法用于获取该匹配器的当前结果状态。

**语法:**

```
public MatchResult toMatchResult()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个**匹配结果**，匹配结果状态为该匹配器的当前匹配结果状态。

以下示例说明了 Matcher.toMatchResult()方法:

**例 1:**

```
// Java code to illustrate toMatchResult() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "Geeks";

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

        // Get the result state
        // using toMatchResult() method
        System.out.println("Result: "
                           + matcher.toMatchResult());
    }
}
```

**输出:**

> 结果:Java . util . regex . matcher[pattern = Geeks region = 0，13 last matcher =]

**例 2:**

```
// Java code to illustrate toMatchResult() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "GFG";

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

        // Get the result state
        // using toMatchResult() method
        System.out.println("Result: "
                           + matcher.toMatchResult());
    }
}
```

**输出:**

> 结果:java.util.regex.Matcher【模式=GFG 地区=0，19 last match =】

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#toMatchResult--)