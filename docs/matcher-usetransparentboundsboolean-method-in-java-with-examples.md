# Matcher 在 Java 中使用 TransparentBounds(布尔)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-usetransparentbounds boolean-in-Java-method-with-examples/](https://www.geeksforgeeks.org/matcher-usetransparentboundsboolean-method-in-java-with-examples/)

**匹配器类**的**使用透明边界(布尔)**方法设置该匹配器的透明边界。通过透明边界，这意味着如果透明边界设置为真，匹配器将在区域边界之外匹配匹配模式以获得匹配。此方法返回一个具有修改后的透明边界的匹配器。

**语法:**

```java
public boolean useTransparentBounds(
               boolean setTransparentBounds)

```

**参数:**这个方法取一个参数 **setTransparentBounds** ，这个参数是一个描述这个匹配器的透明边界的布尔值。

**返回值:**这个方法返回一个**匹配器**，修改后的透明边界。

下面的例子说明了 Matcher.useTransparentBounds()方法:

**例 1:**

```java
// Java code to illustrate useTransparentBounds() method

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

        // set the transparent bounds to true
        // using useTransparentBounds() method
        matcher = matcher
                      .useTransparentBounds(true);

        // Check if this matcher
        // has transparent bounds or not
        System.out.println("Does this matcher"
                               + " has transparent bounds: "
                               + matcher.hasTransparentBounds());
    }
}
```

**输出:**

```java
Does this matcher has transparent bounds: true

```

**例 2:**

```java
// Java code to illustrate useTransparentBounds() method

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

        // set the transparent bounds to true
        // using useTransparentBounds() method
        matcher = matcher
                      .useTransparentBounds(false);

        // Check if this matcher
        // has transparent bounds or not
        System.out.println("Does this matcher"
                               + " has transparent bounds: "
                               + matcher.hasTransparentBounds());
    }
}
```

**输出:**

```java
Does this matcher has transparent bounds: false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # useTransparentBounds-boolean-](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#useTransparentBounds-boolean-)