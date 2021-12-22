# Java 中 Matcher replaceAll(函数)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-replace all function-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-replaceallfunction-method-in-java-with-examples/)

**匹配器类**的**替换所有(函数)**方法表现为一种追加和替换方法。此方法用参数中传递的函数替换匹配器中匹配的模式的所有实例。
**语法:**

```java
public String replaceAll(
        Function replacerFunction)
```

**参数:**该方法取一个参数**replace function**，该函数定义了匹配器的替换。
**返回值:**该方法返回一个**字符串**，目标字符串通过替换字符串来构造。
**异常:**此方法抛出以下异常:

*   **空指针异常**:如果替换函数为空
*   **ConcurrentModificationException**:如果检测到替换器功能修改了该匹配器的状态

以下示例说明了 Matcher.replaceAll()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate replaceAll() method

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
        // using replaceAll() method
        System.out.println("After Replacement: "
                           + matcher
                                 .replaceAll(
                                     x -> x.group().toUpperCase()));
    }
}
```