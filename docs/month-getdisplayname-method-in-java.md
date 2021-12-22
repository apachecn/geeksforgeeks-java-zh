# Java 中的 Month getDisplayName()方法

> 原文:[https://www . geesforgeks . org/month-getdisplayname-method-in-Java/](https://www.geeksforgeeks.org/month-getdisplayname-method-in-java/)

**getDisplayName()** 方法是 Month ENUM 的内置方法，用于获取这个 Month 实例指定的年月的文本表示。

**语法** :

```
public String getDisplayName(TextStyle style,
                             Locale locale)

```

**参数**:该方法接受如下所述的两个参数:

*   **Style** : This parameter specifies the style or length of the text to be used, i.e. short, long, etc.
*   **regional setting** : this parameter specifies the regional setting to be used.

**返回值**:该方法返回本月实例指定月份的文本表示。

下面的程序说明了上述方法:

**程序 1** :

```
import java.time.*;
import java.time.Month;
import java.time.format.TextStyle;
import java.util.Locale;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.of(3);

        // Generate textual representation
        System.out.println(month.getDisplayName(TextStyle.SHORT,
                                                Locale.ENGLISH));
    }
}
```

**输出:**

```
Mar

```

**程序二** :

```
import java.time.*;
import java.time.Month;
import java.time.format.TextStyle;
import java.util.Locale;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.of(12);

        // Generate textual representation
        System.out.println(month.getDisplayName(TextStyle.SHORT,
                                                Locale.ENGLISH));
    }
}
```

**输出:**

```
Dec

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # getDisplayName-Java . time . format . textstyle-Java . util . locale-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#getDisplayName-java.time.format.TextStyle-java.util.Locale-)