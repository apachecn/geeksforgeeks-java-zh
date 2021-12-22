# 匹配器使用 Java 中的 nchoringBounds(布尔)方法，示例

> 原文:[https://www . geeksforgeeks . org/matcher-useanchoringboundsboondo-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-useanchoringboundsboolean-method-in-java-with-examples/)

**使用**匹配器类**的**方法来设置该匹配器的锚定边界。通过锚定边界，这意味着匹配者将匹配像^这样的锚，如果锚定边界设置为真，匹配者将获得$ 1。此方法返回一个具有修改的锚定边界的匹配器。

**语法:**

```java
public boolean useAnchoringBounds(
               boolean setAnchoringBounds)

```

**参数:**该方法采用参数**设置锚定边界**，这是一个布尔值，描述了要修改的匹配器的锚定边界。

**返回值:**该方法返回一个锚定边界修改后的**匹配器**。

下面的例子说明了 Matcher.useAnchoringBounds()方法:

**例 1:**

```java
// Java code to illustrate useAnchoringBounds() method

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

        // set the anchoring bounds to true
        // using useAnchoringBounds() method
        matcher = matcher
                      .useAnchoringBounds(true);

        // Check if this matcher has anchoring bounds or not
        System.out.println("Does this matcher"
                           + " has anchoring bounds: "
                           + matcher.hasAnchoringBounds());
    }
}
```

**输出:**

```java
Does this matcher has anchoring bounds: true

```

**例 2:**

```java
// Java code to illustrate useAnchoringBounds() method

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
            = "FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // set the anchoring bounds to true
        // using useAnchoringBounds() method
        matcher = matcher
                      .useAnchoringBounds(false);

        // Check if this matcher has anchoring bounds or not
        System.out.println("Does this matcher"
                           + " has anchoring bounds: "
                           + matcher.hasAnchoringBounds());
    }
}
```

**输出:**

```java
Does this matcher has anchoring bounds: false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # usenchoringbounds-boolean-](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#useAnchoringBounds-boolean-)