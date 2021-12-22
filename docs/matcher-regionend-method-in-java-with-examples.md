# Java 中 Matcher regionEnd()方法，带示例

> 原文:[https://www . geesforgeks . org/matcher-regionend-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-regionend-method-in-java-with-examples/)

**匹配器类**的 **regionEnd()** 方法用于获取当前匹配器中模式要匹配的区域的 endIndex。这个方法返回一个整数值，它是这个匹配器区域的 endIndex。

**语法:**

```
public int regionEnd()

```

**参数:**该方法不取参数。

**返回值:**这个方法返回一个**整数值**，它是这个匹配器区域的 endIndex。

以下示例说明了 Matcher.regionEnd()方法:

**例 1:**

```
// Java code to illustrate regionEnd() method

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

        // Get previous endIndex of region
        // using regionEnd() method
        System.out.println("Before changing region, "
                           + " Region ends from: "
                           + matcher.regionEnd());

        // Restrict the region to 0, 10
        matcher = matcher.region(0, 10);

        // Get previous endIndex of region
        // using regionEnd() method
        System.out.println("After changing region, "
                           + " Region ends from: "
                           + matcher.regionEnd());
    }
}
```

**输出:**

```
Before changing region,  Region ends from: 38
After changing region,  Region ends from: 10

```

**例 2:**

```
// Java code to illustrate regionEnd() method

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
            = "GFGFGFGFGFGFGFGFGFG FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // Get previous endIndex of region
        // using regionEnd() method
        System.out.println("Before changing region, "
                           + " Region ends from: "
                           + matcher.regionEnd());

        // Restrict the region to 0, 5
        matcher = matcher.region(0, 5);

        // Get previous endIndex of region
        // using regionEnd() method
        System.out.println("After changing region, "
                           + " Region ends from: "
                           + matcher.regionEnd());
    }
}
```

**输出:**

```
Before changing region,  Region ends from: 35
After changing region,  Region ends from: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # regionEnd–](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#regionEnd--)