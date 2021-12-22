# Java 中的 Locale toLanguageTag()方法，带示例

> 原文:[https://www . geeksforgeeks . org/locale-tolanguagetag-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-tolanguagetag-method-in-java-with-examples/)

Java 中 **[Locale 类](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)** 的 **toLanguageTag()** 方法用来返回一个格式良好的 *IETF BCP 47 语言标记*表示这个 Locale 对象。现在，当一种语言、国家或变体不能满足上述标签时，就不会有什么复杂的情况了，这种方法可以很好地处理:

*   如果提到的语言不满足标签，那么它将作为“未定”或“und”发出。
*   如果提到的国家不满足标签，将被省略。
*   如果变量也出现同样的情况，那么每个子段都作为一个子标记发出。

**语法:**

```
public String toLanguageTag()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回这个区域的 IETF BCP 47 语言标签表示。

以下程序说明了 toLanguageTag()方法的工作:
**程序 1:**

```
// Java code to illustrate
// toLanguageTag() method

import java.util.*;

public class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("Germany");

        // Displaying first locale
        System.out.println("Locale: "
                           + first_locale);

        // Displaying the LanguageTag
        System.out.println("The LanguageTag: "
                           + first_locale.toLanguageTag());
    }
}
```

**Output:**

```
Locale: germany
The LanguageTag: germany

```

**程序 2:**

```
// Java code to illustrate
// toLanguageTag() method

import java.util.*;

public class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("en", "USA");

        // Displaying first locale
        System.out.println("Locale: "
                           + first_locale);

        // Displaying the LanguageTag
        System.out.println("The LanguageTag: "
                           + first_locale.toLanguageTag());
    }
}
```

**Output:**

```
Locale: en_USA
The LanguageTag: en

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/locale . html # toLanguageTag()](https://docs.oracle.com/javase/7/docs/api/java/util/Locale.html#toLanguageTag())