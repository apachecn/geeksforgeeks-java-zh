# Java 中的匹配器引用放置(字符串)方法，示例

> 原文:[https://www . geeksforgeeks . org/matcher-quotereplementstring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-quotereplacementstring-method-in-java-with-examples/)

**匹配器类**的**引用放置(字符串)**方法用于获取作为参数传递的字符串的替换字符串文本。这个字符串文字充当替换方法的参数。因此，quoteReplacement()方法充当替换方法中的中间方法。

**语法:**

```
public static String quoteReplacement(String string)

```

**参数:**该方法取一个参数**字符串**，即 Matcher 中要替换的字符串。

**返回值:**这个方法返回一个**字符串文字**，它是匹配器的替换字符串。

以下示例说明了 Matcher.quoteReplacement()方法:

**例 1:**

```
// Java code to illustrate quoteReplacement() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "Geek";

        // Create a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Get the String to be matched
        String
            stringToBeMatched
            = "GeeksForGeeks Geeks for For Geeks Geek";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "Geeks";

        // Get the String literal
        // using quoteReplacement() method
        System.out.println(
            matcher
                .quoteReplacement(stringToBeReplaced));
    }
}
```

**输出:**

```
Geeks

```

**例 2:**

```
// Java code to illustrate quoteReplacement() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "FGF";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String
            stringToBeMatched
            = "GFGFGFGFGFGFGFGFGFG FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "GFG";

        // Get the String literal
        // using quoteReplacement() method
        System.out.println(
            matcher
                .quoteReplacement(stringToBeReplaced));

        System.out.println(
            matcher
                .replaceAll(
                    matcher
                        .quoteReplacement(
                            stringToBeReplaced)));
    }
}
```

**输出:**

```
GFG
GGFGGGFGGGFGGGFGGFG GFG GFG GFG GFG

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#quoteReplacement-java.lang.String-)