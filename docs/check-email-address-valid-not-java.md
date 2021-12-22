# 检查电子邮件地址在 Java 中是否有效

> 原文:[https://www . geesforgeks . org/check-email-address-valid-not-Java/](https://www.geeksforgeeks.org/check-email-address-valid-not-java/)

给定一个字符串，查找给定的字符串是否是有效的电子邮件。

```java
Input : email = "review-team@geeksforgeeks.org"
Output : Yes

Input : email = "contribute@geeksforgeeks..org"
Output : No
Explanation : There is an extra dot(.) before org.
```

> **先决条件:**[Java 中的正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)

#### 正则表达式

正则表达式或正则表达式是一个定义字符串模式的应用编程接口，可用于在 Java 中搜索、操作和编辑字符串。电子邮件验证和密码是字符串的几个领域，Regex 被广泛用于定义约束。正则表达式在 **java.util.regex** 包下提供。

为了检查电子邮件地址是否有效，我们使用下面给出的正则表达式，该表达式在 OWASP Validation Regex 存储库中提供。

```java
^[a-zA-Z0-9_+&*-] + (?:\\.[a-zA-Z0-9_+&*-]
+ )*@(?:[a-zA-Z0-9-]+\\.) + [a-zA-Z]{2, 7}$ 
```

**代码–**

## Java

```java
// Java program to check if an email address
// is valid using Regex.
import java.util.regex.Matcher;
import java.util.regex.Pattern;
import java.util.*;

class Test
{
    public static boolean isValid(String email)
    {
        String emailRegex = "^[a-zA-Z0-9_+&*-]+(?:\\."+
                            "[a-zA-Z0-9_+&*-]+)*@" +
                            "(?:[a-zA-Z0-9-]+\\.)+[a-z" +
                            "A-Z]{2,7}{content}quot;;

        Pattern pat = Pattern.compile(emailRegex);
        if (email == null)
            return false;
        return pat.matcher(email).matches();
    }

    public static void main(String[] args)
    {
        ArrayList<String> address = new ArrayList<>();

          address.add("review-team@geeksforgeeks.org");
          address.add("writing.geeksforgeeks.org");

        for(String i : address){
            if (isValid(i))
                System.out.println(i + " - Yes");
            else
                System.out.println(i + " - No");
        }
    }
}
```

**输出**

```java
review-team@geeksforgeeks.org - Yes
writing.geeksforgeeks.org - No
```

本文由**普拉纳夫**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。