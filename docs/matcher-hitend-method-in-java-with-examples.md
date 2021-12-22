# Java 中 Matcher hitEnd()方法，带示例

> 原文:[https://www . geesforgeks . org/matcher-hitend-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-hitend-method-in-java-with-examples/)

**匹配器类**的 **hitEnd()** 方法用于检查该匹配器上的图案匹配是否已经停止。当在匹配器中没有找到更多匹配的组时，匹配结束。此方法返回一个表示相同内容的布尔值。

**语法:**

```
public boolean hitEnd()

```

**参数:**该方法不取参数。

**返回值:**该方法返回一个**布尔值**，表示该匹配器是否完成匹配。

以下示例说明了 Matcher.hitEnd()方法:

**例 1:**

```
// Java code to illustrate hitEnd() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(Geeks)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GeeksForGeeks Geeks for For Geeks Geek";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        while (matcher.find()) {

            System.out.println("Group matched: "
                               + matcher.group());

            // Check if the matching has ended
            // using hitEnd() method
            System.out.println("Has matching hit end: "
                               + matcher.hitEnd());
        }

        // Check if the matching has ended
        // using hitEnd() method
        System.out.println("Has matching hit end: "
                           + matcher.hitEnd());
    }
}
```

**输出:**

```
Group matched: Geeks
Has matching hit end: false
Group matched: Geeks
Has matching hit end: false
Group matched: Geeks
Has matching hit end: false
Group matched: Geeks
Has matching hit end: false
Has matching hit end: true

```

**例 2:**

```
// Java code to illustrate hitEnd() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(GFG)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFGFGFGFGFGFGFGFGFG FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        while (matcher.find()) {

            System.out.println("Group matched: "
                               + matcher.group());

            // Check if the matching has ended
            // using hitEnd() method
            System.out.println("Has matching hit end: "
                               + matcher.hitEnd());
        }

        // Check if the matching has ended
        // using hitEnd() method
        System.out.println("Has matching hit end: "
                           + matcher.hitEnd());
    }
}
```

**输出:**

```
Group matched: GFG
Has matching hit end: false
Group matched: GFG
Has matching hit end: false
Group matched: GFG
Has matching hit end: false
Group matched: GFG
Has matching hit end: false
Group matched: GFG
Has matching hit end: false
Group matched: GFG
Has matching hit end: false
Group matched: GFG
Has matching hit end: false
Has matching hit end: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # hitEnd–](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#hitEnd--)