# Java 中的 Matcher reset()方法，示例

> 原文:[https://www . geesforgeks . org/matcher-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-reset-method-in-java-with-examples/)

**matcher 类**的 **reset()** 方法是用来重置这个 Matcher 的，为了更好的理解，建议有 java regex 子包中 [Pattern 和 Matcher 类](https://www.geeksforgeeks.org/regular-expressions-in-java/)的先验知识。在这里，我们将借助 Java 程序来说明这一点。

**语法:**

```
public Matcher reset()
```

**参数:**该方法不取任何参数。

**返回值:**此方法复位后返回此**火柴人**。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate reset() method
// of Matcher class

// Importing class from java.util.regex package
// where regex is a subpackage
import java.util.regex.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the regex to be checked
        // taking via string input
        String regex = "Geeks";

        // Creating a pattern from regex
        // using Pattern class
        Pattern pattern = Pattern.compile(regex);

        // Getting the String to be matched
        String stringToBeMatched = "GeeksForGeeks";

        // Creating a matcher for the input String
        // using Matcher class
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // Reseting the Matcher using reset() method
        matcher = matcher.reset();

        // Getting the current matcher state
        // using tomatchResult() method and
        // printing it
        System.out.println(matcher.toMatchResult());
    }
}
```

**Output**

```
java.util.regex.Matcher$ImmutableMatchResult@448139f0
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate reset() method
// of Matcher class

// Importing class from java.util.regex package
// where regex is a subpackage
import java.util.regex.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Getting the regex to be checked
        String regex = "GFG";

        // Creating a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Getting the String to be matched
        String stringToBeMatched = "GFGFGFGFGFGFGFGFGFG";

        // Creating a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // Resetting the Matcher
        // using reset() method
        matcher = matcher.reset();

        // Getting the current matcher state
        // using toMatchResult() method
        System.out.println(matcher.toMatchResult());
    }
}
```

**Output**

```
java.util.regex.Matcher$ImmutableMatchResult@448139f0
```