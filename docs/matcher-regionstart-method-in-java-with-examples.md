# Java 中 Matcher regionStart()方法，带示例

> 原文:[https://www . geesforgeks . org/matcher-regionstart-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-regionstart-method-in-java-with-examples/)

**匹配器类**的 **regionStart()** 方法用于获取当前匹配器中模式要匹配的区域的 startIndex。此方法返回一个整数值，它是此匹配器区域的开始索引。

**语法:**

```java
public int regionStart()

```

**参数:**该方法不取参数。

**返回值:**这个方法返回一个**整数值**，它是这个匹配器区域的开始索引。

以下示例说明了 Matcher.regionStart()方法:

**例 1:**

```java
// Java code to illustrate regionStart() method

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

        // Get previous startIndex of region
        // using regionStart() method
        System.out.println("Before changing region, "
                           + " Region starts from: "
                           + matcher.regionStart());

        // Restrict the region to 2, 10
        matcher = matcher.region(2, 10);

        // Get previous startIndex of region
        // using regionStart() method
        System.out.println("After changing region, "
                           + " Region starts from: "
                           + matcher.regionStart());
    }
}
```

**输出:**

```java
Before changing region,  Region starts from: 0
After changing region,  Region starts from: 2

```

**例 2:**

```java
// Java code to illustrate regionStart() method

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
            = pattern.matcher(stringToBeMatched);

        // Get previous startIndex of region
        // using regionStart() method
        System.out.println("Before changing region, "
                           + " Region starts from: "
                           + matcher.regionStart());

        // Restrict the region to 5, 10
        matcher = matcher.region(5, 10);

        // Get previous startIndex of region
        // using regionStart() method
        System.out.println("After changing region, "
                           + " Region starts from: "
                           + matcher.regionStart());
    }
}
```

**输出:**

```java
Before changing region,  Region starts from: 0
After changing region,  Region starts from: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # regionStart–](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#regionStart--)