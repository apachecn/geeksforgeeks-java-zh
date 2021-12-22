# Java 中的 Matcher appendTail(StringBuilder)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-appendtailsringbuilder-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-appendtailstringbuilder-method-in-java-with-examples/)

**匹配器类**的**appendTail(StringBuilder)**方法表现为一种追加和替换方法。此方法读取输入字符串，并将其附加到尾部位置的给定 StringBuilder。

**语法:**

```
public StringBuilder appendTail(StringBuilder builder)

```

**参数:**这个方法取一个参数 **builder** ，它是存储目标字符串的 StringBuilder。

**返回值:**该方法返回一个替换了目标字符串的**字符串生成器**。

下面的例子说明了 Matcher.appendTail()方法:

**例 1:**

```
// Java code to illustrate appendTail() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(Geeks)";

        // Create a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GeeksForGeeks Geeks for For Geeks Geek";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "GFG";
        StringBuilder builder = new StringBuilder();

        // Replace every matched pattern
        // with the target String
        while (matcher.find()) {
            matcher
                .appendReplacement(builder,
                                   stringToBeReplaced);
        }

        // Add the replaced string at the tail
        // using the appendTail() method
        matcher.appendTail(builder);

        // Print the replaced matcher
        System.out.println("After Replacement: "
                           + builder.toString());
    }
}
```

**输出:**

```
Before Replacement: GeeksForGeeks Geeks for For Geeks Geek
After Replacement: GFGForGFG GFG for For GFG Geek

```

**例 2:**

```
// Java code to illustrate appendTail() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(FGF)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = " FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "Geeks";
        StringBuilder builder = new StringBuilder();

        // Replace every matched pattern
        // with the target String
        while (matcher.find()) {
            matcher
                .appendReplacement(builder,
                                   stringToBeReplaced);
        }

        // Add the replaced string at the tail
        // using the appendTail() method
        matcher.appendTail(builder);

        // Print the replaced matcher
        System.out.println("After Replacement: "
                           + builder.toString());
    }
}
```

**输出:**

```
Before Replacement:  FGF GFG GFG FGF
After Replacement:  Geeks GFG GFG Geeks

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # appendTail-Java . lang . stringbuilder-](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#appendTail-java.lang.StringBuilder-)