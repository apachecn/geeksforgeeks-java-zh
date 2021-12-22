# Java 中的 Matcher find()方法，示例

> 原文:[https://www . geesforgeks . org/matcher-find-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-find-method-in-java-with-examples/)

**匹配器类**的 **find()** 方法试图找到输入序列中找到模式的下一个子序列。它返回一个显示相同内容的布尔值。

**语法:**

```java
public boolean find()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**布尔值**，显示输入序列的子序列是否找到这个匹配器的模式

下面的例子说明了 Matcher.find()方法:

**例 1:**

```java
// Java code to illustrate find() method

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

        // Get the subsequence
        // using find() method
        System.out.println(matcher.find());
    }
}
```

**输出:**

```java
true

```

**例 2:**

```java
// Java code to illustrate find() method

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

        // Get the subsequence
        // using find() method
        System.out.println(matcher.find());
    }
}
```

**输出:**

```java
true

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#find--)