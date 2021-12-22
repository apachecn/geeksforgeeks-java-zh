# Matcher replace Java 中 First(函数)方法示例

> 原文:[https://www . geeksforgeeks . org/matcher-replacefirst function-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-replacefirstfunction-method-in-java-with-examples/)

**匹配器类**的**替换第一个(函数)**方法表现为一个追加和替换方法。此方法用参数中传递的函数替换匹配器中匹配的模式的第一个实例。

**语法:**

```java
public String replaceFirst(
        Function replacerFunction)

```

**参数:**该方法取一个参数**replace function**，该函数定义了匹配器的替换。

**返回值:**该方法返回一个**字符串**，目标字符串通过替换字符串来构造。

**异常:**此方法抛出以下异常:

*   null 指针异常:你好你好空值
*   **Concurrentmodification Exception** : If it is detected that the replacer function has modified the state of this matcher.

下面的例子说明了 Matcher.replaceFirst()方法:

**例 1:**

```java
// Java code to illustrate replaceFirst() method

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
        String stringToBeReplaced = "Geeks";
        StringBuilder builder
            = new StringBuilder();

        // Replace every matched pattern
        // with the target String
        // using replaceFirst() method
        System.out.println("After Replacement: "
                           + matcher
                                 .replaceFirst(
                                     x -> x.group().toUpperCase()));
    }
}
```

**输出:**

```java
Before Replacement: GeeksForGeeks Geeks for For Geeks Geek
After Replacement: GEEKSForGeeks Geeks for For Geeks Geek

```

**例 2:**

```java
// Java code to illustrate replaceFirst() method

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
            = "GFG FGF GFG GFG FGF";

        // Create a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Get the String to be replaced
        String stringToBeReplaced = "(GFG)";
        StringBuilder builder
            = new StringBuilder();

        // Replace every matched pattern
        // with the target String
        // using replaceFirst() method
        System.out.println("After Replacement: "
                           + matcher
                                 .replaceFirst(
                                     x -> x.group().toLowerCase()));
    }
}
```

**输出:**

```java
Before Replacement: GFG FGF GFG GFG FGF
After Replacement: GFG fgf GFG GFG FGF

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # replace first-Java . util . function . function-](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#replaceFirst-java.util.function.Function-)