# Java 中的 Matcher groupCount()方法，带示例

> 原文:[https://www . geesforgeks . org/matcher-group count-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-groupcount-method-in-java-with-examples/)

**匹配器类**的 **groupCount()** 方法用于获取该匹配器模式中的捕获组数。

**语法:**

```
public int groupCount()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回该匹配器模式下**的捕获组数**。

以下示例说明了 Matcher.groupCount()方法:

**例 1:**

```
// Java code to illustrate groupCount() method

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

        // Get the number of capturing groups
        // using groupCount() method
        System.out.println(matcher.groupCount());
    }
}
```

**输出:**

```
0

```

**例 2:**

```
// Java code to illustrate groupCount() method

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

        // Get the number of capturing groups
        // using groupCount() method
        System.out.println(matcher.groupCount());
    }
}
```

**输出:**

```
0

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#groupCount--)