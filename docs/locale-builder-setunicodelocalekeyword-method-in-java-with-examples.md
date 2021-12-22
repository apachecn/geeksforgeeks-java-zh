# 场所。Java 中的 Builder setUnicodeLocaleKeyword()方法，带示例

> 原文:[https://www . geeksforgeeks . org/locale-builder-setunicodelocalekeyword-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setunicodelocalekeyword-method-in-java-with-examples/)

**[的](https://www.geeksforgeeks.org/java-util-package-java/)**方法。[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/) 用来设置这个 Locale。生成器添加到指定的 unicodeLocaleKeyword 键。这意味着此方法将设置 Locale 的当前 unicodeLocaleKeyword。生成器实例，以匹配所提供的 unicodeLocaleKeyword 键，并键入和返回它。如果指定的 unimodelocalekeyword 为 null 或空，则此 LocaleBuilder 的 unimodelocalekeyword 将被删除。

**语法:**

```
public Locale.Builder
  setUnicodeLocaleKeyword(
    String unicodeLocaleKeywordKey, 
    String unicodeLocaleKeywordType)

```

**参数:**此方法接受两个参数:

*   **[single mode local key]** : This is the key string to be set for this region. Generator instance of unicode locale
*   [T0】 unicode localeKeyWordType 【T1]: This is the string type to be set for this locale. Builder instance of unicode locale

**返回类型:**该方法返回一个**地区。构建器实例**带有此区域设置的 unicodeLocaleKeyword 集。生成器转换为指定的 unicodeLocaleKeyword。

**异常:**此方法抛出以下异常:

*   **非法招标例外**:你好 unicodelocalekeyword 朱庇特·朱庇特·朱庇特

**程序 1:**

```
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleBuilderDemo {
    public static void main(String[] args)
    {

        // Creating a new Locale.Builder
        Locale.Builder localeBuilder
            = new Builder();

        // Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

        // setting the unicodeLocaleKeyword
        // of Locale.Builder
        String unicodeLocaleKeywordKey = "nu";
        String unicodeLocaleKeywordType = "thai";

        System.out.println("Setting the "
                           + "unicodeLocaleKeyword: "
                           + unicodeLocaleKeywordKey + "-"
                           + unicodeLocaleKeywordType);

        localeBuilder
            = localeBuilder
                  .setUnicodeLocaleKeyword(
                      unicodeLocaleKeywordKey,
                      unicodeLocaleKeywordType);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the unicodeLocaleKeyword: nu-thai
Updated LocaleBuilder: java.util.Locale$Builder@232204a1

```

**程序二:**

```
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleBuilderDemo {
    public static void main(String[] args)
    {

        // Creating a new Locale.Builder
        Locale.Builder localeBuilder
            = new Builder();

        // Displaying Locale.Builder
        System.out.println("LocaleBuilder: "
                           + localeBuilder);

        // setting the unicodeLocaleKeyword
        // of Locale.Builder
        String unicodeLocaleKeywordKey = "asf@";
        String unicodeLocaleKeywordType = "afaf{content}quot;;

        System.out.println("Setting the "
                           + "unicodeLocaleKeyword: "
                           + unicodeLocaleKeywordKey + "-"
                           + unicodeLocaleKeywordType);

        try {

            localeBuilder
                = localeBuilder
                      .setUnicodeLocaleKeyword(
                          unicodeLocaleKeywordKey,
                          unicodeLocaleKeywordType);

            // Displaying Locale.Builder
            System.out.println("Updated LocaleBuilder: "
                               + localeBuilder);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the unicodeLocaleKeyword: asf@-afaf$
java.util.IllformedLocaleException:
 Ill-formed Unicode locale keyword key:
 asf@ [at index 0]

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # setUnicodeLocaleKeyword-Java . lang . string-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setUnicodeLocaleKeyword-java.lang.String-java.lang.String-)