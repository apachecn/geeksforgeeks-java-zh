# Java 中的 Matcher 区域(int，int)方法，示例

> 原文:[https://www . geesforgeks . org/matcher-regionint-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/matcher-regionint-int-method-in-java-with-examples/)

**匹配器类**的**区域(int，int)** 方法限制该区域被模式匹配。该区域必须小于或等于前一个区域，但不能大于前一个区域。否则会导致 IndexOutOfBoundsException。此方法返回具有新匹配区域的匹配器。

**语法:**

```java
public Matcher region(int startIndex, int endIndex)

```

**参数:**该方法取两个参数:

*   **startindex** serves as the starting index of the new constraint region.
*   **End index** is the end index of the new constraint region.

**返回值:**这个方法返回一个**匹配器**，要匹配的区域，对比。

**异常:**如果:

*   startIndex 位置阿力 endIndex(结束索引)是阿俊，
*   StartIndex or endIndex is greater than the length of the input sequence.
*   startIndex 位置哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟 endIndex(结束索引)，吴经熊和吴经熊**对束缚性知觉的指数化**。

以下示例说明了 Matcher.region()方法:

**例 1:**

```java
// Java code to illustrate region() method

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

        System.out.println("Before changing region, "
                           + " Groups found are: ");

        while (matcher.find()) {

            // Get the group matched using group() method
            System.out.println(matcher.group());
        }

        System.out.println("\nAfter changing region, "
                           + " Groups found are: ");

        // Restrict the region to 0, 10
        // using region() method
        Matcher matcher1
            = matcher.region(0, 10);

        while (matcher1.find()) {

            // Get the group matched using group() method
            System.out.println(matcher1.group());
        }
    }
}
```

**输出:**

```java
Before changing region,  Groups found are: 
Geeks
Geeks
Geeks
Geeks

After changing region,  Groups found are: 
Geeks

```

**例 2:**

```java
// Java code to illustrate region() method

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

        System.out.println("Before changing region, "
                           + " Groups found are: ");

        while (matcher.find()) {

            // Get the group matched using group() method
            System.out.println(matcher.group());
        }

        System.out.println("\nAfter changing region, "
                           + " Groups found are: ");

        // Restrict the region to 0, 5
        // using region() method
        Matcher matcher1 = matcher.region(0, 5);

        while (matcher1.find()) {

            // Get the group matched using group() method
            System.out.println(matcher1.group());
        }
    }
}
```

**输出:**

```java
Before changing region,  Groups found are: 
FGF
FGF

After changing region,  Groups found are: 
FGF

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/regex/matcher . html # region-int-int-](https://docs.oracle.com/javase/9/docs/api/java/util/regex/Matcher.html#region-int-int-)