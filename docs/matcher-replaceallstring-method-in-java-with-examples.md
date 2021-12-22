# Java 中 Matcher replaceAll(String)方法示例

> 原文:[https://www . geesforgeks . org/matcher-replace all string-in-Java-method-with-examples/](https://www.geeksforgeeks.org/matcher-replaceallstring-method-in-java-with-examples/)

**匹配器类**的**替换所有(字符串)**方法表现为一种追加和替换方法。此方法读取输入字符串，并用匹配器字符串中匹配的模式替换它。

**语法:**

```
public String replaceAll(String stringToBeReplaced)

```

**参数:**该方法取一个参数 **stringToBeReplaced** ，即匹配器中要替换的字符串。

**返回值:**该方法返回一个**字符串**，目标字符串通过替换字符串来构造。

下面的例子说明了 Matcher.replaceAll()方法:

**例 1:**

```
// Java code to illustrate replaceAll() method

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

        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "GFG";
        StringBuilder builder
            = new StringBuilder();

        // Replace every matched pattern
        // with the target String
        // using replaceAll() method
        System.out.println("After Replacement: "
                           + matcher
                                 .replaceAll(stringToBeReplaced));
    }
}
```

**输出:**

```
Before Replacement: GeeksForGeeks Geeks for For Geeks Geek
After Replacement: GFGForGFG GFG for For GFG Geek

```

**例 2:**

```
// Java code to illustrate replaceAll() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "(FGF)";

        // Create a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFGFGFGFGFGFGFGFGFG FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "GFG";
        StringBuilder builder
            = new StringBuilder();

        // Replace every matched pattern
        // with the target String
        // using replaceAll() method
        System.out.println("After Replacement: "
                           + matcher
                                 .replaceAll(stringToBeReplaced));
    }
}
```

**输出:**

```
After Replacement: GGFGGGFGGGFGGGFGGFG GFG GFG GFG GFG

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # replace all-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#replaceAll-java.lang.String-)