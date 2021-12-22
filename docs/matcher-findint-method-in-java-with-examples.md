# Java 中的 Matcher find(int)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-find int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-findint-method-in-java-with-examples/)

**匹配器类**的 **find(int start)** 方法试图在作为参数传递的指定子序列编号之后找到找到模式的输入序列的下一个子序列。它返回一个显示相同内容的布尔值。

**语法:**

```java
public boolean find(int start)

```

**参数:**该方法取一个参数**开始**，该参数是子序列编号，在该编号之后将找到下一个子序列。

**返回值:**这个方法返回一个**布尔值**，显示输入序列的子序列是否找到这个匹配器的模式

**异常:**如果 start 小于零或大于输入序列的长度，该方法将抛出**indexout of boundsexception**。

下面的例子说明了 Matcher.find()方法:

**例 1:**

```java
// Java code to illustrate find() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "Geeks";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GeeksForGeeks";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the subsequence
        // using find() method
        System.out.println(matcher.find(1));
    }
}
```

**输出:**

```java
true

```

**例 2:**

```java
// Java code to illustrate find() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the regex to be checked
        String regex = "GFG";

        // Create a pattern from regex
        Pattern pattern
            = Pattern.compile(regex);

        // Get the String to be matched
        String stringToBeMatched
            = "GFGFGFGFGFGFGFGFGFG";

        // Create a matcher for the input String
        Matcher matcher
            = pattern
                  .matcher(stringToBeMatched);

        // Get the subsequence
        // using find() method
        System.out.println(matcher.find(0));
    }
}
```

**输出:**

```java
true

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#find-int-)