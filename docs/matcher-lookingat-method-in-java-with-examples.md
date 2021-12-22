# Java 中的 Matcher lookingAt()方法，带示例

> 原文:[https://www . geesforgeks . org/matcher-lookingat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-lookingat-method-in-java-with-examples/)

**匹配器类**的 **lookingAt()** 方法尝试在匹配器中部分或全部匹配图案。它返回一个布尔值，显示模式是否从模式开始部分或完全匹配。

**语法:**

```
public boolean lookingAt()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**布尔值**，显示输入序列的前缀是否匹配这个匹配器的模式。

下面的例子说明了 Matcher.lookingAt()方法:

**例 1:**

```
// Java code to illustrate lookingAt() method

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

        // Get the possible result
        // using lookingAt() method
        System.out.println(matcher.lookingAt());
    }
}
```

**输出:**

```
true

```

**例 2:**

```
// Java code to illustrate lookingAt() method

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

        // Get the possible result
        // using lookingAt() method
        System.out.println(matcher.lookingAt());
    }
}
```

**输出:**

```
true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # lookingAt–](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#lookingAt--)