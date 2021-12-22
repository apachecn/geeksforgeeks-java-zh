# Java 中 StringTokenizer 和 Split 方法的区别

> 原文:[https://www . geeksforgeeks . org/stringtokenizer-and-split-method-in-Java/](https://www.geeksforgeeks.org/difference-between-stringtokenizer-and-split-method-in-java/)

遗留类和接口是在早期版本的 Java 中形成[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的类和接口，现在如何被重组或重新设计。字符串拆分基本上是在给定正则表达式的匹配项周围断开字符串。

**在 java 中，字符串可以以多种方式拆分，但最常见的两种方式是使用:**

1.  StringTokenizer()
2.  拆分()方法

> 尽管 split()方法比 StringTokenizer 相对慢，但它是首选的，也是推荐的。这是因为它比 StringTokenizer 更健壮，更容易使用。

**1。** [**字符串标记器**](https://www.geeksforgeeks.org/stringtokenizer-class-java-example-set-1-constructors/)

通过获取用于创建 StringTokenizer 对象的字符串的子字符串来返回标记。StringTokenizer 对象在内部维护要标记化的字符串中的当前位置。

**有 3 个构造函数:**

*   StringTokenizer(字符串 str)
*   StringTokenizer(字符串 str，字符串分隔符)
*   StringTokenizer(字符串、字符串 delim、布尔标志)

在这里，

*   字符串:要标记的字符串
*   分隔符:标记字符串的分隔符(+、/等)
*   标志:决定是否将分隔符视为标记(真/假)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of StringTokenizer()

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        String str = "This  is  geek";
        StringTokenizer st = new StringTokenizer(str, " ");

        // counting tokens
        System.out.println("Total tokens : "
                           + st.countTokens());

        // checking tokens
        for (int i = 0; st.hasMoreTokens(); i++)
            System.out.println("#" + i + ": "
                               + st.nextToken());
    }
}
```

**Output**

```java
Total tokens : 3
#0: This
#1: is
#2: geek
```

**2。** [**分裂()**](https://www.geeksforgeeks.org/split-string-java-examples/) **弦法**

string split()方法在给定正则表达式的匹配项周围断开给定的字符串。

**Java 中的 split()方法有两种变体:**

*   **弦类法**

```java
public String [ ] split ( String regex, int limit )

Here,
split(): method to split stri
regex:a delimiting regular expression
limit:the result threshold
```

*   使用 **java.util.regex** 包

```java
public String[] split(String regex) 

Here,
split(): method to split string
regex:a delimiting regular expression
limit: default is 0
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate split()

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        String str = " This  is  geek";
        String[] split = str.split(" ");

        for (int i = 0; i < split.length; i++)
            System.out.println("#" + i + ": " + split[i]);
    }
}
```

**Output**

```java
#0: 
#1: This
#2: 
#3: is
#4: 
#5: geek
```

### Java 中字符串化和拆分方法的区别

<figure class="table">

| 字符串标记器 | 拆分() |
| --- | --- |
| 这是一个遗留类，允许应用程序将字符串分解成标记。 | 它是 String 类或 java.util.regex 包的一个方法，该方法在给定正则表达式的匹配项周围拆分该字符串。 |
| 它一次返回一个子字符串。 | 它返回一个子字符串数组。 |
| 它不能很好地处理空字符串。 | 当你需要像*蚂蚁、*T4】蝙蝠、T6】轻拍这样解析空令牌时，它可以处理空字符串 |
| 它相对来说不那么健壮&在语法上也不那么繁琐。 | 它更健壮&语法简单。 |
| 它只接受一个字符串，通过它来拆分字符串 | 它接受正则表达式。 |
| 分隔符只有一个字符长。 | 分隔符是正则表达式。 |
| 它本质上是为拉出由固定子字符串分隔的标记而设计的。 | 它本质上是用来解析来自程序之外的源的文本数据，比如文件或用户的文本数据。 |
| 因为这个限制，它的速度大约是 split()的两倍。 | 比 stringtokenizer 慢 |
| 由带有参数的构造函数组成，该参数允许您指定可能的分隔符。 | 没有构造函数。 |

</figure>