# 匹配器替换 Java 中的 First(字符串)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-replaceferstring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-replacefirststring-method-in-java-with-examples/)

[Matcher 类](https://www.geeksforgeeks.org/regular-expressions-in-java/)的 ***replaceFirst()*** 方法表现为一种追加和替换方法。此方法读取输入字符串，并用匹配器字符串中的第一个匹配模式替换它。

**语法:**

```
public String replaceFirst(String stringToBeReplaced)
```

**参数:**要替换的字符串，即匹配器中要替换的字符串。

**返回类型:**通过替换字符串构造目标字符串的字符串。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate replaceFirst() Method
// of Matcher class

// Importing required classes
import java.util.regex.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the regex to be checked
        String regex = "(Geeks)";

        // Creating a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Getting the String to be matched
        String stringToBeMatched
            = "GeeksForGeeks Geeks for For Geeks Geek";

        // Creating a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // Displaying the string to be matched
        // before replacing
        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Getting the string to be replaced
        String stringToBeReplaced = "GFG";
        StringBuilder builder = new StringBuilder();

        // Replacing every matched pattern with the target
        // string using replaceFirst() method
        System.out.println(
            "After Replacement: "
            + matcher.replaceFirst(stringToBeReplaced));
    }
}
```

**Output:** 

```
Before Replacement: GeeksForGeeks Geeks for For Geeks Geek
After Replacement: GFGForGeeks Geeks for For Geeks Geek
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate replaceFirst() Method

// Importing required classes
import java.util.regex.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Getting the regex to be checked
        String regex = "(FGF)";

        // Creating a pattern from regex
        Pattern pattern = Pattern.compile(regex);

        // Getting the string to be matched
        String stringToBeMatched = "FGF FGF FGF FGF";

        // Creating a matcher for the input String
        Matcher matcher
            = pattern.matcher(stringToBeMatched);

        // Printing string on console
        // before replacement
        System.out.println("Before Replacement: "
                           + stringToBeMatched);

        // Getting the string to be replaced
        String stringToBeReplaced = "GFG";
        StringBuilder builder = new StringBuilder();

        // Replacing every matched pattern with target
        // string using replaceFirst() method and printing
        // the string to be replaced
        System.out.println(
            "After Replacement: "
            + matcher.replaceFirst(stringToBeReplaced));
    }
}
```

**Output:** 

```
Before Replacement: FGF FGF FGF FGF
After Replacement: GFG FGF FGF FGF
```