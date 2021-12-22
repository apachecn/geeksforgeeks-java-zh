# Java 中的 Matcher requireEnd()方法，示例

> 原文:[https://www . geesforgeks . org/matcher-required-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-requireend-method-in-java-with-examples/)

**匹配器类**的 **requireEnd()** 方法用于检查是否有任何锚的组合导致匹配被限制在终点。这些锚可以是任何锚，例如单词锚或前瞻锚。此方法返回一个表示相同内容的布尔值。

**语法:**

```
public boolean requireEnd()

```

**参数:**该方法不取参数。

**返回值:**该方法返回一个**布尔值**，说明锚的任何组合是否导致匹配在末尾被限制。

以下示例说明了 Matcher.requireEnd()方法:

**例 1:**

```
// Java code to illustrate requireEnd() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        // with an anchor
        String regex = "Geeks{content}quot;;

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFG GFG GEEKS Geeks";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        matcher.find();

        // Check if a match has been found
        // using requireEnd() method
        System.out.println("Has any anchor "
                           + "bounded the search: "
                           + matcher.requireEnd());
    }
}
```

**输出:**

```
Has any anchor bounded the search: true

```

**例 2:**

```
// Java code to illustrate requireEnd() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        // without any anchor
        String regex = "Geeks";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFG GFG GEEKS Geeks";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        matcher.find();

        // Check if a match has been found
        // using requireEnd() method
        System.out.println("Has any anchor "
                           + "bounded the search: "
                           + matcher.requireEnd());
    }
}
```

**输出:**

```
Has any anchor bounded the search: false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # required–](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#requireEnd--)