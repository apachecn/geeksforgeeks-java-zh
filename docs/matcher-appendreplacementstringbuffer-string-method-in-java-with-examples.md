# Java 中的 Matcher appendReplacement(StringBuffer，String)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-appendreplacementstringbuffer-string-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-appendreplacementstringbuffer-string-method-in-java-with-examples/)

**匹配器类**的**追加替换(StringBuffer，String)** 方法表现为追加替换方法。此方法读取输入字符串，并用匹配器字符串中匹配的模式替换它。

**语法:**

```
public Matcher 
    appendReplacement(StringBuffer buffer, 
                      String stringToBeReplaced)

```

**参数:**该方法取两个参数:

*   **Buffer** : StringBuffer for storing the target string.
*   [T0】 String tobe replaced 【T1]: the string to be replaced in the matcher.

**返回值:**该方法返回一个替换了目标字符串的**匹配器**。

**异常:**此方法抛出以下异常:

*   **[illegalstateexception]** : If you have not tried to match, or if the previous matching operation failed.
*   [T0】 IllegalArgumentException 【T1]: If the replacement string refers to the named capture group that does not exist in the pattern.
*   **Indexoutoofboundsexception** : If the replacement string refers to the capture group that does not exist in the pattern.

下面的例子说明了 Matcher.appendReplacement()方法:

**例 1:**

```
// Java code to illustrate appendReplacement() method

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

        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "GEEKS";
        StringBuffer buffer = new StringBuffer();

        // Replace every matched pattern
        // with the target String
        // using appendReplacement() method
        while (matcher.find()) {
            matcher.appendReplacement(buffer,
                                      stringToBeReplaced);
        }
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
// Java code to illustrate appendReplacement() method

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
        // using appendReplacement() method
        while (matcher.find()) {
            matcher.appendReplacement(buffer,
                                      stringToBeReplaced);
        }
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

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # append replacement-Java . lang . stringbuffer-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#appendReplacement-java.lang.StringBuffer-java.lang.String-)