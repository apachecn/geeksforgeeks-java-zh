# 场所。Java 中的 Builder setScript()方法，示例

> 原文:[https://www . geesforgeks . org/locale-builder-set script-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-builder-setscript-method-in-java-with-examples/)

**[的 **setScript(String)** 方法。](https://www.geeksforgeeks.org/java-util-package-java/)[场所。Java 中的 Builder 类](https://www.geeksforgeeks.org/tag/java-locale-builder/)** 用来设置这个 Locale。生成器转换为指定的脚本。这意味着此方法将设置 Locale 的当前脚本。生成器实例来匹配所提供的脚本并返回它。如果指定的脚本为空，则删除该本地生成器的脚本。格式良好的脚本值由 ISO 15924 标准定义的 4 个字母的脚本代码组成。

**语法:**

```
public Locale.Builder setScript(String script)

```

**参数:**该方法接受**脚本**作为参数，该参数是要设置到该地区的字符串。生成器实例。

**返回值:**该方法返回一个**地区。构建器实例**带有此区域设置的脚本集。生成器转换为指定的脚本。

**异常:**此方法抛出以下异常:

*   [T0】 illformed localeexception 【T1]: If the specified script has any fields with incorrect format,

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

        // setting the script of Locale.Builder
        String script = "Gujr";
        System.out.println("Setting the script: "
                           + script);

        localeBuilder
            = localeBuilder.setScript(script);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
    }
}
```

**输出:**

```
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the script: Gujr
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

        // setting the script of Locale.Builder
        String script = "asda@vasdev#";
        System.out.println("Setting the script: "
                           + script);

        try{
        localeBuilder
            = localeBuilder.setScript(script);

        // Displaying Locale.Builder
        System.out.println("Updated LocaleBuilder: "
                           + localeBuilder);
                           }
        catch(Exception e)
        {
            System.out.println(e);
            }
    }
}
```

**输出:**

```
LocaleBuilder: java.util.Locale$Builder@232204a1
Setting the script: asda@vasdev#
java.util.IllformedLocaleException:
 Ill-formed script: asda@vasdev# [at index 0]

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.builder . html # setScript-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Builder.html#setScript-java.lang.String-)