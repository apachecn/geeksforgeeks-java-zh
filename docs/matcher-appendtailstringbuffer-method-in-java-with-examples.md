# Java 中的 Matcher appendTail(StringBuffer)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-appendtailstringbuffer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-appendtailstringbuffer-method-in-java-with-examples/)

**匹配器类**的 **appendTail(StringBuffer)** 方法表现为一种追加和替换方法。此方法读取输入字符串，并将其附加到尾部位置的给定字符串。

**语法:**

```
public StringBuffer appendTail(StringBuffer buffer)

```

**参数:**这个方法取一个参数**缓冲区**，它是存储目标字符串的 StringBuffer。

**返回值:**该方法返回一个替换了目标字符串的**字符串。**

下面的例子说明了 Matcher.appendTail()方法:

**例 1:**

```
// Java code to illustrate appendTail() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(Geeks)";

        // Create a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched = "GeeksForGeeks Geeks for For Geeks Geek";

        // Create a matcher for the input String
        Matcher matcher = pattern.matcher(stringToBeMatched);

        System.out.println("Before Replacement: " + stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "GEEKS";
        StringBuffer buffer = new StringBuffer();

        // Replace every matched pattern
        // with the target String
        while (matcher.find()) {
            matcher.appendReplacement(buffer,
                                      stringToBeReplaced);
        }

        // Add the replaced string at the tail
        // using the appendTail() method
        matcher.appendTail(buffer);

        // Print the replaced matcher
        System.out.println("After Replacement: "
                           + buffer.toString());
    }
}
```

**输出:**

```
Before Replacement: GeeksForGeeks Geeks for For Geeks Geek
After Replacement: GEEKSForGEEKS GEEKS for For GEEKS Geek

```

**例 2:**

```
// Java code to illustrate appendTail() method

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
            = "FGF FGF FGF FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "GFG";
        StringBuffer buffer = new StringBuffer();

        // Replace every matched pattern
        // with the target String
        while (matcher.find()) {
            matcher.appendReplacement(buffer,
                                      stringToBeReplaced);
        }

        // Add the replaced string at the tail
        // using the appendTail() method
        matcher.appendTail(buffer);

        // Print the replaced matcher
        System.out.println("After Replacement: "
                           + buffer.toString());
    }
}
```

**输出:**

```
Before Replacement: FGF FGF FGF FGF
After Replacement: GFG GFG GFG GFG

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # appendTail-Java . lang . stringbuffer-](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#appendTail-java.lang.StringBuffer-)