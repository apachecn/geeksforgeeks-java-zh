# Matcher 在 Java 中有一个 AnchoringBounds()方法，示例

> 原文:[https://www . geeksforgeeks . org/matcher-hasanchoringbounds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-hasanchoringbounds-method-in-java-with-examples/)

**匹配器类**的 **hasAnchoringBounds()** 方法用于检查该匹配器是否有锚定边界。通过锚定边界，这意味着匹配者将匹配像^这样的锚，如果锚定边界设置为真，匹配者将获得$ 1。此方法返回一个表示相同内容的布尔值。

**语法:**

```
public boolean hasAnchoringBounds()

```

**参数:**该方法不取参数。

**返回值:**这个方法返回一个**布尔值**，说明这个匹配器是否有锚定边界

下面的例子说明了 Matcher.hasAnchoringBounds()方法:

**例 1:**

```
// Java code to illustrate hasAnchoringBounds() method

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

        // Check if this matcher has anchoring bounds or not
        // using hasAnchoringBounds() method
        System.out.println("Does this matcher"
                           + " has anchoring bounds: "
                           + matcher.hasAnchoringBounds());
    }
}
```

**输出:**

```
Does this matcher has anchoring bounds: true

```

**例 2:**

```
// Java code to illustrate hasAnchoringBounds() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(F*F)";

        // Create a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = " FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // set the anchoring bounds to true
        matcher = matcher
                      .useAnchoringBounds(false);

        // Check if this matcher has anchoring bounds or not
        // using hasAnchoringBounds() method
        System.out.println("Does this matcher"
                           + " has anchoring bounds: "
                           + matcher.hasAnchoringBounds());
    }
}
```

**输出:**

```
Does this matcher has anchoring bounds: false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # hasAnchoringBounds–](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#hasAnchoringBounds--)