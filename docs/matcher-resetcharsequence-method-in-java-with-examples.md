# Java 中的匹配器重置(CharSequence)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-resetcharsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-resetcharsequence-method-in-java-with-examples/)

**匹配器类**的**重置(字符序列输入)**方法用于重置该匹配器，并将作为参数传递的输入字符串插入该匹配器。

**语法:**

```java
public Matcher reset(CharSequence input)

```

**参数:**该方法取参数**输入**，即复位后要插入匹配器的字符串。

**返回值:**此方法用此输入复位后返回此**匹配器**。

以下示例说明了 Matcher.reset()方法:

**例 1:**

```java
// Java code to illustrate reset() method

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
        String stringToBeMatched = "GeeksForGeeks";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the current matcher state
        System.out.println("Current Matcher: "
                           + matcher.toMatchResult());

        // Reset the Matcher using reset() method
        String newStringToBeMatched
            = "GeeksGeeksGeeks";
        matcher = matcher
                      .reset(newStringToBeMatched);

        // Get the current matcher state
        System.out.println("Current Matcher after Reset: "
                           + matcher.toMatchResult());
    }
}
```

**Output:**

> Current Matcher:Java . util . regex . Matcher[pattern = Geeks region = 0，13 last match =]
> Reset 后的 Current Matcher:Java . util . regex . Matcher[pattern = Geeks region = 0，15 lastmatch=]

**例 2:**

```java
// Java code to illustrate reset() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "GFG";

        // Create a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFGFGFGFGFGFGFGFGFG";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the current matcher state
        System.out.println("Current Matcher: "
                           + matcher.toMatchResult());

        // Reset the Matcher using reset() method
        String newStringToBeMatched
            = "GFG means GeeksForGeeks";
        matcher = matcher
                      .reset(newStringToBeMatched);

        // Get the current matcher state
        System.out.println("Current Matcher after Reset: "
                           + matcher.toMatchResult());
    }
}
```

**Output:**

> 当前匹配器:Java . util . regex . Matcher[模式=GFG 区域=0，19 lastmatch=]
> 重置后的当前匹配器:Java . util . regex . Matcher[模式=GFG 区域=0，23 lastmatch=]

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#reset-java.lang.CharSequence-)