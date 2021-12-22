# Matcher 有 Java 中的 hasTransparentBounds()方法，示例

> 原文:[https://www . geesforgeks . org/matcher-hastransparentbounds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-hastransparentbounds-method-in-java-with-examples/)

**匹配器类**的 **hasTransparentBounds()** 方法用于检查该匹配器是否有透明边界。通过透明边界，这意味着如果透明边界设置为真，匹配器将在区域边界之外匹配匹配模式以获得匹配。此方法返回一个表示相同内容的布尔值。

**语法:**

```java
public boolean hasTransparentBounds()

```

**参数:**该方法不取参数。

**返回值:**这个方法返回一个**布尔值**，说明这个匹配器是否有透明边界

以下示例说明了 Matcher.hasTransparentBounds()方法:

**例 1:**

```java
// Java code to illustrate hasTransparentBounds() method

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
            = pattern
                  .matcher(stringToBeMatched);

        // Check if this matcher
        // has transparent bounds or not
        // using hasTransparentBounds() method
        System.out.println("Does this matcher"
                               + " has transparent bounds: "
                               + matcher
                                     .hasTransparentBounds());
    }
}
```

**输出:**

```java
Does this matcher has transparent bounds: false

```

**例 2:**

```java
// Java code to illustrate hasTransparentBounds() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(F*F)";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFGFGFGFGFGFGFGFGFG FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // set the transparent bounds to true
        matcher = matcher
                      .useTransparentBounds(true);

        // Check if this matcher
        // has transparent bounds or not
        // using hasTransparentBounds() method
        System.out.println("Does this matcher"
                               + " has transparent bounds: "
                               + matcher
                                     .hasTransparentBounds());
    }
}
```

**输出:**

```java
Does this matcher has transparent bounds: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # hasTransparentBounds–](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#hasTransparentBounds--)