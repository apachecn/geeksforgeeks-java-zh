# Java 中 Matcher toString()方法，带示例

> 原文:[https://www . geesforgeks . org/matcher-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-tostring-method-in-java-with-examples/)

**匹配器类**的 **toString()** 方法用于获取该匹配器的字符串表示。此方法从对象类派生而来，其行为方式类似。

**语法:**

```
public String toString()

```

**参数:**该方法不取参数。

**返回值:**这个方法返回一个**字符串值**，这是这个匹配器的字符串表示。

以下示例说明了 Matcher.toString()方法:

**例 1:**

```
// Java code to illustrate toString() method

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
            = " Geeks for For Geeks Geek";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // Get the String representation of this matcher
        // using toString() method
        System.out.println(matcher.toString());
    }
}
```

**输出:**

```
java.util.regex.Matcher[pattern=(Geeks) region=0,25 lastmatch=]

```

**例 2:**

```
// Java code to illustrate toString() method

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
            = "FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // Get the String representation of this matcher
        // using toString() method
        System.out.println(matcher.toString());
    }
}
```

**输出:**

```
java.util.regex.Matcher[pattern=(GFG) region=0,15 lastmatch=]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#toString--)