# 在 Java 字符串中转义 XML 特殊字符

> 原文:[https://www . geesforgeks . org/escaping-XML-特殊字符-in-java-string/](https://www.geeksforgeeks.org/escaping-xml-special-characters-in-java-string/)

当我们读取一个 XML 文件并尝试写入另一个 XML 文件时，注意 XML 中的特殊字符是很重要的。Java 中有一些保留字符需要转换或转义才能被视为字符串。如果我们不转义这些特殊字符，那么像 java 中的 DOM 或 SAX 解析器这样的解析器会将它们视为 XML 标签，特别是在< and >的情况下。即使我们使用 XSLT 转换，这些解析器也会失败。因此，我们需要在 Java 中将这些特殊字符作为字符串文字读取之前对其进行转义或转换。

**XML 中的特殊字符**

XML 中有 5 个最常用的特殊字符，当用作 Java 字符串时需要转义

*   & — &

*   >— >
*   “— "
*   ——'

这些特殊字符也被称为 XML 元字符。在转义过程中，我们会用替换字符串替换这些字符，以给出特殊字符的文字结果。

**示例:**

```java
*<GeeksForGeeks> Data Structures & Java </GeeksForGeeks>*

// is an invalid string in java because '&' is a reserved literal 
// in XML that is used to import other XML entity. For converting this 
// to a valid String literal we need to &amp; instead of & here.

*<GeeksForGeeks> Data Structure &amp; Java </GeeksForGeeks>*

// now becomes a valid String.
```

在 Java 中，我们总是可以编写自己的函数来用等价的字符串来转义 XML 特殊字符，但是我们也可以使用 Apache Commons 提供的 Java 库“StringEscapeUtils”。这个库为我们提供了一个通用的应用编程接口，可以为我们进行 XML 转义。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to escape all the five characters
// mentioned above using the StringEscapeUtils class

import java.io.*;
import org.apache.commons.lang.StringEscapeUtils;

class GeeksForGeeks {
    public static void main (String[] args) {

      System.out.println("Program to escape XML Special Characters !!");

      // Escape & character in XML String 
      String unescapedXMLString = "DataStructures & Java";

      System.out.println("Unescaped String: " + unescapedXMLString);

      // using StringEscapeUtils
      System.out.println("Escaped String: " 
                         + StringEscapeUtils.escapeXml(unescapedXMLString));

      // Escape > character in XML String 
      unescapedXMLString = "DataStructures > Java";

      System.out.println("Unescaped String: " + unescapedXMLString);

      // using StringEscapeUtils
      System.out.println("Escaped String: " 
                         + StringEscapeUtils.escapeXml(unescapedXMLString));

      // Escape < character in XML String 
      unescapedXMLString = "DataStructures < Java";

      System.out.println("Unescaped String: " + unescapedXMLString);

      // using StringEscapeUtils
      System.out.println("Escaped String: " 
                         + StringEscapeUtils.escapeXml(unescapedXMLString));

      // Escape " character in XML String 
      unescapedXMLString = "DataStructures \" Java";

      System.out.println("Unescaped String: " + unescapedXMLString);

      // using StringEscapeUtils
      System.out.println("Escaped String: " 
                         + StringEscapeUtils.escapeXml(unescapedXMLString));

      // Escape ' character in XML String 
      unescapedXMLString = "DataStructures ' Java";

      System.out.println("Unescaped String: " + unescapedXMLString);

      // using StringEscapeUtils
      System.out.println("Escaped String: " 
                         + StringEscapeUtils.escapeXml(unescapedXMLString));

    }
}
```

**输出:**

```java
Program to escape XML Special Characters !!
Unescaped String: DataStructures & Java
Escaped String: DataStructures &amp; Java
Unescaped String: DataStructures > Java
Escaped String: DataStructures &gt; Java
Unescaped String: DataStructures < Java
Escaped String: DataStructures &lt; Java
Unescaped String: DataStructures " Java
Escaped String: DataStructures &quot; Java
Unescaped String: DataStructures ' Java
Escaped String: DataStructures &apos; Java
```