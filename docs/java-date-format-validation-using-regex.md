# Java |使用 Regex 的日期格式验证

> 原文:[https://www . geesforgeks . org/Java-date-format-validation-use-regex/](https://www.geeksforgeeks.org/java-date-format-validation-using-regex/)

我们使用[方法将给定的正则表达式编译成一个模式。这里正则表达式是要编译的表达式。](https://www.geeksforgeeks.org/regular-expressions-in-java/)

```java
// Java program to check if given date is
// valid or not.
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class GeeksforGeeks {

    // Returns true if d is in format
    // /dd/mm/yyyy
    public static boolean isValidDate(String d)
    {
        String regex = "^(1[0-2]|0[1-9])/(3[01]"
                       + "|[12][0-9]|0[1-9])/[0-9]{4}{content}quot;;
        Pattern pattern = Pattern.compile(regex);
        Matcher matcher = pattern.matcher((CharSequence)d);
        return matcher.matches();
    }

    public static void main(String args[])
    {
        System.out.println(isValidDate("10/12/2016"));
        System.out.println(isValidDate("10/02/18"));
    }
}
```

[**输出:**

```java
true
false

```](https://www.geeksforgeeks.org/regular-expressions-in-java/) 

**验证日期的更多方法:**

1.  [Simple date format class](https://www.geeksforgeeks.org/java-text-simpledateformat-class-set-1/) . We can use the parsing method of this class to verify the date.
2.  [Write our own method to check whether the date is valid.](https://www.geeksforgeeks.org/program-check-date-valid-not/)